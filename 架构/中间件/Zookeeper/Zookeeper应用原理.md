# ZooKeeper 的 Leader 选举



## 1. 前言

我们在 Zookeeper 集群模式一节中，我们学习了为什么要使用 Zookeeper 的集群模式，是因为我们需要保证 Zookeeper 服务的高性能和高可用性。既然使用 Zookeeper 的集群模式，那么避免不了的问题就是 Zookeeper 如何进行 Leader 的选举以及和如何保证 Zookeeper 服务的数据一致性。那么本节我们就来讲解 Zookeeper 服务是如何进行 Leader 选举的。



## 2. Zookeeper 的 Leader 选举

Zookeeper 的 Leader 选举发生在两个阶段：

1. Zookeeper 服务初次启动时的 Leader 选举。
2. Zookeeper 崩溃恢复时的 Leader 选举。

首先我们来讲解在 Zookeeper 服务启动时的 Leader 选举。



### 2.1 Zookeeper 服务启动时的 Leader 选举

在 Zookeeper 服务启动阶段，每个 Zookeeper 服务会根据配置文件选择启动模式。

在选择集群模式的情况下，获取配置文件中所有 Zookeeper 服务的地址，然后向其它 Zookeeper 服务发起通信检查，确认 Zookeeper 服务间的通信状态。然后在这些 Zookeeper 服务间寻找 Leader 节点，初次启动时无 Leader 节点，此时就会进入 Leader 选举的状态。

在选举状态中，所有 Zookeeper 服务的状态都会变为 Looking 选举状态，每台 Zookeeper 服务都把自己当作 Leader 候选者向其它 Zookeeper 服务发送自己的选票信息。我们这里以 3 个 Zookeeper 服务为例子：
![Zookeeper第一轮选举](http://qiniu.cdn.easyspring.net/20210102235556.jpg)
选票信息包括 Zookeeper 的服务ID，也就是 myid 文件中的内容，还有就是 Zookeeper 服务最新的事务ID，也就是 ZXID，当然初次启动的 Zookeeper 服务的事务 ID 都是相同的 。发送选票信息的同时，也会接收到其它 Zookeeper 服务发送的选票信息。

> **Tips：** ZXID：节点本地的事务编号，由64位的数字组成，包含纪元值（ epoch ）和计数两部分。

正常情况下，在第一轮的选举中，每个 Zookeeper 服务的选票信息都是自身的信息，所以不会产生 Leader，此时就会开启第二轮选举。

在第二轮选举之前，Zookeeper 服务会把自己的选票信息和接收到的其它 Zookeeper 服务的选票信息一起做比较，产生新的选票信息，首先比较 ZXID，选取拥有较大的 ZXID 的选票信息作为自己新的选票，如果 ZXID 相同，则会比较服务ID，也就是 myid 的值，选取拥有较大的 myid 值的选票信息作为自己新的选票。
![Zookeeper选票更新](http://qiniu.cdn.easyspring.net/20210102235603.jpg)
产生了新的选票之后，发起第二轮投票，此时 Zookeeper 服务器会统计所有服务器发出的选票，如果超过半数的 Zookeeper 服务的选票信息是相同的，那么该选票中的 myid 值相对应的 Zookeeper 服务就当选为 Leader 服务，其状态变为 Leading，其它 Zookeeper 服务的状态由 Looking 状态变为 Following，也就是 Follower 服务。如果选票的统计未达到半数以上，则更新各个节点的选票信息，重新开始新一轮的选举，直到选举出 Leader。
![Zookeeper第二轮选举](http://qiniu.cdn.easyspring.net/20210102235609.jpg)
以上就是 Zookeeper 服务启动时的 Leader 选举的过程。接下来我们讲解 Zookeeper 在崩溃恢复阶段的 Leader 选举。



### 2.2 Zookeeper 的 ZAB 协议

#### 2.2.1 什么是 ZAB 协议

Zookeeper 使用 ZAB 协议来保证 Zookeeper 的数据一致性，ZAB 协议全称 Zookeeper Atomic Broadcast ，原子消息广播协议。

ZAB 协议的两种工作模式：

1. **崩溃恢复**
2. **消息广播**

ZAB 协议定义了三种节点状态：

1. **Looking**：选举状态；
2. **Following**：从节点所处的状态；
3. **Leading**：主节点所处的状态。

那么 ZAB 协议的这两种模式什么时候使用呢？三种节点的状态又是如何变化的呢？

接下来，我们来详细了解一下 ZAB 的崩溃恢复模式是如何工作的。

#### 2.2.2 ZAB 的崩溃恢复模式

在 Zookeeper 集群服务的运行过程中，如果 Leader 节点发生故障，无法处理 Follower 节点提交的事务请求，根据 ZAB 协议，此时的 Zookeeper 集群就会暂时停止对外提供服务，进入崩溃恢复。如果此时崩溃的 Leader 服务故障被排除，加入到 Zookeeper 集群中，它也会进入 Looking 状态，参与选举。

Zookeeper 的崩溃恢复分为 3 个阶段：

1. **Leader election**
   在 Leader 选举阶段，Zookeeper 服务都为 Looking 状态，每个 Zookeeper 服务都会用自身的 ZXID 和 myid 值形成选票，第一轮选举和 Zookeeper 启动时第一轮选举的结果一样，Zookeeper 服务的选票信息都是自身的信息，所以不会产生 Leader，无 Leader 产生 Zookeeper 服务就会更新自身的选票信息，进入下一轮选举，直到选举出 Leader。

   这一阶段选举出来的 Leader 还不能直接作为真正的 Leader 去处理事务请求，它还需要再次确认自身的数据是最新的，避免网络等原因出现多个 Leader 的情况，接下来就进入 Discovery 发现阶段。

2. **Discovery**
   在 Discovery 发现阶段，上一阶段产生的 Follower 服务会把自身 ZXID 中的 epoch 纪元值发送给 Leader 服务，Leader 接收到所有 Follower 的 epoch 纪元值后，会选出其中最大的 epoch 纪元值，然后在这基础上进行加 1 ，作为最新的 epoch 纪元值，返回给所有的 Follower 。

   Follower 接收到 Leader 发送的最新 epoch 纪元值后，根据此 epoch 纪元值来更新自己的 ZXID ，然后再把更新后的 ZXID 、最新的历史事务日志和 ACK 确认信息返回到 Leader。

   Leader 接收到 ACK 确认信息后，把接收到最新的 ZXID 和 最新的历史事务日志和自身作比较，把最新的更新到自身。

   经过这一阶段就能确认 Leader 服务的数据是最新的了，然后就进入下一阶段，Synchronization 同步阶段。

3. **Synchronization**
   Synchronization 同步阶段的主要作用是把 Leader 最新的数据和日志同步到 Follower 中，当半数以上的 Follower 同步数据成功后，Leader 才能成为真正的 Leader ，就可以处理事务请求了。

经过崩溃恢复的 3 个阶段，真正的 Leader 选举完成后，Zookeeper 就会进入消息广播模式，重新对外提供服务。



## 3. 总结

经过本节的学习，我们知道了 Zookeeper 在启动时和崩溃恢复时的 Leader 选举时如何完成的，也了解了 Zookeeper 崩溃恢复的 3 个阶段。以下是本节内容的总结：

1. Zookeeper 在启动时的 Leader 选举。
2. Zookeeper 的 ZAB 协议。
3. ZAB 协议的崩溃恢复过程。
4. Zookeeper 崩溃恢复的 3 个阶段。





# ZooKeeper 集群的数据同步



## 1. 前言

在 Zookeeper 的集群模式一节中，我们学习过了 Zookeeper 的每个 Follower 节点都可以对外提供服务，而且为了保证整个 Zookeeper 集群的数据一致，Zookeeper 集群的服务之间还会进行数据同步。那么这个数据同步的过程是如何实现的呢？接下来我们就对 Zookeeper 集群的数据同步机制进行详细的讲解。



## 2. ZAB 的消息广播模式

Zookeeper 为了保证 Zookeeper 集群的数据一致性，使用了 ZAB 协议，在正常工作模式下，ZAB 协议会使用消息广播模式来让 Leader 来对事务性消息进行广播，而且只能有一个 Leader 进行广播。接下来我们就来讲解这个消息广播模式是如何工作的。



### 2.1 消息广播的数据同步

在我们使用 Zookeeper 客户端向 Zookeeper 集群的某一个 Follower 发送事务请求时，也就是对 Znode 节点的增删改操作时，这个Follower 节点并不会自己去处理这个事务请求，而是会把这个请求转发给 Leader 节点，让 Leader 节点来处理事务请求。

![事务请求](http://qiniu.cdn.easyspring.net/20210102235619.jpg)

Leader 节点接收到 Follower 转发过来的请求，会生成与事务请求相对应的 Proposal 事务提案，并为这个 Proposal 事务提案分配全局唯一的单调递增的事务ID，也就是 ZXID，然后把 Proposal 事务提案发送到集群中所有的 Follower 节点。

如果 Leader 节点接收到了多个 Follower 节点转发的请求，Leader 节点会根据 Proposal 事务提案的 ZXID 的先后顺序来对 Follower 节点进行广播。

![Proposal 事务提案](http://qiniu.cdn.easyspring.net/20210103000321.jpg)

Follower 节点接收到 Proposal 事务提案后，会把接收到的 Proposal 事务提案以事务日志的方式写入本地磁盘中，成功后会向 Leader 节点返回 Ack 确认信息，确定自己能够执行该事务。在这一步骤中， Follower 向 Leader 发送反馈，确认 Follower 节点能够执行该事务，但不会去提交该事务请求。

![ 发送反馈](http://qiniu.cdn.easyspring.net/20210103000329.jpg)

Leader 节点接收到半数以上的 Follower 节点返回的 Ack 确认信息后，就会向所有的 Follower 节点广播 Commit 消息，通知 Follower 节点提交事务请求，同时 Leader 节点自己也会提交该事务请求。接收到 Commit 消息的 Follower 节点就会开始进行事务提交。

![事务提交](http://qiniu.cdn.easyspring.net/20210103000334.jpg)

当 Follower 节点完成事务的提交后，Leader 节点就会把该 Follower 节点加入可用的 Follower 列表中，该Follower 节点就可以对外提供服务了。

除了 Follow 节点需要进行数据同步外，Zookeeper 集群还有一种叫做 Observer 的节点会进行数据同步，那么我们接下来简单介绍一下 Observer 节点。



## 3. Observer

Observer 节点是 Zookeeper 3.3.0 版本新增的 Zookeeper 集群的角色，Observer 作为观察者在 Zookeeper 集群中观察 Zookeeper 集群的最新的数据变化，然后从 Leader 节点获取最新变化的数据并同步到自身，然后再向外提供服务。

Observer 节点可以独立的处理 Zookeeper 客户端的非事务请求，也就是查询请求。如果接收到 Zookeeper 客户端的事务请求，Observer 节点会把请求转发给 Leader 节点，但不会接收到 Leader 节点的 Proposal 事务提案，避免影响 Zookeeper 集群处理事务请求的效率。这是 Observer 节点与 Follower 节点的区别之一。

Observer 节点与 Follower 节点的区别之二，Observer 节点不会参与 Zookeeper 集群的 Leader 选举，避免太多候选者而降低 Zookeeper 集群选举 Leader 的效率。

简单的介绍了 Observer 节点是什么，以及 Observer 节点和 Follower 节点的区别，接下来我们讲解 Observer 节点是如何实现与 Leader 节点进行数据同步的。



### 3.1 Observer 的数据同步

增加 Observer 节点的主要作用是用来提高 Zookeeper 集群的非事务请求的效率，我们可以在 zoo.cfg 配置文件中添加如下配置：

```cfg
# 声明此服务为 Observer 节点
peerType=observer
```

在 zoo.cfg 中配置 Zookeeper 服务列表时需要添加 observer 标识：

```cfg
# 添加 observer 标识，声明 server.1 为 Observer 节点
server.1:192.168.0.77:2181:3181:observer
```

我们启动 Zookeeper 服务时，会加载配置文件的 peerType 属性来识别该服务是否为 Observer 节点，如果是 Observer 节点，就会使用 ObserverZooKeeperServer 类来实例化该 Observer 节点。

由于 Observer 节点不接收 Leader 节点广播的 Proposal 事务提案，也就不能在这一步获取 Proposal 事务提案中的事务请求，那么 Observer 节点如何获得事务请求的信息呢？答案是 Observer 节点会从 INFORM 消息中获取已提交的事务信息。

INFORM 消息是 Leader 节点在自身的事务提交成功后向 Observer 节点发出的消息，通知 Observer 更新数据。Observer 接收到 Leader 节点发出的 INFORM 消息后，从 INFORM 消息中获取 Leader 节点已经提交的事务，就可以对自身的数据进行更新了，而且不需要向Leader 节点发送反馈信息。

![5f5f676c0935e16606220376](http://qiniu.cdn.easyspring.net/20210103000604.png)



## 4. 总结

在本节内容中，我们学习了 Zookeeper ZAB 协议的消息广播模式，以及在消息广播模式中 Zookeeper 集群的各个节点的数据同步过程，还有 Observer 节点的特点以及 Observer 节点的数据同步。以下是本节内容总结：

1. Zookeeper ZAB 协议的消息广播模式。
2. 消息广播模式下的数据同步过程。
3. Observer 节点的特点。
4. Observer 节点与 Leader 节点的数据同步。



# ZooKeeper 实现分布式锁



## 1. 前言

在我们的应用中，经常会碰见多个请求去访问同一个资源的情况。如果请求 A 拿到这个资源数据，想要对它进行修改，但是还没有进行事务提交，此时请求 B 访问这个资源就会拿到修改前的数据，很显然请求 B 拿到的是历史数据，是不正确的。

在单个服务器的应用中，我们可以使用系统的线程来对这个资源进行加锁。那么在分布式环境中我们有什么方案来解决这个问题呢？答案就是使用分布式锁。那么什么是分布式锁？分布式锁又是如何实现的呢？本节我们就来讲解如何使用 Zookeeper 实现分布式锁，以及它的实现原理。



## 2. 分布式锁

在讲解 Zookeeper 实现的分布式锁之前，我们先来了解什么是分布式锁，分布式锁的实现技术，以及分布式锁常用的类型。



### 2.1 分布式锁的特点

顾名思义，分布式锁就是实现在分布式网络环境中的锁。也就是说，在锁的基础上加上分布式的特性，我们来分析一下分布式锁实现的必要条件：

1. 在分布式环境中，多个进程对资源的访问必须具有顺序性；
2. 获取锁和释放锁的过程需要高可用和高性能；
3. 具有锁失效的机制，避免死锁；
4. 非阻塞的锁，没有获取到锁直接返回获取锁失败。

介绍了分布式锁的特点，那么有哪些技术能够实现分布式锁呢？



### 2.2 分布式锁的实现技术

1. **Memcached：** 使用 `add` 命令来添加 `key`，`key` 添加成功说明当前无人使用此 `key`，也就是说无人使用此资源，相当于获取锁。再次使用 `add` 命令来添加相同的 `key` 时，此时 `key` 已存在就会添加失败，说明有人已经使用了这个 `key`，也就是说此资源被人占用，相当于获取锁失败；
2. **Redis：** 使用 `setnx` 命令来添加 `key`，`key` 添加成功说明当前无人使用此 `key`，也就是说无人使用此资源，相当于获取锁。再次使用 `setnx` 命令来添加相同的 `key` 时，此时 `key` 已存在就会添加失败，说明有人已经使用了这个 `key`，也就是说此资源被人占用，相当于获取锁失败；
3. **Chubby：** Google 使用 Paxos 一致性算法实现的粗粒度分布式锁；
4. **Zookeeper：** 使用 Zookeeper 临时顺序节点的特性，实现分布式锁和锁的等待队列。

介绍了分布式锁的实现技术，接下来我们来介绍分布式锁常用的类型。



### 2.3 分布式锁常用的类型

分布式锁常用的类型有两种：一种是排他锁，一种是共享锁。接下来我们分别介绍这两锁的特点。

- **排他锁**

排他锁也叫独占锁，顾名思义，也就是对资源进行独占。排他锁只允许获取了该锁的线程，对具有排他锁的资源进行访问，无论是写操作还是读操作，直到该线程主动释放掉排他锁。

- **共享锁**

共享锁也就是把资源进行共享，当然共享的只有读操作。共享锁只对写操作进行加锁，其它线程的读操作不做加锁操作，这样的共享机制提高了对资源访问的性能。

介绍完分布式锁的常用类型，接下来我们开始学习如何使用 Zookeeper 实现分布式锁。



## 3. Zookeeper 实现分布式锁

上面我们提到，Zookeeper 是根据它的临时顺序节点来实现的分布式锁，这里我们来回顾一下临时顺序节点的特性。



### 3.1 临时顺序节点

**临时顺序节点：**

- 节点具有临时性，创建该节点的 Zookeeper 客户端与 Zookeeper 服务端断开连接时，该节点会自动被 Zookeeper 服务端删除；
- 节点具有顺序性，创建该节点时，Zookeeper 服务端会根据创建时间的顺序在该节点名称后面加上顺序编号。

回顾了临时顺序节点的特性，接下来我们就使用 Zookeeper 的 Java 客户端 Curator 来创建临时顺序节点，我们可以使用在 Zookeeper Curator 一节创建的 Spring Boot 测试项目来进行测试。

我们可以在测试类 CuratorDemoApplicationTests 中编写测试用例：

```java
@SpringBootTest
class CuratorDemoApplicationTests {

    @Autowired
    private CuratorService curatorService;

    @Test
    void contextLoads() throws Exception {
        // 获取客户端
        CuratorFramework client = curatorService.getCuratorClient();
        // 开启会话
        client.start();
        
        // 第一次创建临时顺序节点
        String s1 = client.create()
            // 如果有父节点会一起创建
            .creatingParentsIfNeeded()
            // 节点类型：临时顺序节点
            .withMode(CreateMode.EPHEMERAL_SEQUENTIAL)
            // 节点路径 /wiki
            .forPath("/wiki-");
        // 输出
        System.out.println(s1);
        
        // 第二次创建临时顺序节点
        String s2 = client.create()
            // 如果有父节点会一起创建
            .creatingParentsIfNeeded()
            // 节点类型：临时顺序节点
            .withMode(CreateMode.EPHEMERAL_SEQUENTIAL)
            // 节点路径 /wiki
            .forPath("/wiki-");
        // 输出
        System.out.println(s2);
        
        // 关闭客户端
        client.close();
    }
}
```

执行测试方法，控制台输出：

```
/wiki-0000000000
/wiki-0000000001
```

我们可以发现，控制台一共输出了两个 /wiki 节点，而且每个 /wiki 节点后面都增加了编号，此时我们去 zkCli 命令行客户端查看所有节点，发现并没有 /wiki 节点。因为在我们的测试程序中，我们关闭了客户端，所以临时节点会被移除。

> **Tips：** 如果这里创建失败，请同学们注意父节点是否存在 ACL 访问控制。

回顾了临时顺序节点，那么如何使用 Zookeeper 的临时顺序节点来实现分布式锁呢？接下来我们就开始介绍如何使用 Zookeeper 的临时顺序节点来控制它们的访问顺序。



### 3.2 分布式锁实现

本节我们来介绍分布式锁实现的具体步骤：

1. **创建临时顺序节点：** 每一次获取资源的请求，我们都需要使用 Zookeeper 客户端创建一个临时顺序节点，用这个临时顺序节点在 Zookeeper 服务端中获取锁。
2. **获取锁：** 这里的锁并不具体指代什么，而是根据 Zookeeper 的临时顺序节点的顺序来决定是否获取了锁。如果该节点的顺序编号是最小的，则说明该节点是排在最前面的，在它之前无人占领资源，也就可以说该节点获取了锁，具有访问资源的权限。

![图片描述](http://qiniu.cdn.easyspring.net/20210103000632.jpg)

1. **监听锁：** 如果获取锁这一步发现 Zookeeper 客户端创建的临时顺序节点的顺序编号不是最小的，也就是在这个临时顺序节点之前存在其它临时顺序节点，那么就可以说这个节点获取锁失败了，它会进入等待队列。我们可以监听它的前一个节点，只要它的前一个临时顺序节点的删除事件触发，我们就可以获取临时顺序节点的列表来重新确认这个节点的顺序。

![图片描述](http://qiniu.cdn.easyspring.net/20210103000635.jpg)

1. **释放锁：** 当一个请求对资源的操作结束后，我们可以使用 Zookeeper 客户端的节点删除 API 来删除这个请求创建的临时顺序节点。除了使用 API 来主动释放锁之外，根据临时顺序节点的特性，当创建这个临时顺序节点的 Zookeeper 客户端与 Zookeeper 服务端断开连接时，这个临时顺序节点会被 Zookeeper 服务端移除。这两种方式都会触发临时节点的删除事件，让下一个临时顺序节点来确认自身的顺序。



## 4. 总结

本节内容中，我们学习了什么是分布式锁，以及它的特点和类型，还学习了使用 Zookeeper 实现分布式锁的主要步骤。以下是本节内容的总结：

1. 分布式锁的特点和常用类型。
2. 临时顺序节点的特性。
3. 使用 Zookeeper 实现分布式锁的主要步骤。



# ZooKeeper 实现分布式 ID



## 1. 前言

在我们使用数据库进行数据存储时，会给数据加上唯一标识，也就是我们常说的 ID，通过唯一的 ID， 我们可以精确的定位到每一条数据，设置 ID 常用的方式有 MySQL 的主键自增，UUID，雪花算法等。

除了数据库的数据需要进行唯一标识的设置之外，在分布式环境中，集群中的每一个服务或者分布式服务的地址列表，我们都可以为它们设置唯一标识 ID，通过这个 ID 我们可以更方便的获取它们的服务提供者的信息和地址列表等数据。

本节我们就来学习如何使用 Zookeeper 来生成分布式的全局唯一 ID。



## 2. 分布式 ID

在使用 Zookeeper 生成分布式的全局唯一 ID 之前，我们先来了解什么是分布式 ID，为什么要使用分布式 ID ，以及分布式 ID 的实现方式有哪些。

分布式 ID，也就是在分布式的环境下，全局的唯一的 ID 。那么我们为什么要使用分布式 ID 呢？

在单体结构的应用中，我们可以使用 MySQL 数据库的主键自增来为我们的数据设置唯一标识 ID，但是在分布式环境中，单个数据库的吞吐量成为整个应用的性能瓶颈，我们就可以搭建数据库集群来提升数据库的性能，此时如果还使用 MySQL 的主键自增来设置数据 ID 的话，就会出现重复的 ID，这样就会出现主键冲突的情况。

如果使用分布式的全局唯一 ID 就不用担心会出现这个问题了。那么分布式 ID 的实现方式有哪些呢？接下来我们就对分布式 ID 的实现方式进行介绍。



### 2.1 分布式 ID 的实现方式

本小节我们来简单介绍一下常用的分布式 ID 的实现方式，例如：UUID，Redis，雪花算法等。

- **UUID**

  Universally Unique Identifier 通用唯一标识符，由 32 个字符组成，采用 16 进制进行编码，定义了在时间和空间都完全唯一的系统信息。

  在 Java 中可以使用 java.util.UUID 的 randomUUID() 方法来获得：

  ```java
  java.util.UUID.randomUUID().toString();
  ```

  UUID 可以在本地生成，生成速度快，不依赖网络和其它服务，但是 UUID 没有可以识别的特点，也没有顺序性。

- **Redis 实现分布式 ID**

  我们都知道 Redis 的性能非常高，而且还可以搭建集群。我们可以使用 Redis 的 Incr 命令来把 <key,value> 中 key 的数值加 1 并返回，如果这个 key 不存在，则 key 值会被初始化为 0，再执行 Incr 命令来进行加 1 操作。

  ```java
  // 使用 incr(key) 来让 key 加 1
  long id = jedis.incr("id");
  ```

  使用 Redis 的方式生成分布式 ID 需要依赖 Redis 服务，还要保证 Redis 的高可用，否则 Redis 服务宕机会影响整个应用。

- **雪花算法**

  SnowFlake 雪花算法是 Twitter 公司推出的⼀个⽤于⽣成分布式 ID 的策略，基于这个算法可以生成 64 位 Long 型的 ID，它是由 1 位符号位，41 位的时间戳毫秒数，10 位的机器 ID，12 位的序列号这 4 种元素来组成的。理论上，雪花算法每秒可以生成 400 多万个 ID，完全可以支撑住分布式环境下高并发的场景。

  一些公司在雪花算法的基础上实现了自己的分布式 ID 的算法，比如：滴滴的 Tinyid，百度的 UidGenerator，美团的 Leaf 等。

简单介绍了一些分布式 ID 的实现方式，接下来我们就使用 Zookeeper 来实现分布式 ID 。



## 3. Zookeeper 实现分布式 ID

在 Zookeeper 中，我们可以使用 Zookeeper 的 顺序节点来完成分布式 ID 的生成。这里我们来回顾一下顺序节点的特性。

顺序节点，在 Zookeeper 客户端创建顺序节点时，Zookeeper 会根据创建的时间顺序，在节点名称后添加 10 位的顺序编号。

这里我们使用在 Zookeeper Curator 一节创建的 Spring Boot 测试项目来进行测试：

```java
@SpringBootTest
class CuratorDemoApplicationTests {

    @Autowired
    private CuratorService curatorService;

    @Test
    void contextLoads() throws Exception {
        // 获取客户端
        CuratorFramework client = curatorService.getCuratorClient();
        // 开启会话
        client.start();
        
        // 第一次创建 /wiki-
        String s = client.create().
            creatingParentsIfNeeded().
            withMode(CreateMode.PERSISTENT_SEQUENTIAL).
            forPath("/wiki-");
        // 输出第一次创建的 /wiki-
        System.out.println(s);
        
        // 第二次创建 /wiki-
        String s1 = client.create().
            creatingParentsIfNeeded().
            withMode(CreateMode.PERSISTENT_SEQUENTIAL).
            forPath("/wiki-");
        // 输出第二次创建的 /wiki-
        System.out.println(s1);
        
        // 第三次创建 /wiki-
        String s2 = client.create().
            creatingParentsIfNeeded().
            withMode(CreateMode.PERSISTENT_SEQUENTIAL).
            forPath("/wiki-");
        // 输出第三次创建的 /wiki-
        System.out.println(s2);
        
        // 关闭客户端
        client.close();
    }
}
```

执行测试方法。控制台输出：

```
/wiki-0000000000
/wiki-0000000001
/wiki-0000000002
```

我们可以观察到，每个 `/wiki-` 节点后都增加了 10 位的顺序编号，而且都是按照添加顺序来进行编号的。

再加上我们在创建 Curator 客户端时设置的命名空间 `imooc`，就可以形成完整的节点路径 `/imooc/wiki-0000000000`，这个完整的路径就可以当作我们的分布式 ID 了，而且这样我们也能根据命名空间来区别不同的业务模块，还可以添加不同的命名空间来扩展不同的业务模块。

![图片描述](http://qiniu.cdn.easyspring.net/20210103000642.jpg)



## 4. 总结

在本节内容中，我们学习了什么是分布式 ID ，在分布式环境下为什么要使用分布式 ID，我们还介绍了几种常用的分布式 ID 实现方式，以及它们的优缺点，最后我们回顾了 Zookeeper 顺序节点， 并使用 Zookeeper 的顺序节点的特性实现了分布式 ID 的生成。以下是本节内容的总结：

1. 为什么要使用分布式 ID 。
2. 分布式 ID 实现方式。
3. 使用 Zookeeper 的顺序节点实现分布式 ID。





# ZooKeeper 实现负载均衡



## 1. 前言

在分布式的环境中，我们常常使用集群部署的方式来提高某个服务的可用性，为了让高并发的请求能够平均的分配到集群中的每一个服务，避免有些服务压力过大，而有些服务处于空闲状态这样的情况，我们需要制定一些规则来把请求进行路由，这种分配请求的做法就叫做负载均衡，路由请求的规则就是负载均衡的策略。

那么负载均衡的策略有哪些呢？如何使用 Zookeeper 实现负载均衡呢？接下来我们就带着这些问题开始本节的内容。



## 2. 负载均衡的策略

当我们使用集群的方式部署的服务在不同的机器上时，根据机器的性能以及网络环境，我们可能需要使用负载均衡策略来分配请求到不同的机器，这里我们就开始讲解负载均衡的策略。

- **Round Robin 轮询策略**

  轮询策略，按照集群的服务列表的顺序，依次进行请求的分配，直到列表中所有的服务都分配了一次请求，就完成了一轮的请求分配，然后再从第一个服务开始分配请求。

  轮询策略是很多负载均衡技术的默认策略，这样的方式保证了的每个服务所承受的请求压力是平均的，我们可以把服务列表按照顺序放到一个数组来循环分配请求。

  ```java
  /**
   * 轮询策略 Demo
   */
  public class RoundRobinStrategy {
      public static void main(String[] args) {
          // 模拟 Server 地址列表
          String[] serverList = {"192.168.0.77","192.168.0.88","192.168.0.99"};
          // 模拟 5 次请求
          for (int i = 0; i < 5; i++) {
              // 根据数组长度取模，顺序获取地址索引
              int i1 = i % serverList.length;
              // 根据索引获取服务器地址
              System.out.println(serverList[i1]);
          }
      }
  }
  ```

  执行 main 方法，查看控制台输出：

  ```
  192.168.0.77
  192.168.0.88
  192.168.0.99
  192.168.0.77
  192.168.0.88
  ```

  我们可以观察到控制台输出的服务地址是顺序的。

- **Random 随机策略**

  随机策略，顾名思义就是根据随机算法把请求随机的分配给服务列表中的任意一个服务。

  随机策略的实现方式：我们可以把服务列表放到一个数组，然后根据数组的长度来获取随机数，取到的随机数就是服务在数组中的索引，根据这个索引，我们就可以拿到服务地址来发送请求了。

  ```java
  /**
   * 随机策略 Demo
   */
  public class RandomStrategy {
      public static void main(String[] args) {
          // 服务地址数组
          String[] serverList = {"192.168.0.77","192.168.0.88","192.168.0.99"};
          // 模拟发送 5 次请求
          for (int j = 0; j < 5; j++) {
              // 随机获取数组的索引
              int i = new Random().nextInt(serverList.length);
              // 根据索引获取服务器地址
              System.out.println(serverList[i]);
          }
      }
  }
  
  ```

  执行 main 方法，查看控制台输出：

  ```
  192.168.0.88
  192.168.0.88
  192.168.0.99
  192.168.0.77
  192.168.0.77
  ```

  我们可以观察到控制台输出的服务地址是随机的，还有可能会出现多次请求连续随机到同一个服务的情况。

- **Consistent Hashing 一致性哈希策略**

  一致性哈希策略的实现方式：我们先把服务列表中的地址进行哈希计算，把计算后的值放到哈希环上，接收到请求后，根据请求的固定属性值来进行哈希计算，然后根据请求的哈希值在哈希环上顺时针寻找服务地址的哈希值，寻找到哪个服务地址的哈希值，就把请求分配给哪个服务。

![一致性哈希](http://qiniu.cdn.easyspring.net/20210103000647.jpg)

> **Tips：** 哈希环的范围，从 0 开始，到 2 的32 次方减 1 结束，也就是到 Integer 的最大取值范围。

在示例的图中，哈希环上有 3 个 Server 的 Hash 值，每个请求的 Hash 值都顺时针去寻找 Server 的 Hash 值，找到哪个就将请求分配给哪个服务。接下来我们用 Java 实现一致性哈希策略，使用 IP 地址进行 Hash 计算：

```java
/**
 * 一致性哈希策略 Demo
 */
public class ConsistentHashingStrategy {
    public static void main(String[] args) {
        // 模拟 Server 地址列表
        String[] serverList = {"192.168.0.15", "192.168.0.30", "192.168.0.45"};
        // 新建 TreeMap 集合 ，以 Key，Value 的方式绑定 Hash 值与地址
        SortedMap<Integer, String> serverHashMap = new TreeMap<>();
        // 计算 Server 地址的 Hash 值
        for (String address : serverList) {
            int serverHash = Math.abs(address.hashCode());
            // 绑定 Hash 值与地址
            serverHashMap.put(serverHash, address);
        }
        // 模拟 Request 地址
        String[] requestList = {"192.168.0.10", "192.168.0.20", "192.168.0.40", "192.168.0.50"};
        // 计算 Request 地址的 Hash 值
        for (String request : requestList) {
            int requestHash = Math.abs(request.hashCode());
            // 在 serverHashMap 中寻找所有大于 requestHash 的 key
            SortedMap<Integer, String> tailMap = serverHashMap.tailMap(requestHash);
            //如果有大于 requestHash 的 key， 第一个 key 就是离 requestHash 最近的 serverHash
            if (!tailMap.isEmpty()) {
                Integer key = tailMap.firstKey();
                // 根据 key 获取 Server address
                String address = serverHashMap.get(key);
                System.out.println("请求 " + request + " 被分配给服务 " + address);
            } else {
                // 如果 serverHashMap 中没有比 requestHash 大的 key
                // 则直接在 serverHashMap 取第一个服务
                Integer key = serverHashMap.firstKey();
                // 根据 key 获取 Server address
                String address = serverHashMap.get(key);
                System.out.println("请求 " + request + " 被分配给服务 " + address);
            }
        }
    }
}
```

执行 main 方法，查看控制台输出：

```
请求 192.168.0.10 被分配给服务 192.168.0.15
请求 192.168.0.20 被分配给服务 192.168.0.30
请求 192.168.0.40 被分配给服务 192.168.0.45
请求 192.168.0.50 被分配给服务 192.168.0.15
```

- **加权轮询策略**

  加权轮询策略就是在轮询策略的基础上，对 Server 地址进行加权处理，除了按照服务地址列表的顺序来分配请求外，还要按照权重大小来决定请求的分配次数。加权的目的是为了让性能和网络较好的服务多承担请求分配的压力。

  比如 Server_1 的权重是 3，Server_2 的权重是 2，Server_3 的权重是 1，那么在进行请求分配时，Server_1 会被分配 3 次请求，Server_2 会被分配 2 次请求，Server_3 会被分配 1 次请求，就这样完成一轮请求的分配，然后再从 Server_1 开始进行分配。

- **加权随机策略**

  加权随机策略就是在随机策略的基础上，对 Server 地址进行加权处理，Server 地址的加权有多少，那么 Server 地址的数组中的地址就会有几个，然后再从这个数组中进行随机选址。

- **Least Connection 最小连接数策略**

  最小连接数策略，就是根据客户端与服务端会话数量来决定请求的分配情况，它会把请求分配到会话数量小的服务，会话的数量越少，也能说明服务的性能和网络较好。

学习完负载均衡的策略，接下来我们使用 Zookeeper 实现负载均衡。



## 3. Zookeeper 实现负载均衡

Zookeeper 实现负载均衡，我们可以使用 Zookeeper 的临时节点来维护 Server 的地址列表，然后选择负载均衡策略来对请求进行分配。

我们回顾一下临时节点的特性：当创建该节点的 Zookeeper 客户端与 Zookeeper 服务端断开连接时，该节点会被 Zookeeper 服务端移除。使用临时节点来维护 Server 的地址列表就保证了请求不会被分配到已经停机的服务上。

在上面的讲解中，轮询策略，随机策略和一致性哈希策略都使用 Java 简单的实现了 Demo，那么接下来我们就使用最小连接数策略来实现请求的分配。



### 3.1 临时节点和最小连接数策略实现负载均衡

首先我们需要在集群的每一个 Server 中都使用 Zookeeper 客户端 Curator 来连接 Zookeeper 服务端，当 Server 启动时，使用 Curator 连接 Zookeeper 服务端，并用自身的地址信息创建临时节点到 Zookeeper 服务端。

我们还可以提供手动下线 Server 的方法，需要 Server 下线时可以手动调用删除节点的方法，需要 Server 上线时再次使用自身的地址信息来创建临时节点。

除了维护 Server 的地址信息外，我们还需要维护请求的会话连接数，我们可以使用节点的 data 来保存请求会话的连接数。

我们使用在 Zookeeper Curator 一节创建的 Spring Boot 测试项目来实现：

```java
/**
 * 最小连接数策略 Demo
 * Server 服务端注册地址
 */
@Component
public class MinimumConnectionsStrategyServer implements ApplicationRunner {

    @Autowired
    private CuratorService curatorService;

    // Curator 客户端
    public CuratorFramework client;
    // 当前服务地址的临时节点
    public static String SERVER_IP;
    // 当前服务地址临时节点的父节点，节点类型为持久节点
    public static final String IMOOC_SERVER = "/imooc-server";

    /**
     * 服务启动后自动执行
     *
     * @param args args
     * @throws Exception Exception
     */
    @Override
    public void run(ApplicationArguments args) throws Exception {
        // Curator 客户端开启会话
        client = curatorService.getCuratorClient();
        client.start();
        // 注册地址信息到 Zookeeper
        registerAddressToZookeeper();
    }

    /**
     * 注册地址信息到 Zookeeper
     * 服务启动时和服务手动上线时调用此方法
     *
     * @throws Exception Exception
     */
    public void registerAddressToZookeeper() throws Exception {
        // 判断父节点是否存在，不存在则创建持久节点
        Stat stat = client.checkExists().forPath(IMOOC_SERVER);
        if (stat == null) {
            client.create().creatingParentsIfNeeded().forPath(IMOOC_SERVER);
        }
        // 获取本机地址
        String address = InetAddress.getLocalHost().getHostAddress();
        // 创建临时节点，节点路径为 /IMOOC_SERVER/address，节点 data 为 请求会话数，初始化时为 0.
        // /imooc-server/192.168.0.77
        SERVER_IP = client.create()
                .withMode(CreateMode.EPHEMERAL)
                .forPath(IMOOC_SERVER + "/" + address, "0".getBytes());
    }

    /**
     * 注销在 Zookeeper 上的注册的地址
     * 服务手动下线时调用此方法
     *
     * @throws Exception Exception
     */
    public void deregistrationAddress() throws Exception {
        // 检查该节点是否存在
        Stat stat = client.checkExists().forPath(SERVER_IP);
        // 存在则删除
        if (stat != null) {
            client.delete().forPath(SERVER_IP);
        }
    }
}
```

在客户端的请求调用集群服务之前，先使用 Curator 获取 IMOOC_SERVER 下所有的临时节点，并寻找出 data 最小的临时节点，也就是最小连接数的服务。

在客户端发送请求时，我们可以让当前 Server 的请求会话数加 1，并更新到临时节点的 data，完成请求时，我们可以让当前 Server 的请求会话数减 1，并更新到临时节点的 data 。

```java
/**
 * 最小连接数策略 Demo
 * Client 客户端发送请求
 */
@Component
public class MinimumConnectionsStrategyClient implements ApplicationRunner {

    @Autowired
    private CuratorService curatorService;

    // Curator 客户端
    public CuratorFramework client;
    // 服务列表节点的 父节点
    public static final String IMOOC_SERVER = "/imooc-server";

    @Override
    public void run(ApplicationArguments args) throws Exception {
        // Curator 客户端开启会话
        client = curatorService.getCuratorClient();
        client.start();
    }

    /**
     * 获取最小连接数的服务
     * 发送请求前调用此方法，获取服务地址
     *
     * @return String
     * @throws Exception Exception
     */
    public String getTheMinimumNumberOfConnectionsService() throws Exception {
        // 获取所有子节点
        List<String> list = client.getChildren().forPath(IMOOC_SERVER);
        // 新建 Map
        Map<String, Integer> map = new HashMap<>();
        // 遍历服务列表，保存服务地址与请求会话数的映射关系
        for (String s : list) {
            byte[] bytes = client.getData().forPath(IMOOC_SERVER + "/" + s);
            int i = Integer.parseInt(new String(bytes));
            map.put(s, i);
        }
        // 寻找 map 中会话数最小的值
        Optional<Map.Entry<String, Integer>> min = map.entrySet().stream().min(Map.Entry.comparingByValue());
        // 不为空的话
        if (min.isPresent()) {
            // 返回 服务地址 ip
            Map.Entry<String, Integer> entry = min.get();
            return entry.getKey();
        } else {
            // 没有则返回服务列表第一个服务地址 ip
            return list.get(0);
        }
    }

    /**
     * 增加该服务的请求会话数量
     * 使用服务地址处理业务前调用此方法
     *
     * @param ip 服务地址
     * @throws Exception Exception
     */
    public void increaseTheNumberOfRequestedSessions(String ip) throws Exception {
        byte[] bytes = client.getData().forPath(IMOOC_SERVER + "/" + ip);
        int i = Integer.parseInt(new String(bytes));
        i++;
        client.setData().forPath(IMOOC_SERVER + "/" + ip, String.valueOf(i).getBytes());
    }

    /**
     * 减少该服务的请求会话数量
     * 请求结束时调用此方法减少会话数量
     *
     * @param ip 服务地址
     * @throws Exception Exception
     */
    public void reduceTheNumberOfRequestedSessions(String ip) throws Exception {
        byte[] bytes = client.getData().forPath(IMOOC_SERVER + "/" + ip);
        int i = Integer.parseInt(new String(bytes));
        i--;
        client.setData().forPath(IMOOC_SERVER + "/" + ip, String.valueOf(i).getBytes());
    }
}
```

这样我们就使用 Zookeeper 的临时节点完成了一个简单的最小连接数策略的负载均衡。



## 4. 总结

在本节的内容中，我们学习了为什么要使用负载均衡，负载均衡的策略，以及使用 Zookeeper 的临时节点来实现负载均衡。以下是本节内容的总结：

1. 分布式环境下为什么要使用负载均衡。
2. 负载均衡的策略有哪些。
3. 使用 Zookeeper 的临时节点实现负载均衡。