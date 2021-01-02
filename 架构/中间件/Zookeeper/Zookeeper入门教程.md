# Zookeeper 简介


![图片描述](http://qiniu.cdn.easyspring.net/20210102232150.jpg)



## 1. 前言

大家好，今天我们来介绍一个在分布式环境中经常使用的技术—— **Apache Zookeeper** 。Apache ZooKeeper 是 Apache Software Foundation 下的开源志愿者项目。接下来我们主要来介绍一下 Zookeeper 是什么？它有什么作用？以及我们为什么要学习 Zookeeper。



## 2. 什么是 Zookeeper

什么是 Zookeeper 呢？我们先来看一下 [Zookeeper 的官网](https://zookeeper.apache.org/)介绍：

![Zookeeper 的官网介绍](http://qiniu.cdn.easyspring.net/20210102232156.jpg)
原文直接翻译过来的概念很抽象，那我们简单的解释一下。在分布式环境中，存在着大量的服务，服务与服务之间难以做到彼此协调，也不便于开发人员对服务进行维护管理，而 Zookeeper 使用它简单的结构和 API ，协调服务与服务之间的关系，让开发人员专注于应用程序的核心业务逻辑，更方便的对应用程序的服务进行管理维护。
所以我们可以把 Zookeeper 叫做**分布式协调服务**。

简单介绍了 Zookeeper 是什么，接下来我们就来了解一下 Zookeeper 具体的应用场景。



## 3. Zookeeper 的应用

1. **服务注册与发现**
   当我们的分布式系统增加了一个服务，我们只需要利用 Znode 和 Watcher，让它注册到 Zookeeper 中，我们就可以很方便的对这个服务进行管理；
2. **分布式锁**
   为了防止在分布式环境下，服务中多个进程之间互相干扰，我们可以用 Zookeeper 的临时顺序节点实现分布式锁，对这些进程进行调度，让它们顺序执行；
3. **配置管理**
   我们可以把核心的配置文件交给 Zookeeper 管理。当我们修改配置文件时，Zookeeper 就会把配置文件的信息同步到集群中的所有节点中去。

那么 Zookeeper 是依靠什么来实现这些功能的呢？接下来我们来关注 Zookeeper 有什么特点。



## 4. Zookeeper 的特点

1. 在分布式环境下，Zookeeper 的部署方式为一主（ Leader ）多从（ Follower ）的集群方式，只要半数以上的节点（包括 Leader 节点）存活，Zookeeper 集群就能正常服务。就算是 Leader 节点挂掉了，Zookeeper 也会进行崩溃恢复，所说 Zookeeper 集群本身是高可用的；
2. Zookeeper 集群的数据具有全局一致性。也就是说，无论客户端连接到 Zookeeper 集群的哪一个从节点，获取的数据都是一致的；
3. 在 Zookeeper 集群节点进行数据同步更新时，要么全部成功，要么全部失败。所以 Zookeeper 的数据更新具有原子性；
4. 在同一个客户端对 Zookeeper 节点进行更新请求操作时，会根据发送的顺序依次去执行；
5. 由于 Zookeeper 能存储的数据量非常小，所以数据的同步更新也会非常快。也就可以说在一定时间段内，客户端获取的数据是实时的。

根据上面的特点，我们可以了解到 Zookeeper 在分布式环境中的作用还是非常强大的。所以我们还是有必要去学习一下 Zookeeper 的。
说了这么多 Zookeeper 的功能，那它与其他类似功能的技术相比较有什么区别呢？接下来我们用 Zookeeper 和其他技术进行一下比较。



## 5. Zookeeper 与其他技术的比较

1. **Zookeeper 与 Redis 分布式锁比较**
   除了 Zookeeper 可以实现分布式锁之外，我们还可以使用高性能缓存技术 Redis 来实现，我们来比较一下它们的优缺点。

   | 分布式锁  | 优点                                                         | 缺点                                                         |
   | :-------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
   | Zookeeper | 1. 功能已经封装，实现简单 2. 有等待锁的队列，提升了抢锁的效率 | 添加和删除节点性能较低                                       |
   | Redis     | Set 和 Del 指令的性能高                                      | 1. 实现较复杂，需要考虑超时、原子性、误删的情况 2. 没有等锁队列，只能通过客户端自旋来等锁，效率低下 |

2. **Zookeeper 与 Eureka 的比较**
   Eureka 是 Spring Cloud 微服务架构的分布式注册中心。
   在进行比较之前，我们来了解一下 CAP 定理。什么是 CAP 定理呢？

   - **C ：** Consistent ，一致性，需要保证数据的一致性。
   - **A ：** Availability ，可用性，需要保证服务的可用性。
   - **P ：** Partition tolerance ，分区容错性，服务对网络分区故障的容错性。

   在 CAP 这个定理中，任何分布式系统都只能保证其中两条。那么 Zookeeper 和 Eureka 又是保证的哪两条呢？

   | 分布式注册中心        | 优点                                                         | 缺点                                                         |
   | :-------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
   | Zookeeper （保证 CP） | 新的服务注册时会同步到其他节点，保证了节点数据的一致性       | 为了保证一致性，在 Leader 选举阶段服务不能注册，失去了可用性 |
   | Eureka （保证 AP）    | Eureka 的各个节点是平等的，只要有一个节点存在，就可以提供服务 | 新服务注册时，不会把数据同步到其他节点上，失去了数据一致性   |



## 6. 学习 Zookeeper 的必要条件

想要学习 Zookeeper ，我们必须有以下技能：

1. **Java** ：Zookeeper 是基于 Java 语言开发的，这是学习 Zookeeper 最基本的要求；
2. **Linux** ：Zookeeper 一般都是部署在 Linux 上的，所以我们需要知道如何操作 Lunix ，以及如何部署 Zookeeper ；
3. **分布式开发**：Zookeeper 作为分布式环境中重要的组件，我们必须了解什么是分布式项目，如何去开发分布式项目，以及分布式的项目会遇到什么问题。



## 7. 课程设计思路

在 Zookeeper 的课程中，我们的学习路线从 Zookeeper 的基础知识入门，到简单使用 Zookeeper ，再到 Zookeeper 的实现原理，最后使用 Zookeeper 进行应用实战，一步一步从入门到 Zookeeper 应用高手。以下是 Zookeeper 课程的学习路线：

- **Zookeeper 基础入门**：
  包括 Zookeeper 的数据模型，Zookeeper 安装及部署，以及两种 Zookeeper 的 Java 客户端的初步使用，有了扎实的基础我们才能深入学习它的实现原理；
- **Zookeeper 实现原理**：
  包括 Zookeeper 通信原理，Zookeeper 监听机制，Zookeeper ACL，Zookeeper 序列化方式，Zookeeper ZAB 协议。其中重点是 Zookeeper ZAB 协议，包括两种运行模式：崩溃恢复模式和消息广播模式。了解了 Zookeeper 的实现原理，我们才能更好的来使用 Zookeeper；
- **Zookeeper 应用实战**：
  在 Zookeeper 实战内容中，我们使用 Zookeeper 实现了分布式锁、分布式 ID、负载均衡、配置中心、集群管理等，学习了如何使用了高效的部署方式 —— Docker 来构建我们的 Zookeeper 集群，以及如何对 Zookeeper 的 Java 进程和运行状态进行监控，最后我们还学习了在 Kafka 和 Dubbo 两大框架中是如何使用 Zookeeper 的。

相信通过这些内容的学习，同学们一定会熟练的掌握 Zookeeper，并使用 Zookeeper 解决在实际的开发中遇到的分布式环境所带来的问题。



## 8. 小结

本节课程我们主要了解了 Zookeeper 是什么，Zookeeper 的特点。我们来对本节内容进行总结：

- Zookeeper 是一种**分布式协调服务**。
- Zookeeper 的应用有服务注册与发现，分布式锁，配置管理。
- Zookeeper 的特点：集群的高可用性，数据的一致性、原子性，执行的顺序性，实时性。
- Zookeeper 优缺点：Zookeeper 是 CP 系统，在保证数据一致性的同时，不能保证服务注册的高可用。



# Zookeeper 的数据模型



## 1. 前言

开始学习 Zookeeper 的第一步，我们首先来学习 Zookeeper 的数据模型。那么我们为什么要先学习 Zookeeper 的数据模型呢？Zookeeper 的数据模型又是什么样的呢？Zookeeper 的数据模型又有什么样的特点呢？接下来我们就带着这几个问题开始 Zookeeper 的数据模型学习之旅。



## 2. Zookeeper 数据模型的结构

Zookeeper 数据模型的结构是基于节点的，我们把这种节点叫做 **Znode** ，具体结构我们来看下图：

![Zookeeper 数据模型的结构](http://qiniu.cdn.easyspring.net/20210102232827.jpg)
我们可以看见，这种结构和数据结构中的树类似，也和文件系统的目录类似。我们知道文件系统的引用是非常方便的，那么我们想引用 Zookeeper 某个节点，那么我们该如何引用呢？
我们可以通过路径引用的方式来访问 Znode 节点：

```shell
/电脑/戴尔
/手机/华为
```

我们来说明一下书写规则：第 1 个 `/` 为根节点，`电脑` 为根节点的子节点，第 2 个 `/` 是对下一个子节点的引用，后面跟上哪个节点的名称，就是对哪个节点的引用。

> **Tips：** 我们对节点的引用，必须书写全路径，也就是说必须要从根节点开始。在 Zookeeper 底层的实现中，把 Znode 的绝对路径作为 key ，Znode 本身作为 value 来保存的。使用绝对路径来查询也提高了 Zookeeper 的性能。

介绍完 Zookeeper 数据模型的结构，也了解了如何引用 Znode 节点，接下来我们对 Znode 节点进行详细的讲解。



## 3. Znode 的元素组成

我们先来了解 Znode 节点中由哪些元素组成，请看下图：

![Znode 的元素组成](http://qiniu.cdn.easyspring.net/20210102232848.jpg)
我们可以看到，Znode 节点中由 4 种元素组成，接下来我们来分别介绍一下每个元素具体是什么。
Znode 节点元素介绍：

- **data ：** Znode 存储的数据信息，这里的数据指用户保存的数据；
- **ACL ：** 对节点进行权限控制，记录了哪些用户或者哪些 IP 地址可以访问本节点；
- **child ：** 当前节点的子节点引用，通过这个节点来找到它的子节点；
- **stat ：** 包含 Znode 的各种元数据，比如事务 ID、版本号、时间戳、大小等 Znode 本身的数据。

> **Tips：** Znode 的 data 元素存储的信息最大不能超过 1MB 。太大的数据会影响 Zookeeper 的同步性能。

在了解了 Znode 的元素组成，每个元素的具体作用之后，我们接下来学习 Znode 节点有哪些类型，以及他们的特点。



## 4. Znode 的类型

本节我们来学习 Znode 的类型以及它们各自的特点。Znode 的类型分为一下 4 种：

- **持久节点：** 持久节点是 Zookeeper 的默认节点，持久节点被创建后会一直存在，除非进行手动删除；
- **持久顺序节点：** 持久顺序节点是在持久节点的基础上，增加了顺序性。也就是说，持久顺序节点被创建时，会根据创建的时间进行编号，根据编号我们就可以判断它们的顺序；
- **临时节点：** 临时节点与持久节点的特点相反，临时节点被创建之后，如果与创建它的客户端断开连接，临时节点就会被销毁；
- **临时顺序节点：** 临时顺序节点就是在临时节点的基础上，增加了顺序性。

学习了 Znode 节点的类型以及它们的特点，那么我们可以利用节点的特点做什么事情呢？接下来我们来了解节点的应用。



## 5. Znode 的应用

根据节点的类型以及它们的特点，我们可以实现以下功能：

1. 我们可以使用**临时节点**来实现服务注册与发现。在某个服务注册到 ZooKeeper 时，我们可以让这个这个服务创建一个临时节点，并把它的访问信息交给到 Zookeeper 维护。当这个服务与 Zookeeper 断开连接时，这个临时节点就会被销毁，这时 Zookeeper 发现这个服务离线了，就会移除它的访问地址，避免出现 404 的情况。我们也可以手动删除某个临时节点让相对应的服务下线；
2. 当我们有大量的服务时，一旦配置信息需要修改，会消耗我们大量的时间去每个服务中修改，而且还有可能会出错，这种情况我们就可以使用**持久节点**来保存全局的配置信息。当某个服务注册到 ZooKeeper 时，可以去保存配置信息的节点读取配置信息。当我们修改配置时，Zookeeper 会通知这些服务，服务就会重新去读取配置信息；
3. 我们可以使用**临时顺序节点**来实现**分布式锁**。当多个服务同时对一个资源进行修改时，会出现数据错误，所以我们要避免这种情况。我们这里采取的方式就是为这个资源加锁，想要获取这个资源的服务会创建一个临时顺序节点，根据它的顺序判断这个临时顺序节点是否为第一个，如果是第一个则成功获得锁，这时这个服务就可以对这个资源进行修改了。完成操作后或者这个服务断线了都会删除这个节点，也就是释放了锁。后面的服务会根据它创建的临时顺序节点的顺序来依次对资源进行操作。

根据 Znode 特点的来实现的应用还有很多，后面的文章我们再详细介绍。了解了节点的一些应用，那么我们该如何对节点进行操作呢？接下来我们就来介绍 Znode 节点的操作命令。



## 6. Znode 节点的操作

使用 Zookeeper 客户端，我们可以通过以下命令来操作 Znode 节点。

- **创建节点：** `create`

  ```bash
  # 创建一个持久节点
  create /persistent_node
  # 创建一个持久的顺序节点
  create -s /persistent_sequential_node
  # 创建一个临时节点
  create -e /ephemeral_node
  # 创建一个临时的顺序节点
  create -s -e /ephemeral_sequential_node
  ```

- **删除节点：** `delete`

  ```bash
  delete /config/topics/test
  ```

- **获得一个节点的数据：** `get`

  ```bash
  get /persistent_node
  ```

- **设置一个节点的数据：** `set`

  ```bash
  set /brokers myNewData
  ```

- **获取子节点：** `ls`

  ```bash
  # 获取根节点下的子节点
  ls /
  # 根节点下的子节点有 zk-watcher-2，zookeeper
  [zk-watcher-2, zookeeper]
  ```

> **Tips：** 我们在使用这些命令操作节点时，后面的节点必须是全路径引用。



## 7. 总结

经过上面的讲解，我们知道了很多功能的实现都是基于 Zookeeper 的结构以及 Znode 的类型和它们的特点，所以学习 Zookeeper 的数据模型还是很有必要的。现在我们来对本节的内容进行总结：

- Zookeeper 数据模型的结构为树形节点。
- Znode 的元素组成有 4 种：data（用户数据）、ACL（权限信息）、child（子节点引用）、stat（元数据）。
- Znode 的类型有 4 种：持久节点、持久顺序节点、临时节点、临时顺序节点。
- 我们可以根据 Znode 的特点来实现各种功能，比如服务注册与发现、配置中心、分布式锁等。
- Zookeeper 客户端操作节点的常用命令。





# Zookeeper 单机模式



## 1. 前言

本小节我们来学习如何在 Linux 环境下部署 Zookeeper 的单机模式，以及 Zookeeper 的单机模式是如何运行的。在学习本小节之前，同学们需要准备好 Linux 环境，我们这里使用的是 Ubuntu-18.04.2 的镜像。



## 2. Zookeeper 的安装



### 2.1 安装 Zookeeper 前置条件

在安装 Zookeeper 之前，我们需要在 Linux 环境中安装 Java 环境，我们这里使用的是 JDK 1.8.0_261，JDK 安装本小节不做演示。我们执行 `java -version` 命令就可以看见我们的 JDK 版本信息：

```shell
java version "1.8.0_261"
Java(TM) SE Runtime Environment (build 1.8.0_261-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.261-b12, mixed mode)
```

有了 Java 环境，我们就可以进行 Zookeeper 的安装了。



### 2.2 安装 Zookeeper

先让我们进入到一段视频来感受一下安装的过程吧~

视频可以[去这里](http://www.imooc.com/wiki/Zookeeper/zookeeperstandalone.html)看

#### 2.2.1 下载安装包

首先我们去 Zookeeper 官网下载 Zookeeper 的安装包，这里我们的版本为 Apache ZooKeeper 3.6.1
地址：https://zookeeper.apache.org/releases.html

> **Tips：** Zookeeper 官方建议 Apache ZooKeeper 3.6.1 使用 JDK 1.8.0_211 及以上版本。

#### 2.2.2 解压安装包

我们在 `/usr/local` 文件夹下新建 `zookeeper`文件夹，把下载好的 `apache-zookeeper-3.6.1-bin.tar.gz` 使用 ftp 工具放到 `zookeeper` 文件夹中进行解压，然后进入解压后的文件夹，查看 zookeeper 的文件列表，操作如下：

```shell
# 新建 zookeeper 文件夹
mkdir /usr/local/zookeeper
# 进入 zookeeper 文件夹
cd /usr/local/zookeeper/
# 解压 
tar -zxvf apache-zookeeper-3.6.1-bin.tar.gz 
# 进入解压完成后的文件夹
cd apache-zookeeper-3.6.1-bin/
# 使用 ll 命令查看文件列表
ll
```

#### 2.2.3 Zookeeper 文件目录

我们来介绍一下文件列表的信息：

```shell
## 存放 zookeeper 命令的文件夹
drwxr-xr-x 2 cdd  cdd   4096 4月  21 14:59 bin/
## 存放 zookeeper 的配置文件
drwxr-xr-x 2 cdd  cdd   4096 4月  21 14:59 conf/
## 存放 zookeeper 的说明文档
drwxr-xr-x 5 cdd  cdd   4096 4月  21 15:00 docs/
## 存放 zookeeper 相关 jar 包的文件夹
drwxr-xr-x 2 root root  4096 8月   1 10:01 lib/
## 开源声明
-rw-r--r-- 1 cdd  cdd  11358 4月  21 14:59 LICENSE.txt
## 公告文件
-rw-r--r-- 1 cdd  cdd    432 4月  21 14:59 NOTICE.txt
-rw-r--r-- 1 cdd  cdd   1963 4月  21 14:59 README.md
-rw-r--r-- 1 cdd  cdd   3166 4月  21 14:59 README_packaging.md
```

Zookeeper 的安装包是解压版的，开箱即用，不需要进行编译工作。接下来我们就可以启动 Zookeeper 服务了。



### 2.3 启动 Zookeeper 服务

我们在 Zookeeper 的根目录新建一个 data 文件夹来存放 Zookeeper 服务的数据信息。

```shell
mkdir data
```

接下来我们进入 `conf` 文件夹来配置 Zookeeper 服务的启动信息：

```shell
# 进入配置文件夹
cd conf/
# 查看文件列表
ll
-rw-r--r-- 1 cdd  cdd   535 4月  21 14:59 configuration.xsl
# 日志配置文件
-rw-r--r-- 1 cdd  cdd  3435 4月  21 14:59 log4j.properties
# zookeeper 核心配置文件样本
-rw-r--r-- 1 cdd  cdd  1148 4月  21 14:59 zoo_sample.cfg
```

我们复制一份 `zoo_sample.cfg` 为 `zoo.cfg` ，然后进行编辑：

```shell
cp zoo_sample.cfg zoo.cfg
vi zoo.cfg
```

我们配置 dataDir 数据文件夹为我们刚才新建的 data 目录：

```shell
# 心跳检查间隔时间：毫秒
tickTime=2000
# 初始连接时心跳检查的最大数量
initLimit=10
# 请求和应答时心跳检查的最大数量
syncLimit=5
# 数据文件夹的路径
dataDir=/usr/local/zookeeper/apache-zookeeper-3.6.1-bin/data
# 通信端口，默认2181
clientPort=2181
```

配置好 `zoo.cfg` ，接下来我们进入命令文件夹 `bin`，使用启动命令就可以启动 zookeeper 服务了

```shell
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/
# zookeeper 服务 启动
./zkServer.sh start
```

控制台输出以下信息，就说明我们已经启动成功了：

```shell
ZooKeeper JMX enabled by default
Using config: /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/../conf/zoo.cfg
Starting zookeeper ... STARTED
```



### 2.4 Zookeeper 服务端命令

这里我们来介绍一下可以控制 Zookeeper 服务的命令：

```shell
# 启动
./zkServer.sh start
# 停止
./zkServer.sh stop
# 重启
./zkServer.sh restart
# 当前状态
./zkServer.sh status
```

我们来看一下 Zookeeper 服务启动之后的状态是什么样的：

```shell
./zkServer.sh status
#我们可以通过客户端连接 Zookeeper 服务，地址为本机ip地址，端口号为 2181
Client port found: 2181. Client address: localhost.
# standalone 表示单机模式
Mode: standalone
```

接下来我们就可以使用 Zookeeper 的客户端来连接 Zookeeper 服务了。



## 3. Zookeeper 客户端

使用 Zookeeper 客户端连接 Zookeeper 服务，我们需要使用 `./zkCli.sh` 命令：

```shell
# 进入 bin 文件夹
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/
# 连接命令
./zkCli.sh 
# 连接时输出信息
Connecting to localhost:2181
...
# 出现下面这一行时，表示我们连接成功
[zk: localhost:2181(CONNECTED) 0] 
```

这里我们就可以使用上一节学习过的命令来操作节点了，我们来测试一下：

```shell
# 获取根节点的子节点
ls /
# 输出默认的子节点 zookeeper
[zookeeper]
# 创建根节点的子节点 imooc
create /imooc
# 输出创建成功信息
Created /imooc
# 创建后再次获取根节点的子节点
ls /
# 输出两个子节点
[imooc, zookeeper]
# 我们可以给节点设置数据
set /imooc wiki
# 然后我们再获取 imooc 节点的数据
get /imooc
# 输出我们设置的信息
wiki
# 最后我们测试一下删除命令
delete /imooc
# 删除后再次获取根节点的子节点
ls /
# 输出子节点 zookeeper，imooc 节点被删除
[zookeeper]
# 退出 Zookeeper 客户端命令
quit
```

通过上面的学习，我们知道了如何部署单机模式的 Zookeeper 服务，以及如何通过 Zookeeper 客户端连接 Zookeeper 服务端，来对 Znode 节点进行操作。那么 Zookeeper 是如何为我们提供服务的呢，接下来我们就来了解单机模式下的 Zookeeper 的工作流程。



## 4. 单机模式下 Zookeeper 服务的工作流程

本小节我们来了解单机模式下 Zookeeper 服务的工作流程。



### 4.1 Zookeeper 服务启动

1. 在我们执行启动命令 `./zkServer.sh start` 时，会启动 Java 类 `org.apache.zookeeper.server.quorum.QuorumPeerMain` ，并执行该类里面的方法 `main.initializeAndRun(args)`，这个方法就是 Zookeeper 服务的启动入口；
2. 在 Zookeeper 服务启动的过程中，会去解析 `zoo.cfg` 配置文件，包括数据文件目录，端口号等信息；
3. 读取完配置文件，Zookeeper 服务会创建 `DatadirCleanupManager` 类作为数据清除管理器，用于清理历史数据，保证 Zookeeper 服务不会因为存储空间影响其正常运行。



### 4.2 Zookeeper 服务初始化

Zookeeper 服务初始化的过程主要是实例化服务对象，下面我们来介绍会实例化哪些对象

1. **ServerStats：** ServerStats 类用于统计 ZooKeeper 服务运行过程中的状态信息，包括接受到客户端的请求次数，处理客户端请求的次数，向客户端发送请求的次数以及出现请求延迟情况的次数。也就是说这个类会对 Zookeeper 服务的运行状态和性能进行监控；
2. **FileTxnSnapLog：** 我们用 FileTxnSnapLog 类来实现 Zookeeper 服务的数据存储，对数据进行持久化操作。数据存储的路径会读取 `zoo.cfg` 配置文件的 `dataDir`；
3. **ServerCnxnFactory：** 我们可以通过 ServerCnxnFactory 类来指定 Zookeeper 的通信框架。在 Zookeeper 3.4.0 版本后，引入了第三方 Netty 等框架供我们选择使用。

经过一系列的对象实例化，Zookeeper 还需要从快照数据和事务日志中恢复数据，才真正的完成启动，这时就可以使用 Zookeeper 客户端来进行连接发送请求了。



### 4.3 Zookeeper 服务请求处理器

不同的客户端发送的请求， ZooKeeper 服务会使用不同的请求处理器来处理不同的逻辑。在单机模式下的 Zookeeper 服务，使用了 3 种请求处理器：

![请求处理器](http://qiniu.cdn.easyspring.net/20210102232906.jpg)

1. PrepRequestProcessor
2. SyncRequestProcessor
3. FinalRequestProcessor

这三个处理器都实现了接口 RequestProcessor 。当客户端请求到达 ZooKeeper 服务进行处理的时候，严格按照上面的顺序分别调用这 3 个处理器来处理请求中的对应逻辑。



## 5. 总结

本小节我们学习了在 Linux 环境下部署单机模式的 Zookeeper 服务，使用 Zookeeper 客户端连接 Zookeeper 服务，然后使用命令来操作 Znode 节点，以及单机模式的 Zookeeper 服务的工作流程。接下来我们对本节内容进行总结：

1. 单机模式下的 Zookeeper 的安装。
2. Zookeeper 服务端命令 `./zkServer.sh` 。
3. Zookeeper 客户端连接 Zookeeper 服务端命令 `./zkCli.sh` 。
4. Zookeeper 客户端操作 Znode 节点的命令。
5. 单机模式的 Zookeeper 工作流程。





# Zookeeper 集群模式



## 1. 前言

在我们的生产环境中，Zookeeper 的单机模式无法保证 Zookeeper 服务的高可用性，也就是我们常说的单点故障问题，性能也存在瓶颈。所以在生产环境中，Zookeeper 最好的使用方式就是 Zookeeper 的集群模式，这样不仅在性能方面比单机模式更好，服务的高可用性也得到了保障。本节我们就来学 Zookeeper 集群模式的部署，以及在集群模式下的 Zookeeper 服务是如何工作的。



## 2. Zookeeper 集群模式部署

在上一节中，我们学习了 Zookeeper 的单机模式，我们可以在此基础上进行 Zookeeper 集群模式的部署。Zookeeper 集群的数量通常是大于等于 3 的奇数，比如 3、5、7，但也不宜太多，太多的集群数量会影响集群之间的同步性能。这里我们以 3 的集群数量来进行讲解。

> **Tips：** Zookeeper 集群的数量为什么需要奇数个呢？如果采用偶数，在 Leader 节点选举投票时，有可能会产生两个 Leader 节点，两个 Leader 都不能满足大多数选票的原则，这时就会出现**脑裂**问题。


![集群模式](http://qiniu.cdn.easyspring.net/20210102232914.jpg)



### 2.1 集群环境准备

我们需要提供相同环境的 3 台虚拟机，Zookeeper 和 JDK 环境都已准备好。

| Server  | IP           |
| :------ | :----------- |
| Server1 | 192.168.0.77 |
| Server2 | 192.168.0.88 |
| Server3 | 192.168.0.99 |

> **Tips：** 同学们进行配置的时候使用自己的服务器 IP 地址进行配置。

接下来我们来对这 3 台虚拟机中的 Zookeeper 进行配置。



### 2.2 集群的 myid 配置

myid 文件的内容为服务器编号，服务器编号我们可以自定义，**只要每台机器不同即可**。
首先我们进入 Zookeeper 的根目录，在 data 文件夹中新建 myid 文件，添加服务器编号，操作如下：

```shell
# 进入 Zookeeper 根目录
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/
```

**Server1 的 myid 配置为 1 ：**

```shell
# echo 在文件末尾添加内容，若文件不存在，会新建此文件
echo '1' > data/myid
```

**Server2 的 myid 配置为 2：**

```shell
# echo 在文件末尾添加内容，若文件不存在，会新建此文件
echo '2' > data/myid
```

**Server3 的 myid 配置为 3：**

```shell
# echo 在文件末尾添加内容，若文件不存在，会新建此文件
echo '3' > data/myid
```

配置好了 myid，接下来我们对 zoo.cfg 进行配置。



### 2.3 集群的 cfg 配置

我们进入 Zookeeper 根目录中的 conf 文件夹，编辑 zoo.cfg 文件：

```shell
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/conf/
vi zoo.cfg
```

在 zoo.cfg 配置文件的末尾添加以下配置，**这里每台机器都是同样的配置**。

```properties
server.1=192.168.0.77:2888:3888
server.2=192.168.0.88:2888:3888
server.3=192.168.0.99:2888:3888
```

我们来介绍一下这一段配置的含义，以 `server.1=192.168.0.77:2888:3888` 为例：

- **server.1：** 表示编号为 1 的服务器，这里的 1 要与该服务器的 myid 文件的内容相同；
- **192.168.0.77：** 该服务器的地址；
- **2888：** 服务之间通信的端口，默认值 2888；
- **3888：** 服务之间选举的端口，默认值 3888。

到这里我们的配置部分就完成了，接下来我们依次启动 3 台机器的 Zookeeper 服务。



### 2.4 启动服务

进入 bin 目录，使用 start 命令启动 Zookeeper 服务：

```shell
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/
# 启动命令
./zkServer.sh start
```

启动完成控制台会输出以下内容：

```shell
ZooKeeper JMX enabled by default
Using config: /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/../conf/zoo.cfg
Starting zookeeper ... STARTED
```



### 2.5 查看服务状态

完成 3 台机器的 Zookeeper 服务启动后，我们使用 status 命令来观察 Zookeeper 服务的状态：

```shell
./zkServer.sh status 
```

**Server1：**

```shell
ZooKeeper JMX enabled by default
Using config: /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/../conf/zoo.cfg
Client port found: 2181. Client address: localhost.
# follower 表示为集群中的从节点
Mode: follower 
```

**Server2：**

```shell
ZooKeeper JMX enabled by default
Using config: /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/../conf/zoo.cfg
Client port found: 2181. Client address: localhost.
# follower 表示为集群中的从节点
Mode: follower
```

**Server3：**

```shell
ZooKeeper JMX enabled by default
Using config: /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/../conf/zoo.cfg
Client port found: 2181. Client address: localhost.
# leader 表示为集群中的主节点
Mode: leader
```

我们可以观察到，Server1 和 Server2 的状态是 follower，也就是从节点，Server3 的状态是 leader，也就是主节点。这样我们 Zookeeper 一主多从的集群环境就部署好了。接下来我们使用 Zookeeper 客户端进行测试。



## 3. Zookeeper 集群的同步

在 Zookeeper 集群服务中，每个 Follower 节点都可以对外提供服务，那么我们操作其中一个 Follower 节点时，如何确保我们获取的数据与其它 Follower 节点的数据是一样的呢？在接下来的测试中，我们来观察 Follower 节点的数据。
我们首先对其中一个 Server 进行操作，使用 [zkCli.sh](http://zkcli.sh/) 连接 Server1 的 Zookeeper 服务，查看 Znode 节点：

```shell
# 进入 bin 文件夹
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/
# 连接命令
./zkCli.sh 
# 查看根节点下的子节点
ls /
# 只有默认的 zookeeper 节点
[zookeeper]
```

此时我们使用 create 命令对 Server1 的节点进行增加操作：

```shell
 # 创建根节点的子节点 imooc
 create /imooc
 # 输出 imooc 创建成功
 Created /imooc
```

创建成功之后我们再来查看一下 Server1 根节点的子节点：

```shell
# 查看根节点下的子节点
ls /
# 根节点下的子节点，新增了 imooc 节点
[imooc, zookeeper]
```

对 Server1 的 Znode 操作成功之后，接下来我们来查看一下 Server2 和 Server3 的 Zookeeper 节点信息：

```shell
# 进入 bin 文件夹
cd /usr/local/zookeeper/apache-zookeeper-3.6.1-bin/bin/
# 连接命令
./zkCli.sh 
# 查看根节点下的子节点
ls /
# 新增加的 imooc 节点和默认的 zookeeper 节点
[imooc, zookeeper]
```

我们发现，Server2 和 Server3 的 Zookeeper 服务的根节点也有 Server1 中新增的 imooc 节点，为什么 Server1 增加的节点，另外两个服务也会出现呢？
这个问题其实就是 Zookeeper 集群的同步机制。当其中一个节点的信息被修改时，首先会修改 Leader 节点，然后再将数据同步到集群中所有的 Follower 节点，这样就确保了集群中所有节点的数据一致。



## 4. Zookeeper 集群的启动流程

Zookeeper 集群启动时，首先会通过配置文件判断 Zookeeper 的启动方式是否为集群模式，如果为集群模式，则通过配置文件进行初始化工作，然后集群的节点进行 Leader 选举，选举完毕后， Follower 节点与 Leader 节点进行数据同步，完成同步后就可以启动 Leader 和 Follower 实例了。

![ Zookeeper 集群的启动流程](http://qiniu.cdn.easyspring.net/20210102233044.jpg)



### 4.1 初始化

首先在集群启动的过程中，每个 Zookeeper 服务的主函数会都通过 zoo.cfg 配置文件来判定这个 Zookeeper 服务是以哪种模式启动的，然后通过配置文件进行初始化工作。
与单机模式初始化不同的是，集群模式的 Zookeeper 服务在初始化过程中还需要配置服务器列表、Leader 选举算法、会话超时时间等参数。



### 4.2 Leader 选举

在所有 Zookeeper 服务初始化完成后，第一件事情就是创建 Java 类 QuorumCnxManager 来进行 Zookeeper 集群的 Leader 选举。
在选举过程中，每个 Zookeeper 服务会使用自身的服务器编号 SID 、最新的事务编号 ZXID 、和当前服务器纪元值 currentEpoch 这三个参数去参加选举，然后根据 zoo.cfg 的 electionAlg 参数来选择 Leader 选举算法，来完成 Leader 的选举，完成选举后 Leader 会向其它 Zookeeper 服务发起数据同步的通知。



### 4.3 Follower 同步

Leader 选举完毕，其它 Zookeeper 服务的状态就会变为 Follower ，在 Follower 接收到来自 Leader 的通知后， Follower 会创建一个 LearnerHandler 类的实例来处理与 Leader 的数据同步，在半数以上的 Follower 完成数据同步后，Leader 和 Follower 的实例就可以启动了。



### 4.4 Leader 和 Follower 启动

在 Leader 和 Follower 实例启动时，创建和启动会话管理器，初始化 Zookeeper 的请求处理链，处理器也会在启动阶段串联请求处理链，然后把 Zookeeper 实例注册到 JMX 服务中，整个 Zookeeper 集群的启动才算完成。



## 5. 总结

本节我们学习了如何部署 Zookeeper 集群，Zookeeper 集群的同步机制，以及 Zookeeper 集群的启动流程。以下是本节内容的总结：

1. Zookeeper 集群模式的部署。
2. Zookeeper 集群模式的同步机制。
3. Zookeeper 集群模式的启动流程。



# Zookeeper ZkClient



## 1. 前言

无论是选择 Zookeeper 的单机模式还是选择 Zookeeper 的集群模式，实际开发中我们都会使用 Java 客户端向Zookeeper 服务端发送请求。本节我们就来学习如何使用 Zookeeper 的 Java 客户端之一 ZkClient。



## 2. ZkClient 客户端

ZkClient 是一个开源的客户端，在 Zookeeper 原生 API 接口的基础上进行了包装，更便于开发人员使用。内部实现了Session超时重连，Watcher反复注册等功能。想要使用 ZkClient，我们需要搭建 Java 开发环境，这里我们使用 IntelliJ IDEA 为开发工具，JDK 我们使用了长期维护的版本 JDK-11.0.8 。接下来我们开始搭建 ZkClient 运行的环境。



### 2.1 ZkClient 的依赖

首先我们新建 Spring Boot 项目，在 pom.xml 文件中加入 zkclient 的依赖：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.3.2.RELEASE</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>cn.cdd</groupId>
    <artifactId>zkclient-demo</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>zkclient-demo</name>
    <description>zkclient-demo project for Spring Boot</description>

    <properties>
        <java.version>11</java.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter</artifactId>
        </dependency>

        <!-- https://mvnrepository.com/artifact/com.101tec/zkclient -->
        <dependency>
            <groupId>com.101tec</groupId>
            <artifactId>zkclient</artifactId>
            <version>0.11</version>
            <!-- 排除冲突 -->
            <exclusions>
                <exclusion>
                    <artifactId>log4j</artifactId>
                    <groupId>log4j</groupId>
                </exclusion>
                <exclusion>
                    <artifactId>slf4j-log4j12</artifactId>
                    <groupId>org.slf4j</groupId>
                </exclusion>
                <exclusion>
                    <artifactId>slf4j-api</artifactId>
                    <groupId>org.slf4j</groupId>
                </exclusion>
            </exclusions>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
            <exclusions>
                <exclusion>
                    <groupId>org.junit.vintage</groupId>
                    <artifactId>junit-vintage-engine</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

</project>
```

加入了 ZkClient的依赖，我们就可以编写程序使用 zkclient 的 API 来向 Zookeeper 服务端发送请求了。



### 2.2 编写 ZkClientServer 类

我们在 Spring Boot 主函数的同级新建目录 service ，在 service 目录中新建类 ZkClientServer ：

```java
package cn.cdd.zkclientdemo.service;

import org.I0Itec.zkclient.ZkClient;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.stereotype.Component;
// 声明 ZkClientServer 类为 Bean，交给 Spring 管理
@Component
public class ZkClientServer {
	// Zookeeper 集群的地址
    @Value(value = "${zookeeper.address}")
    private String address;
	// 获取 ZkClient
    public ZkClient getZkClient() {
        return new ZkClient(address);
    }
}
```

在 application.properties 配置文件中配置 Zookeeper 集群的地址：

```properties
zookeeper.address=192.168.0.77:2181,192.168.0.88:2181,192.168.0.99:2181
```

配置完成后，我们就可以去测试类中进行测试了。



### 2.3 测试

我们在项目中与 main 目录同级的 test 目录中找到测试类 ZkClientDemoApplicationTests ，在其中添加测试方法。

#### 2.3.1 查询测试

```java
package cn.cdd.zkclientdemo;

import cn.cdd.zkclientdemo.service.ZkClientServer;
import org.I0Itec.zkclient.ZkClient;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;

import java.util.List;

@SpringBootTest
class ZkClientDemoApplicationTests {
	// 依赖注入
    @Autowired
    private ZkClientServer zkClientServer;
    
    @Test
    void contextLoads() {
        // 获取 ZkClient 对象
        ZkClient zkClient = zkClientServer.getZkClient();
        // 获取子节点集合
        List<String> children = zkClient.getChildren("/");
        System.out.println(children);
        // 释放资源
        zkClient.close();
    }
}
```

执行测试方法，控制台输出：

```tex
[zookeeper, imooc]
```

我们可以看到控制台输出了在上一节中我们增加的节点 imooc，说明我们的查询成功执行了。接下来我们测试其它的 API。

#### 2.3.2 创建持久节点

创建持久节点测试：

```java
@Test
void contextLoads() {
    ZkClient zkClient = zkClientServer.getZkClient();
    // 在 imooc 节点下创建持久节点 wiki
    zkClient.createPersistent("/imooc/wiki");
    // 获取 imooc 节点的子节点集合
    List<String> children = zkClient.getChildren("/imooc");
    System.out.println(children);
    // 释放资源
    zkClient.close();
}
```

执行测试方法，控制台输出：

```tex
[wiki]
```

#### 2.3.3 删除节点

删除节点测试：

```java
@Test
void contextLoads() {
    ZkClient zkClient = zkClientServer.getZkClient();
    // 删除 imooc 的 子节点 wiki
    boolean delete = zkClient.delete("/imooc/wiki");
    System.out.println(delete);
    // 释放资源
    zkClient.close();
}
```

执行测试方法，控制台输出：

```
true
```

true 表示删除 wiki 节点成功。

#### 2.3.4 读写数据

节点数据读写测试：

```java
@Test
void contextLoads() {
    ZkClient zkClient = zkClientServer.getZkClient();
    // 给 imooc 节点写入数据 wiki
    zkClient.writeData("/imooc","wiki");
    // 读取 imooc 节点的数据
    Object data = zkClient.readData("/imooc");
    System.out.println(data);
    // 释放资源
    zkClient.close();
}
```

执行测试方法，控制台输出：

```
wiki
```

> **Tips：** 当我们使用 API 操作节点时，节点参数必须是全路径。

测试完成后，我们来对 ZkClient 常用的 API 做一下介绍。



## 3. ZkClient API

- ZkClient 初始化 API

```java
// serverstring：服务器地址的字符串
// 如：192.168.0.77:2181,192.168.0.88:2181,192.168.0.99:2181
public ZkClient(String serverstring);
// zkServers：服务器地址的字符串，connectionTimeout：连接超时时间，单位：ms
public ZkClient(String zkServers, int connectionTimeout);
// sessionTimeout： session 超时时间
public ZkClient(String zkServers, int sessionTimeout, int connectionTimeout);
// ZkSerializer：序列化方式，实现类有：SerializableSerializer、BytesPushThroughSerializer
public ZkClient(String zkServers, int sessionTimeout, int connectionTimeout, ZkSerializer zkSerializer);
```

- 节点创建 API

```java
// path：节点全路径
public void createPersistent(String path);
// createParents：是否创建父节点
public void createPersistent(String path, boolean createParents);
// acl：权限列表
public void createPersistent(String path, boolean createParents, List<ACL> acl);
// data：节点数据
public void createPersistent(String path, Object data);
public void createPersistent(String path, Object data, List<ACL> acl);
// 创建持久顺序节点
public String createPersistentSequential(String path, Object data);
public String createPersistentSequential(String path, Object data, List<ACL> acl);
// 创建临时节点
public void createEphemeral(String path);
public void createEphemeral(String path, List<ACL> acl);
// mode：节点类型
public String create(String path, Object data, CreateMode mode);
public String create(final String path, Object data, final List<ACL> acl, final CreateMode mode);
public void createEphemeral(String path, Object data);
public void createEphemeral(String path, Object data, List<ACL> acl);
// 创建临时顺序节点
public String createEphemeralSequential(String path, Object data);
public String createEphemeralSequential(String path, Object data, List<ACL> acl);
```

- 查询节点 API

```java
// 获取子节点列表
public List<String> getChildren(String path);
// watch：是否开启观察
protected List<String> getChildren(final String path, final boolean watch);
// 获取子节点数量
public int countChildren(String path);
// 节点是否存在
protected boolean exists(final String path, final boolean watch);
public boolean exists(String path);
```

- 删除节点 API

```java
public boolean delete(String path);
// version：节点版本
public boolean delete(final String path, final int version);
```

- 读写节点数据 API

```java
public <T> T readData(String path);
public <T> T readData(String path, boolean returnNullIfPathNotExists);
public <T> T readData(String path, Stat stat);
protected <T> T readData(final String path, final Stat stat, final boolean watch);
public void writeData(String path, Object object);
public void writeData(String path, Object datat, int expectedVersion);
```

- 观察节点 API

```java
// 观察节点的数据变化
public void watchForData(final String path);
// 观察子节点的变化
public List<String> watchForChilds(final String path);
```



## 4. 总结


![图片描述](http://qiniu.cdn.easyspring.net/20210102233250.jpg)
本节我们学习了如何使用 ZkClient 的 API 对 Zookeeper 服务节点的操作，还介绍了一些常用的 API。以下是本节内容的总结：

1. 使用 Spring Boot 集成 ZkClient 。
2. ZkClient 的 API。





# Zookeeper Curator



## 1. 前言

在上一节中我们学习了 Zookeeper 的 Java 客户端之一 ZkClient ，除了 ZkClient 之外，还有就是 Zookeeper 最流行的 Java 客户端之一的 Curator。Curator 与 ZkClient 相比较又有什么区别呢？接下来我们就开始 Curator 的学习。



## 2. Curator 简介

我们来看一下 Curator 的官网介绍：

![Curator 的官网介绍](http://qiniu.cdn.easyspring.net/20210102233304.jpg)
Curator 是 Netflix 公司开源的一套 Zookeeper 客户端框架，后来捐献给 Apache 成为顶级的开源项目。
Curator 和 ZkClient 同样简化了 Zookeeper 原生 API 的开发工作，而 Curator 提供了一套易用性和可读性更强的 Fluent 风格的客户端 API ，还提供了 Zookeeper 各种应用场景的抽象封装，比如：分布式锁服务、集群领导选举、共享计数器、缓存机制、分布式队列等。
Curator 相较其它 Zookeeper 客户端功能更强大，应用更广泛，使用更便捷，所以它能成为当下最流行的 Zookeeper 的 Java 客户端之一。
接下来我们就开始学习如何使用 Curator 客户端对 Zookeeper 服务进行操作。

> **Tips：** Fluent 风格类似于链式编程，使用 Fluent 风格编写的类，调用该类的方法会返回该类本身，然后可以继续调用该类方法。



## 3. Curator 使用

我们新建一个 Spring Boot 项目来对 Curator 进行集成。首先我们要在 pom.xml 文件中加入 Curator 的 Maven 依赖。



### 3.1 Curator 依赖

pom.xml 文件配置如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.3.2.RELEASE</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>cn.cdd</groupId>
    <artifactId>curator-demo</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>curator-demo</name>
    <description>curator-demo project for Spring Boot</description>

    <properties>
        <java.version>11</java.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter</artifactId>
        </dependency>

        <!-- https://mvnrepository.com/artifact/org.apache.curator/curator-framework -->
        <dependency>
            <groupId>org.apache.curator</groupId>
            <artifactId>curator-framework</artifactId>
            <version>5.1.0</version>
        </dependency>
        <dependency>
            <groupId>org.apache.curator</groupId>
            <artifactId>curator-recipes</artifactId>
            <version>5.1.0</version>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
            <exclusions>
                <exclusion>
                    <groupId>org.junit.vintage</groupId>
                    <artifactId>junit-vintage-engine</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

</project>
```

引入 Curator 的依赖后，我们先来介绍一下 Curator 的 API ，然后再编写测试用例进行 API 测试。



### 3.2 Curator API

本小节我们来对 Curator 的 API 进行介绍，主要有 Curator 客户端实例的创建，session 的重连策略，节点的添加，获取节点数据，修改节点的数据，删除节点等。

#### 3.2.1 创建客户端

我们这里讲解 3 种创建客户端的方法，Curator 客户端的实现类为 CuratorFrameworkImpl，我们可以用它的接口 CuratorFramework 来接收创建客户端的返回值 。

- 第 1 种：

   

  使用创建 Curator 客户端的 API newClient 方法，其中第一个参数 connectString 为 Zookeeper 服务端的地址字符串，第二个参数 RetryPolicy 为会话重连策略，关于重连策略我们稍后再进行详细的讲解。

  ```java
  public static CuratorFramework newClient(String connectString, RetryPolicy retryPolicy) {
      return newClient(connectString, DEFAULT_SESSION_TIMEOUT_MS, DEFAULT_CONNECTION_TIMEOUT_MS, retryPolicy);
  }
  ```

- 第 2 种：

   

  在上面的 newClient 方法中，其实还是调用的下面的 newClient 方法，增加了参数 sessionTimeoutMs 会话超时时间，connectionTimeoutMs 连接超时时间。

  ```java
  public static CuratorFramework newClient(String connectString, int sessionTimeoutMs, int connectionTimeoutMs, RetryPolicy retryPolicy) {
      return builder().connectString(connectString).sessionTimeoutMs(sessionTimeoutMs).connectionTimeoutMs(connectionTimeoutMs).retryPolicy(retryPolicy).build();
  }
  ```

- 第 3 种：

   

  我们可以直接调用工厂类 CuratorFrameworkFactory 的 builder 方法，并且使用 Fluent 风格的写法来完成客户端的实例化。写法如下：

  ```java
  /**
  * 获取 CuratorClient
  * 使用 Fluent 风格
  * @return CuratorFramework
  */
  public CuratorFramework getCuratorClient(){
      // 使用 CuratorFrameworkFactory 来构建 CuratorFramework
      CuratorFramework client = CuratorFrameworkFactory.builder()
          // Zookeeper 服务器地址字符串
          .connectString(connectString)
          // session 会话超时时间
          .sessionTimeoutMs(sessionTimeoutMs)
          // 使用哪种重连策略
          .retryPolicy(retryOneTime)
          // 命名空间，表示当前客户端的父节点，我们可以用它来做业务区分
          .namespace(namespace)
          .build();
      return client;
  }
  ```

Curator 客户端创建完毕后，我们使用 start 方法就可以创建会话，使用 close 方法结束会话。

```java
client.start();
client.close();
```

#### 3.2.2 会话重连策略

Curator 提供了会话重连策略的接口 RetryPolicy，并且提供了几种默认的实现，下面我们介绍几种常用的策略。

1. RetryForever

   ```java
   // RetryForever：间隔{参数1}毫秒后重连，永远重试
   private RetryPolicy retryForever = new RetryForever(3000);
   ```

2. RetryOneTime

   ```java
   // RetryOneTime：{参数1}毫秒后重连，只重连一次
   private RetryPolicy retryOneTime = new RetryOneTime(3000);
   ```

3. RetryNTimes

   ```java
   // RetryNTimes： {参数2}毫秒后重连，重连{参数1}次
   private RetryPolicy retryNTimes = new RetryNTimes(3,3000);
   ```

4. RetryUntilElapsed

   ```java
   // RetryUntilElapsed：每{参数2}毫秒重连一次，总等待时间超过{参数1}毫秒后停止重连
   private RetryPolicy retryUntilElapsed = new RetryUntilElapsed(10000,3000);
   ```

5. ExponentialBackoffRetry

   ```java
   // ExponentialBackoffRetry：可重连{参数2}次，并增加每次重连之间的睡眠时间，递增加公式如下：
   // {参数1} * Math.max(1,random.nextInt(1 << ({参数2} + 1)))
   private RetryPolicy exponential = new ExponentialBackoffRetry(1000,3);
   ```

Curator 的会话重连策略方案介绍完毕，我们选择其中一种实现即可。

#### 3.2.3 创建节点

创建好客户端实例，开启会话之后，我们就可以开始创建节点了，我们使用 create 方法来创建节点，Fluent 风格的方式可以让我们自由组合创建方式。

```java
// 节点路径前必须加上/
String path = "/imooc";
// forPath 指定路径创建节点，内容默认为客户端ip。默认为持久节点。
client.create().forPath(path);
// 创建 imooc 节点，内容为 Wiki,内容参数需要字节数组。
client.create().forPath(path,"Wiki".getBytes());
// 创建节点时，同时创建它的父节点。withMode 声明节点是什么类型的，可以使用枚举类型CreateMode来确定。
client.create().creatingParentsIfNeeded().withMode(CreateMode.EPHEMERAL).forPa
th(path);
```

#### 3.2.4 获取节点数据

获取节点数据我们使用 getData 方法，同时我们还可以使用 Stat 来获取节点的最新状态信息。

```java
// 普通查询
client.getData().forPath(path);
// 包含状态的查询
Stat stat = new Stat();
client.getData().storingStatIn(stat).forPath(path);
```

#### 3.2.5 更新节点数据

更新节点数据我们使用 setData 方法，我们可以指定 version 来更新对应版本的数据。如果 version 已过期，则抛出 BadVersionException 异常，表示更新节点数据失败。

```java
// 普通更新
client.setData().forPath(path,"wiki".getBytes());
// 指定版本更新
client.setData().withVersion(1).forPath(path);
```

#### 3.2.4 删除节点

删除节点我们使用 delete 的方法，我们可以对节点进行递归删除，我们也可以指定 version 进行删除，我们还可以强制删除一个节点，只要当前客户端的会话有效，客户端在后台就会持续进行删除操作，直到删除成功。

```java
// 普通删除
client.delete().forPath(path);
// 递归删除子节点
client.delete().deletingChildrenIfNeeded().forPath(path);
// 指定版本删除
client.delete().withVersion(1).forPath(path);
// 强制删除
client.delete().guaranteed().forPath(path);
```

这里的 version 过期也会抛出 BadVersionException 异常，表示删除失败。
Curator 的 API 介绍完毕，我们接下来进行 API 测试。



### 3.3 API 测试

我们在 Spring Boot 主函数的同级新建 service 目录，在 service 目录中新建 CuratorService 类来获取客户端实例：

```java
package cn.cdd.curatordemo.service;

import org.apache.curator.RetryPolicy;
import org.apache.curator.framework.CuratorFramework;
import org.apache.curator.framework.CuratorFrameworkFactory;
import org.apache.curator.retry.ExponentialBackoffRetry;
import org.apache.curator.retry.RetryNTimes;
import org.apache.curator.retry.RetryOneTime;
import org.apache.curator.retry.RetryUntilElapsed;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.stereotype.Component;

@Component
public class CuratorService {
    // Zookeeper 服务器地址
    @Value("${curator.connectString}")
    private String connectString;
    // session 会话超时时间
    @Value("${curator.sessionTimeoutMs}")
    private int sessionTimeoutMs;
    // 名称空间：在操作节点时，会以 namespace 为父节点
    @Value("${curator.namespace}")
    private String namespace;

    /**
     * session 重连策略，使用其中一种即可
     */
    // RetryForever：间隔{参数1}毫秒后重连，永远重试
    private RetryPolicy retryForever = new RetryForever(3000);
    
    // RetryOneTime：{参数1}毫秒后重连，只重连一次
    private RetryPolicy retryOneTime = new RetryOneTime(3000);
    
    // RetryNTimes： {参数2}毫秒后重连，重连{参数1}次
    private RetryPolicy retryNTimes = new RetryNTimes(3,3000);
    
    // RetryUntilElapsed：每{参数2}毫秒重连一次，总等待时间超过{参数1}毫秒后停止重连
    private RetryPolicy retryUntilElapsed = new RetryUntilElapsed(10000,3000);
    
    // ExponentialBackoffRetry：可重连{参数2}次，并增加每次重连之间的睡眠时间，增加公式如下：
    // {参数1} * Math.max(1,random.nextInt(1 << ({参数2：maxRetries} + 1)))
    private RetryPolicy exponential = new ExponentialBackoffRetry(1000,3);


    /**
     * 获取 CuratorClient
     * 使用 Fluent 风格
     * @return CuratorFramework
     */
    public CuratorFramework getCuratorClient(){
         // 使用 CuratorFrameworkFactory 来构建 CuratorFramework
         return CuratorFrameworkFactory.builder()
                 // Zookeeper 服务器地址字符串
                 .connectString(connectString)
                 // session 会话超时时间
                 .sessionTimeoutMs(sessionTimeoutMs)
                 // 使用哪种重连策略
                 .retryPolicy(retryOneTime)
                 // 配置父节点
                 .namespace(namespace)
                 .build();
    }
}
```

在 application.properties 配置文件中添加配置：

```properties
# Zookeeper 地址
curator.connectString=192.168.0.77:2181,192.168.0.88:2181,192.168.0.88:2181
# 会话超时时间
curator.sessionTimeoutMs=5000
# 命名空间，当前客户端的父节点
curator.namespace=imooc
```

配置完成后，在 CuratorDemoApplicationTests 测试类中编写测试用例。
首先我们来测试节点的创建：

```java
package cn.cdd.curatordemo;

import cn.cdd.curatordemo.service.CuratorService;
import org.apache.curator.framework.CuratorFramework;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;

@SpringBootTest
class CuratorDemoApplicationTests {
    // 注入 CuratorService 依赖
    @Autowired
    private CuratorService curatorService;

    @Test
    void contextLoads() throws Exception {
        // 获取客户端
        CuratorFramework curatorClient = curatorService.getCuratorClient();
        // 开启会话
        curatorClient.start();
        // 在 namespace 下创建节点 Mooc , 节点前需要加 “/” 表示命名空间下的子节点
        // 节点内容为 Wiki ,使用字节数组传入
        String mooc = curatorClient.create().forPath("/Mooc", "Wiki".getBytes());
        // 返回 /Mooc
        System.out.println(mooc);
        curatorClient.close();
    }
}
```

控制台输出当前创建的节点：

```
/Mooc 
```

创建完成后我们来查询命名空间下的子节点：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework curatorClient = curatorService.getCuratorClient();
    // 开启会话
    curatorClient.start();
    // 查询命名空间下的子节点
    List<String> strings = curatorClient.getChildren().forPath("/");
    System.out.println(strings);
    curatorClient.close();
}
```

控制台输出命名空间的子节点列表：

```
[Mooc]
```

> **Tips：** 在我们创建客户端使用了命名空间时，API 中可用 `/` 表示命名空间，也表示当前客户端的根节点。

获取节点数据测试：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework curatorClient = curatorService.getCuratorClient();
    // 开启会话
    curatorClient.start();
    // 获取 Mooc 节点的内容
    byte[] bytes = curatorClient.getData().forPath("/Mooc");
    // 输出
    System.out.println(new String(bytes));
    curatorClient.close();
}
```

控制台输出当前节点的内容：

```
Wiki
```

更新节点数据测试：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework curatorClient = curatorService.getCuratorClient();
    // 开启会话
    curatorClient.start();
	// 更新节点数据，返回当前节点状态
    Stat stat = curatorClient.setData().forPath("/Mooc", "wiki".getBytes());
    // 输出
    System.out.println(stat);
    curatorClient.close();
}
```

控制台输出表示当前节点状态的数字：

```
4294967345,4294967352,1597805299226,1597850397723,1,0,0,0,4,0,4294967345
```

上面这串数字表示当前节点的状态 Stat，我们可以查看 Stat 类来找到对应的信息：

```java
public class Stat implements Record {
    // 创建节点时的事务 id
    private long czxid;
    // 修改节点时的事务 id
    private long mzxid;
    // 节点创建时的毫秒值
    private long ctime;
    // 节点修改时的毫秒值
    private long mtime;
    // 节点数据修改的次数
    private int version;
    // 子节点修改的次数
    private int cversion;
    // ACL修改的次数
    private int aversion;
    // 如果是临时节点，该值为节点的 SessionId，其它类型的节点则为 0
    private long ephemeralOwner;
    // 数据长度
    private int dataLength;
    // 子节点数量
    private int numChildren;
    // 添加和删除子节点的事务 id
    private long pzxid;
}
```

删除节点数据测试：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework curatorClient = curatorService.getCuratorClient();
    // 开启会话
    curatorClient.start();
	// 删除节点
    curatorClient.delete().forPath("/Mooc");
    curatorClient.close();
}
```

执行完成后，我们再次查询命名空间下的子节点：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework curatorClient = curatorService.getCuratorClient();
    // 开启会话
    curatorClient.start();
    // 查询命名空间下的子节点
    List<String> strings = curatorClient.getChildren().forPath("/");
    System.out.println(strings);
    curatorClient.close();
}
```

控制台输出为空，表示删除成功

```
[]
```

> **Tips：** 使用 API 时，我们需要注意是否配置 namespace ，如果没有配置 namespace 的话，我们使用 API 进行操作时，path 参数需要填写全路径。如果配置了 namespace ，我们使用 API 时，Curator 会自动帮我们在 path 前加上 namespace 。



## 4. 总结

本节我们学习了 Curator 是什么，Curator 可以是实现什么功能，我们还介绍了 Curator 常用的 API，并做了相应的测试。以下是本节内容的总结：

1. 为什么要学习使用 Curator 客户端。
2. Curator 常用的 API。
3. 使用 Spring Boot 集成 Curator。





# Zookeeper 的通信及会话



## 1. 前言

在前面的章节中，我们学习了 Zookeeper 的 Java 客户端 ZkClient 和 Curator 的基本使用，那这些客户端是如何与 Zookeeper 服务端建立通信的呢？我们就带着这个问题开启本节的内容。



## 2. Zookeeper 的通信协议

首先我们从 Zookeeper 的通信协议开始说起。我们都知道最常用的网络通信协议 TCP/IP 协议，而 Zookeeper 就是基于 TCP/IP 协议实现了自己的通信方式。

![Zookeeper 的通信协议](http://qiniu.cdn.easyspring.net/20210102233802.jpg)
Zookeeper 的通信协议分为两部分，请求协议和响应协议，接下来我们分别进行介绍。



### 2.1 请求协议

请求协议是 Zookeeper Client 向 Zookeeper Server 发送请求时所使用的协议，包含了请求头和请求体。在 Zookeeper 中使用了 RequestHeader 类作为请求头。

```java
// RequestHeader 类实现了 Record 接口来进行序列化操作
public class RequestHeader implements Record{
    // 客户端序号，记录客户端请求发起的顺序
    private int xid;
    // 请求类型
    private int type;
}
```

而请求体会根据不同的请求类型来进行封装，接下来我们以会话创建、节点查询、节点更新三种类型的请求分别介绍相对应的请求体。

- **会话创建请求**
  当 Zookeeper 客户端向 Zookeeper 服务端发送会话创建的请求时，使用 ConnectRequest 类来封装请求体：

```java
// ConnectRequest 类实现了 Record 接口来进行序列化操作
public class ConnectRequest implements Record {
	// 请求协议的版本信息
    private int protocolVersion;
    // 最后一次接收到响应的服务端 zxid
    private long lastZxidSeen;
    // 会话超时时间
    private int timeOut;
    // 会话 id
    private long sessionId;
    // 密码
    private byte[] passwd;
}
```

- 节点查询请求

  当 Zookeeper 客户端向 Zookeeper 服务端发送节点查询的请求时，使用 GetDataRequest 类来封装请求体：

  ```java
  // GetDataRequest 类实现了 Record 接口来进行序列化操作
  public class GetDataRequest implements Record {
      // 节点全路径
      private String path;
      // 是否对该节点开启监听
      private boolean watch;
  }
  ```

- 节点更新请求

  当 Zookeeper 客户端向 Zookeeper 服务端发送节点更新的请求时，使用 SetDataRequest 类来封装请求体：

  ```java
  // SetDataRequest 类实现了 Record 接口来进行序列化操作
  public class SetDataRequest implements Record {
  	// 节点全路径
      private String path;
      // 节点更新的数据
      private byte[] data;
      // 节点更新后的版本，也就是在当前版本上加 1
      private int version;
  }
  ```

介绍了 Zookeeper 的请求协议之后，接下来我们继续学习 Zookeeper 的响应协议。



### 2.2 响应协议

响应协议会在接收到 Zookeeper 客户端的请求后，对请求协议进行解析并作出响应。和 Zookeeper 的请求协议相对应的，Zookeeper 的响应协议也是由响应头和响应体组成，响应体也需要根据不同的请求类型来封装响应体。在接收到 Zookeeper 客户端的请求后，由 ReplyHeader 类来解析请求头并对响应头进行封装：

```java
// ReplyHeader 类实现了 Record 接口来进行序列化操作
public class ReplyHeader implements Record {
    // 客户端序号，记录客户端请求发起的顺序
    private int xid;
    // 事务id
    private long zxid;
    // 错误状态码
    private int err;
}
```

- 会话创建响应

  当 Zookeeper 服务端接收到 Zookeeper 客户端的会话创建请求时，使用 ConnectResponse 类来封装响应体：

  ```java
  // ConnectResponse 类实现了 Record 接口来进行序列化操作
  public class ConnectResponse implements Record {
      // 请求协议的版本信息
      private int protocolVersion;
      // 会话超时时间
      private int timeOut;
      // 会话 id
      private long sessionId;
      // 密码
      private byte[] passwd;
  }
  ```

- 节点查询响应

  当 Zookeeper 服务端接收到 Zookeeper 客户端的节点查询请求时，使用 GetDataResponse 类来封装响应体：

  ```java
  // GetDataResponse 类实现了 Record 接口来进行序列化操作
  public class GetDataResponse implements Record {
      // 节点的数据
      private byte[] data;
      // 节点的状态
      private org.apache.zookeeper.data.Stat stat;
  }
  ```

- 节点更新响应

  当 Zookeeper 服务端接收到 Zookeeper 客户端的节点更新请求时，使用 SetDataResponse 类来封装响应体：

  ```java
  // SetDataResponse 类实现了 Record 接口来进行序列化操作
  public class SetDataResponse implements Record {
      // 节点的状态
      private org.apache.zookeeper.data.Stat stat;
  }
  ```

介绍完 Zookeeper 的通信协议后，接下来我们要学习的是 Zookeeper 的会话，包括会话的结构，会话的状态等。



## 3. Zookeeper 的会话

Zookeeper 是一个 C/S 架构的服务，也就是 Client — Server 的形式。在我们使用 Zookeeper 时，都是使用 Zookeeper 的客户端向服务端发送请求，然后由服务端做出响应返回到客户端。在这个过程中，Zookeeper 的客户端需要与 Zookeeper 服务端建立连接，建立一个连接就是新建一个会话，那么会话的状态也就是 Zookeeper 客户端与 Zookeeper 服务端的连接状态。
接下来我们从会话的结构开始进行讲解：



### 3.1 Session 的结构

会话 Session 的结构包括会话ID、会话超时时间、会话关闭状态 3 个属性：

![Session 的结构](http://qiniu.cdn.easyspring.net/20210102233811.jpg)

- **SessionID：** 会话的唯一标识，由 Zookeeper 自动分配。
- **TimeOut：** 会话从新建到被关闭的时长，这个时间由 Zookeeper 服务端来管理。
- **isClosing：** 会话关闭的状态，如果会话已经被关闭，该会话就不会再被使用了。



### 3.2 Session 的状态

在 Zookeeper 的运行过程中，会话 Session 会经历各种状态的变化，从 Zookeeper 客户端与 Zookeeper 服务端开始建立连接到连接被关闭，会话的状态会经历以下几种：

- **CONNECTING**：正在连接状态，Zookeeper 客户端与 Zookeeper 服务端建立连接时的状态；
- **CONNECTIED**：已连接状态，Zookeeper 客户端与 Zookeeper 服务端完成连接的状态；
- **RECONNECTING**：正在重新连接状态，当 Zookeeper 客户端与 Zookeeper 服务端断开连接，Session 重连策略发起重新连接时的状态；
- **RECONNECTED**：已经重新连接状态，在 RECONNECTING 的基础上，完成了 Zookeeper 客户端与 Zookeeper 服务端的重新连接；
- **CLOSE**：连接关闭状态，Zookeeper 客户端与 Zookeeper 服务端断开连接的状态。



## 4. 总结

在本节内容中，我们学习了 Zookeeper 的通信协议的实现方式，以及 Zookeeper 会话 Session 的结构和运行中的状态变化。以下是本节内容的总结：

1. Zookeeper 的通信协议。
2. Zookeeper 的会话。



# Zookeeper Watch



## 1. 前言

在我们使用 Zookeeper 来实现服务注册与发现、配置中心、分布式通知等功能时，需要使用 Zookeeper 的核心功能 Watch，来对节点进行监听。那么 Zookeeper 的 Watch 是如何实现对节点的监听，并响应事件到客户端的呢？我们就带着这个问题开始本节的内容。



## 2. Watch 的实现

我们在 Zookeeper 的数据模型这一小节中学习过 Znode 节点的类型和 Znode 节点的特点，这是 Zookeeper 核心特性之一。在大多数情况下，我们都会把 Znode 与 Watch 捆绑使用，接下来我们就使用 Zookeeper 的 Java 客户端 Curator 来实现 Watch 对 Znode 节点的监听。
我们可以继续使用我们在 Zookeeper Curator 这一节中创建的 Spring Boot 测试项目，在测试方法中对 Watch 进行实现。



### 2.1 CuratorWatcher

在我们使用 Curator 的 Fluent 风格进行链式调用时，我们可以使用 usingWatcher 来注册 CuratorWatcher 来对我们的节点变化事件进行监听：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework curatorClient = curatorService.getCuratorClient();
    // 开启会话
    curatorClient.start();
    // CuratorWatcher 为接口，我们需要实现 process 方法
    CuratorWatcher watcher = new CuratorWatcher(){
        @Override
        // 监听事件处理
        public void process(WatchedEvent watchedEvent) {
            // 输出 监听事件
            System.out.println(watchedEvent.toString());
        }
    };
    // 在命名空间下创建持久节点 mooc，内容为 Wiki
    curatorClient.create().forPath("/mooc","Wiki".getBytes());
    // 获取 mooc 节点的 data 数据，并对 mooc 节点开启监听
    byte[] bytes = curatorClient.getData().usingWatcher(watcher).forPath("/mooc");
    // 输出 data
    System.out.println(new String(bytes));
    // 第一次更新
    curatorClient.setData().forPath("/mooc", "Wiki001".getBytes());
    // 第二次更新
    curatorClient.setData().forPath("/mooc","Wiki002".getBytes());
}
```

控制台输出：

```tex
Wiki
WatchedEvent state:SyncConnected type:NodeDataChanged path:/mooc
```

控制台输出的第一行 Wiki 为 mooc 节点的 data 数据。第二行输出的 WatchedEvent 为监听到的事件，state 表示监听状态；type 表示监听到的事件类型，我们可以判断事件的类型来做相应的处理；path 表示监听的节点。
介绍完 WatchedEvent，我们发现控制台只输出了一次 WatchedEvent，也就是说 CuratorWatcher 只进行了一次监听。如果想要重复使用我们需要重新使用 usingWatcher 进行注册。那么有没有不需要重复注册的监听呢？接下来我们就来介绍 Curator 一种功能强大的监听 CuratorCacheListener。



### 2.2 CuratorCacheListener

CuratorCacheListener 是基于 CuratorCache 缓存实现的监听器，CuratorCache 对 ZooKeeper 事件监听进行了封装，能够自动处理反复注册监听。我们使用 CuratorCacheListener 时，需要使用构建器 CuratorCacheListenerBuilder 来对具体的事件监听进行构建，并且把 CuratorCacheListener 注册到 CuratorCache 缓存中。
首先我们需要构建 CuratorCache 缓存实例，在 CuratorCache 接口中，build 为静态方法，我们可以直接调用：

```java
// 构建 CuratorCache 缓存实例
static CuratorCache build(CuratorFramework client, String path, CuratorCache.Options... options) {
    return builder(client, path).withOptions(options).build();
}
```

我们来说明以下入参：`CuratorFramework client` 是 Curator 客户端；`String path` 是需要被监听的节点的路径；`CuratorCache.Options... options` 是对缓存设置的参数，我们可以设置以下 3 种：

```java
public static enum Options {
    // 单节点缓存
    SINGLE_NODE_CACHE,
    // 对数据进行压缩
    COMPRESSED_DATA,
    // CuratorCache 关闭后不清除缓存
    DO_NOT_CLEAR_ON_CLOSE;
}
```

构建完缓存实例，我们再来构建 CuratorCacheListener ，在 CuratorCacheListener 接口中的构建方法 builder 为静态方法，我们可以直接调用：

```java
// builder 方法，返回 CuratorCacheListenerBuilder 构建器，我们就可以使用具体的监听方法了
static CuratorCacheListenerBuilder builder() {
    return new CuratorCacheListenerBuilderImpl();
}
```

最后我们需要把 CuratorCacheListener 注册到 CuratorCache 中，并开启缓存：

```java
// 注册 CuratorCacheListener 
cache.listenable().addListener(listener);
// 开启缓存
cache.start();
```

我们来看一个完整的例子：

```java
@Test
void contextLoads() throws Exception {
    // 获取客户端
    CuratorFramework client = curatorService.getCuratorClient();
    // 开启会话
    client.start();
    // 构建 CuratorCache 实例
    CuratorCache cache = CuratorCache.build(client, "/mooc");
	// 使用 Fluent 风格和 lambda 表达式来构建 CuratorCacheListener 的事件监听
    CuratorCacheListener listener = CuratorCacheListener.builder()
        // 开启对所有事件的监听
        // type 事件类型：NODE_CREATED, NODE_CHANGED, NODE_DELETED;
        // oldNode 原节点：ChildData 类，包括节点路径，节点状态 Stat，节点 data
        // newNode 新节点：同上
       .forAll((type, oldNode, newNode) -> {
           System.out.println("forAll 事件类型：" + type);
           System.out.println("forAll 原节点：" + oldNode);
           System.out.println("forAll 新节点：" + newNode);
       })
        // 开启对节点创建事件的监听
        .forCreates(childData -> {
            System.out.println("forCreates 新节点：" + childData);
        })
        // 开启对节点更新事件的监听
        .forChanges((oldNode, newNode) -> {
            System.out.println("forChanges 原节点：" + oldNode);
            System.out.println("forChanges 新节点：" + newNode);
        })
        // 开启对节点删除事件的监听
        .forDeletes(oldNode -> {
            System.out.println("forDeletes 原节点：" + oldNode);
        })
        // 初始化
        .forInitialized(() -> {
            System.out.println("forInitialized 初始化");
        })
        // 构建
        .build();

    // 注册 CuratorCacheListener 到 CuratorCache
    cache.listenable().addListener(listener);
    // CuratorCache 开启缓存
    cache.start();
    // mooc 节点创建
    client.create().forPath("/mooc");
    // mooc 节点更新
    client.setData().forPath("/mooc","Wiki".getBytes());
    // mooc 节点删除
    client.delete().forPath("/mooc");
}
```

我们来查看 CuratorCacheListenerBuilder 接口中具体的事件监听，我们需要监听哪种事件就使用哪种方法：

```java
public interface CuratorCacheListenerBuilder {
    // 全部事件
    CuratorCacheListenerBuilder forAll(CuratorCacheListener var1);
	// 创建事件
    CuratorCacheListenerBuilder forCreates(Consumer<ChildData> var1);
	// 更新事件
    CuratorCacheListenerBuilder forChanges(CuratorCacheListenerBuilder.ChangeListener var1);
	// 创建和更新事件
    CuratorCacheListenerBuilder forCreatesAndChanges(CuratorCacheListenerBuilder.ChangeListener var1);
	// 删除事件
    CuratorCacheListenerBuilder forDeletes(Consumer<ChildData> var1);
	// 初始化后开启线程异步执行
    CuratorCacheListenerBuilder forInitialized(Runnable var1);
	// 子节点的事件
    CuratorCacheListenerBuilder forPathChildrenCache(String var1, CuratorFramework var2, PathChildrenCacheListener var3);
	// 节点本身的事件和子节点的事件
    CuratorCacheListenerBuilder forTreeCache(CuratorFramework var1, TreeCacheListener var2);
	// 节点本身的事件
    CuratorCacheListenerBuilder forNodeCache(NodeCacheListener var1);
 	// 初始化后开启监听
    CuratorCacheListenerBuilder afterInitialized();
	// 构建方法
    CuratorCacheListener build();
	/*
	* 更新事件时被调用
	*/
    @FunctionalInterface
    public interface ChangeListener {
        void event(ChildData var1, ChildData var2);
    }
}
```

接下来我们执行测试方法，查看控制台输出：

```
forInitialized 初始化
forAll 事件类型：NODE_CREATED
forAll 原节点：null
forAll 新节点：ChildData{path='/mooc', stat=2760,2760,1598451457977,1598451457977,0,0,0,0,13,0,2760
, data=[49, 57, 50, 46, 49, 54, 56, 46, 48, 46, 49, 48, 53]}
forCreates 新节点：ChildData{path='/mooc', stat=2760,2760,1598451457977,1598451457977,0,0,0,0,13,0,2760
, data=[49, 57, 50, 46, 49, 54, 56, 46, 48, 46, 49, 48, 53]}
forAll 事件类型：NODE_CHANGED
forAll 原节点：ChildData{path='/mooc', stat=2760,2760,1598451457977,1598451457977,0,0,0,0,13,0,2760
, data=[49, 57, 50, 46, 49, 54, 56, 46, 48, 46, 49, 48, 53]}
forAll 新节点：ChildData{path='/mooc', stat=2760,2761,1598451457977,1598451457984,1,0,0,0,4,0,2760
, data=[87, 105, 107, 105]}
forChanges 原节点：ChildData{path='/mooc', stat=2760,2760,1598451457977,1598451457977,0,0,0,0,13,0,2760
, data=[49, 57, 50, 46, 49, 54, 56, 46, 48, 46, 49, 48, 53]}
forChanges 新节点：ChildData{path='/mooc', stat=2760,2761,1598451457977,1598451457984,1,0,0,0,4,0,2760
, data=[87, 105, 107, 105]}
forAll 事件类型：NODE_DELETED
forAll 原节点：ChildData{path='/mooc', stat=2760,2761,1598451457977,1598451457984,1,0,0,0,4,0,2760
, data=[87, 105, 107, 105]}
forAll 新节点：null
forDeletes 原节点：ChildData{path='/mooc', stat=2760,2761,1598451457977,1598451457984,1,0,0,0,4,0,2760
, data=[87, 105, 107, 105]}
```

我们发现，我们设置的 create，setData，delete 这 3 种事件都被监听到了，而且 forAll 每一种事件都监听到了，所以我们在使用的时候，选择我们需要的事件监听即可。
介绍完 CuratorCacheListener 监听器，并完成了事件监听的测试，那么 Zookeeper 的 Watch 是如何运行的呢？接下来我们就来介绍 Watch 的运行原理。



## 3. Watch 的原理

在介绍 Watch 的原理之前，我们先熟悉一个概念：Zookeeper 客户端对 Znode 的写操作，也就是新增节点、更新节点、删除节点这些操作，默认会开启监听；Zookeeper 客户端对 Znode 的读操作，也就是查询节点数据、查询节点是否存在、查询子节点等操作，需要手动设置开启监听。这也是为什么在 GetDataRequest 请求体中会有 watch 这个属性的原因。
Watch 的运行过程分为 4 部分，分别是：客户端注册 Watch 、服务端注册 Watch、服务端触发 Watch、客户端处理回调。

![Watch 的运行过程](http://qiniu.cdn.easyspring.net/20210102234119.jpg)

- **客户端注册 Watch**
  当我们使用 Zookeeper 客户端向 Zookeeper 服务端发送带有事件监听的请求时，Zookeeper 客户端会把该请求标记成带有 Watch 的请求，然后把 Watch 监听器注册到 ListenerManager 中。
- **服务端注册 Watch**
  Zookeeper 服务端接收到 Zookeeper 客户端发送过来的请求，解析请求体，判断该请求是否带有 Watch 事件，如果有 Watch 事件，就会把 Watch 事件注册到 WatchManager 中。
- **服务端触发 Watch**
  Zookeeper 服务端注册完 Watch 事件后，会调用 WatchManager 的 triggerWatch 方法来触发 Watch 事件，Watch 事件完成后，向客户端发送响应。
- **客户端处理回调**
  Zookeeper 客户端接收到 Zookeeper 服务端的响应后，解析响应体，根据响应体的类型去 ListenerManager 中查找相对应的 Watch 监听器，然后触发监听器的回调函数。



## 4. 总结

在本节中，我们学习了使用 Curator 的两种方式开启对事件的监听，也了解了 Watch 运行过程的 4 个部分。以下是本节内容的总结：

1. Zookeeper Watch 的实现。
2. Zookeeper Watch 的原理。



# Zookeeper ACL



## 1. 前言

经过前面几节的学习，我们了解了基于 Zookeeper 的 Znode 和 Watch 可以实现很多业务场景，使用 Zookeeper 的 Java 客户端对 Znode 的操作也非常方便。如果我们对 Znode 操作失误，导致数据丢失，那么我们的应用也会受到影响，所以我们需要对 Znode 的操作加以控制。在 Zookeeper 中就是使用 Access Control Lists 访问控制列表的方式来避免这种情况的发生。本节我们就来介绍 Zookeeper ACL 的实现以及 ACL 的实现原理。



## 2. Zookeeper ACL 组成

ACL 全称 Access Control Lists，访问控制列表。一个 Znode 的 ACL 可以分为 3 部分：

![Zookeeper ACL 组成](http://qiniu.cdn.easyspring.net/20210102234124.jpg)
ACL 就是由以上 3 部分组成 **Scheme:ID:Permission** 这种形式的访问控制信息，接下来我们来接介绍这 3 部分分别代表什么意思：

- 授权模式 Scheme：

   

  授权模式 Scheme 就是选择 Zookeeper 分配权限的方式，我们可以选择的授权方式有 6 种：

  - **IP ：** 我们可以使用 IP 或 IP 段来对授权对象进行授权；
  - **HOST ：** 我们可以使用主机名的后缀来对授权对象进行授权，如果我们设置的 host 为 [imooc.com](http://imooc.com/)，就可以匹配 [coding.imooc.com](http://coding.imooc.com/)，[class.imooc.com](http://class.imooc.com/)；
  - **Auth ：** 给所有的认证用户授权，需要使用 `addauth digest username:password` 命令添加认证用户，Zookeeper 会把密码使用 SHA-1 和 BASE64 算法进行加密；
  - **Digest ：** 使用用户名和密码的方式验证，不需要使用 `addauth` 添加认证用户，需要手动使用SHA-1 和 BASE64 算法对密码进行加密；
  - **World ：** 默认权限 `world:anyone:cdrwa`，任何人都可以对节点做任意操作。
  - **Super ：** 超级权限，授权对象可以对节点做任意操作；

- 授权对象 ID：

   

  授权对象的意思就是我们要把 Scheme 设置的权限授权给谁。

  - 如果我们设置的 Scheme 是 Auth ，那么授权对象就是所有使用 `addauth digest username:password` 命令添加认证用户，那么我们在设置 ACL 时就不需要写入授权对象了，例如：`auth::crwda` ；
  - 如果我们设置的 Scheme 是 Digest ，那么授权对象就是用户名和被加密后的密码，例如：`digest:mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=:crwda` ；

- 权限信息 Permission：

   

  权限信息是指对 Znode 操作的权限，一共有 5 种操作权限，分别是：

  

  - **Create 节点创建权限：** 授权对象可以在该节点下创建子节点；
  - **Read 节点数据读取权限：** 授权对象可以读取该节点的 data 以及其子节点的 stat 和 ACL；
  - **Write 节点数据写入权限：** 授权对象可以更新该节点的 data；
  - **Delete 节点删除权限：** 授权对象可以删除该节点的子节点；
  - **Admin 节点 ACL修改权限：** 授权对象可以修改节点的 ACL 权限信息。

我们在设置权限信息时使用简写的方式，也就是使用权限信息的小写首字母 `crwda` 来表示每一种操作，需要哪种权限信息就写上哪种简写即可。

介绍完 ACL 的组成，接下来我们来使用 Zookeeper 的客户端来实现 ACL 访问控制。



## 3. Zookeeper ACL 实现

在这里我们使用 [zkCli.sh](http://zkcli.sh/) 命令行客户端的方式来设置节点的 ACL 信息。



### 3.1 命令行客户端设置 ACL

我们使用 Zookeeper 的客户端 zkCli 命令行工具来设置节点的 ACL ，使用 [zkCli.sh](http://zkcli.sh/) 连接 Zookeeper 服务端后，然后查看节点的 ACL 信息：

```shell
# 创建 /imooc
[zk: localhost:2181(CONNECTED) 1] create /imooc
# 创建成功
Created /imooc
# 查询 /imooc 节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 2] getAcl /imooc
# 输出 ACL
'world,'anyone
: cdrwa
```

我们可以发现，imooc 节点的 ACL 信息为默认的 `world:anyone:cdrwa`.
接下来我们使用 Auth 的方式改变该节点的 ACL 设置：

```shell
# 添加认证用户 mooc，密码为 mooc
[zk: localhost:2181(CONNECTED) 3] addauth digest mooc:mooc
# 给 /imooc 节点设置 ACL，验证模式为 auth，授权对象为所有认证用户，所以可以不用填写参数，权限信息为所有操作
[zk: localhost:2181(CONNECTED) 4] setAcl /imooc auth::cdrwa
# 查看 /imooc 节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 5] getAcl /imooc
# 输出 ACL
'digest,'mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=
: cdrwa
```

我们可以看到 imooc 节点的 ACL 信息已经修改成功，密码也被加密了。接下来我们使用 Digest 的方式来设置节点的 ACL ：

```shell
# 给 /imooc 节点设置 ACL，验证模式为 digest
# 用户名为 mooc，密码是被加密后的 mooc，加密方式为 BASE64(SHA1(mooc))，权限信息为所有操作
[zk: localhost:2181(CONNECTED) 6] [zk: localhost:2181(CONNECTED) 6] setAcl /imooc digest:mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=:cdrwa
# 查看 /imooc 节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 7]  getAcl /imooc
# 输出 ACL
'digest,'mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=
: cdrwa
```

我们可以发现，使用 Auth 和 Digest 设置的 ACL 信息是相同的，都是基于 Digest 的授权模式，它们的区别是：

- Auth 需要在设置 ACL 之前添加认证用户，并且无需手动加密，它的授权范围是所有的使用 `addauth digest username:password` 命令添加的用户。
- Digest 不需要提前添加认证用户，但是需要自己完成密码的加密，而且授权范围只有当前设置的用户。

> **Tips：** 我们需要注意，当前客户端添加的认证用户只针对当前客户端有效，客户端断开连接后也需要重新进行认证。

如果此时客户端断开连接，再重新连接，或者新开一个客户端进行操作，访问节点可能会出现以下错误：

```shell
[zk: localhost:2181(CONNECTED) 1] get /imooc
# 错误 1
org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /imooc
[zk: localhost:2181(CONNECTED) 2] getAcl /imooc
# 错误 2
Authentication is not valid : /imooc
```

此时我们需要重新使用 `addauth digest username:password` 来对新的客户端添加认证用户，才可以访问有 ACL 权限的节点。

```shell
# 添加认证用户，用户名密码和设置 ACL 时的一致
[zk: localhost:2181(CONNECTED) 3] addauth digest mooc:mooc
[zk: localhost:2181(CONNECTED) 4] get /imooc
null
[zk: localhost:2181(CONNECTED) 5] getAcl /imooc
'digest,'mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=
: cdrwa
```

> **Tips：** 如果是密码设置错误导致对节点的访问无权限，我们可以在 zoo.cfg 配置文件中加入 skipACL=yes，跳过 ACL 验证，重启服务后再修改 ACL 信息或者删除错误节点。本设置不建议在生产环境下使用！

上面的设置方式都是针对当前节点的 ACL 的设置，一个一个的对每个节点去设置它们的 ACL 信息是一件非常繁琐的事情，所以我们可以使用 -R 参数来递归设置子节点的 ACL 信息：

```shell
# 创建子节点 /imooc/mooc
[zk: localhost:2181(CONNECTED) 8] create /imooc/mooc
# 创建子节点 /imooc/mooc 成功
Created /imooc/mooc
# 创建子节点 /imooc/mooc/wiki
[zk: localhost:2181(CONNECTED) 9] create /imooc/mooc/wiki
# 创建子节点 /imooc/mooc/wiki 成功
Created /imooc/mooc/wiki
# 使用 digest 设置 /imooc 节点的 ACL，使用 —R 来递归设置子节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 10] setAcl -R /imooc digest:mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=:cdrwa
# 查看 /imooc 节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 11] getAcl /imooc 
'digest,'mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=
: cdrwa
# 查看 /imooc/mooc 节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 12] getAcl /imooc/mooc
'digest,'mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=
: cdrwa
# 查看 /imooc/mooc/wiki 节点的 ACL 信息
[zk: localhost:2181(CONNECTED) 13] getAcl /imooc/mooc/wiki
'digest,'mooc:0xEep90zjLm6hbWMlQ2BGbaQWzI=
: cdrwa
```

我们发现 imooc 的 ACL 信息和它的子节点的 ACL 信息都是相同的，说明我们使用 `-R` 递归设置子节点的 ACL 信息成功了。
成功的实现了节点 ACL 的设置之后，接下来我们来讲解 Zookeeper ACL 实现的原理。



## 4. Zookeeper ACL 原理

由于 Zookeeper 是 C/S 架构，所以 Zookeeper ACL 的实现原理也分为两部分，Zookeeper 客户端和 Zookeeper 服务端。我们首先从 Zookeeper 客户端开始介绍。



### 4.1 Zookeeper 客户端处理 ACL 请求

在 Zookeeper 客户端中，当我们使用 `addauth digest mooc:mooc` 命令来添加认证用户信息时，Zookeeper 客户端会使用 ClientCnxn 客户端类的 addAuthInfo 方法来封装请求信息，把请求类型包装成权限类请求，封装完毕后发送给服务端。

```java
// 添加认证信息，参数一：授权类型，参数二：认证信息的字节数组
public void addAuthInfo(String scheme, byte[] auth) {
    // 判断当前客户端状态
    if (this.state.isAlive()) {
        // 封装认证信息 scheme:digest 
        this.authInfo.add(new ClientCnxn.AuthData(scheme, auth));
        // 封装请求头 -4为请求头的xid，100为请求类型：auth
        this.queuePacket(new RequestHeader(-4, 100), (ReplyHeader)null, new AuthPacket(0, scheme, auth), (Record)null, (AsyncCallback)null, (String)null, (String)null, (Object)null, (WatchRegistration)null);
    }
}
```

简单地介绍了 Zookeeper 客户端处理权限类请求的过程，接下来就是 Zookeeper 服务端的处理过程了。



### 4.2 Zookeeper 服务端处理 ACL 请求

在 Zookeeper 服务端接收到 Zookeeper 客户端发送过来的请求后，首先解析请求头，识别请求的类型，发现客户端的请求类型是 auth 时，也就是权限类请求时，Zookeeper 会使用 scheme 来判断授权类型，找具体处理授权的实现类，在实现类中来进行权限验证，然后把认证用户保存到认证信息的集合中。
在 Zookeeper 客户端使用刚才添加的认证用户信息来进行节点操作时，向 Zookeeper 服务端发送权限请求，服务端解析完成请求类型和授权类型后，再去具体的认证信息集合中去匹配请求中携带的授权信息，匹配成功则执行具体操作，匹配不到则说明该请求无授权，返回 NoAuthException 异常信息。



## 5. 总结

在本节内容中我们学习了 Zookeeper 的 ACL 访问控制列表的组成，并使用命令行客户端的方式进行了实现，最后简单的介绍了以下 Zookeeper 处理 ACL 请求的过程。以下是本节内容总结：

1. Zookeeper ACL 的组成
2. 使用命令行客户端实现 ACL
3. Zookeeper ACL 的原理





# Zookeeper Jute



## 1. 前言

在我们使用 Zookeeper 客户端和 Zookeeper 服务端建立连接，发送请求时，Zookeeper 客户端需要把请求协议进行序列化才能进行发送，Zookeeper 服务端接收到请求，还需要把请求协议进行反序列化才能解析请求，这样才完成了一次请求的发送。那么序列化是什么呢？我们为什么要使用序列化？Zookeeper 中又是如何使用序列化的呢？我们就带着这些问题开始本节的内容。



## 2. Zookeeper 序列化

在 Zookeeper 的通信与会话一节中，我们学习了 Zookeeper 使用的是基于 TCP 的通信协议，TCP 协议是一种面向连接的、可靠的、基于字节流的通信协议。
我们想要使用 Zookeeper 客户端向 Zookeeper 服务端发送请求，我们就需要把请求发送的 Java 对象转换为字节流的形式，这个转换的过程就是序列化。相对来说，把字节流转换为 Java 对象的过程就是反序列化。

![Zookeeper 序列化](http://qiniu.cdn.easyspring.net/20210102234140.jpg)
那么我们什么时候使用序列化呢？

1. 对象需要持久化时；
2. 对象进行网络传输时。

Zookeeper 的应用场景就需要大量的网络传输，所以需要使用序列化来提高 Zookeeper 客户端与服务端之间的通信效率。
在 Zookeeper 中，这一过程不需要我们自己去实现，无论是 Zookeeper 客户端还是 Zookeeper 服务端，都已经把序列化和反序列化的过程进行了封装。那么 Zookeeper 时如何实现序列化的呢？接下来我们就来介绍 Zookeeper 的序列化实现方式 Jute。



### 2.1 Jute 介绍

Jute 前身是 Hadoop Record IO 中的序列化组件，从 Zookeeper 第一个正式版，到目前最新的稳定版本 Apache ZooKeeper 3.6.1 都是用的 Jute 作为序列化组件。
为什么 Zookeeper 会一直选择 Jute 作为它的序列化组件呢？并不是 Jute 的性能比其他的序列化框架好，相反的，现在市面上有许多性能更好的序列化组件，比如 Apache Thrift，Apache Avro 等组件，性能都要优于 Jute。之所以还使用 Jute，是因为到目前为止，Jute 序列化还不是 Zookeeper 的性能瓶颈，没有必要强行更换，而且很难避免因为替换基础组件而带来的一系列版本兼容的问题。
简单的介绍了一下 Jute ，那么在 Zookeeper 中，Jute 又是如何实现的呢？接下来我们就来讲解 Jute 在 Zookeeper 中的实现。



### 2.2 Jute 实现

在 Zookeeper 的通信及会话一节中，我们学习了 Zookeeper 的请求协议和响应协议，并查看了部分源码。我们可以发现，无论是请求协议还是响应协议的具体类，都实现了接口 Record，Record 接口其实就是 Jute 定义的序列化接口。

```java
package org.apache.jute;

import java.io.IOException;
import org.apache.yetus.audience.InterfaceAudience.Public;

@Public
public interface Record {
    // 序列化
    void serialize(OutputArchive var1, String var2) throws IOException;
	// 反序列化
    void deserialize(InputArchive var1, String var2) throws IOException;
}
```

我们这里使用请求头 RequestHeader 作为例子来查看序列化和反序列化的实现：

```java
// 请求头，实现了 Record 
public class RequestHeader implements Record  {
    private int xid;
    private int type;
    // 使用 OutputArchive 进行序列化，tag：序列化标识符
    public void serialize(OutputArchive a_, String tag) throws IOException {
        a_.startRecord(this, tag);
        a_.writeInt(this.xid, "xid");
        a_.writeInt(this.type, "type");
        a_.endRecord(this, tag);
    }
	// 使用 InputArchive 进行反序列化，tag 序列化标识符
    public void deserialize(InputArchive a_, String tag) throws IOException {
        a_.startRecord(tag);
        this.xid = a_.readInt("xid");
        this.type = a_.readInt("type");
        a_.endRecord(tag);
    }
}
```

在 serialize 序列化方法中，根据成员变量的数据类型来选择 OutputArchive 的方法来进行序列化操作。在 deserialize 反序列化方法中，根据成员变量的数据类型来选择 InputArchive 的方法来进行反序列化操作。
在这里我们可以发现，Record 只是定义了序列化方法和反序列化方法，真正执行序列化操作是 OutputArchive 和 InputArchive 这两个接口的实现类。接下来我们讲解 OutputArchive 序列化接口的实现类 BinaryOutputArchive。



### 2.3 BinaryOutputArchive

BinaryOutputArchive 是二进制的序列化方式，这种方式将 Java 对象转化成二进制的格式来进行数据传输。在它的具体方法中，使用的是 java.io.DataOutputStream 的方法来完成 Java 对象到二进制的转换，我们来看看具体实现：

```java
/**
* 二进制的序列化
*/
public class BinaryOutputArchive implements OutputArchive {
    // 定义字节缓冲区大小
    private ByteBuffer bb = ByteBuffer.allocate(1024);
    // 数据输出接口 DataOutput 
    private DataOutput out;
	// 使用 OutputStream 初始化 BinaryOutputArchive
    public static BinaryOutputArchive getArchive(OutputStream strm) {
        return new BinaryOutputArchive(new DataOutputStream(strm));
    }
	// 构造方法传入 DataOutput
    public BinaryOutputArchive(DataOutput out) {
        this.out = out;
    }

    // 输出 byte 类型为二进制
    public void writeByte(byte b, String tag) throws IOException {
        this.out.writeByte(b);
    }
	// 输出 boolean 类型为二进制
    public void writeBool(boolean b, String tag) throws IOException {
        this.out.writeBoolean(b);
    }
	// 输出 int 类型为二进制
    public void writeInt(int i, String tag) throws IOException {
        this.out.writeInt(i);
    }
	// 输出 long 类型为二进制
    public void writeLong(long l, String tag) throws IOException {
        this.out.writeLong(l);
    }
	// 输出 float 类型为二进制
    public void writeFloat(float f, String tag) throws IOException {
        this.out.writeFloat(f);
    }
	// 输出 double 类型为二进制
    public void writeDouble(double d, String tag) throws IOException {
        this.out.writeDouble(d);
    }
	// 工具方法：字符串转字节缓冲区
    private ByteBuffer stringToByteBuffer(CharSequence s) {
        this.bb.clear();
        int len = s.length();

        for(int i = 0; i < len; ++i) {
            if (this.bb.remaining() < 3) {
                ByteBuffer n = ByteBuffer.allocate(this.bb.capacity() << 1);
                this.bb.flip();
                n.put(this.bb);
                this.bb = n;
            }

            char c = s.charAt(i);
            if (c < 128) {
                this.bb.put((byte)c);
            } else if (c < 2048) {
                this.bb.put((byte)(192 | c >> 6));
                this.bb.put((byte)(128 | c & 63));
            } else {
                this.bb.put((byte)(224 | c >> 12));
                this.bb.put((byte)(128 | c >> 6 & 63));
                this.bb.put((byte)(128 | c & 63));
            }
        }

        this.bb.flip();
        return this.bb;
    }
	// 输出 String 类型为二进制
    public void writeString(String s, String tag) throws IOException {
        if (s == null) {
            this.writeInt(-1, "len");
        } else {
            // String 不为空转字节缓冲区
            ByteBuffer bb = this.stringToByteBuffer(s);
            this.writeInt(bb.remaining(), "len");
            // 输出 字节数组
            this.out.write(bb.array(), bb.position(), bb.limit());
        }
    }
	// 输出 字节数组为二进制
    public void writeBuffer(byte[] barr, String tag) throws IOException {
        if (barr == null) {
            this.out.writeInt(-1);
        } else {
            this.out.writeInt(barr.length);
            this.out.write(barr);
        }
    }
}
```

介绍了序列化的具体实现类，接下来就是反序列化接口 InputArchive 的实现类 BinaryInputArchive。



### 2.4 BinaryInputArchive

BinaryInputArchive 是二进制的反序列化，也就是把二进制格式转换成 Java 对象。在它的具体方法中，使用了 java.io.DataOutputStream 的方法来完成二进制格式到 Java 对象的转换，我们来看具体实现：

```java
package org.apache.jute;

import java.io.DataInput;
import java.io.DataInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.nio.charset.StandardCharsets;
/**
 * 二进制的反序列化
 */
public class BinaryInputArchive implements InputArchive {
	// 长度异常的字符串
    public static final String UNREASONBLE_LENGTH = "Unreasonable length = ";

    // 最大缓冲区
    public static final int maxBuffer = Integer.getInteger("jute.maxbuffer", 0xfffff);
    // 额外的最大缓冲区
    private static final int extraMaxBuffer;

    static {
        final Integer configuredExtraMaxBuffer =
            Integer.getInteger("zookeeper.jute.maxbuffer.extrasize", maxBuffer);
        if (configuredExtraMaxBuffer < 1024) {
            extraMaxBuffer = 1024;
        } else {
            extraMaxBuffer = configuredExtraMaxBuffer;
        }
    }
	// 数据输入接口 DataInput
    private DataInput in;
    // 最大缓冲区的大小
    private int maxBufferSize;
    // 额外的最大缓冲区的大小
    private int extraMaxBufferSize;
	// 使用 InputStream 实例化 BinaryInputArchive
    public static BinaryInputArchive getArchive(InputStream strm) {
        return new BinaryInputArchive(new DataInputStream(strm));
    }
	
    private static class BinaryIndex implements Index {
        private int nelems;

        BinaryIndex(int nelems) {
            this.nelems = nelems;
        }

        public boolean done() {
            return (nelems <= 0);
        }

        public void incr() {
            nelems--;
        }
    }

    // 构造方法
    public BinaryInputArchive(DataInput in) {
        this(in, maxBuffer, extraMaxBuffer);
    }

    // 构造方法
    public BinaryInputArchive(DataInput in, int maxBufferSize, int extraMaxBufferSize) {
        this.in = in;
        this.maxBufferSize = maxBufferSize;
        this.extraMaxBufferSize = extraMaxBufferSize;
    }
	// 读取二进制到 Byte 类型
    public byte readByte(String tag) throws IOException {
        return in.readByte();
    }
	// 读取二进制到 Boolean 类型
    public boolean readBool(String tag) throws IOException {
        return in.readBoolean();
    }
	// 读取二进制到 int 类型
    public int readInt(String tag) throws IOException {
        return in.readInt();
    }
	// 读取二进制到 long 类型
    public long readLong(String tag) throws IOException {
        return in.readLong();
    }
	// 读取二进制到 float 类型
    public float readFloat(String tag) throws IOException {
        return in.readFloat();
    }
	// 读取二进制到 double 类型
    public double readDouble(String tag) throws IOException {
        return in.readDouble();
    }
	// 读取二进制到 String 类型
    public String readString(String tag) throws IOException {
        int len = in.readInt();
        if (len == -1) {
            return null;
        }
        checkLength(len);
        byte[] b = new byte[len];
        in.readFully(b);
        return new String(b, StandardCharsets.UTF_8);
    }
	// 读取二进制到字节数组
    public byte[] readBuffer(String tag) throws IOException {
        int len = readInt(tag);
        if (len == -1) {
            return null;
        }
        checkLength(len);
        byte[] arr = new byte[len];
        in.readFully(arr);
        return arr;
    }
}
```



## 3. 总结

在本节内容中我们学习了什么是序列化，为什么要使用序列化来进行数据传输， 以及 Zookeeper 的序列化方式 Jute 的具体实现。以下是本节内容总结：以下是本节内容总结：

1. 什么是序列化。
2. 什么时候使用序列化。
3. Zookeeper 的序列化方式 Jute。