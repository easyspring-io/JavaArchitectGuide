









![u=2219522005,242568446&fm=26&gp=0](http://qiniu.cdn.easyspring.net/20201218165945.jpg)




<h1 align = "center">网络编程之Netty一站式精讲</h1>




<div style="page-break-after:always;"></div>
 # 目录

[toc]



<div style="page-break-after:always;"></div>

 # 第 1 章 基础知识

 ## 01 开篇词：拿下 Netty 这座城，度过职场和人生的重要时刻，come on


![img](https://img1.sycdn.imooc.com/5f182701000186d806400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)如果不想在世界上虚度一生，那就要学习一辈子。——高尔基![img](https://www.imooc.com/static/img/column/bg-r.png)



你好，我是彤哥，技术公众号 “彤哥读源码” 的运营者。

其实，我刚学习 Netty 的时候，也是很迷茫的，直到有一天，一个同事收到了阿里的 offer，他要去阿里做中台了，临走前他偷偷地告诉我，多看看 Netty，特别是源码。

之后，我把市面上有关 Netty 的书籍和博客几乎全部看了一遍，并跟着书中的示例边看边练，但是，最后，我发现，在 Netty 的知识方面，我只是从一个学徒变成了一个熟练工，对 Netty 的理解还是谈不上有多深刻，因为很多书籍或者博客对 Netty 的讲解都停留在使用的角度，对于核心知识和底层原理，讲解得很少，或者说是很不全面。

所以，我决定自己动手，把 Netty 的源码撸一遍，没多久，我就发现，我不仅在 Netty 方面的知识飞速增长，对于 Java 底层的很多原理也理解得更透彻了，得益于此，我后面进入了国内某互联网游戏公司担任平台架构的设计与实现。现在，我在国内某互联网大厂担任中台架构的设计与实现，这其中，Netty 对我的影响无疑是巨大的。

这是我自己学习 Netty 的经历，现在，你可以想想你的情况。

- 是不是一直想学习 Java 网络编程，却不知道怎么入门？
- 是不是看完《Netty 实战》，还是只会写入门级的示例？
- 是不是学习其他开源框架，一深入到通信层就无所适从？
- 是不是面试过程中，提及 Netty，只能简单地说说请求的执行流程？对于更底层的线程池、对象池、内存池却一问三不知？

如果你是这种情况，其实你并不孤独，这不是你一个人遇到的问题，在工作中，我喜欢与人交流，发现很多同学，不管新人，还是老人，对 Netty 的掌握都停留在表面。

还是上面那位牛人，他去阿里后，遇到的第一个挑战是他的领导让他一个星期内学习完 Dubbo，并做成 PPT 分享给全组人员，对于从来没学习过 Dubbo 的他，你可能会说，这太难了，几乎不可能完成。然而，他学习 Dubbo 只花了五天时间，并把底层通信研究得非常透彻，剩余两天做成 PPT，汇报时，领导都惊讶于它能在短短一周对 Dubbo 有如此深入的理解。

我觉得这其中他对 Netty 的深入理解占了很大的比例。后面，他跟我说，其实，Java 领域学来学去就那么些东西，最重要的还是掌握底层核心知识，这些核心知识掌握了，学习其他东西真的能事半功倍，这也是他能快速学习并获得成功的秘诀。

那么，作为 Java 开发者，应该掌握哪些底层核心知识呢？

无外乎就是反射、代理、多线程这些东西，当然，还有 NIO，那么，如何快速地学习并掌握这些知识呢？

我认为通过源码是一种不错的途径，不管是 Java 本身的源码，还是开源框架的源码。

而 Netty 作为 Java 网络编程领域的事实标准，无疑是最合适的。
![图片描述](https://img1.sycdn.imooc.com/5f0bd0d600013eb510270508.png)

通过上图，可以看到，在 Java 中，很多大家熟悉的框架都在使用 Netty，而且，这些框架遍布 Java 的各个领域，包括但不仅限于大数据、RPC、消息队列、搜索引擎、数据库等。

所以，我想做一个关于 Netty 的课程，希望通过这个课程能够让你真正掌握到 Netty 的底层核心知识。

那么，我将怎么设计这个课程呢？

我根据自己学习和使用 Netty 的经验，将整个课程分成六个模块来讲解：
![图片描述](https://img1.sycdn.imooc.com/5f0bd1060001db7510270161.png)

**基础知识**，介绍 Netty 的发展历史，并学习 Java 网络编程的基础知识，打好基础，方能事半功倍；

**源码剖析 —— 数据流向**，从数据流向的角度剖析源码，包含服务启动、接收数据、关闭连接等，快速掌握 Netty 应用运行的基本流程，这一部分源码可以使用泛读的技巧，快速阅读，了解大致流程；

**源码剖析 —— 核心知识**，从核心知识的角度剖析源码，包含内存池、对象池、线程池等，深入底层，掌握核心要点，这一部分源码需要精读，对每一个知识点死磕到底；

**项目实战**，从软件开发生命周期的角度，介绍如何使用 Netty 开发一个生产级的游戏项目；

**实战进阶**，对实战项目进行不断调优，使其更稳定、更快速、更安全、更可靠，并介绍如何快速排查生产问题；

**课程总结**，对整个课程做一个总结和回顾。

我很感激当年偷偷告诉我要看 Netty 的那位同事，那无疑是我人生中非常重要的转折点。

没有那位同事的悄悄话，可能就没有今天的我，希望这个专栏也能成为你的人生的一个转折点。

最后，我希望通过这个专栏，不仅能够帮你学习到 Netty 的底层核心知识，更能加深对 Java 底层核心知识的理解，帮你拿下 Netty 这座城，度过职场和人生的重要时刻，come on！





<div style="page-break-after:always;"></div>

 ## 02 Netty是如何发迹的


![img](https://img4.sycdn.imooc.com/5f0594ef00010bec06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)完成工作的方法，是爱惜每一分钟。——达尔文![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

话说天下大势，分久必合，合久必分：网络协议早期便衍生出了 OSI 七层协议，后归于 TCP/IP 协议（最火）；IO 模型早期便衍生出了五种 IO 模型，后归于 NIO 模型（最热）；自 NIO 模型诞生以后，各种基于 NIO 的网络框架群雄并起、割据分争，最后归于 Netty（最闪）。



 ### Java NIO 时代

溥天之下，莫非王土；网络编程，莫非 Java NIO！

2002 年，注定是一个伟大的年代，JDK1.4 版本在这年发布，并加入了对于 NIO 的支持，它虽然不算很强大的框架，但是早期在没有框架可用的情况下也必须使用它来进行网络编程，即使偶然还搞出个空轮询的 bug，这就是属于 Java NIO 的时代 —— 难用也必须得用。

> NIO 模型中的 `N` 一般指代 `Non-blocking`，即非阻塞的意思，NIO 即非阻塞 IO 的意思。
> 广义上来说，NIO 包括 Non-blocking IO（非阻塞 IO）、IO Multiplexing（IO 多路复用）、Signal-Driven IO（信号驱动 IO）。
> 狭义上来说，NIO 仅指 Non-blocking IO。
>
> Java NIO 中的 `N` 是指 `New`，即新的意思，Java NIO 即新的 IO，是相对于 OIO (Old IO) 或者 BIO (Blocking IO) 来说的，在 Java 的实现中是基于 IO Multiplexing 模型实现的。

说起 Java 对于 NIO 的支持，我们有必要揭起那道伤疤，看看使用 Java NIO 编程曾经给大家带来了 “多么痛的领悟”：

- API 复杂难用，尤其是 Buffer 的指针切来切去的，反人类设计
- 需要掌握丰富的知识，比如多线程和网络编程
- 可靠性无法保证，断线重连、半包粘包、网络拥塞统统需要自己考虑
- 空轮询 bug，CPU 又 100% 了，一直未根除此问题

所以，在 Java NIO 末期进入了群雄并起的时代，各种框架层出不穷，都想在 NIO 的热潮中分一杯羹。



 ### 群雄并起



 #### Netty2

2004 年，一个棒子国的游戏浪子 Trustin Lee，怀揣着梦想，站在了 BIO 和 NIO 的十字路口，左顾右盼，最终走向了 NIO。那年，他带着自己最闪亮的作品 `Netty2` 敲响了棒子国最大的移动通信商 ——Arreo 通信公司 —— 的大门，毫无疑问，他被成功录取了。

彼时，Netty2 号称是 Java 社区中第一个基于事件驱动的网络应用框架，它的梦想是做夜空中最闪亮的一颗星：

```xml
<dependency>
    <groupId>net.gleamynode</groupId>
    <artifactId>netty2</artifactId>
    <version>1.9.2</version>
</dependency>
```

> gleamy node，夜空中最闪亮的那一颗。
>
> 启示，梦想还是要有的，万一实现了呢。



 #### Grizzly

同样是 2004 年，一款叫作玻璃鱼（Sun 公司开发的 GlassFish）的应用服务器诞生了，它是为了打败 Tomcat 而生的。使用了最新的 NIO 技术，并封装成了完整的框架 ——Grizzly，专门解决编写成千上万用户访问服务器时候产生的各种问题。

Grizzly 使用 Java NIO 作为基础，提供了高性能的 API，并隐藏了编程的复杂性，使得它一出世就很火。比如，我们熟知的 Jetty、Comet 等都是基于 Grizzly 构建的。

但是，光顾着沉浸在欢乐喜悦之中，却忘了三件非常重要的事：

- 文档少，几乎没什么可用的文档
- 更新慢，好几个月才一次提交
- 用户少，社区没做好，用户不多

基于以上三点原因，使得它被 Netty 甩了一条街，不管是社区活跃度还是流行度：

![图片描述](https://img1.sycdn.imooc.com/5f0bd182000141a611010825.png)

> 启示，东西好，还要用心经营。



 #### Tomcat

2005 年前后，BIO 时代的霸者 ——Tomcat，意识到了 Grizzly 带来的危机，逆势发布了 6.0 版本，它也开始支持 NIO 了，同样使得它的性能有了质的飞跃。

但是，Tomcat 的 NIO 通信层并没有从它本身的代码中解耦出来，形成了一种 “老奶奶裹脚，又臭又长” 的代码，这也使得它在 NIO 的浪潮中只能保住自己的一亩三分地，并不具有进攻他人的属性。

> 启示，代码解耦真的很重要。



 #### MINA

2005 年，另一个年轻人 Alex，他当时正在为 Apache Directory 开发网络框架，但是他自己怎么写都感觉不好，一次偶然的机会，它瞅见了 Netty2，被它的闪亮所折服，就找到了当时还在 Arreo 通信公司的 Trustin Lee，邀请他一起来开发网络框架，后面就诞生了一个伟大的网络通信框架 ——MINA，并把它贡献给了 Apache。

MINA 可帮助用户轻松开发高性能和高可伸缩性的网络应用程序，支持各种传输协议，比如 TCP 和 UDP 等。

这可能是 Trustin Lee 一生的痛，所以后来他一再强调 MINA 没有 Netty 好用：
![图片描述](https://img1.sycdn.imooc.com/5f0bd18f0001df3c09500433.png)

大致意思就是说：

- MINA 的功能繁杂，复杂性高，性能差
- MINA 的功能过于耦合
- Netty 的 API 更整洁、更文档化
- Netty 的更新周期短
- MINA3 会破坏 API 的兼容性

说白了，MINA 虽然是 Trustin Lee 主导开发的，但是它已经贡献给了 Apache，自己不再参与其中了，而且还是自己的亲儿子 Netty 的强力对手，不抨击它抨击谁。

> 启示，千万不要轻易给自己制造竟然对手。



 #### Netty3

2008 年，Trustin Lee 裹挟着迷茫和彷徨加入了 JBoss，并在同年发布了 Netty3。

这是一个全新的 Netty，背靠大厂 JBoss，并借鉴了 MINA 中很多优秀的设计，使得它一发布就引起了社会各界人士的关注，更新频繁，社区也异常活跃，占领了网络通信的半壁江山。

那时，Netty 只想安安稳稳地待在 JBoss 这个大厂中，稳定至上：

```xml
<dependency>
      <groupId>org.jboss.netty</groupId>
      <artifactId>netty</artifactId>
      <version>3.0.0.Final</version>
</dependency>
```

> 启示，背景很重要，你懂得。



 #### Netty4

2012 年，内心中的那份不安和执念终于爆发，Trustin Lee 决定了要想随心所欲地做自己想做的事，还是得出来单干。

那年，他带着 Netty4 又一次出现在了大家的面前，相对于 Netty3，他做了很多改进，比如线程模型、池化的 Buffer 等，性能提升到了极致。

此时，Netty 才算彻底独立，当然，它也终于成为了那颗最闪亮的星：

```xml
<dependency>
    <groupId>io.netty</groupId>
    <artifactId>netty-all</artifactId>
    <version>4.0.0.Final</version>
</dependency>
```

> 启示，追寻自己的内心，随心所欲，为所欲为！



 #### Netty5

2013 年，出来单干的 Trustin Lee 是有野心的，很多 JDK 的新特性他也想去尝试，比如 ForkJoinPool，所以这一年有了 Netty5。

但是，好景并不长，在 Netty5 发布了两个 Alpha 版本，被一个叫 `Norman Maurer`（《Netty in Action》的作者）的家伙在 2015 年双 11 这天提议给废弃了，他的理由很简单也很任性：
![图片描述](https://img1.sycdn.imooc.com/5f0bd1a400017a3409450541.png)

- 使用 ForkJoinPool 提升了复杂性
- 没有带来明显的性能提升
- 同时维护太多分支太耗费精力

> 启示 1，做自己能力范围内的事。
>
> 启示 2，千万不要使用 Alpha、Beta 等非稳定版本。



 ### Netty 时代

现在这个时代是属于 Netty 的，大家越来越喜欢 Netty，以前使用 MINA 等其它通信框架的也在逐步转换为 Netty，说 Netty 统一了 Java 领域中的网络通信一点也不为过，在很多领域都能见到它的身影：

- 框架，gRPC、Dubbo、Spring WebFlux、Spring Cloud Gateway
- 大数据，Spark、Hadoop、Flink
- 消息队列，RocketMQ、ActiveMQ
- 搜索引擎，Elasticsearch
- 分布式协调器，Zookeeper
- 数据库，Cassandra、Neo4j
- 工具类，async-http-client
- 日志，Graylog
- 负载均衡，Ribbon



 ### 后记

Netty 从最初梦想着成为最闪亮的星，经历了群雄割据奋战，现在已经被广大框架所运用，它无疑已经成为 Java 网络通信领域的事实标准，所以我们有必要学好 Netty，并熟练掌握如何在实战中使用 Netty。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0bd1b30001c8e419581097.png)











<div style="page-break-after:always;"></div>

 ## 03 IO的五种模型是什么


![img](https://img2.sycdn.imooc.com/5f0d16270001cc7a06400426.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)立志是事业的大门，工作是登堂入室的旅程。——巴斯德![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节我们一起学习了 Netty 的发展历史，我们提到了 IO、NIO 这些名词。那么，到底什么是 IO 呢？什么又是 NIO 呢？

另外，我们平时又会听到两组很相似的概念：阻塞 / 非阻塞、同步 / 异步。那么，阻塞和非阻塞有什么区别呢？同步和异步又有什么区别呢？很多同学对这两组概念都比较容易混淆，也讲不清楚。

所以，本节就从网络 IO 的角度出发并用生活中常见的案例来白话 IO 的五种模型，以及上面两组概念。



 ### 用户空间和内核空间

操作系统的核心是内核，它独立于普通的应用程序，可以访问受保护的内核空间，也有访问底层硬件设备的所有权限。为了保护内核的安全，现在操作系统一般都强制用户进程不能直接操作内核，所以操作系统把内存空间划分成了两个部分：内核空间和用户空间。
![图片描述](https://img1.sycdn.imooc.com/5f0bdc4b0001b3a805420303.png)

这就好比，饭店老板把整个饭店划分成两个部分：大厅和厨房。大厅用于顾客吃饭，厨房用于厨师做饭，厨房的门上面一般还会写着：“厨房重地，闲人免进”，也就是顾客一般不具有直接使用厨房的特性。
![图片描述](https://img1.sycdn.imooc.com/5f0bdc5e0001161303570165.png)

所以，当我们使用 TCP 发送数据的时候，需要先将数据从用户空间拷贝到内核空间，再由内核操作将数据从内核空间发送出去；当我们使用 TCP 读取数据的时候，数据先在内核空间准备好，再从内核空间拷贝到用户空间供用户进程使用。
![图片描述](https://img1.sycdn.imooc.com/5f0bdc7a00018dc609200315.png)

这就好比，当我们在饭店吃饭的时候，先在客厅点好菜，再由服务员把我们的菜单传递进厨房；当厨房做好了菜，再从厨房由服务员传递到客厅一样。

所以，一次 IO 的读取操作分为两个阶段（写入操作类似）：

- 等待内核空间数据准备阶段
- 数据从内核空间拷贝到用户空间

为此，Unix 根据这两个阶段又把 IO 分成了以下五种 IO 模型：

- 阻塞型 IO
- 非阻塞型 IO
- IO 多路复用
- 信号驱动 IO
- 异步 IO

下面我们一一道来。



 #### 阻塞型 IO

阻塞型 IO，即当用户进程发起请求时，一直阻塞直到数据拷贝到用户空间为止才返回。

阻塞型 IO 在两个阶段是连续阻塞着的，直到数据返回。
![图片描述](https://img1.sycdn.imooc.com/5f0bdcca0001ff9210290479.png)

这就好比，你去路边买快餐，这家店比较低级，只有一辆车一个老板。点完餐后，你傻傻地看着老板开始打菜，然后拿给你。整个过程中，你只能看着老板打完菜并拿给你，这两个阶段你都是阻塞的。
![图片描述](https://img1.sycdn.imooc.com/5f0bf30a0001761c10280469.png)



 #### 非阻塞型 IO

非阻塞型 IO，用户进程不断询问内核，数据准备好了吗？一直重试，直到内核说数据准备好了，然后把数据从内核空间拷贝到用户空间，返回成功，开始处理数据。

非阻塞型 IO 第一阶段不阻塞，第二阶段阻塞。
![图片描述](https://img1.sycdn.imooc.com/5f0bf3360001993710320415.png)

这就好比，你去小炒店，这家店高级一点，有独立的店面。点完餐后，你可以边玩手机边等。隔了一会你跑过去问一下老板 “我的菜好了没”，老板说 “还没好”；隔一会你又跑过去问了下 “我的菜好了没”，老板说 “还没有”；几次后，你又说 “老板，我的菜好了没”，老板说 “来了来了”，然后你看着他把菜端到你面前。整个过程中，询问 “菜好了没” 你不用阻塞，老板立即回应你，你可以立即玩手机，但是端菜的时候你是傻傻地看着他端的，这期间你无法玩手机，你是阻塞的。
![图片描述](https://img1.sycdn.imooc.com/5f0bf34600015a0110210448.png)



 #### IO 多路复用

IO 多路复用，多个 IO 操作共同使用一个 selector（选择器）去询问哪些 IO 准备好了，selector 负责通知那些数据准备好了的 IO，它们再自己去请求内核数据。

IO 多路复用，第一阶段会阻塞在 selector 上，第二阶段拷贝数据也会阻塞。
![图片描述](https://img1.sycdn.imooc.com/5f0bf38200013de210290486.png)

这就好比，你去川菜馆吃饭，这家饭店比较大，人也多，还有个美女服务员。你点完菜后，勾搭了一下美女服务员 “美女，我点个辣子鸡丁，好了通知我一下哦”，美女也没搭理你。其它人也是这么勾搭美女的。然后，美女忙得不可开交，隔一会去厨房看一下，哪些菜好了，每次出来，都会喊 “那谁谁谁，你的啥啥菜好了，自己过来端一下。”。整个过程中，美女去厨房看菜是阻塞的，因为没有菜好的时候她还要等一会；你跑过去端菜也是阻塞的。一部分阻塞在美女身上，一部分阻塞在你身上。
![图片描述](https://img1.sycdn.imooc.com/5f0bf3990001c8a010290468.png)



 #### 信号驱动 IO

信号驱动 IO，用户进程发起读取请求之前先注册一个信号给内核说明自己需要什么数据，这个注册请求立即返回，等内核数据准备好了，主动通知用户进程，用户进程再去请求读取数据，此时，需要等待数据从内核空间拷贝到用户空间再返回。

信号驱动，第一阶段不阻塞，第二阶段阻塞。
![图片描述](https://img1.sycdn.imooc.com/5f0bf3b70001527a10290490.png)

这就好比，你去 “金拱门” 吃麦当劳一样。你在旁边的机器上点完餐后出来一张小票 “1024 号”，然后你边玩手机边等。过了一会，喇叭喊，“1024 号，请取餐。1024 号，请取餐。”，然后，你屁颠屁颠地跑过去取餐。整个过程中，点餐是立即返回的，之后想干啥干啥，不阻塞（也就是说你不用傻等着餐做好）；取餐的过程你需要从柜台端到你的位置上，是阻塞的。
![图片描述](https://img1.sycdn.imooc.com/5f0bf3c50001761c10280469.png)



 #### 异步 IO

异步 IO，用户进程发起读取请求后立马返回，当数据完全拷贝到用户空间后通知用户直接使用数据。

异步 IO，两个阶段都不阻塞。
![图片描述](https://img1.sycdn.imooc.com/5f0bf3d900019f3d10290494.png)

这就好比，你去吃 “渔粉”。扫码点餐后，你完全不用管，过了一会，一个大妈把饭菜端到你面前，还贴心地说了句 “客官，请慢用”，然后你幸福地吃下了这碗 “金汤渔粉”。整个过程中，你既不用傻等着渔粉做好，也不用看着大妈把菜端到你面前或者你自己去端，完全不阻塞，纯异步。所以，这种体验是最好的。
![图片描述](https://img1.sycdn.imooc.com/5f0bf41f0001801710250511.png)

所以，如果把吃饭的过程分成两个部分：“准备饭菜” 和 “端菜”，那么：

1. 如果你傻等着两个阶段完成，就是阻塞 IO；
2. 如果你隔一会询问一下 “菜做好了没”，期间你可以玩手机，但是端菜的时候你傻傻地看着老板端过来，就是非阻塞 IO；
3. 如果你和其他人都委托服务员帮你们隔一会看一下 “菜做好了没”，但是端菜需要自己去端，就是 IO 多路复用；
4. 如果是机器点餐，机器喊话取餐，就是信号驱动 IO；
5. 如果是扫码点餐，自动上餐，就是异步 IO；



 #### 阻塞与非阻塞

阻塞，是指调用结果返回之前，当前线程会被挂起，直到调用结果返回。比如，你傻等着端菜结束，你就是阻塞的。

非阻塞，是指不能立即得到结果之前，当前线程不被挂起，而是可以继续做其它的事。比如，你边玩手机边等饭菜准备好，你就是非阻塞的。

简单点，就是阻塞调用你必须挂起傻等着结果返回，非阻塞调用你不关心结果，调用之后你爱干嘛干嘛。



 #### 同步与异步

关于同步与异步，我们直接看看 POSIX 中的定义：

> A synchronous I/O operation causes the requesting process to be blocked until that I/O operation completes;
>
> An asynchronous I/O operation does not cause the requesting process to be blocked;

同步，调用者会被阻塞直到 IO 操作完成，调用的结果随着请求的结束而返回。

异步，调用者不会被阻塞，调用的结果不随着请求的结束而返回，而是通过通知或回调函数的形式返回。

> 阻塞 / 非阻塞，更关心的是当前线程是不是被挂起。
>
> 同步 / 异步，更关心的是调用结果是不是随着请求结束而返回。

这里的阻塞是指整个 IO 过程中是否有阻塞，更确切地说是 `recvfrom` 这个系统调用是否会阻塞，在我们的案例中，可以理解为 “端菜” 这个行为对于你来说是不是阻塞的。

所以，阻塞型 IO、非阻塞型、IO 多路复用、信号驱动 IO 都是同步 IO，只有最后一种才是异步 IO。



 ### 为什么不选择异步 IO？

通过上面的分析，异步 IO 才是最牛的 IO 模型，那么，我们为什么不选择异步 IO 呢？

那是因为异步 IO 在 linux 上还不成熟，而我们的服务器通常都是 linux，所以现在大部分框架都不是很支持异步 IO，包括 Netty 之前实现了一版，但是后面给废弃掉了。



 ### 后记

本节通过饭店的不同模型来描述了 IO 的五种模型，相信读者们有了清晰的认识和深刻的理解，今天吃饭的时候，你处于哪种模型呢？



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0bd1fd00012beb16500735.png)







<div style="page-break-after:always;"></div>

 ## 04 Java中如何使用BIO、NIO、AIO


![img](https://img3.sycdn.imooc.com/5f0595030001ebd206400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)富贵必从勤苦得。——杜甫![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节我们一起学习了 IO 的五种模型，分别为阻塞型 IO、非阻塞型 IO、IO 多路复用、信号驱动 IO、异步 IO。在计算机的早期，所有的网络通信使用的都是阻塞型 IO，即 BIO，随着计算机技术的不断发展，才衍生出了其它四种模型。而且，在当前这个阶段，linux 系统上 AIO 还不成熟，因此，现在 NIO 才是最流行的。

不过，考虑到很多同学之前没有接触过网络编程，头脑中根本没有 BIO/NIO/AIO 这些概念的代码示例，也不知道从何下手。

所以，本节我将结合代码，简单地描述在 Java 中我们如何编写 BIO/NIO/AIO 的程序。最后，使用 NIO 做一个简单的群聊系统送给你，带你领悟 NIO 编程的魅力。

> BIO，阻塞型 IO，也称为 OIO，Old IO。
>
> NIO，New IO，Java 中使用 IO 多路复用技术实现，放在 `java.nio` 包下，JDK1.4 引入。
>
> AIO，异步 IO，又称为 NIO2，也是放在 `java.nio` 包下，JDK1.7 引入。

好了，现在让我们正式进入今天的学习吧，首先，我们来看看如何编写 BIO 程序。



 ### 如何编写 BIO 程序

我们先来复习一下 BIO 的概念：当用户进程发起请求时，一直阻塞直到数据拷贝到用户空间为止才返回。

BIO 会阻塞当前线程，直到请求结果返回，就像去路边摊打饭一样，只能傻傻地等着老板打完饭交到你手里。

> 声明：本系列课程中如无特殊说明，所有代码示例都是基于 TCP/IP 协议的网络编程。

好了，让我们端上 BIO 这盘菜：

```java
public class BIOEchoServer {
    public static void main(String[] args) throws IOException {
        // 启动服务端，绑定8001端口
        ServerSocket serverSocket = new ServerSocket(8001);

        System.out.println("server start");

        while (true) {
            // 开始接受客户端连接
            Socket socket = serverSocket.accept();

            System.out.println("one client conn: " + socket);
            // 启动线程处理连接数据
            new Thread(()->{
                try {
                    // 读取数据
                    BufferedReader reader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
                    String msg;
                    while ((msg = reader.readLine()) != null) {
                        System.out.println("receive msg: " + msg);
                    }
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }).start();
        }
    }
}
```

首先，我们使用 `ServerSocket serverSocket = new ServerSocket(8001);` 启动了一个服务端，这时候服务端可以接收连接了吗？当然不能，就像路边摊虽然摆好了，但还没开始营业一样。

其次，我们声明了一个死循环 `while (true)`，为什么要声明为死循环呢？因为服务端跟客户端是一对多的关系，可能会有多个客户端连接到服务端，对于每一个连接过来的客户端，服务端都要去 “接待”，就像路边摊的老板，对于每一个顾客他都要亲自接待一样，如果没有死循环，那么老板自始至终只能接待一个顾客。

再次，我们使用 `Socket socket = serverSocket.accept();` 接受客户端的连接，并把这个连接（Socket）保存下来，用于后续读取数据。

接着，我们启动了一个线程来处理这个连接，为什么要启动线程呢？如果不启动线程，那么我们只能把处理连接的数据放在主线程中，这时候主线程只能处理当前连接的这一个客户端，而不能同时处理多个客户端。这就像路边摊老板既要亲自接待顾客，又要亲自给顾客打饭一样，他一次只能处理一个顾客的事务。如果给每个连接的客户端都启动一个线程呢？这样主线程就不会阻塞，又能接待下一下连接了。这就像升级版的路边摊，老板只负责接待顾客，打饭的职责交给服务员，每来一个顾客就给他分配一个服务员，这样就极大地提高了打饭的速度。

最后，我们从连接的 IO（网络 IO）中读取数据，并打印出来，这一块跟普通的 IO 操作没有什么两样。顾客说打什么菜，服务员就给他打什么菜。
![图片描述](https://img1.sycdn.imooc.com/5f0bf4c80001232510310362.png)

好了，BIO 编写网络程序就是这么简单，有效的代码行数不超过 10 行，一个服务端网络应用就诞生了。

但是，你有没有发现什么不对劲的地方呢？每来一个顾客都要给他分配一个服务员，这个老板得雇多少服务员啊？！是的了，BIO 编程也有一样的问题，每来一个客户端连接都要分配一个线程，如果客户端一直增加，服务端线程会无限增加，直到服务器资源耗尽。

那么，怎么解决线程无限增加的烦恼呢？让我们来看看 NIO 是否能解决这个问题。



 ### 如何编写 NIO 程序

因为 Java 中的 NIO 使用的是 IO 多路复用技术实现的，所以我们这里再复习一下 IO 多路复用的概念：多个 IO 操作共同使用一个 selector（选择器）去询问哪些 IO 准备好了，selector 负责通知那些数据准备好了的 IO，它们再自己去请求内核数据。

这就像多名顾客共同交待同一个服务员去后厨帮他们看看他们的菜做好了一样，服务员询问的时候是阻塞的，顾客自己去端菜也是阻塞的。

好了，让我们端上 NIO 这盘菜：

```java
public class NIOEchoServer {
    public static void main(String[] args) throws IOException {
        // 创建一个Selector
        Selector selector = Selector.open();
        // 创建ServerSocketChannel
        ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();
        // 绑定8080端口
        serverSocketChannel.bind(new InetSocketAddress(8002));
        // 设置为非阻塞模式
        serverSocketChannel.configureBlocking(false);
        // 将Channel注册到selector上，并注册Accept事件
        serverSocketChannel.register(selector, SelectionKey.OP_ACCEPT);

        System.out.println("server start");
        
        while (true) {
            // 阻塞在select上（第一阶段阻塞）
            selector.select();

            // 如果使用的是select(timeout)或selectNow()需要判断返回值是否大于0

            // 有就绪的Channel
            Set<SelectionKey> selectionKeys = selector.selectedKeys();
            // 遍历selectKeys
            Iterator<SelectionKey> iterator = selectionKeys.iterator();
            while (iterator.hasNext()) {
                SelectionKey selectionKey = iterator.next();
                // 如果是accept事件
                if (selectionKey.isAcceptable()) {
                    // 强制转换为ServerSocketChannel
                    ServerSocketChannel ssc = (ServerSocketChannel) selectionKey.channel();
                    SocketChannel socketChannel = ssc.accept();
                    System.out.println("accept new conn: " + socketChannel.getRemoteAddress());
                    socketChannel.configureBlocking(false);
                    // 将SocketChannel注册到Selector上，并注册读事件
                    socketChannel.register(selector, SelectionKey.OP_READ);
                } else if (selectionKey.isReadable()) {
                    // 如果是读取事件
                    // 强制转换为SocketChannel
                    SocketChannel socketChannel = (SocketChannel) selectionKey.channel();
                    // 创建Buffer用于读取数据
                    ByteBuffer buffer = ByteBuffer.allocate(1024);
                    // 将数据读入到buffer中（第二阶段阻塞）
                    int length = socketChannel.read(buffer);
                    if (length > 0) {
                        buffer.flip();
                        byte[] bytes = new byte[buffer.remaining()];
                        // 将数据读入到byte数组中
                        buffer.get(bytes);

                        // 换行符会跟着消息一起传过来
                        String content = new String(bytes, "UTF-8").replace("\r\n", "");
                        System.out.println("receive msg: " + content);
                    }
                }
                iterator.remove();
            }
        }
    }
}
```

首先，我们创建了一个 Selector，充当 IO 多路复用中的选择器，类似于饭店中的美女服务员。

其次，我们启动了一个 ServerSocketChannel，并设置其为非阻塞模式，与 BIO 中的 ServerSocket 类似，是服务端进程。

再次，我们把 ServerSocketChannel 注册到 Selector 上，相当于是告诉服务员等会记得帮我去后厨看看我的菜好了没。

然后，又来一个死循环，这个死循环跟 BIO 中的死循环不一样哦，这里的死循环是让 Selector 不要停，一次又一次地轮询下去，因为你的菜好了，还会有更多的人让这个服务员去询问他们的菜好了没。

接着，Selector 轮询完一次之后会拿到一系列 Key，这些 Key 叫作 SelectionKey，每个 SelectionKey 里面都绑定了一个数据准备好了的 Channel，通过这个 Channel 我们就可以去取数据了。就像服务员去询问后厨哪些菜准备好了一样，后厨会告诉她哪些哪些号码的好了，然后她干嘛呢？

最后，遍历这些 SelectionKey，取出其中的 Channel，再根据不同的事件类型用 Channel 去读取数据并打印出来，就像服务员拿到了准备好了菜的顾客号码，通知他们去聚餐一样。在 NIO 中事件类型是什么呢？又有哪些事件类型呢？我们将在下一章讨论。
![图片描述](https://img1.sycdn.imooc.com/5f0bf4e10001547e10310372.png)

好了，NIO 的程序如何编写就介绍完了。可以看到，NIO 的程序代码比 BIO 多好几倍，但是它有一个非常大的优点，就是我们始终只有一个线程，并没有启动额外的线程来处理每个连接的事务，解决了 BIO 线程无限增加的问题，所以，NIO 是非常高效的。

但是，如果连接非常多的情况下，有可能一次 Select 拿到的 SelectionKey 非常多，而且取数据本身还要把数据从内核空间拷贝到用户空间，这是一个阻塞操作，这时候都放在主线程中来遍历所有的 SelectionKey 就会变得非常慢了，当然，我们也可以把处理数据的部分扔到线程池中来处理，那么，除了这种方式有没有更高效的方式了呢？让我们来看看 AIO 是否能解决这个问题。



 ### 如何编写 AIO 程序

AIO，异步 IO，相对于 AIO，其它的 IO 模型本质上都是同步 IO。

同样地，我们再回顾下 AIO 的概念：用户进程发起读取请求后立马返回，当数据完全拷贝到用户空间后通知用户直接使用数据。

就像扫码点餐一样，点完之后坐等饭送到你面前，全程非阻塞，没有一丁点的阻塞操作。

好了，让我们来看看 Java 中如何编写 AIO 程序。

```java
public class AIOEchoServer {
    public static void main(String[] args) throws IOException {
        // 启动服务端
        AsynchronousServerSocketChannel serverSocketChannel = AsynchronousServerSocketChannel.open();
        serverSocketChannel.bind(new InetSocketAddress(8003));

        System.out.println("server start");

        // 监听accept事件，完全异步，不会阻塞
        serverSocketChannel.accept(null, new CompletionHandler<AsynchronousSocketChannel, Object>() {
            @Override
            public void completed(AsynchronousSocketChannel socketChannel, Object attachment) {
                try {
                    System.out.println("accept new conn: " + socketChannel.getRemoteAddress());
                    // 再次监听accept事件
                    serverSocketChannel.accept(null, this);

                    // 消息的处理
                    while (true) {
                        ByteBuffer buffer = ByteBuffer.allocate(1024);
                        // 将数据读入到buffer中
                        Future<Integer> future = socketChannel.read(buffer);
                        if (future.get() > 0) {
                            buffer.flip();
                            byte[] bytes = new byte[buffer.remaining()];
                            // 将数据读入到byte数组中
                            buffer.get(bytes);

                            String content = new String(bytes, "UTF-8");
                            // 换行符会当成另一条消息传过来
                            if (content.equals("\r\n")) {
                                continue;
                            }
                            System.out.println("receive msg: " + content);
                        }
                    }
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }

            @Override
            public void failed(Throwable exc, Object attachment) {
                System.out.println("failed");
            }
        });

        // 阻塞住主线程
        System.in.read();
    }
}
```

首先，我们启动了一个 AsynchronousServerSocketChannel，它与 BIO 中的 ServerSocket 和 NIO 中的 ServerSocketChannel 类似，是一个服务端进程；

然后，我们通过 accept () 方法监听客户端连接，用法跟 BIO 和 NIO 都一样，但是，这个 accept () 执行方式完全不一样了，BIO 中的 accept () 是完全阻塞当前线程的，NIO 中的 accept () 是通过 Accept 事件来实现的，而 AIO 中的 accept () 是完全异步的，执行了这个方法之后会立即执行后续的代码，不会停留在 accept () 这一行，所以，在 main () 方法的最后需要加一行阻塞代码，否则 main () 方法执行完毕，进程就结束了。

最后，在 accept () 方法的回调方法 complete () 中处理数据，这里的数据已经经历过数据准备和从内核空间拷贝到用户空间两个阶段了，到达用户空间是真正可用的数据，而不像 BIO 和 NIO 那样还要自己去阻塞着把数据从内核空间拷贝到用户空间再使用。

所以，从效率上来看，AIO 无疑是最高的，然而，遗憾地是，目前作为广大服务器使用的系统 linux 对 AIO 的支持还不完善，导致我们还不能放心地使用 AIO 这项技术，不过，我相信有一天 AIO 会成为那颗闪亮的星的，现阶段，还是以学好 NIO 为主。



 ### 后记

今天的内容差不多到这里就结束了，本节我们一起学习了在 Java 中如何正确地编写 BIO/NIO/AIO 的程序，相信对照着代码，你能对 IO 的五种模型有更深刻的认识。

另外，在本节内容的附录部分，我会使用 NIO 写一个简单的群聊系统送给大家。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0bf502000147dc15821201.png)



 ### 附录 —— 使用 NIO 实现简单群聊系统



 #### 代码

```java
public class ChatServer {
    public static void main(String[] args) throws IOException {
        Selector selector = Selector.open();
        ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();
        serverSocketChannel.bind(new InetSocketAddress(8080));
        serverSocketChannel.configureBlocking(false);
        // 将accept事件绑定到selector上
        serverSocketChannel.register(selector, SelectionKey.OP_ACCEPT);

        while (true) {
            // 阻塞在select上
            selector.select();
            Set<SelectionKey> selectionKeys = selector.selectedKeys();
            // 遍历selectKeys
            Iterator<SelectionKey> iterator = selectionKeys.iterator();
            while (iterator.hasNext()) {
                SelectionKey selectionKey = iterator.next();
                // 如果是accept事件
                if (selectionKey.isAcceptable()) {
                    ServerSocketChannel ssc = (ServerSocketChannel) selectionKey.channel();
                    SocketChannel socketChannel = ssc.accept();
                    System.out.println("accept new conn: " + socketChannel.getRemoteAddress());
                    socketChannel.configureBlocking(false);
                    socketChannel.register(selector, SelectionKey.OP_READ);
                    // 加入群聊
                    ChatHolder.join(socketChannel);
                } else if (selectionKey.isReadable()) {
                    // 如果是读取事件
                    SocketChannel socketChannel = (SocketChannel) selectionKey.channel();
                    ByteBuffer buffer = ByteBuffer.allocate(1024);
                    // 将数据读入到buffer中
                    int length = socketChannel.read(buffer);
                    if (length > 0) {
                        buffer.flip();
                        byte[] bytes = new byte[buffer.remaining()];
                        // 将数据读入到byte数组中
                        buffer.get(bytes);

                        // 换行符会跟着消息一起传过来
                        String content = new String(bytes, "UTF-8").replace("\r\n", "");
                        if (content.equalsIgnoreCase("quit")) {
                            // 退出群聊
                            ChatHolder.quit(socketChannel);
                            selectionKey.cancel();
                            socketChannel.close();
                        } else {
                            // 扩散
                            ChatHolder.propagate(socketChannel, content);
                        }
                    }
                }
                iterator.remove();
            }
        }
    }

    private static class ChatHolder {
        private static final Map<SocketChannel, String> USER_MAP = new ConcurrentHashMap<>();

        /**
         * 加入群聊
         * @param socketChannel
         */
        public static void join(SocketChannel socketChannel) {
            // 有人加入就给他分配一个id
            String userId = "用户"+ ThreadLocalRandom.current().nextInt(Integer.MAX_VALUE);
            send(socketChannel, "您的id为：" + userId + "\n\r");

            for (SocketChannel channel : USER_MAP.keySet()) {
                send(channel, userId + " 加入了群聊" + "\n\r");
            }

            // 将当前用户加入到map中
            USER_MAP.put(socketChannel, userId);
        }

        /**
         * 退出群聊
         * @param socketChannel
         */
        public static void quit(SocketChannel socketChannel) {
            String userId = USER_MAP.get(socketChannel);
            send(socketChannel, "您退出了群聊" + "\n\r");
            USER_MAP.remove(socketChannel);

            for (SocketChannel channel : USER_MAP.keySet()) {
                if (channel != socketChannel) {
                    send(channel, userId + " 退出了群聊" + "\n\r");
                }
            }
        }

        /**
         * 扩散说话的内容
         * @param socketChannel
         * @param content
         */
        public static void propagate(SocketChannel socketChannel, String content) {
            String userId = USER_MAP.get(socketChannel);
            for (SocketChannel channel : USER_MAP.keySet()) {
                if (channel != socketChannel) {
                    send(channel, userId + ": " + content + "\n\r");
                }
            }
        }

        /**
         * 发送消息
         * @param socketChannel
         * @param msg
         */
        private static void send(SocketChannel socketChannel, String msg) {
            try {
                ByteBuffer writeBuffer = ByteBuffer.allocate(1024);
                writeBuffer.put(msg.getBytes());
                writeBuffer.flip();
                socketChannel.write(writeBuffer);
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
    }
}
```



 #### 模拟群聊

启动四个 XSHELL 窗口，模拟聊天，你可以试试，可好玩儿了 ^^。（文中的三种 IO 实现都可以这么来模拟客户端请求）

> 如果出现了？的乱码，不用理会，那是 XSHELL 的心跳。

![图片描述](https://img1.sycdn.imooc.com/5f0bf5150001325318840806.png)





<div style="page-break-after:always;"></div>

 ## 05 Java NIO的核心组件有哪些


![img](https://img1.sycdn.imooc.com/5f0595100001aea306400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)只有在那崎岖的小路上不畏艰险奋勇攀登的人,才有希望达到光辉的顶点。——马克思![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节我们一起学习了在 Java 中如何编写 BIO/NIO/AIO 的程序，并给出了最小化的示例代码，通过上一节的学习，相信你一定可以写出很优秀的网络应用程序了。并且，在最后我们用 NIO 写了一个简单的群聊系统，领悟了 NIO 编程的魅力。

不过，对于 Java NIO，你会发现，它不仅仅可以用在网络编程中，还能用在文件读写等其它场景，因此，有必要从根本上来了解 Java NIO。学习它的核心组件是一种最佳途径，能够使我们对 Java NIO 有一个完整的认识，而不仅仅局限于网络编程场景中。

所以，本节，我们将对 Java NIO 的核心组件做一个完整的剖析，带你从根上理解 Java NIO。

好了，让我们一起进入今天的学习吧。



 ### Channel

**什么是 Channel 呢？** 让我们来看看 JDK 怎么说：

> // java.nio.channels.Channel
>
> A nexus for I/O operations.
>
> A channel represents an open connection to an entity such as a hardware device, a file, a network socket, or a program component that is capable of performing one or more distinct I/O operations, for example reading or writing.

**Channel 是一种 IO 操作的连接**（nexus，连接的意思），它代表的是到实体的开放连接，这个实体可以是硬件设备、文件、网络套接字或者可执行 IO 操作（比如读、写）的程序组件。

在 linux 系统中，一切皆可看作是文件，所以，简单点讲，Channel 就是到文件的连接，并可以通过 IO 操作这些文件。

![图片描述](https://img1.sycdn.imooc.com/5f0d5d2300010c6610300425.png)
因此，针对不同的文件类型又衍生出了**不同类型的 Channel**：

- FileChannel：操作普通文件
- DatagramChannel：用于 UDP 协议
- SocketChannel：用于 TCP 协议，客户端与服务端之间的 Channel
- ServerSocketChannel：用于 TCP 协议，仅用于服务端的 Channel

> ServerSocketChannel 和 SocketChannel 是专门用于 TCP 协议中的。
> ServerSocketChannel 是一种服务端的 Channel，只能用在服务端，可以看作是到网卡的一种 Channel，它监听着网卡的某个端口。
> SocketChannel 是一种客户端与服务端之间的 Channel，客户端连接到服务器的网卡之后，被服务端的 Channel 监听到，然后与客户端之间建立一个 Channel，这个 Channel 就是 SocketChannel。

那么，这些 **Channel 又该如何使用呢？** 我们以 FileChannel 为代表来写一个简单的示例。

```java
public class FileChannelTest {
    public static void main(String[] args) throws IOException {
        // 从文件获取一个FileChannel
        FileChannel fileChannel = new RandomAccessFile("D:\\object.txt", "rw").getChannel();
        // 声明一个Byte类型的Buffer
        ByteBuffer buffer = ByteBuffer.allocate(10);
        // 将FileChannel中的数据读出到buffer中，-1表示读取完毕
        // buffer默认为写模式
        // read()方法是相对channel而言的，相对buffer就是写
        while ((fileChannel.read(buffer)) != -1) {
            // buffer切换为读模式
            buffer.flip();
            // buffer中是否有未读数据
            while (buffer.hasRemaining()) {
                // 未读数据的长度
                int remain = buffer.remaining();
                // 声明一个字节数组
                byte[] bytes = new byte[remain];
                // 将buffer中数据读出到字节数组中
                buffer.get(bytes);
                // 打印出来
                System.out.println(new String(bytes, StandardCharsets.UTF_8));
            }
            // 清空buffer，为下一次写入数据做准备
            // clear()会将buffer再次切换为写模式
            buffer.clear();
        }
    }
}
```

通过上面的示例，我们可以发现，Channel 是和 Buffer 一起使用的，那么，什么是 Buffer 呢？为什么要和 Buffer 一起使用呢？必须吗？



 ### Buffer

**什么是 Buffer 呢？** 让我们再来看看 JDK 怎么说：

> // java.nio.Buffer
>
> A container for data of a specific primitive type.
>
> A buffer is a linear, finite sequence of elements of a specific primitive type. Aside from its content, the essential properties of a buffer are its capacity, limit, and position.

Buffer 是一个容器，什么样的容器呢？存放数据的容器。存放什么样的数据呢？特定基本类型的数据。这个容器有哪些特点呢？它是线性的，有限的序列，元素是某种基本类型的数据。它又有哪些属性呢？主要有三个属性：capacity、limit、position。

那么，**Buffer 为什么要和 Channel 一起使用呢？必须一起使用吗？**

打个比方，我们知道，山西盛产煤这种资源，一粒一粒的煤我们可以看作是数据。煤要往外运，那就需要修铁路，比如从山西运到上海，那就要修一条从山西到上海的铁路，这条铁路就相当于是连接山西和上海的通道（Channel）。数据和通道都有了，煤要放在哪里运过去呢？那就需要一种容器，有人可能会想到火车，其实火车可以看作是运输的一种方式或者叫协议，不使用火车，使用滑板车可不可以呢？其实也可以，只是运输的风险比较大而已，所以，火车可以看作是 TCP 协议，而滑板车是 UDP 协议。真正的容器应该是装煤的箱子，也就是 Buffer。

它们之间的关系如下图所示：
![图片描述](https://img1.sycdn.imooc.com/5f0d5d100001709e10320349.png)
所以，Channel 和 Buffer 能不能单独使用呢？其实也可以，只是意义不大，比如，声明了一个 Channel 啥也不干，声明了一个 Buffer 里面存放一些数据啥也不干，意义不大，数据有交互才有意义，所以我们一般把 Channel 和 Buffer 一起使用，从 Channel 读取数据到 Buffer 中，或者从 Buffer 写入数据到 Channel 中。

细心的同学可能会发现，**NIO 的传输方式和传统的基于 BIO 的传输方式**基本是类似的，那么，它们**有什么区别呢**？

首先，BIO 是面向流的，而 NIO 是面向 Channel 或者面向缓冲区的，它的效率更高。

其次，流是单向的，所以又分成 InputStream 和 OutputStream，而 Channel 是双向的，既可读也可写。

然后，流只支持同步读写，而 Channel 是可以支持异步读写的。

最后，流一般与字节数组或者字符数组配合使用，而 Channel 一般与 Buffer 配合使用。

好了，通过前面的学习，我们知道了 Buffer 是一个容器，它里面存储的是特定的基本类型，那么，**有哪些类型的 Buffer 呢？**

我们知道基本类型有：byte、char、short、int、long、float、double、boolean，那么是不是每一种基本类型对应一种 Buffer 呢？嗯，基本上是这样，除了 boolean 没有对应的 Buffer 以外，其它的类型都有对应的 Buffer，因为 boolean 本质上就是 0 和 1 两种情况，Java 字节码层面也是用 0 和 1 来表示 boolean 类型的 false 和 true 的。

所以，Buffer 的类型有：ByteBuffer、CharBuffer、ShortBuffer、IntBuffer、LongBuffer、FloatBuffer、DoubleBuffer。

上面是按照基本类型的角度来划分的，其实针对每一种类型还有不同的内存实现，分为**堆内存实现和直接内存实现**，比如，ByteBuffer 又分为 HeapByteBuffer 和 DirectByteBuffer 两种不同的内存实现，关于堆内存和直接内存的话题，我们后面再细说。

OK，Buffer 有这么多种不同的实现，那么，**它们该如何使用呢？**

从前面 Buffer 的定义，我们知道 Buffer 有三个非常重要的属性，分别为：capacity、limit、position。

- capacity，比较好理解，Buffer 的容量，即能够容纳多少数据。
- limit，这个稍微费脑一些，表示的是最大可写或者最大可读的数据。
- position，这个就更难理解一些，表示下一次可使用的位置，针对读模式表示下一个可读的位置，针对写模式表示下一个可写的位置。

上面的描述可能比较抽象，让我们上一张图来细细品味一下：

![图片描述](https://img1.sycdn.imooc.com/5f0d5cf90001a6d110300419.png)
上图中，深蓝色表示已经写入的空间，这部分有数据可读；淡蓝色表示未被写入的空间，这部分没有数据可读。

写模式下，position 指向下一个可写的位置，limit 表示最大可写的数据，capacity 表示容量。比如，Buffer 的大小为 8，已经写了三个单位的数据，则 capacity=8，limit=8，position=3。

读模式下，position 指向下一个可读的位置，limit 表示最大可读的数据，capacity 表示容量。比如，Buffer 的大小为 8，已经写了三个单位的数据，此时切换为读模式，则 capacity=8，limit=3，position=0。

> 注意，position 表示的是位置，类似于数组的下标，是从 0 开始的。而 limit 和 capacity 表示的是大小，类似于数组的长度，是从 1 开始的。当 Buffer 从写模式切换为读模式时，limit 变为原 position 的值，position 变为 0。

好了，Buffer 的结构我们了解了，那么，要如何使用 Buffer 呢？

Buffer 提供了一系列的方法，供我们简单快捷地使用 Buffer，我们从使用的流程上来说的话，大概有下面这么**几个重要的方法：**

- 分配一个 Buffer：allocate ()
- 写入数据：buf.put () 或者 channel.read (buf)，read 为 read to 的意思，从 channel 读出并写入 buffer
- 切换为读模式：buf.flip ()
- 读取数据：buf.read () 或者 channel.write (buf)，write 为 write from 的意思，从 buffer 读出并写入 channel
- 重新读取或重新写入：rewind ()，重置 position 为 0，limit 和 capacity 保持不变，可以重新读取或重新写入数据
- 清空数据：buf.clear ()，清空所有数据
- 压缩数据：buf.compact ()，清除已读取的数据，并将未读取的数据往前移

用生活中的案例来解释的话，就如同饭店门口的排队策略。今天我们来到一家叫 “椰子鸡” 的餐厅，人爆满。服务员在门口依次摆了 10 张椅子（分配 Buffer），过来一对情侣，他们分别坐在 0 号和 1 号椅子上（position 从 0 开始，写入数据），过了一会儿，又过来一对情侣（别扎心老铁），他们紧跟着坐在了 2 号和 3 号椅子上（position 从 2 开始，写入数据），又过了一会儿，有一桌吃完了，且收拾完毕，0 号和 1 号椅子上的情侣可以出列了（切换为读模式，并读取数据），后面排队的人往前移（压缩数据 compact ()，清除已读取的数据，并将未读取的数据前移），我和女朋友一直排队到晚上 10 点，服务员过来说，我们要打烊了，明天再来吧，我的内心有一万只草尼玛跑过，无奈地离开了座位（清空数据 clear ()），带着女朋友去吃了肯德基。

好了，扯淡结束，让我们对照着代码来看看如何使用 Buffer。

```java
public class FileChannelTest {
    public static void main(String[] args) throws IOException {
        // 从文件获取一个FileChannel
        FileChannel fileChannel = new RandomAccessFile("D:\\object.txt", "rw").getChannel();
        // 分配一个Byte类型的Buffer
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        // 将FileChannel中的数据读出到buffer中，-1表示读取完毕
        // buffer默认为写模式
        // read()方法是相对channel而言的，相对buffer就是写
        while ((fileChannel.read(buffer)) != -1) {
            // buffer切换为读模式
            buffer.flip();
            // buffer中是否有未读数据
            while (buffer.hasRemaining()) {
                // 读取数据
                System.out.print((char)buffer.get());
            }
            // 清空buffer，为下一次写入数据做准备
            // clear()会将buffer再次切换为写模式
            buffer.clear();
        }
    }
}
```

细心的同学会发现，跟上面 Channel 的例子基本上是一样的，是的了，因为 Channel 和 Buffer 要配合着一起使用嘛 ^^。

好了，介绍完了 Channel 和 Buffer，我们再来看看 NIO 的另一个核心组件 ——Selector，可以毫不夸张地说，没有 Selector 就无法使用 NIO 来进行网络编程，那么，**Selector 有哪些过人之处呢？**



 ### Selecor

**什么是 Selector？** 让我们再来看看 JDK 怎么说：

> // java.nio.channels.Selector
>
> A multiplexor of {@link SelectableChannel} objects.

首先，Selector 是一个多路复用器。什么的多路复用器？SelectableChannel 对象的多路复用器，注意，这里的对象是复数，说明一个 Selector 可以关联到多个 SelectableChannel。另外，它是 **SelectableChannel** 的多路复用器，可以跟 FileChannel 配合使用吗？不可以，因为 FileChannel 不是 SelectableChannel。那么 SelectableChannel 有哪些呢？跟网络编程相关的那些 Channel 基本上都是 SelectableChannel，比如 SocketChannel、ServerSocketChannel、DatagramChannel 等。

那么，**Selector 跟 Channel 究竟是怎样的关系呢？**

从上面的描述中，我们也能够大胆猜测，Selector 和 Channel 是一对多的关系，一个 Selector 可以为多个 Channel 服务，监听它们准备好的事件。Selector 就像饭店中的服务员一样，一个服务员是可以服务于多位顾客的，时刻监听着顾客的吩咐。

![图片描述](https://img1.sycdn.imooc.com/5f0d5cd40001547e10310372.png)
OK，那么，**Selector 又该怎么使用呢？** 我们还是以饭店来举例。

首先，饭店需要先聘请一个服务员，然后这个服务员来上班。同样地，Selector 也需要先创建出来，创建的方式有两种，一种是调用 `Selector.open()` 方法，一种是调用 `SelectorProvider.openSelector()` 方法，其中 SelectorProvider 是自定义的。鉴于第二种方式不太常用，所以我们只讲第一种方式。

```java
// 创建一个Selector
Selector selector = Selector.open();
```

接着，有顾客上门了，服务员去接待，“吃啥啊兄弟？”，“小炒黄牛肉。”，顾客把点的菜告诉服务员。同样地，你需要 Selector 干什么，也需要告诉他，在 Java 里面，我们叫作注册事件到 Selector 上，当然了，我们是非阻塞式的，所以，注册之前还要先设置为非阻塞式。

```java
// 注册事件到Selector上
channel.configureBlocking(false);
SelectionKey key = channel.register(selector, SelectionKey.OP_READ);
```

Channel 注册到 Selector 上之后，返回了一个叫作 SelectionKey 的对象，**SelectionKey 又是什么呢？**

一般地，我们在饭店点完菜之后，都会给一个牌子到你手上，服务员通过这个牌子可以找到你，你通过这个牌子可以去拿饭。SelectionKey 就相当于是这个牌子，它将 Channel 和 Selector 的牢牢地绑定在一起，并保存着你感兴趣的事件。

**事件又是什么东西？**

事件是 Channel 感兴趣的事情，比如读事件、写事件等等，在 Java 中，定义了四种事件，位于 SelectionKey 这个类中：

- 读事件：SelectionKey.OP_READ = 1 << 0 = 0000 0001
- 写事件：SelectionKey.OP_WRITE = 1 << 2 = 0000 0100
- 连接事件：SelectionKey.OP_CONNECT = 1 << 3 = 0000 1000
- 接受连接事件：SelectionKey.OP_ACCEPT = 1 << 4 = 0001 0000

细心的同学会发现，四种事件的位正好是错开的，所以，我们可以使用 “位或” 操作监听多种感兴趣的事件：

```java
int interestSet = SelectionKey.OP_READ | SelectionKey.OP_WRITE;
```

然后，服务员拿到了好几个顾客的菜单后，不断地去后厨询问，看看有没有做好的，有做好的就通知到这些顾客。在 Java 中，这叫作轮询，“轮” 是一次又一次的意思，包含循环的含义。

```java
// select()只有询问的意思，加上循环才是轮询的意思
while(true) {
    selector.select(); // 一直阻塞直到有感兴趣的事件
    // selector.selectNow(); // 立即返回，不阻塞
    // selector.select(timeout); // 阻塞一段时间返回
    // ...
}
```

与服务员不断地询问后厨不同的是，服务员没问到结果，可能就去忙其它的事了，比如玩手机，而 select () 没询问到结果会一直阻塞着，直到有感兴趣的事件来了为止。当然，你也可以使用的它的兄弟方法 `selectNow()` 不阻塞立即返回，或者 `select(timeout)` 阻塞一段时间后返回。

最后，服务员拿到这些做好的菜单，通知顾客自己过来聚餐（这个服务员比较懒）。在 Java 中，通过 `selector.selectedKeys()` 返回就绪的事件，然后遍历这些事件就可以拿到想要的结果。

```java
Set<SelectionKey> selectedKeys = selector.selectedKeys();
Iterator<SelectionKey> keyIterator = selectedKeys.iterator();
while(keyIterator.hasNext()) {
    SelectionKey key = keyIterator.next();
    if(key.isAcceptable()) {
        // 接受连接事件已就绪
    } else if (key.isConnectable()) {
        // 连接事件已就绪
    } else if (key.isReadable()) {
        // 读事件已就绪
    } else if (key.isWritable()) {
        // 写事件已就绪
    }
    keyIterator.remove();
}
```

剩下的就是从 Channel 中取数据了，也就是 Channel 和 Buffer 的交互了，在上面已经介绍过了，这里我们就不重复介绍了。



 ### Channel、Buffer、Selector 三者如何联合使用

Channel、Buffer、Selector 这三个 NIO 的核心组件我们都剖析完了，那么，它们该如何联合起来使用呢？让我们看一个完整的案例：

```java
public class NIOEchoServer {
    public static void main(String[] args) throws IOException {
        // 创建一个Selector
        Selector selector = Selector.open();
        // 创建ServerSocketChannel
        ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();
        // 绑定8080端口
        serverSocketChannel.bind(new InetSocketAddress(8002));
        // 设置为非阻塞模式
        serverSocketChannel.configureBlocking(false);
        // 将Channel注册到selector上，并注册Accept事件
        serverSocketChannel.register(selector, SelectionKey.OP_ACCEPT);

        System.out.println("server start");

        while (true) {
            // 阻塞在select上（第一阶段阻塞）
            selector.select();

            // 如果使用的是select(timeout)或selectNow()需要判断返回值是否大于0

            // 有就绪的Channel
            Set<SelectionKey> selectionKeys = selector.selectedKeys();
            // 遍历selectKeys
            Iterator<SelectionKey> iterator = selectionKeys.iterator();
            while (iterator.hasNext()) {
                SelectionKey selectionKey = iterator.next();
                // 如果是accept事件
                if (selectionKey.isAcceptable()) {
                    // 强制转换为ServerSocketChannel
                    ServerSocketChannel ssc = (ServerSocketChannel) selectionKey.channel();
                    SocketChannel socketChannel = ssc.accept();
                    System.out.println("accept new conn: " + socketChannel.getRemoteAddress());
                    socketChannel.configureBlocking(false);
                    // 将SocketChannel注册到Selector上，并注册读事件
                    socketChannel.register(selector, SelectionKey.OP_READ);
                } else if (selectionKey.isReadable()) {
                    // 如果是读取事件
                    // 强制转换为SocketChannel
                    SocketChannel socketChannel = (SocketChannel) selectionKey.channel();
                    // 创建Buffer用于读取数据
                    ByteBuffer buffer = ByteBuffer.allocate(1024);
                    // 将数据读入到buffer中（第二阶段阻塞）
                    int length = socketChannel.read(buffer);
                    if (length > 0) {
                        buffer.flip();
                        byte[] bytes = new byte[buffer.remaining()];
                        // 将数据读入到byte数组中
                        buffer.get(bytes);

                        // 换行符会跟着消息一起传过来
                        String content = new String(bytes, "UTF-8").replace("\r\n", "");
                        System.out.println("receive msg: " + content);
                    }
                }
                iterator.remove();
            }
        }
    }
}
```

是不是很简单？三者一起组成了 Java NIO 网络编程的利器。



 ### 后记

本节，我们一起学习了 Java NIO 的三大核心组件 ——Channel、Buffer、Selector。NIO 不仅仅指代网络编程，还可以进行文件操作等，而 Channel 和 Buffer 一般是联合起来使用，共同进行 NIO 操作。再加上 Selector，就形成了 NIO 网络编程的利器。

通过这几节的学习，不知道你有没有发现，其实 NIO 编程也是蛮简单的嘛，使用 Java NIO 似乎也能写出高性能的网络应用，那么，我们为什么还要学习 Netty 呢？它又有什么过人之处呢？从下一节开始我们将全面进入 Netty 的学习进程，等你来找答案哦。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0d5cad00014cc413761908.png)





<div style="page-break-after:always;"></div>

 ## 06 如何从整体上把握Netty的架构


![img](https://img4.sycdn.imooc.com/5f05951b0001ab2c06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)我们活着不能与草木同腐，不能醉生梦死，枉度人生，要有所作为。——方志敏![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

前面几节，我们一起学习了 Netty 的发迹史，以及 IO 的基础知识，从本节开始我们将正式进入 Netty 的学习。

不过，很多同学可能会有所疑问，学习 Netty 应该从哪里切入呢？笔者认为，当先从 Netty 的整体结构入手，从整体到局部，从宏观到微观，是一种不错的学习方法。

所以，本节，我将从架构设计、模块设计两个维度来从宏观上分析 Netty 的整体结构。

好了，让我们进入今天的学习吧。



 ### 架构设计

关于架构设计，让我们看看 Netty 官方网站怎么说：
![图片描述](https://img1.sycdn.imooc.com/5f0d60c40001334d05920348.png)
官网只给了这么一张图片，啥也没说 ^^。

从这张架构图上，我们可以看到 Netty 的分层特别清晰：

- Core，核心层，主要定义一些基础设施，比如事件模型、通信 API、缓冲区等。
- Transport Service，传输服务层，主要定义一些通信的底层能力，或者说是传输协议的支持，比如 TCP、UDP、HTTP 隧道、虚拟机管道等。
- Protocol Support，协议支持层，这里的协议比较广泛，不仅仅指编解码协议，还可以是应用层协议的编解码，比如 HTTP、WebSocket、SSL、Protobuf、文本协议、二进制协议、压缩协议、大文件传输等，基本上主流的协议都支持。

Netty 的核心在于其可扩展的事件模型、通用的通信 API、基于零拷贝的缓冲区等，它们就像厨房中的锅碗瓢盆和油盐酱醋，有了厨房的这些基础设施，才能做出美味的佳肴。然后，我们才能定义更上层的服务，比如传输协议、序列化协议、编解码协议等。传输协议就像是我们的点餐系统，是通过普通的菜单点餐，还是扫码点餐等。编解码协议更像是怎么盛放佳肴的问题，是通过好看的餐盘，还是通过纸质饭盒，当然，有了基础设施和传输服务，怎么编解码传输的内容就更简单了，甚至，我们可以定义自己的编解码方式，比如，JSON 序列化。

好的架构就像指南针，有了这份好的架构设计，才能指引我们更有效地 coding，当然，对于学习者也是一份很重要的参考指南。

看了这份架构，相信你的心中已经有了很多疑惑，什么是事件模型？如何扩展？怎么做到通信 API 的通用性？零拷贝又是什么东西？如何自定义编解码？等等。对于这些问题，我们后面都会解答，这里先埋个伏笔哦。

好了，看完了架构设计，我们再来看看模块设计。



 ### 模块设计

Netty 是一个多模块的项目，它的模块设计得非常完美，使得对于 Netty 的扩展相当方便，至于怎么个方便法，请听我娓娓道来。

我大概数了下，一共有 40 个 jar 包，我们来归下类：

![图片描述](https://img1.sycdn.imooc.com/5f0d60b00001999d10340739.png)
细心的同学有没有发现一个很有兴趣的点？哈哈，跟上面的架构图几乎一模一样？对的，就是一样一样的，让我们自底向上、自左向右来分析分析：



 #### netty-common

`netty-common` 包主要定义了一些工具类，归纳下来大概如下：

- 通用的工具类，比如 `StringUtil` 等
- 对于 JDK 原生类的增强，比如 `Future`、`FastThreadLocal` 等
- Netty 自定义的并发包，比如 `EventExecutor` 等
- Netty 自定义的集合包，主要是对 HashMap 的增强

注意，其它所有模块都依赖于 common 包。

> 如果你是直接从 github 克隆下来的工程，会发现并没有集合包，那是怎么回事呢？
>
> 仔细观察一下 common 包，会发现 src/main 目录下还有两个目录：script 和 templates，一个是 groovy 脚本，一个是模板。粗略地看一下，会发现很像生成集合的代码模板，那么，怎么生成呢？无疑是在 maven 的 pom 文件中定义的，打开 pom.xml，搜索 groovy，果然能找到，而且有 `generate-sources` 这样的字眼，还配置了上面脚本的路径，所以，很简单，只要 compile 一下就可以了，当然，这里生成的不是源码，而是生成 class 文件到 target 下面。



 #### netty-buffer

Netty 自己实现的 Buffer，不同于 JDK 原生的 ByteBuffer 那么难用，Netty 的 ByteBuf 要好用得多，等后面讲例子你就知道差距了。而且 Netty 做了很多优化，比如池化 Buffer、组合 Buffer 等都是在这个包里，Netty 把性能优化到了极致。



 #### netty-resolver

主要是做地址解析用的。

其实，上面三个都可以看作是工具类，它们是构成整个 Netty 的基石，是底盘，很重要。



 #### netty-transport

`netty-transport` 主要定义了一些服务于传输层的接口和类，比如 Channel、ChannelHandler、ChannelHandlerContext、EventLoop 等，这些接口和类都非常的酷，它们支撑起了 Netty 的半边天。

而且，`netty-transport` 还实现了对于 TCP、UDP 通信协议的支持，另外三个包 `netty-transport-sctp`、`netty-transport-rxtx`、`netty-transport-udt` 也是对不同协议的支持，不过后两个已经废弃了，为什么呢？原因很任性，写得不好，不好用，就像废弃 Netty5.0 一样，任性！

> TCP，传输控制协议，Java 中一般用 SocketXxx、ServerSocketXxx 表示基于 TCP 协议通信。
>
> UDP，用户数据报文协议，Java 中一般用 DatagramXxx 表示基于 UDP 协议通信，Datagram，数据报文的意思。
>
> SCTP，流控制传输协议。
>
> RXTX，串口通讯协议。
>
> UDT，基于 UDP 的数据传输协议。



 #### netty-handler

`netty-handler` 中定义了各种不同的 Handler，满足不同的业务需求，这些 Handler 都是 Netty 中非常棒的功能，比如，IP 过滤、日志、SSL、空闲检测、流量整形等，有了这些 Handler，我们不仅能让我们的程序可运行，更能使我们的程序安全地运行，非常棒。

如果说 `netty-transport` 让你觉得 Netty 很酷，那 `netty-handler` 绝对会让你爱上了 Netty。



 #### netty-codec

`netty-codec` 中定义了一系列编码解码器，比如，base64、json、marshalling、protobuf、serializaion、string、xml 等，几乎市面上能想到的编码、解码、序列化、反序列化方式，Netty 中都可以支持，它们是一类特殊的 ChannelHandler，专门负责编解码的工作。

> 编码和解码实际并没有明确的界限，是指把内容从一种形式转换成另一种形式，就像把水变成冰，把冰变成水一样，我们需要施加一些手段来达到这个目的，这种施加手段的过程就是编解码。
>
> 不过，一般来说，编码是把对象逐步转换成字节序列的过程，解码是把字节序列逐步转换成对象的过程。其中，序列化和反序列化是特殊的编码和解码过程。在 Netty 中，我们并不严格区分序列化反序列化与编解码的界限，统一叫作编解码。
>
> 为什么说是逐步转换的过程呢？因为我们可以把多个编解码器串在一起实现最终的转换，比如，冰先转成水，再转成水气，相当于是两个编解码器。

另外，Netty 还帮我们实现了很多主流协议的编解码器，比如，http、http2、mqtt、redis、stomp 等等，可以说覆盖了我们能遇到的 99% 的场景，另外 1% 我们也可以基于优秀的 ChannelHandler 接口自定义编解码器来解决。

> `netty-codec` 与 `netty-handler` 是两个平齐的模块，并不互相依赖，没有包含和被包含的关系，ChannelHandler 接口位于 `netty-transport` 模块中，两者都依赖于 `netty-transport` 模块。

如果说 `netty-handler` 让我们爱上了 Netty，那么，`netty-codec` 可以说让我们爱死了 Netty。



 #### netty-example

`netty-example` 包含了各种各样的案例，比如，我们经常拿来举例的 `echo` 和 `worldclock` 等。

如果说你已经爱死了 Netty，那么，`netty-example` 绝对会让你欲罢不能，因为，这里是专门提供给你抄代码的地方 ^^。



 ### 后记

本节，我们一起学习了 Netty 的架构设计以及模块设计，通过本文的介绍，不知道你有没有爱上 Netty 呢？



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0d609b0001ac8215281648.png)







<div style="page-break-after:always;"></div>

 ## 07 如何优雅地编写Netty应用程序


![img](https://img3.sycdn.imooc.com/5f059525000145c606400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)人生的旅途，前途很远，也很暗。然而不要怕，不怕的人的面前才有路。—— 鲁 迅![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起从架构设计和模块设计两个方面分析了 Netty 的整体结构，有了上一节的学习，相信你一定知道从哪里 “抄” 代码了，并且能够 “抄” 出一份不错的 Netty 使用案例了。

不过，抄归抄，我们还是要大致了解一下编写 Netty 的常用步骤，笔者总结了一下，大概可以分为十大步骤。

所以，本节我们一起来学习下如何使用 Netty 编写简单的示例程序，并在文章的最后手写一个简单的群聊系统，同学们可以将 Netty 的群聊系统跟 Java NIO 的群聊系统进行对比。

好了，让我们开始今天的学习吧。



 ### Netty 编码十步曲

我从 `netty-example` 工程下抄了一份 EchoServer 过来，并删减了部分代码，归纳出来一份编写 Netty 服务端程序的模板，我把它称为 “Netty 编码十步曲”。



 #### 1. 声明线程池（必须）

一般来说，我们会声明两个 Group，一个是 bossGroup，用于处理 Accept 事件，一个是 workerGroup，用于处理消息的读写事件。其中，bossGroup 一般声明为一个线程。当然，如果声明一个 Group 也是可以的，只是不建议。

```java
EventLoopGroup bossGroup = new NioEventLoopGroup(1);
EventLoopGroup workerGroup = new NioEventLoopGroup();
```

这就像是大型餐厅一般有接待生和服务员两种职位一样，接待生一般形象良好，专门负责接待客人，服务员形象稍差，专门负责上菜收碟，你要说不区分两种职位，混用行不行呢，当然也可以，只是不建议，专人干专事。



 #### 2. 创建服务端引导类（必须）

引导类，是用来集成所有配置，引导程序加载的，分成两种，一种是客户端引导类 Bootstrap（个人觉得叫 ClientBootstrap 可能更贴切），另一种是服务端引导类 ServerBootstrap，我们这里编写的是服务端程序，创建的当然是服务端引导类。
注意，Bootstrap 和 ServerBootstrap 之间并不是继承关系，他们是平等的，都继承了 AbstractBootstrap 抽象类。

```java
ServerBootstrap serverBootstrap = new ServerBootstrap();
```

Bootstrap/ServerBootstrap 就像是店长，它负责统筹整个 Netty 程序的正常运行。



 #### 3. 设置线程池（必须）

把第一步声明的线程池设置到 ServerBootstrap 中，它说明了 Netty 应用程序以什么样的线程模型运行，正如前面所说 bossGroup 负责接受（Accept）连接，workerGroup 负责读写数据。

```java
serverBootstrap.group(bossGroup, workerGroup);
```



 #### 4. 设置 ServerSocketChannel 类型（必须）

设置 Netty 程序以什么样的 IO 模型运行，我们这里介绍的是 NIO 编程，选择的当然是 NioServerSocketChannel。

```java
serverBootstrap.channel(NioServerSocketChannel.class);
```

如果您需要使用阻塞型 IO 模型，直接把 Nio 改成 Oio 就可以了，即 OioServerSocketChannel，不过它已经废弃了，所以不建议。

另外，如果您的程序运行在 Linux 系统上，还可以使用一种更高效的方式，即 EpollServerSocketChannel，它使用的是 Linux 系统上的 epoll 模型，比 select 模型更高效，可见 Netty 把性能优化做到了极致。



 #### 5. 设置参数（可选）

设置 Netty 中可以使用的任何参数，这些参数都在 ChannelOption 及其子类中，后面我们会详细介绍各个参数的含义，不过，很遗憾地告诉你，大多数情况下并不需要修改 Netty 的默认参数，这就是 Netty 比较牛的地方。

```java
serverBootstrap.option(ChannelOption.SO_BACKLOG, 100);
```

我们这里设置了一个 SO_BACKLOG 系统参数，它表示的是最大等待连接数量。



 #### 6. 设置 Handler（可选）

设置 ServerSocketChannel 对应的 Handler，注意只能设置一个，它会在 SocketChannel 建立起来之前执行，等我们看源码的时候会详细介绍它的执行时机。

```java
serverBootstrap.handler(new LoggingHandler(LogLevel.INFO))
```

我们这里简单地设置一个打印日志的 Handler。



 #### 7. 编写并设置子 Handler（必须）

Netty 中的 Handler 分成两种，一种叫做 Inbound，一种叫做 Outbound。我们这里简单地写一个 Inbound 类型的 Handler，它接收到数据后立即写回客户端。

```java
public class EchoServerHandler extends ChannelInboundHandlerAdapter {

	@Override
	public void channelRead(ChannelHandlerContext ctx, Object msg) {
		// 读取数据后写回客户端
		ctx.write(msg);
	}

	@Override
	public void channelReadComplete(ChannelHandlerContext ctx) {
		ctx.flush();
	}

	@Override
	public void exceptionCaught(ChannelHandlerContext ctx, Throwable cause) {
		cause.printStackTrace();
		ctx.close();
	}
}
```

设置子 Handler 设置的是 SocketChannel 对应的 Handler，注意也是只能设置一个，它用于处理 SocketChannel 的事件。

```java
serverBootstrap.childHandler(new ChannelInitializer<SocketChannel>() {
	@Override
	public void initChannel(SocketChannel ch) throws Exception {
		ChannelPipeline p = ch.pipeline();
		// 可以添加多个子Handler
		p.addLast(new LoggingHandler(LogLevel.INFO));
		p.addLast(new EchoServerHandler());
	}
});
```

虽然只能设置一个，但是 Netty 的提供了一种可以设置多个 Handler 的途径，即使用 ChannelInitializer 方式，当然，第六步的设置 Handler 也可以使用这种方式设置多个 Handler。

这里，我们设置了一个打印的 Handler 和一个自定义的 EchoServerHandler。



 #### 8. 绑定端口（必须）

绑定端口，并启动服务端程序，sync () 会阻塞直到启动完成才执行后面的代码。

```java
ChannelFuture f = serverBootstrap.bind(PORT).sync();
```



 #### 9. 等待服务端端口关闭（必须）

等待服务端监听端口关闭，sync () 会阻塞主线程，内部调用的是 Object 的 wait () 方法。

```java
f.channel().closeFuture().sync();
```



 #### 10. 优雅地关闭线程池（建议）

最后，是在 finally 中调用 shutdownGracefully () 方法优雅地关闭线程池，优雅停机。

```java
bossGroup.shutdownGracefully();
workerGroup.shutdownGracefully();
```

好了，Netty 编码十步曲介绍完毕了，不知道你有没有什么疑问呢？至少我是有的。

**为什么需要设置 ServerSocketChannel 的类型，而不需要设置 SocketChannel 的类型呢？**

那是因为 SocketChannel 是 ServerSocketChannel 在接受连接之后创建出来的，所以，并不需要单独再设置它的类型，比如，NioServerSocketChannel 创建出来的肯定是 NioSocketChannel，而 EpollServerSocketChannel 创建出来的肯定是 EpollSocketChannel。

你还有什么疑问呢？欢迎留言。



 ### 如何调试

其实学 Netty 的 99% 都是服务端的同学，所以，我们的课程并不会刻意介绍如何编写客户端的 Netty 程序，但是我们怎么调试呢？

这里，我教给大家一个技巧，通过 XSHELL 这个工具调试，这个工具几乎是后端同学必备的一个工具，所以调试起来也是比较容易的。

比如，我上面启动了一个 Netty 服务端，它的端口是 8007，只要打开 XSHELL，不要连接任何服务器，输入以下代码即可连接到我们的 Netty 服务端：

```java
telnet localhost 8007
```

然后，输入任何你想输入的内容，它都会照样返回，比如下面这样：

![图片描述](https://img1.sycdn.imooc.com/5f0d611b0001883104450245.png)



 ### 后记

本节，我们学习了 Netty 编码的十步曲，其中，有些步骤是必须的，有些步骤可选的，有些步骤是建议保留的，相信通过本节的学习，你一定可以写出十分健壮且优雅的 Netty 服务端程序了。

别急哦，本节还没有结束，在附录部分有一份简单的群聊系统，您也可以尝试按照本节介绍的十步曲自己尝试写一个简单的示例练练手。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0d610d0001afcc10830670.png)



 ### 附录 —— 使用 Netty 实现简单群聊系统



 #### 代码

```java
public final class NettyChatServer {

	static final int PORT = Integer.parseInt(System.getProperty("port", "8007"));

	public static void main(String[] args) throws Exception {
		// 1. 声明线程池
		EventLoopGroup bossGroup = new NioEventLoopGroup(1);
		EventLoopGroup workerGroup = new NioEventLoopGroup();
		try {
			// 2. 服务端引导器
			ServerBootstrap serverBootstrap = new ServerBootstrap();
			// 3. 设置线程池
			serverBootstrap.group(bossGroup, workerGroup)
					// 4. 设置ServerSocketChannel的类型
					.channel(NioServerSocketChannel.class)
					// 5. 设置参数
					.option(ChannelOption.SO_BACKLOG, 100)
					// 6. 设置ServerSocketChannel对应的Handler，只能设置一个
					.handler(new LoggingHandler(LogLevel.INFO))
					// 7. 设置SocketChannel对应的Handler
					.childHandler(new ChannelInitializer<SocketChannel>() {
						@Override
						public void initChannel(SocketChannel ch) throws Exception {
							ChannelPipeline p = ch.pipeline();
							// 可以添加多个子Handler
							p.addLast(new LoggingHandler(LogLevel.INFO));
							// 只需要改这一个地方就可以了
							p.addLast(new ChatNettyHandler());
						}
					});

			// 8. 绑定端口
			ChannelFuture f = serverBootstrap.bind(PORT).sync();
			// 9. 等待服务端监听端口关闭，这里会阻塞主线程
			f.channel().closeFuture().sync();
		} finally {
			// 10. 优雅地关闭两个线程池
			bossGroup.shutdownGracefully();
			workerGroup.shutdownGracefully();
		}
	}

	private static class ChatNettyHandler extends SimpleChannelInboundHandler<ByteBuf> {

		@Override
		public void channelActive(ChannelHandlerContext ctx) throws Exception {
			System.out.println("one conn active: " + ctx.channel());
			// channel是在ServerBootstrapAcceptor中放到EventLoopGroup中的
			ChatHolder.join((SocketChannel) ctx.channel());
		}

		@Override
		protected void channelRead0(ChannelHandlerContext ctx, ByteBuf byteBuf) throws Exception {
			byte[] bytes = new byte[byteBuf.readableBytes()];
			byteBuf.readBytes(bytes);
			String content = new String(bytes, StandardCharsets.UTF_8);
			System.out.println(content);

			if (content.equals("quit\r\n")) {
				ctx.channel().close();
			} else {
				ChatHolder.propagate((SocketChannel) ctx.channel(), content);
			}
		}

		@Override
		public void channelInactive(ChannelHandlerContext ctx) throws Exception {
			System.out.println("one conn inactive: " + ctx.channel());
			ChatHolder.quit((SocketChannel) ctx.channel());
		}
	}

	private static class ChatHolder {
		static final Map<SocketChannel, String> USER_MAP = new ConcurrentHashMap<>();

		/**
		 * 加入群聊
		 * 
		 * @param socketChannel
		 */
		static void join(SocketChannel socketChannel) {
			// 有人加入就给他分配一个id
			String userId = "用户" + ThreadLocalRandom.current().nextInt(Integer.MAX_VALUE);
			send(socketChannel, "您的id为：" + userId + "\n\r");

			for (SocketChannel channel : USER_MAP.keySet()) {
				send(channel, userId + " 加入了群聊" + "\n\r");
			}

			// 将当前用户加入到map中
			USER_MAP.put(socketChannel, userId);
		}

		/**
		 * 退出群聊
		 * 
		 * @param socketChannel
		 */
		static void quit(SocketChannel socketChannel) {
			String userId = USER_MAP.get(socketChannel);
			send(socketChannel, "您退出了群聊" + "\n\r");
			USER_MAP.remove(socketChannel);

			for (SocketChannel channel : USER_MAP.keySet()) {
				if (channel != socketChannel) {
					send(channel, userId + " 退出了群聊" + "\n\r");
				}
			}
		}

		/**
		 * 扩散说话的内容
		 * 
		 * @param socketChannel
		 * @param content
		 */
		public static void propagate(SocketChannel socketChannel, String content) {
			String userId = USER_MAP.get(socketChannel);
			for (SocketChannel channel : USER_MAP.keySet()) {
				if (channel != socketChannel) {
					send(channel, userId + ": " + content);
				}
			}
		}

		/**
		 * 发送消息
		 * 
		 * @param socketChannel
		 * @param msg
		 */
		static void send(SocketChannel socketChannel, String msg) {
			try {
				ByteBufAllocator allocator = ByteBufAllocator.DEFAULT;
				ByteBuf writeBuffer = allocator.buffer(msg.getBytes().length);
				writeBuffer.writeCharSequence(msg, Charset.defaultCharset());
				socketChannel.writeAndFlush(writeBuffer);
			} catch (Exception e) {
				e.printStackTrace();
			}
		}
	}
}
```

可以发现，只需要改动设置子 Handler 里面的那一个地方就可以了，其它地方完全不需要修改，非常便捷。



 #### 模拟群聊

![图片描述](https://img1.sycdn.imooc.com/5f0d60fa0001e30018860803.png)
最后一行出现乱码，这个不用管，它是 XSHELL 本身发出的心跳，我们的代码中并没有处理 XSHELL 的心跳，所以显示了一些奇怪的字符。



 #### 问题

通过简单群聊系统，相信你一定被 Netty 的魅力所折服，然而，你可能会发现一个问题，上面的简单群聊系统只能支持所有人一起聊天，那么，我提出一个问题，你可以尝试完成，如何将上述简单群聊系统修改为真正的类似微信的聊天系统？







<div style="page-break-after:always;"></div>

 ## 08 Netty的核心组件有哪些


![img](https://img4.sycdn.imooc.com/5f05952f000195a006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)书是人类进步的阶梯。——高尔基![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节我们一起学习了 Netty 编码的十步曲，通过上一节的学习，相信大家一定可以写出十分优雅的 Netty 代码了。

不过，Netty 之所以这么好用，离不开它的核心组件，我归纳了一下，大概有十种，我们暂且称之为 “十大核心组件”，其中，一部分是上一节中我们见过的，还有一部分是幕后的英雄，有了这些幕后英雄的默默支持，才有了这么健壮优雅的 Netty。

所以，本节，我们将一起学习 Netty 的十大核心组件，从宏观上理解 Netty 的架构设计。

好了，让我们进入今天的学习吧。



 ### 十大核心组件



 #### 1. Bootstrap 与 ServerBootstrap

Bootstrap 与 ServerBootstrap 是 Netty 程序的引导类，主要用于配置各种参数，并启动整个 Netty 服务。它们俩都继承自 AbstractBootstrap 抽象类，不同的是，Bootstrap 用于客户端引导，而 ServerBootstrap 用于服务端引导。

![图片描述](https://img1.sycdn.imooc.com/5f0d64b30001a08c03850287.png)
相对于 Bootstrap，ServerBootstrap 多了一个维度，用于处理 Accept 事件，所以它的很多方法都会多一份 `childXxx()`，比如，`childHandler()`、`childOption()` 等，但是，没有 `childChannel()` 这个方法哦 ^^，因为子 Channel 是通过 ServerSocketChannel 创建出来的，跟踪源码会发现 ServerSocketChannel 读取到消息的时候会把这个消息转换成连接，即 SocketChannel，具体的源码分析我们后面再详细介绍。



 #### 2. EventLoopGroup

EventLoopGroup 可以理解为一个线程池，对于服务端程序，我们一般会绑定两个线程池，一个用于处理 Accept 事件，一个用于处理读写事件。

我们以 NioEventLoopGroup 这个实现类为例看看它的继承体系：

![图片描述](https://img1.sycdn.imooc.com/5f0d64a50001247d05420787.png)

细心的同学会发现，上面四个接口好熟悉：

- Iterable，迭代器的接口，说穿 EventLoopGroup 是一个容器，可以通过迭代的方式查看里面的元素。
- Executor，线程池的顶级接口，包含一个 execute () 方法，用于提交任务到线程池中。
- ExecutorService，扩展自 Executor 接口，提供了通过 submit () 方法提交任务的方式，并增加了 shutdown () 等其它方法。
- ScheduledExecutorService，扩展自 ExecutorService，增加了定时任务执行相关的方法。

其中，后面三个都是线程池中的接口，位于著名的 `java.util.concurrent` 包下面。

下面的几个接口或者类自然就属于 Netty 了：

- EventExecutorGroup，扩展自 ScheduledExecutorService，并增加了两大功能，一是提供了 next () 方法用于获取一个 EventExecutor，二是管理这些 EventExecutor 的生命周期。

- EventLoopGroup，扩展自 EventExecutorGroup，并增加或修改了两大功能，一是提供了 next () 方法用于获取一个 EventLoop，二是提供了注册 Channel 到事件轮询器中。

- MultithreadEventLoopGroup，抽象类，EventLoopGroup 的所有实现类都继承自这个类，可以看作是一种模板，从名字也可以看出来它里面包含多个线程来处理任务。

- NioEventLoopGroup，具体实现类，使用 NIO 形式（多路复用中的 select）工作的 EventLoopGroup。更换前缀就可以得到不同的实现类，比如 EpollEventLoopGroup 专门用于 Linux 平台，KQueueEventLoopGroup 专门用于 MacOS/BSD 平台。

  > select/epoll/kqueue，它们是实现 IO 多路复用的不同形式，select 支持的平台比较广泛，epoll 和 kqueue 比 select 更高效，epoll 只支持 linux，kqueue 只支持 BSD 平台，其中 MacOS 衍生自 BSD，所以 kqueue 也支持 MacOS。Netty 专门为两个平台做了的不同实现，也是对性能的极致追求，而且，我们服务端通常都是运行在 Linux 系统上，所以在上线的时候完全可以使用 EpollEventLoopGroup 来代替 NioEventLoopGroup。

有的同学可能会说，为什么 Netty 要把继承体系搞这么复杂，这么深呢？其实，通过上面的分析也可以得出一些蛛丝马迹，每一个接口都是在上一层接口的基础上扩展一些新的功能，属于每一个接口自己的功能都特别纯粹，并不是很多，这也是单一职责原则的具体使用，使用多个单一的接口比使用一个总接口要好。



 #### 3. EventLoop

EventLoop 可以理解为是 EventLoopGroup 中的工作线程，类似于 ThreadPoolExecutor 中的 Worker，但是，实际上，它并不是一个线程，它里面包含了一个线程，控制着这个线程的生命周期。

让我们以 NioEventLoop 为例看看它的继承体系：

![图片描述](https://img1.sycdn.imooc.com/5f0d646c0001adfe08050987.png)
可以看到这个继承体系比 EventLoopGroup 还复杂，不用过于纠结，这里，我们介绍几个关键的接口或类：

- EventExecutor，扩展自 EventLoopGroup，主要增加了判断一个线程是不是在 EventLoop 中的方法。
- OrderedEventExecutor，扩展自 EventExecutor，这是一个标记接口，标志着里面的任务都是按顺序执行的。
- EventLoop，扩展自 EventLoopGroup，它将为已注册进来的 Channel 处理所有的 IO 事件，另外，它还扩展自 OrderedEventExecutor 接口，说明里面的任务是按顺序执行的。
- SingleThreadEventLoop，抽象类，EventLoop 的所有实现类都继承自这个类，可以看作是一种模板，从名字也可以看出来它是使用单线程处理的。
- NioEventLoop，具体实现类，绑定到一个 Selector 上，同时可以注册多个 Channel 到 Selector 上，同时，它继承自 SingleThreadEventLoop，也就说明了一个 Selector 对应一个线程。同样地，更换前缀就可以得到不同的实现，比如 EpollEventLoop、KQueueEventLoop。

![图片描述](https://img1.sycdn.imooc.com/5f0d64590001e71110300611.png)



 #### 4. ByteBuf

ByteBuf，咋一看名字跟 ByteBuffer 还挺像，还记得 ByteBuffer 吗？没错，既然 Java NIO 中已经定义处理字节的缓冲区，为什么 Netty 还要另辟蹊径，再搞一个 ByteBuf 出来呢？

让我们先来回忆一下 Buffer 的基本内容：

- 它包含三个主要属性：position、limit、capacity。
- 写模式，position 从 0 开始，表示下一个可写的位置，limit 等于 capacity。
- 读模式，position 重置为 0，表示下一个可读的位置，limit 等于切换之前 position 的位置，capacity 不变。
- 通过 flip () 方法切换为读模式
- 通过 clean () 方法或 compact () 方法清除（部分）数据
- 通过 rewind () 方法重新读取或重新写入数据
- 通过 buf.put () 或者 channel.read (buf) 方法写入数据
- 通过 buf.read () 或者 channel.write (buf) 方法读取数据

上面的内容你还记得哪些呢？是不是很复杂？Java NIO 自带的 Buffer 操作起来特别繁琐，一会儿切换成写模式，一会儿切换在读模式，position 的位置在哪，是个正常人都会被绕进去。Netty 的作者也是一样，他也被绕进去了，索性，他就创建了一个新的 ByteBuf 来处理缓冲区数据。

那么 Netty 是怎么实现的呢？让我们一起来看看吧。

ByteBuf 声明了两个指针：一个读指针 `readIndex` 用于读取数据，一个写指针 `writeIndex` 用于写数据。

![图片描述](https://img1.sycdn.imooc.com/5f0d644700016c2e10270217.png)
使用读写指针分离带来的好处是明显的，彻底解决了读写模式切换来切换去、position 指针变来变去的问题。那么，新的 **ByteBuf 都有哪些特性呢？**

首先，让我们看看 ByteBuf 的分类，常见的分类方式有三种：

- Pooled 和 Unpooled，池化和非池化

  池化，即初始化时分配好一块内存作为内存池，每次创建 ByteBuf 时从这个内存池中分配一块连续的内存给这个 ByteBuf 使用，待这个 ByteBuf 使用完了之后再放回内存池中，供后续的 ByteBuf 使用。利用池化技术，可以减少虚拟机频繁的内存回收带来的性能开销及资源消耗。池化技术在很多场景中都有使用到，比如，数据库连接池、线程池等，它们都有一些共同的特点，就是创建对象比较耗费资源。

  池化技术在生活中也随处可见，比如饭店的大厅、快递公司的网点。我们以饭店的大厅为例，它就像一块内存，来一个客人就给他分配一个桌子，如果没有大厅怎么办呢？来一个客人，饭店老板先去买个空间，也可能买块地建个空间，然后分配给这个客人，这个客人用完了再把这个空间卖掉，等下一个客人来的时候再重复以上步骤，想像一下都很美 ^^，所以，老板直接买下一个大厅，来一个客人给他分配一个桌子，用完回收，完全自己管理这片空间，省时又省力。

  非池化，即完全利用 JVM 本身的内存管理能力来管理对象的生命周期，即我们平时开发使用的模式，对象的内存分配完全交给 JVM 来管理，我们不用管对象内存的管理和回收。

- Heap 和 Direct，堆内存和直接内存

  堆内存，比较好理解，即 JVM 本身的堆内存。

  直接内存，独立于 JVM 内存之外的内存空间，直接向操作系统申请一块内存。

- Safe 和 Unsafe，安全和非安全

  Unsafe，底层使用 Java 本身的 Unsafe 来操作底层的数据结构，即直接利用对象在内存中的指针来操作对象，所以，比较危险。

基于以上三个维度，而且是完全不相干的三个维度，就形成了 `2 * 2 * 2 = 8` 种完全不一样的 ByteBuf，即 PooledHeapByteBuf、PooledUnsafeHeapByteBuf、PooledDirectByteBuf、PooledUnsafeDirectByteBuf、UnpooledHeapByteBuf、UnpooledUnsafeHeapByteBuf、UnpooledDirectByteBuf、UnpooledUnsafeDirectByteBuf。
![图片描述](https://img1.sycdn.imooc.com/5f0d641a0001bf4113780487.png)
好了，上面介绍了 ByteBuf 的分类，你一定会说，这么多 ByteBuf，到底用哪个呢？怎么使用呢？

其实，Netty 都已经为我们想好了，关于上面八种 ByteBuf，我们并不需要显式地去调用它们的构造方法，而是使用一种叫作 `ByteBufAllocator` 分配器的东西来为我们创建 ByteBuf 对象，而这种分配器又有四种不同的类型：

- PooledByteBufAllocator，使用池化技术，内部会根据平台特性自行决定使用哪种 ByteBuf
- UnpooledByteBufAllocator，不使用池化技术，内部会根据平台特性自行决定使用哪种 ByteBuf
- PreferHeapByteBufAllocator，更偏向于使用堆内存，即除了显式地指明了使用直接内存的方法都使用堆内存
- PreferDirectByteBufAllocator，更偏向于使用直接内存，即除了显式地指明了使用堆内存的方法都使用直接内存
  ![图片描述](https://img1.sycdn.imooc.com/5f0d64060001930110400287.png)
  看到这里，你可能已经想骂粗口了，别急，淡定，八种 ByteBuf，四种 Allocator，对于拥有选择恐惧症的我该怎么办？

Netty 真的为你想好了，只需要简单地调用如下几行代码，Netty 就可以帮你创建最适合当前平台的 ByteBuf：

```java
ByteBufAllocator allocator = ByteBufAllocator.DEFAULT;
ByteBuf buffer = allocator.buffer(length);
buffer.writeXxx(xxx);
```

是不是很贴心呢？

默认地，Netty 将`最大努力`地使用池化、Unsafe、直接内存的方式为你创建 ByteBuf，为什么说是`最大努力`呢？因为在有些平台下某种特性支持地不是很好，所以 Netty 默认不会开启，比如 Android 平台下不会使用 Unsafe。

```java
// io.netty.util.internal.PlatformDependent#unsafeUnavailabilityCause0
if (isAndroid()) {
    logger.debug("sun.misc.Unsafe: unavailable (Android)");
    return new UnsupportedOperationException("sun.misc.Unsafe: unavailable (Android)");
}
```



 #### 5. Channel

上面我们介绍了 ByteBuf，它是 Netty 在 Java NIO 的 Buffer 之上创造的一个新的缓冲区，比 Java 自带的语义清晰很多，也好用很多。那么，Channel 是不是也是凌驾于 Java NIO 的 Channel 之上的一个新事物呢？

答案是肯定的，Netty 的 Channel 是对 Java 原生 Channel 的进一步封装，不仅封装了原生 Channel 操作的复杂性，还提供了一些很酷且实用的功能，比如：

- 可以获取当前连接的状态及配置参数
- 通过 ChannelPipeline 来处理 IO 事件
- 在 Netty 中的所有 IO 操作都是异步的
- 可继承的 Channel 体系

与原生 Channel 对应，Netty 的 Channel 都有相应的包装类，并且还扩展了其它协议的实现：

- DatagramChannel：UDP 协议的支持
- SocketChannel：TCP 协议的支持
- ServerSocketChannel：TCP 协议的支持
- SctpChannel：SCTP 协议的支持
- SctpServerChannel：SCTP 协议的支持
- RxtxChannel：RXTX 协议的支持，已废弃
- UdtChannel：UDT 协议的支持，已废弃

可以看到，对各种协议的支持在 Netty 中很容易实现，且它很擅长。

Netty 不仅支持这些协议的 NIO 通用平台实现，还支持特定平台的实现，而且只需要简单地更换前缀就可以达到对不同平台的支持，比如，ServerSocketChannel 的通用实现为 NioServerSocketChannel，在 Linux 下完全可以更换成 EpollServerSocketChannel，代码只需要做很小的修改，就可以达到平台级的性能提升。

![图片描述](https://img1.sycdn.imooc.com/5f0d619500013e6b11270187.png)



 #### 6. ChannelHandler

ChannelHandler 是核心业务处理接口，用于处理或拦截 IO 事件，并将其转发到 ChannelPipeline 中的下一个 ChannelHandler，运用的是责任链设计模式。

ChannelHandler 分为入站和出站两种：ChannelInboundHandler 和 ChannelOutboundHandler，不过一般不建议直接实现这两个接口，而是它们的抽象类：

- SimpleChannelInboundHandler：处理入站事件，不建议直接使用 ChannelInboundHandlerAdapter
- ChannelOutboundHandlerAdapter：处理出站事件
- ChannelDuplexHandler：双向的

其中，SimpleChannelInboundHandler 相比于 ChannelInboundHandlerAdapter 优势更明显，它可以帮我们做资源的自动释放等操作。



 #### 7. ChannelHandlerContext

ChannelHandlerContext 保存着 Channel 的上下文，同时关联着一个 ChannelHandler，通过 ChannelHandlerContext，ChannelHandler 方能与 ChannelPipeline 或者其它 ChannelHandler 进行交互，ChannelHandlerContext 是它们之间的纽带。



 #### 8. ChannelFuture

我们上面说了 Netty 中所有的 IO 操作都是异步的，既然是异步的就会返回在将来用来获取返回值的对象，也就是 Future，在 Netty 中，这个 Future 我们称之为 ChannelFuture，因为是跟 Channel 的 IO 事件相关联的，当然，Netty 中还有其它各种各样的 Future。

通过 ChannelFuture，可以查看 IO 操作是否已完成、是否成功、是否已取消等等。



 #### 9. ChannelPipeline

ChannelPipeline 是 ChannelHandler 的集合，它负责处理和拦截入站和出站的事件和操作，每个 Channel 都有一个 ChannelPipeline 与之对应，会自动创建。

更确切地说，ChannelPipeline 中存储的是 ChannelHandlerContext 链，通过这个链把 ChannelHandler 连接起来，让我们仔细研究一下几者之间的关系：

- 一个 Channel 对应一个 ChannelPipeline
- 一个 ChannelPipeline 包含一条双向的 ChannelHandlerContext 链
- 一个 ChannelHandlerContext 中包含一个 ChannelHandler
- 一个 Channel 会绑定到一个 EventLoop 上
- 一个 NioEventLoop 维护了一个 Selector（使用的是 Java 原生的 Selector）
- 一个 NioEventLoop 相当于一个线程

通过以上分析，可以得出，ChannelPipeline、ChannelHandlerContext 都是线程安全的，因为同一个 Channel 的事件都会在一个线程中处理完毕（假设用户不自己启动线程）。但是，ChannelHandler 却不一定，ChannelHandler 类似于 Spring MVC 中的 Service 层，专门处理业务逻辑的地方，一个 ChannelHandler 实例可以供多个 Channel 使用，所以，不建议把有状态的变量放在 ChannelHandler 中，而是放在消息本身或者 ChannelHandlerContext 中。

好了，上面的关系已经描述清楚，让我们画个图直观地感受一下：

![图片描述](https://img1.sycdn.imooc.com/5f0d6180000114a212880566.png)



 #### 10. ChannelOption

ChannelOption 严格来说不算是一种组件，它保存了很多我们拿来即用的参数，使用这些参数能够让我们以类型安全地方式来配置 Channel，比如，我们前面使用过的 ChannelOption.SO_BACKLOG，Netty 还提供了很多这种类似的参数，使得我们能够以更精细地方式控制程序正确、正常、高性能地运行。



 ### 后记

本节，我们一起学习了 Netty 的十大核心组件，理解了这些组件的含义和使用方式，相信你一定能够从宏观上对 Netty 有一个更高的认识，这些组件看似散乱，其实内含逻辑，如果非要给它们归类的话，我认为可以分成以下四类：

1. 引导相关：Bootstrap 和 ServerBootstrap
2. 线程相关：EventLoopGroup、EventLoop（EventExecutorGroup、EventExecutor）
3. Buffer 相关：ByteBuf
4. Channel 相关：Channel、ChannelHandler、ChannelHandlerContext、ChannelFuture、ChannelPipeline、ChannelOption

其实，每一块甚至每一个类拿出来讲，都能讲很多内容，本节只是从宏观上认识这些组件，待后面分析源码的时候再来深入了解它们。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0d616c00013bc015351093.png)





<div style="page-break-after:always;"></div>

 ## 09 什么是Reactor模式


![img](https://img4.sycdn.imooc.com/5f0595390001f14206400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)如果说我比别人看得要远一点，那是因为我站在巨人的肩上。——牛顿![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节我们一起学习了 Netty 的十大核心组件，通过上一节的学习，相信你一定能从宏观上理解 Netty 的架构设计。

在上一节，学习 EventLoopGroup 的时候，我们说过服务端建议设置两个线程池，一个用于处理 Accept 事件，一个用于处理读写事件，不知道你还有没有印象呢？

本节，我们就来说说为什么需要两个线程池，也就是鼎鼎大名的 Reactor 模式。

好了，让我们进入今天的学习吧。



 ### 什么是 Reactor 模式？

关于 Reactor 模式的定义，让我们看看维基百科怎么说：

> The reactor design pattern is an event handling pattern for handling service requests delivered concurrently to a service handler by one or more inputs. The service handler then demultiplexes the incoming requests and dispatches them synchronously to the associated request handlers.

从这段定义中，我们能得出以下几个信息：

1. Reactor 模式是一种事件处理模式；
2. 用于处理服务请求，把它们并发地传递给一个服务处理器（service handler）；
3. 有一个或多个输入源（inputs）；
4. 服务处理器将这些请求以多路复用的方式分离（demultiplexes ），并把它们同步地分发到相关的请求处理器（request handlers）；

总结一下，Reactor 模式包含一个或多个输入源，一个 service handler，多个 request handler，service handler 是输入源和 request handler 之间的桥梁，用于分发输入的请求，我画了一个图来表示：

![图片描述](https://img1.sycdn.imooc.com/5f0d67e00001022910320325.png)
为了方便描述，本节，我们把 input 叫作事件，service handler 叫作事件分离器，request handler 叫作事件处理器。

我们举个形象的例子，稍微有点 Javascript 开发经验的同学，应该都写过类似下面的代码：

```javascript
txt.onblur(function() {
    if(!content) {
        alert("请您输入用户名");
    }
});
btn.onclick(function() {
    alert("登录成功");
});
```

没有过 Javascript 开发经验的同学也没关系，我稍微解释一下，比如登录页面，用户名输入框失去焦点时如果为空则提示 “请您输入用户名”，点击按钮的时候弹出对话框显示 “登录成功”，类似于下面这张图：
![图片描述](https://img1.sycdn.imooc.com/5f0d67b10001316204440279.png)
这就是典型的事件驱动模型，事件即网页上的各种事件，比如按钮点击事件、失去焦点事件、鼠标右击事件等等，事件处理器即我们编写的回调函数，即上面代码中括号中的 function，事件分离器即 Javascript 内部根据不同的事件分发到不同的回调的处理器。



 ### Reactor 的几种模式

上面的定义可能理解起来比较模糊，让我们再看看大神 Doug Lea 是怎么把 Reactor 模式带到 Java 中的。[1]



 #### 网络请求的处理过程

一般地，网络请求都要经过以下几个处理过程：

- Read request，读取请求
- Decode request，解码请求
- Process service，处理业务
- Encode reply，编码响应
  ![图片描述](https://img1.sycdn.imooc.com/5f0d67700001528f10320164.png)



 #### 传统的服务设计

基于以上处理过程，传统的服务是如何设计的呢？

![图片描述](https://img1.sycdn.imooc.com/5f0d674500015bde10290390.png)
每次来一个客户端都启动一个新的线程来处理，每一个 handler 都在它自己的线程中。是不是很像我们前面介绍 BIO 的模型？没错，它们是相通的。

使用这种服务设计自然有它的优点：

1. 编码简单；
2. 每一个 handler 都在自己的线程中，不存在线程切换的问题，不需要考虑线程安全的问题；

但是，随着服务请求量越来越大，启动的线程数量会越来越多，最后，会导致服务端的线程无限增多，然而，其实大部分的线程可能都处于 IO 阻塞状态，并没有使用到 CPU，无法充分利用 CPU。

那么，怎么改进呢？

采用基于事件驱动的设计，当有事件触发时，才调用相应的处理器来处理事件。



 #### Reactor 单线程模式

Reactor 单线程模式应运而生，使用一个线程就可以处理大量的事件。
![图片描述](https://img1.sycdn.imooc.com/5f0d66ea0001afa310310381.png)
Reactor 单线程模式，就像一个饭店只有老板一个人一样，既要负责接待客人，又要当厨师，又要当服务员，一个人干所有的事，效率势必非常低下。

在服务端，对于网络请求有三种不同的事件：Accept 事件、Read 事件、Write 事件，对应于上图中的 acceptor、read、send。

> Connect 事件属于客户端事件。
>
> 为什么 acceptor（Accept 事件处理器）是双向箭头，而 read 和 send 是单向箭头呢？因为服务端启动的时候是先注册 Accept 事件到 Reactor 上，当收到客户端连接时，也就是 Accept 事件时，才会注册 Read 和 Write 事件，所以 acceptor 是双向的，Reactor 不仅要向 acceptor 分发 Accept 事件，acceptor 也要向 Reactor 注册 Read 和 Write 事件。

一个 Reactor 就相当于一个事件分离器，而单线程模式下，所有客户端的所有事件都在一个线程中完成，这就出现了一个新的问题，如果哪个请求有阻塞，直接影响了所有请求的处理速度，所以，自然而然就进化出了 Reactor 的多线程模式。

> 早期都是单核 CPU，一个请求阻塞会影响所有请求，注意，是阻塞，而不是处理缓慢，处理缓慢是有大量的计算，这时候即使启动多个线程也无法提高其它请求处理的速度。



 #### Reactor 多线程模式

Reactor 多线程模式，还是把 IO 事件放在 Reactor 线程中来处理，同时，把业务处理逻辑放到单独的线程池中来处理，这个线程池我们称为工作线程池（Worker Thread Pool）或者业务线程池。![图片描述](https://img1.sycdn.imooc.com/5f0d66bf00010b0110310681.png)
此时，如果业务处理逻辑中有 IO 阻塞，则不会影响其它请求的处理，能很大程度提高系统的并发量。

Reactor 多线程模式，就像饭店中老板只负责主要事务，比如，接待客人、接收客人的下单请求等，具体的事务交给服务员去处理。

但是，这种模式还不够完美，一个客户端连接过程需要三次握手，是一个比较耗时的操作，将 Accept 事件和 Read 事件与 Write 事件放在一个 Reactor 中来处理，明显降低了 Read 和 Write 事件的响应速度。而且，一个 Reactor 只有一个线程，也无法利用多核 CPU 的性能提升。因此，又自然而然的出现了 Reactor 主从模式。



 #### Reactor 主从模式

Reactor 主从模式把 Accept 事件的处理单独拿出来放到主 Reactor 中来处理，把 Read 和 Write 事件放到子 Reactor 中来处理，而且，像这样的子 Reactor 我们可以启动多个，充分利用多核 CPU 的资源。

![图片描述](https://img1.sycdn.imooc.com/5f0d66ab0001709f10330682.png)
Reactor 主从模式，就像饭店中的老板只负责客人接待这一件事，其它事务全部交给服务员来处理，而且服务员也可以按区域划分，比如 1 号服务员负责 1 到 5 号包厢，2 号服务员负责 6 到 10 号包厢，极大地提高了效率。

在 Reactor 主从模式中，我们依然把业务逻辑的处理放到业务线程池中来处理，但是，既然子 Reactor 本身就可以启动多个，所以，我们直接让子 Reactor 池化，利用子 Reactor 本身的线程来处理业务逻辑，可不可以呢？



 #### 变异的 Reactor 模式

基于主从模式可以有很多种变异的模式，比如使用子 Reactor 线程池来处理业务逻辑。

![图片描述](https://img1.sycdn.imooc.com/5f0d65aa00019eb110320529.png)
正常情况下，在 Netty 中，我们也是这么使用的，当然，依据不同的业务场景也可以有不同的变异。

如果说，正常的 Reactor 主从模式下，一批服务员负责不同包厢的下单请求（多个子 Reactor），另外一批服务员负责包厢的其它事务，比如上菜、端茶、倒水（业务线程池）。那么，变异的 Reactor 主从模式下，就是一个服务员负责几个包厢的所有事务，不管下单请求，还是上菜、端茶、倒水，另一个服务员再负责另几个包厢的所有事务，海底捞貌似就是这种变异的 Reactor 模式。

好了，Reactor 的几种模式介绍完了，那么，在 Netty 中怎么使用以上几种模式呢？



 ### Netty 中使用 Reactor 的不同模式



 #### Reactor 单线程模式的使用

Reactor 单线程模式，只有一个 Reactor，也就是一个线程处理所有事务，所以，在 Netty 中，只需要声明一个 EventLoopGroup 就可以了。

```java
EventLoopGroup bossGroup = new NioEventLoopGroup(1);
ServerBootstrap serverBootstrap = new ServerBootstrap();
serverBootstrap.group(bossGroup); 
```



 #### Reactor 多线程模式的使用

Reactor 多线程模式，实际上还是只有一个 Reactor，但是这个 Reactor 只负责处理 IO 事件，而不负责处理业务逻辑，所以，在 Netty 中，需要将业务逻辑的处理，也就是 Handler，放到另外的线程池中。

```java
EventLoopGroup bossGroup = new NioEventLoopGroup(1); // 一个Reactor
ServerBootstrap serverBootstrap = new ServerBootstrap();
serverBootstrap.group(bossGroup); 
// Handler使用线程池处理
```



 #### Reactor 主从模式的使用

Reactor 主从模式，有一个主 Reactor 和多个子 Reactor，但是，业务逻辑的处理还是在线程池中，所以，在 Netty 中，需要声明两个不同的 EventLoopGroup，Handler 依然使用线程池处理。

```java
EventLoopGroup bossGroup = new NioEventLoopGroup(1); // 一个主Reactor
EventLoopGroup workerGroup = new NioEventLoopGroup(); // 多个子Reactor
ServerBootstrap serverBootstrap = new ServerBootstrap();
serverBootstrap.group(bossGroup, workerGroup); 
// Handler使用线程池处理
```



 #### Reactor 变异主从模式的使用

Reactor 变异主从模式，业务线程池和子 Reactor 池合并为一，所以，在 Netty 中，Handler 放在子 Reactor 池中处理即可，默认情况，Netty 也是使用的这种模式。

```java
EventLoopGroup bossGroup = new NioEventLoopGroup(1); // 一个主Reactor
EventLoopGroup workerGroup = new NioEventLoopGroup(); // 多个子Reactor
ServerBootstrap serverBootstrap = new ServerBootstrap();
serverBootstrap.group(bossGroup, workerGroup); 
```

看了这几种模式的使用，你可能会有个疑问：为什么只能有一个主 Reactor 呢？启动多个主 Reactor 可不可以呢？

答案是，可以，但没必要，因为底层的 Accept 事件的处理依然要排队处理，具体可以查看源码 `sun.nio.ch.ServerSocketChannelImpl#accept()`:

```java
public SocketChannel accept() throws IOException {
        Object var1 = this.lock;
        synchronized(this.lock) {
            // 省略具体代码
        }
}
```

可以看到，accept () 方法中使用了一个 synchronized 锁来控制同时只能处理一个客户端的连接请求，使用一个线程来处理，相应地，还能减少线程的切换，提高一定的性能，有兴趣的同学，可以去查查 synchronized 的偏向锁、轻量级锁、重量级锁相关的内容。



 ### Reactor 模式的优点和缺点

好了，Reactor 的几种模式介绍完了，但是，Reactor 并不是一剂万能药，所以我们有必要了解它的的优点和缺点，综合对比，我们才能决定要不要使用它。

首先，我们来看看它的优点，也是 Reactor 的主要卖点：

1. 能够解耦模块，将 IO 操作与业务逻辑解耦；
2. 能够提高并发量，充分利用 CPU 资源；
3. 可扩展性好，简单地增加子 Reactor 的数量就能很好地扩展；
4. 可复用性好，Reactor 框架本身不与具体的业务逻辑挂钩，复用性好；

等等。

然而 ，同样地，它也有一些缺点

1. 相比于传统的简单模式，Reactor 增加了一定复杂度，增加了学习成本、试错成本和调试成本；
2. 需要编程语言支持事件分离器，比如 Java 中的 Selector，如果自己实现不现实；
3. 多个客户端共用同一个 Reactor，如果有文件传输这种耗时的 IO 操作， 不适合使用 Reactor 模式；



 ### 后记

本节，我们一起学习了 Reactor 的几种模式以及它们在 Netty 中的使用，总结下来，我们在 Netty 中，一般使用变异的主从模式就够了，除非有比较耗时的 IO 阻塞，我们才需要使用主从模式那种更复杂的情形。Netty 本身默认使用的也是这种变异的主从模式。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0d64e50001801112681011.png)



 ### 参考

1. Doug Lea 大神关于 Reactor 在 Java NIO 中运用的讲述：http://gee.cs.oswego.edu/dl/cpjslides/nio.pdf





<div style="page-break-after:always;"></div>

 ## 10 如何解决粘包半包问题


![img](https://img3.sycdn.imooc.com/5f0595430001af3b06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)只有在那崎岖的小路上不畏艰险奋勇攀登的人,才有希望达到光辉的顶点。——马克思![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了 Netty 中支持的线程模型相关的知识，今天我们再来学习一对跟 TCP 相关的底层概念 —— 粘包 / 半包。

在网络编程中，我们经常听到粘包 / 半包这对名词，它们是什么意思呢？Netty 又是怎么处理的呢？

今天我们就一起来学习吧。



 ### 何为粘包 / 半包？

比如，我们发送两条消息：ABC 和 DEF，那么对方收到的就一定是 ABC 和 DEF 吗？

不一定，对方可能一次就把两条消息接收完了，即 ABCDEF；也可能分成了好多次，比如 AB、CD 和 EF。

![图片描述](https://img1.sycdn.imooc.com/5f0d71740001f0f410360227.png)
对方一次性接收了多条消息这种现象，我们就称之为**粘包现象**。

对方多次接收了不完整消息这种现象，我们就称之为**半包现象**。



 ### 为什么会出现粘包 / 半包？



 #### 粘包的原因

我们知道，TCP 发送消息的时候是有缓冲区的，当**消息的内容远小于缓冲区**的时候，这条消息不会立马发送出去，而是跟其它的消息合并之后再发送出去，这样合并发送是明显能够提高效率的。

这就好比寄快递的时候一样，不可能你寄一个快递就给你派送一样，而是先放到仓库里，等够一车了再统一装车拉走。

![图片描述](https://img1.sycdn.imooc.com/5f0d71690001350a10310305.png)
但是，**对方接收到的消息就是一个粘包**，无法有效区分出来到底是几条消息。

当然，接收消息也是会通过 TCP 的缓冲区的，**如果接收方读取得不及时，也有可能出现粘包现象**。

比如，缓冲区里面的 ABC 还没来得及读取，又来了一条消息 DEF，这时候两条消息就合并在一起了，也就出现了粘包了。

总结起来，出现粘包的原因无非两种：

- 发送方发送的消息 < 缓冲区大小
- 接收方读取消息不及时



 #### 半包的原因

类比粘包，如果发送的消息太大，已经**超过了缓冲区的大小**，这时候就**必须拆分发送**，也就**形成了半包现象**。

这就好比你发的快递太多了，一车拉不完，要分成好几车拉走一样（似乎不太常见☺）。

![图片描述](https://img1.sycdn.imooc.com/5f0d715d0001eee010270263.png)
还有一种情况，网络协议各层是有最大负载的，所以，对应到各种协议它们是有最大发送数据的限制的，这种可以发送的最大数据称作 MTU（Maximum Transmission Unit，最大传输单元）。

![图片描述](https://img1.sycdn.imooc.com/5f0d71530001d08c05290154.png)
所以一次发送的数据如果**超过了协议的 MTU**，也要**进行拆分发送**，也会**形成半包现象**。

总结起来，出现半包的原因有两种：

- 发送方发送的消息 > 缓冲区的大小
- 发送方发送的消息 > 协议的 MTU



 #### 本质原因

发送消息的时候如果消息太小，先放到缓冲区里面放着，等数据够多了再一起发送；如果消息太大，则拆成多个消息分批发送。

那么，本质原因是缓冲区吗？

当然不是，缓冲区的存在是为了提高发送消息的效率。

**本质原因是：TCP 是流式协议，消息无边界。**

TCP 协议本身像水流一样，源源不断，完全不知道消息的边界在哪里。

> UDP 协议不会出现粘包 / 半包现象，它的消息是有明确边界的，不会像 TCP 一样出现粘包 / 半包现象。



 ### 怎么解决粘包 / 半包？

上面我们分析了出现粘包 / 半包现象的本质原因，所以我们只要能解决消息的边界是不是就可以解决粘包 / 半包问题了呢？

答案是肯定的。

所以，业界就衍生出了三种常用的解决粘包 / 半包问题的方法：**定长法、分割符法、长度 + 内容法**。



 #### 定长法

固定长度确定消息的边界，比如传输的消息分别为 ABC、D、EF。

那么，就找最长的那条消息，这里是 ABC，那就以 3 为固定长度，不足三位的补足三位。

![图片描述](https://img1.sycdn.imooc.com/5f0d714400011f2510310281.png)
所以，这种方式最大的缺点就是**浪费空间**，所以不推荐。



 #### 分割符法

使用固定的分割符分割消息，比如传输的消息分别为 ABC、DEFG、HI\n，假如使用 \n 作为分割符。

那么，就在消息的边界处加一个 \n 作为分割符，这样接收方拿到消息之后使用 \n 去分割消息即可。
![图片描述](https://img1.sycdn.imooc.com/5f0d71380001bbe110310283.png)
但是，这种方式的缺点是一是**分割符本身作为传输内容时要转义**，二是**要扫描消息的内容才能确定消息的边界在哪里**，所以也不是特别推荐。



 #### 长度 + 内容法

使用固定的字节数存储消息的长度，后面跟上消息的内容，读取消息的时候先读取长度，再一次性把消息的内容读取出来。

比如，传输的消息分别为 ABC、DEFG、HI。

那么，就在消息前面分别加上长度一起传输，后面再跟上内容，这样即使三条消息一起传输也可以分得清清楚楚。

![图片描述](https://img1.sycdn.imooc.com/5f0d712c0001afea10330289.png)
这种方式的缺点是**需要预先知道消息的最大长度**，但是跟这个缺点相比，优点太明显了，所以是我们推荐的方式。



 #### 其它方法

上面介绍了业界公认的三种处理粘包 / 半包的方法，那么，还有没有其它方法呢？

其实，可以说有，也可以说没有，万变不离其宗，这三种方法是基础。比如，使用 JSON 协议，可以通过查找匹配到的 `{`和`}` 的数量，来处理粘包 / 半包，说白了，也是一种分割符法，只不过不是基础版。



 #### 比较

下面是三种方法的整体比较：

| 方法          | 如何确定消息边界                   | 优点               | 缺点                                     | 推荐度     |
| :------------ | :--------------------------------- | :----------------- | :--------------------------------------- | :--------- |
| 定长法        | 使用固定长度分割消息               | 简单               | 空间浪费                                 | 不推荐     |
| 分割符法      | 使用固定分割符分割消息             | 简单               | 分割符本身需要转义，且需要扫描消息的内容 | 不特别推荐 |
| 长度 + 内容法 | 先获取消息的长度，再按长度读取内容 | 精确获取消息的内容 | 需要预先知道消息的最大长度               | 推荐       |



 ### Netty 是如何支持的？

Netty 是通过三组类来处理粘包 / 半包问题的，分别对应于上面提到的三种方式。

| 方法          | 编码                 | 解码                         |
| :------------ | :------------------- | :--------------------------- |
| 定长法        | 无                   | FixedLengthFrameDecoder      |
| 分割符法      | 无                   | DelimiterBasedFrameDecoder   |
| 长度 + 内容法 | LengthFieldPrepender | LengthFieldBasedFrameDecoder |

细心的同学会发现，定长法和分割符法没有编码对应的类，那是因为太简单了，Netty 都懒得实现了。

细心的同学可能又发现了，为什么解码类后面都是 *FrameDecoder 呢？那是因为被解码之后的消息又叫作一帧一帧的消息，所以称为 “帧解码器”。

那么，在 Netty 中如何使用它们呢？

其实，使用方法非常简单，只需要在 childHandler 中添加一个解码器就可以了，比如，以 FixedLengthFrameDecoder 为例：

```java
public final class EchoServer {

    static final int PORT = Integer.parseInt(System.getProperty("port", "8007"));

    public static void main(String[] args) throws Exception {
        // 省略其它代码
                    .childHandler(new ChannelInitializer<SocketChannel>() {
                        @Override
                        public void initChannel(SocketChannel ch) throws Exception {
                            ChannelPipeline p = ch.pipeline();
                            p.addLast(new LoggingHandler(LogLevel.INFO));
                            // 添加固定长度解码器，长度为3
                            p.addLast(new FixedLengthFrameDecoder(3));
                            p.addLast(echoServerHandler);
                        }
                    });
        // 省略其它代码
    }
}
```

启动服务器，使用 XSHELL 连接到服务器，并发送一串数字 “12345”，看看控制台的日志：

![图片描述](https://img1.sycdn.imooc.com/5f0d71190001eb9212550700.png)
可以看到，我们收到的消息为 “12345…”，后面的两个点一个是回车符 “\r”，一个是换行符 “\n”，然后看发送的消息，一个是 “123”，一个是 “45.”，还有一个点，不够三位，所以不会发送。

> 回车符的作用是输入完一行内容后光标回到当前行的开头却不向下移一行。
>
> 换行符的作用是跳到下一个新行，输入完一行内容后光标下移一行却不会移到这一行的开头。
>
> 不过，不同的操作系统表现上来说略有区别。

是不是超级简单呢？编解码器可以说是 Netty 的一大灵魂所在，也是 Netty 好用的地方。



 ### 后记

本节，我们一起学习了粘包 / 半包的相关知识，并详细介绍了三种处理粘包 / 半包的解决方法，最后，我们介绍了在 Netty 中如何使用这些解决方法。

本节介绍的粘包 / 半包的编解码器可以说是一次编解码器，主要是对协议本身的编解码，那么，是不是还有二次编解码器呢？答案是肯定的，且听下回分解。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f0d710a00015e0e12671153.png)





<div style="page-break-after:always;"></div>

 ## 11 Netty是如何支持常见的编解码方式的


![img](https://img2.sycdn.imooc.com/5f0595500001f65a06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)古之立大事者，不唯有超世之才，亦必有坚韧不拔之志。——苏轼![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了粘包 / 半包的相关知识以及解决方案，在上一节的最后，我们说粘包 / 半包的处理在 Netty 中是一次编解码，那么，二次编解码是什么呢？

所以，本节，我们就来谈谈 Netty 中常见的二次编解码。

好了，让我们进入今天的学习吧。



 ### 一次编解码和二次编解码

关于一次编解码和二次编解码，我想通过三个问题来叙述：

- 为什么需要一次编解码和二次编解码呢？
- 一次编解码和二次编解码可以合并吗？
- Netty 中如何快速地区分一次编解码和二次编解码呢？

首先，让我们先来看第一个问题：**为什么需要一次编解码和二次编解码呢？**

> 为了便于描述，我这里统一使用解码过程来描述，也就是收到请求处理的过程，编码的过程正好是反过来的。

上一节，我们说了，一次解码主要用于解决粘包 / 半包的问题，将缓冲区中的字节数组按照协议本身的格式进行分割，其实，分割后的数据还是字节数组。

那么，分割后的字节数组如何转换成 Java 里面我们可以直接使用的对象呢？

这就需要二次解码了，通过二次解码，可以将字节数组转换成 Java 对象，然后传入我们自定义的 Handler 里面进行业务逻辑的处理。

比如，上一节中，固定长度为 3 的一次编解码器的那个例子，如果我们需要在控制台打印出来输入的内容，那么就要经历以下几个过程：

1. 运用一次解码将 “12345\r\n” 的字节数组拆分成 “123” 和 “45\r” 的字节数组；
2. 运用二次解码将 “123” 和 “45\r” 转换成 Java 的 String 类型的对象；
3. 打印上面的 String 对象；
   ![图片描述](https://img1.sycdn.imooc.com/5f179e66000118ca10340264.png)

既然一次解码的时候都已经解出了对应的字节数组，何不顺势而为将其序列化成 Java 对象呢？

所以，**一次编解码和二次编解码可以合并吗？**

可以，但是不建议，这里主要运用了分层的思想，举个简单的例子，比如一次编解码我们采用的是 “长度 + 内容法”，二次编解码一开始使用的是 XML，后面换成了 JSON，其实一次编解码我们不需要修改，只需要修改二次编解码就可以了。但是，如果二者合为一体了，那我们在后面实现 JSON 编解码的时候又要重新实现一下 “长度 + 内容” 的一次编解码的过程。

分层的思想很重要，在 Java 中随处可见，比如，著名的 MVC 分层思想。

> 凡事都有特例，Netty 中也有一些编解码没有严格地按照分层的思想来实现，比如 MarshallingEncoder，但是，还是那句话，不建议合并，分层很重要。

最后，**Netty 中如何快速区分一次编解码和二次编解码呢？**

其实，贴心的 Netty 也想到了这个问题，所以她定义了下面两组类来分别表示一次编解码和二次编解码：

- 一次编解码：MessageToByteEncoder/ByteToMessageDecoder
- 二次编解码：MessageToMessageEncoder/MessageToMessageDecoder

正常来说，继承自 `MessageToByteEncoder` 或者 `ByteToMessageDecoder` 类的就是一次编解码，继承自 `MessageToMessageEncoder` 或者 `MessageToMessageDecoder` 类的就是二次编解码，其实，也很好理解，服务端接收请求的过程也是先拿到字节数组（在 Netty 中可以理解为 ByteBuf），然后通过 ByteToMessageDecoder 转换成协议格式的字节数组，再把协议格式的字节数组通过 MessageToMessageDecoder 转换成 Java 对象。
![图片描述](https://img1.sycdn.imooc.com/5f179e780001aa4710310142.png)

> 正如前文所说，凡事都有特例，比如 MarshallingEncoder，它继承自 MessageToByteEncoder，但是它把二次编码的工作也给干了。从 ByteToMessageDecoder 的名称也可以知道，字节数组直接转成 Java 对象也没有毛病，而且，MessageToMessageDecoder 也可以表示 Java 对象 A 转换成 Java 对象 B。不过，对于我们自己来写编解码，最好还是遵循分层的思想来实现。



 ### 常见的二次编解码方式

常见的二次编解码方式有很多，比如 XML、JSON、Java 序列化等，这些大家都比较熟悉，也比较常用，特别是 JSON，现在随着 RESTful 的流行，基本上基于 Web 开发都使用 JSON 来传输数据。还有一种序列化方式比较流行 ——Google 的 Protobuf，它主要运用在客户端与服务端需要长连接的场景，比如游戏行业，另外，Go 语言中也喜欢用 Protobuf，非常方便，而且高效。

> 二次编解码略等同于序列化方式，如果非要说区别，二次编解码的范围略大于序列化，序列化仅指把 Java 对象转换成字节数组的过程，而二次编解码实际上还包括 Java 对象之间的互相转换，也就是 Message to Message，比如 String 转 Integer，当然，一般不会为这么小的需求还写一个编解码器。

那么，Netty 中支持哪些二次编解码方式呢？

让我们打开 Netty 工程，找到 `netty-codec` 这个工程，展开目录：
![图片描述](https://img1.sycdn.imooc.com/5f179e8f0001c77704640379.png)

> 不要打开了 `netty-codec-xxx` 工程了，那些是对各种协议的支持，编解码的范围比较广，Netty 也是因为有了这么多协议、序列化方式的支持才变得这么好用。

可以看到，这个目录下有 base64、bytes、json、protobuf 等等，让我们一个一个来看一下：

- base64，大家都比较熟，BASE64 的支持，常用来把一个字符串转换成另一个字符串，简单加密
- bytes，ByteBuf 与 Java 本身的字节数组 `byte[]` 之间的互相转换
- compression，各种压缩协议的支持，比如 BZip、Snappy、Zlib 等
- json，通过 JSON 的形式来分割协议，不过，这里只有一个 JSON 一次解码器，因为 JSON 比较简单，只需要 toString () 就能拿到 JSON 文本了，所以，没有相应的二次编解码器，JSON 的优点很多，跨语言，结构清晰，易读
- marshalling，JBoss 的 Marshalling 的支持，也是比较有名的，不过这里的实现没有很好地分层，通过源码可以看到 MarshallingEncoder 继承自 MessageToByteEncoder，而 MarshallingDecoder 继承自 LengthFieldBasedFrameDecoder，缺少一种对称美
- protobuf，Google 的 Protobuf，因体积小，多语言支持而出名，而且不用写多少代码，只需要简单地定义好协议，使用工具一键生成 Java 对象，而且非常方便客户端与服务端不同语言的开发场景
- serialization，基于 Java 序列化做了一些优化，减小了序列化之后字节数组的大小，缺点很明显，只能 Java 中使用
- string，将 ByteBuf 转换成 Java 中的 String 对象，查看源码，其实很简单，只是调用 msg.toString (charset) 就完事了
- xml，XML 的支持，现在很少系统使用 XML 来传输数据了，缺点很明显，报文太大了

好了，我们这里拿三个比较常用的做下简单地对比：

| 序列化方式                            | 优点                                 | 缺点                                 |
| :------------------------------------ | :----------------------------------- | :----------------------------------- |
| serialization（优化过的 Java 序列化） | Java 原生，使用方便                  | 报文太大，不便于阅读，只能 Java 使用 |
| json                                  | 结构清晰，便于阅读，效率较高，跨语言 | 报文较大                             |
| protobuf                              | 使用方便，效率很高，报文很小，跨语言 | 不便于阅读                           |

其实，对于性能要求不是特别高的系统，我是非常推荐使用 JSON 这种方式的，毕竟写起来简单，看起来也简单。如果对于性能要求比较高，强烈推荐使用 Protobuf，性能非常高，而且也不用写多少代码，还能很好地定义客户端与服务端之间的协议，比如客户端使用 Javascript，服务端使用 Java，只要双方定好协议，各自使用工具生成对应的代码就可以直接使用了，再也不会为了协议的事儿扯皮了。



 ### 后记

本节，我们一起学习了 Netty 中常见的二次编解码，可以看到，Netty 对于大部分的编解码方式都是支持的，即使有少部分不支持，参考现有的代码，相信你也能很快地实现出来。

通过这两节关于 Netty 中编解码的学习，你会发现，其实，使用 Netty 编写服务端程序，只需要写一点 Handler 来处理自己的业务逻辑即可，其它事基本上 Netty 都为我们考虑到了，是不是很爽？



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f179e9c0001530116400828.png)




<div style="page-break-after:always;"></div>

 # 第 2 章 源码剖析——数据流向

 ## 12 Netty服务启动的时候都做了什么


![img](https://img1.sycdn.imooc.com/5f05955d00017c7e06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)一个人追求的目标越高，他的才力就发展得越快，对社会就越有益。——高尔基![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

前面的章节，我们一起学习了 NIO 以及 Netty 的基本知识，通过前面的学习，相信你对 Netty 编程有了一定的了解。

不过，学习一个框架，还是得从源码的角度来深刻领悟它，所以，从本节开始，我将从源码的角度来剖析 Netty。

源码剖析我准备分成两个部分来讲解，第一部分从数据流向的角度剖析源码，这部分源码具有整体性，关联性比较强；第二部分从 Netty 核心知识的角度剖析源码，这部分源码比较散乱，关联性不强，比如，FastThreadLocal，它比 JDK 自带的快在哪里，等等。中间我会穿插着讲一些源码调试的技巧，Java 方面的高阶知识等等。

本节，我们将从服务启动的过程来看看服务启动的时候 Netty 都做了些什么。

好了，让我们一起进入今天的学习吧。



 ### 源码剖析的原则

源码剖析有一个非常重要的原则 —— **针对性原则**，当然，这是我起的名字，意思为一定要有一个明确的目标，针对这个特定的目标死磕到底，跟这个目标无关的内容只要看懂大概逻辑就可以了，不能太深陷，否则容易迷失，特别是开源框架的源码，因为要考虑很多兼容性的问题，会有很多奇奇怪怪的代码，针对这些代码，我们可以略微一瞥，或者直接跳过，如果遇到你感兴趣的问题，但又是跟本次目标无关的，可以先记下来，等本次目标完成了，再把记录的问题归类，重新设置新的目标。

> 何为明确的目标？目标一定是可量化的，不能是含糊的，比如，我要看懂 Netty 所有源码，这就是含糊的目标，比如，我要看懂 Netty 服务启动相关的源码，那就相对明确一些，当然，初期能有这么个目标已经不错了。随着研究的深入，会不断发现新的问题，这些新的问题又可以成为新的目标，只有这样才能不断进步。

为了让我们的主题不跑偏，针对源码剖析的部分，每节开头，我将设置几个问题，大家可以带着这些问题来学习。



 ### 案例回顾

在正式学习今天的内容之前，我们先来回顾一下之前讲过的 EchoServer：

```java
public final class EchoServer {

    static final int PORT = Integer.parseInt(System.getProperty("port", "8007"));

    public static void main(String[] args) throws Exception {
        // 1. 声明线程池
        EventLoopGroup bossGroup = new NioEventLoopGroup(1);
        EventLoopGroup workerGroup = new NioEventLoopGroup();
        EchoServerHandler echoServerHandler = new EchoServerHandler();
        try {
            // 2. 服务端引导器
            ServerBootstrap serverBootstrap = new ServerBootstrap();
            // 3. 设置线程池
            serverBootstrap.group(bossGroup, workerGroup)
                    // 4. 设置ServerSocketChannel的类型
                    .channel(NioServerSocketChannel.class)
                    // 5. 设置参数
                    .option(ChannelOption.SO_BACKLOG, 100)
                    // 6. 设置ServerSocketChannel对应的Handler，只能设置一个
                    .handler(new LoggingHandler(LogLevel.INFO))
                    // 7. 设置SocketChannel对应的Handler
                    .childHandler(new ChannelInitializer<SocketChannel>() {
                        @Override
                        public void initChannel(SocketChannel ch) throws Exception {
                            ChannelPipeline p = ch.pipeline();
                            // 可以添加多个子Handler
                            p.addLast(new LoggingHandler(LogLevel.INFO));
                            p.addLast(echoServerHandler);
                        }
                    });

            // 8. 绑定端口
            ChannelFuture f = serverBootstrap.bind(PORT).sync();
            // 9. 等待服务端监听端口关闭，这里会阻塞主线程
            f.channel().closeFuture().sync();
        } finally {
            // 10. 优雅地关闭两个线程池
            bossGroup.shutdownGracefully();
            workerGroup.shutdownGracefully();
        }
    }
}
```

我们后面的源码分析也会基于这个案例来讲解，请记住这里的序号，我们后面还会使用到它们。



 ### 问题

通过前面使用案例的学习，我们知道，Netty 启动的时候主要是下面这行代码：

```java
ChannelFuture f = serverBootstrap.bind(PORT).sync();
```

这里主要有两个方法，一个是 bind ()，一个是 sync ()，sync () 属于 ChannelFuture 的范畴，今天暂不讨论，所以，今天我们只讨论 bind () 相关的问题：

1. Netty 的 Channel 跟 Java 原生的 Channel 是否有某种关系？
2. bind () 是否调用了 Java 底层的 Socket 相关的操作？
3. Netty 服务启动之后 ChannelPipeline 里面长什么样？

好了，让我们带着这几个问题探索吧。



 ### 服务启动过程剖析

让我们将断点打在 `ChannelFuture f = serverBootstrap.bind(PORT).sync();` 这行，以 Debug 模式启动程序，程序会停在此处，按 F7 或者 Shirft+F7 进入 bind () 方法内部：

```java
public ChannelFuture bind(int inetPort) {
    return bind(new InetSocketAddress(inetPort));
}
```

可以看到，我们只传进来了一个端口，而使用 `InetSocketAddress` 类构造了一个地址，默认的，会生成一个 `0.0.0.0:8007` 的地址。

接着往下走，会来到一个叫 `doBind()` 的方法，一般地，在开源框架中带 `doXxx` 开头的方法都是干正事的方法。

```java
private ChannelFuture doBind(final SocketAddress localAddress) {
    // key1，初始化并注册什么呢？
    final ChannelFuture regFuture = initAndRegister();
    final Channel channel = regFuture.channel();
    // 注册失败
    if (regFuture.cause() != null) {
        return regFuture;
    }
    // 已完成，上面未失败，所以这里是已完成且成功了
    if (regFuture.isDone()) {
        ChannelPromise promise = channel.newPromise();
        // key2，绑定什么呢？取决于initAndRegister()中异步执行的快慢，所以不一定到这里，这里可以打一个断点
        doBind0(regFuture, channel, localAddress, promise);
        return promise;
    } else {
        // 未完成
        final PendingRegistrationPromise promise = new PendingRegistrationPromise(channel);
        // 设置回调等待完成，回调内部处理注册的结果
        regFuture.addListener(new ChannelFutureListener() {
            @Override
            public void operationComplete(ChannelFuture future) throws Exception {
                Throwable cause = future.cause();
                // 注册失败
                if (cause != null) {
                    promise.setFailure(cause);
                } else {
                    // 注册成功
                    promise.registered();
                    // key2，绑定什么呢？取决于initAndRegister()中异步执行的快慢，所以不一定到这里，这里可以打一个断点
                    doBind0(regFuture, channel, localAddress, promise);
                }
            }
        });
        return promise;
    }
}
```

> 关键方法，我前面加上一个 `key` 表示。

`doBind()` 主要干了两件事：

- initAndRegister ()，初始化并注册什么呢？
- doBind0 ()，到底绑定的是什么？

让我们继续跟进到 `initAndRegister()` 方法中：

```java
final ChannelFuture initAndRegister() {
    Channel channel = null;
    try {
        // key1，通过ChannelFactory创建一个Channel，使用反射的形式创建一个Channel
        // 反射的类为我们第4步中设置的NioServerSocketChannel.class
        channel = channelFactory.newChannel();
        // key2，初始化Channel，干了些什么？
        init(channel);
    } catch (Throwable t) {
        // 异常处理，可以不看
        if (channel != null) {
            channel.unsafe().closeForcibly();
            return new DefaultChannelPromise(channel, GlobalEventExecutor.INSTANCE).setFailure(t);
        }
        return new DefaultChannelPromise(new FailedChannel(), GlobalEventExecutor.INSTANCE).setFailure(t);
    }
    // key3，注册Channel到哪里？这里有个group()，难道是EventLoopGroup？
    ChannelFuture regFuture = config().group().register(channel);
    // 失败了，关闭Channel
    if (regFuture.cause() != null) {
        if (channel.isRegistered()) {
            channel.close();
        } else {
            channel.unsafe().closeForcibly();
        }
    }
    
    return regFuture;
}
```

`initAndRegister` 主要干了三个事：

- channelFactory.newChannel ()，通过反射的形式创建 Channel，而且是无参构造方法，new 的时候做了哪些事儿？
- `init(channel)`，初始化 Channel 的什么？
- `register(channel)`，注册 Channel 到哪里？

因为我们这里使用的是 NioServerSocketChannel，所以，直接查看它的无参构造方法即可：

```java
// 1. 无参构造方法
public NioServerSocketChannel() {
    this(newSocket(DEFAULT_SELECTOR_PROVIDER));
}
// 1.1 使用Java底层的SelectorProvider创建一个Java原生的ServerSocketChannel
// windows平台下使用的是WindowsSelectorProvider，因为ServerSocketChannel是跟操作系统交互的，所以是平台相关的，每个平台下都不一样
private static ServerSocketChannel newSocket(SelectorProvider provider) {
    try {
        // key，创建Java原生ServerSocketChannel
        return provider.openServerSocketChannel();
    } catch (IOException e) {
        throw new ChannelException(
            "Failed to open a server socket.", e);
    }
}
// 1.2 有参构造方法，参数是Java原生的ServerSocketChannel
public NioServerSocketChannel(ServerSocketChannel channel) {
    // 调用父类的构造方法，注意parent参数为null
    // key，感兴趣的事件为Accept事件
    super(null, channel, SelectionKey.OP_ACCEPT);
    // 创建ChannelConfig
    config = new NioServerSocketChannelConfig(this, javaChannel().socket());
}
// 1.2.1 调用父类构造方法
protected AbstractNioMessageChannel(Channel parent, SelectableChannel ch, int readInterestOp) {
    super(parent, ch, readInterestOp);
}
// 1.2.1.1 调用父类父类的构造方法
protected AbstractNioChannel(Channel parent, SelectableChannel ch, int readInterestOp) {
    // 调用父类的构造方法，parent为null
    super(parent);
    // ch为Java原生的Channel
    this.ch = ch;
    // 感兴趣的事件，这里为Accept事件
    this.readInterestOp = readInterestOp;
    try {
        // 将channel设置为非阻塞（是不是跟NIO案例中的用法一样？！）
        ch.configureBlocking(false);
    } catch (IOException e) {
        try {
            ch.close();
        } catch (IOException e2) {
            logger.warn(
                "Failed to close a partially initialized socket.", e2);
        }

        throw new ChannelException("Failed to enter non-blocking mode.", e);
    }
}
//  1.2.1.1.1 调用父类父类父类的构造方法
protected AbstractChannel(Channel parent) {
    // 此时parent为null
    this.parent = parent;
    // 赋予一个id
    id = newId();
    // 赋值了一个unsafe，非Java的Unsafe，而是Netty自己的Unsafe
    unsafe = newUnsafe();
    // 创建ChannelPipeline
    pipeline = newChannelPipeline();
}
// 1.2.1.1.1.1 创建默认的ChannelPipeline
protected DefaultChannelPipeline(Channel channel) {
    this.channel = ObjectUtil.checkNotNull(channel, "channel");
    succeededFuture = new SucceededChannelFuture(channel, null);
    voidPromise =  new VoidChannelPromise(channel, true);
    // ChannelPipeline中默认有两个节点，head和tail，且是双向链表
    tail = new TailContext(this);
    head = new HeadContext(this);

    head.next = tail;
    tail.prev = head;
}
```

到这里 NioServerSocketChannel 的创建过程就完毕了，我们简单总结一下：

1. Netty 的 ServerSocketChannel 会与 Java 原生的 ServerSocketChannel 绑定在一起；
2. 会注册 Accept 事件；
3. 会为每一个 Channel 分配一个 id；
4. 会为每一个 Channel 创建一个叫作 unsafe 的东西；
5. 会为每一个 Channel 分配一个 ChannelPipeline；
6. ChannelPipeline 中默认存在一个双向链表 `head<=>tail`；

好了，再来看 `init(channel)` 方法：

```java
// io.netty.bootstrap.ServerBootstrap#init
@Override
void init(Channel channel) {
    // 将第5步中设置到ServerBootstrap中的Option设置到Channel的Config中
    setChannelOptions(channel, options0().entrySet().toArray(EMPTY_OPTION_ARRAY), logger);
    // 设置一些属性到Channel中，用法与Option一样
    setAttributes(channel, attrs0().entrySet().toArray(EMPTY_ATTRIBUTE_ARRAY));
    // 从Channel中取出ChannelPipeline，上面创建的
    ChannelPipeline p = channel.pipeline();
    
    // 子Channel的配置，子Channel也就是SocketChannel
    final EventLoopGroup currentChildGroup = childGroup;
    final ChannelHandler currentChildHandler = childHandler;
    final Entry<ChannelOption<?>, Object>[] currentChildOptions =
        childOptions.entrySet().toArray(EMPTY_OPTION_ARRAY);
    final Entry<AttributeKey<?>, Object>[] currentChildAttrs = childAttrs.entrySet().toArray(EMPTY_ATTRIBUTE_ARRAY);
    
    // 将ServerBootstrap中的Handler设置到ChannelPipeline的最后
    // ChannelInitializer的实现原理？
    p.addLast(new ChannelInitializer<Channel>() {
        @Override
        public void initChannel(final Channel ch) {
            final ChannelPipeline pipeline = ch.pipeline();
            // 第6步设置的Handler
            ChannelHandler handler = config.handler();
            if (handler != null) {
                pipeline.addLast(handler);
            }
            
            // 同时，又向ChannelPipeline的最后添加了一个叫作ServerBootstrapAcceptor的Handler
            // 这是什么写法？
            ch.eventLoop().execute(new Runnable() {
                @Override
                public void run() {
                    // 把子Channel相关的参数传到这个Handler里面，那它是干什么的呢？
                    pipeline.addLast(new ServerBootstrapAcceptor(
                        ch, currentChildGroup, currentChildHandler, currentChildOptions, currentChildAttrs));
                }
            });
        }
    });
}
```

`init(channel)` 方法整体来说还是比较简单的，就是把 ServerBootstrap 中的配置设置到 Channel 中，不过依然有几处我们现在可能还不太理解的地方：

- ChannelInitializer 的实现原理是什么？
- `ch.eventLoop().execute()` 这是什么写法？
- ServerBootstrapAcceptor 是干什么？

这三个问题，我们留到后面的章节中再解答。

好了，我们再来看看 `initAndRegister()` 方法的最后一个关键步骤，`ChannelFuture regFuture = config().group().register(channel);` 注册 Channel 到什么地方？

查看源码，可以发现，这里的 group 就是我们的 bossGroup，所以这里就是调用 bossGroup 的 `register(channel)` 方法。

```java
@Override
public ChannelFuture register(Channel channel) {
    return next().register(channel);
}
```

这里会调用 `next()` 方法选择出来一个 EventLoop 来注册 Channel，里面实际上使用的是一个叫做 `EventExecutorChooser` 的东西来选择，它实际上又有两种实现方式 ——`PowerOfTwoEventExecutorChooser` 和 `GenericEventExecutorChooser`，本质上就是从 EventExecutor 数组中选择一个 EventExecutor，我们这里就是 NioEventLoop，那么，它们有什么区别呢？有兴趣的可以点开它们的源码看看，我简单地提一下，本质都是按数组长度取余数 ，不过，2 的 N 次方的形式更高效。

最后，来到了 EventLoop 的 `register(channel)` 方法：

```java
// io.netty.channel.SingleThreadEventLoop#register(io.netty.channel.Channel)
@Override
public ChannelFuture register(Channel channel) {
    return register(new DefaultChannelPromise(channel, this));
}

@Override
public ChannelFuture register(final ChannelPromise promise) {
    ObjectUtil.checkNotNull(promise, "promise");
    // key，调用的是channel的unsafe的register()方法
    promise.channel().unsafe().register(this, promise);
    return promise;
}
```

可以看到，先创建了一个叫做 `ChannelPromise` 的东西，它是 ChannelFuture 的子类，暂时先把它当作 ChannelFuture 来看待。最后，又调回了 Channel 的 Unsafe 的 register () 方法，这里第一个参数是 this，也就是 NioEventLoop，第二个参数是刚创建的 ChannelPromise。

```java
// io.netty.channel.AbstractChannel.AbstractUnsafe#register
public final void register(EventLoop eventLoop, final ChannelPromise promise) {
    // 各种检查，可以跳过
    ObjectUtil.checkNotNull(eventLoop, "eventLoop");
    if (isRegistered()) {
        promise.setFailure(new IllegalStateException("registered to an event loop already"));
        return;
    }
    if (!isCompatible(eventLoop)) {
        promise.setFailure(
            new IllegalStateException("incompatible event loop type: " + eventLoop.getClass().getName()));
        return;
    }
    // key1，将上面传进来的EventLoop绑定到Channel上
    AbstractChannel.this.eventLoop = eventLoop;
    // 判断当前线程是否跟EventLoop线程是同一个
    if (eventLoop.inEventLoop()) {
        // key2，调用register0
        register0(promise);
    } else {
        try {
            eventLoop.execute(new Runnable() {
                @Override
                public void run() {
                    // key2，调用register0，实际走的是这里，所以这里需要打个断点
                    register0(promise);
                }
            });
        } catch (Throwable t) {
            // 异常处理，可以跳过
            logger.warn(
                "Force-closing a channel whose registration task was not accepted by an event loop: {}",
                AbstractChannel.this, t);
            closeForcibly();
            closeFuture.setClosed();
            safeSetFailure(promise, t);
        }
    }
}
```

这个方法主要干了两件事：

- 把 EventLoop 与 Channel 绑定在一起；
- 调用 register0 () 方法；

这里又出现了 eventLoop.execute () 这种写法，先忽略它，专注于主要逻辑。

接着，跟踪到 `register0()` 方法中：

```java
// io.netty.channel.AbstractChannel.AbstractUnsafe#register0
private void register0(ChannelPromise promise) {
    try {
        // 判断检查，可以跳过
        if (!promise.setUncancellable() || !ensureOpen(promise)) {
            return;
        }
        boolean firstRegistration = neverRegistered;
        // key1，调用doRegister()方法
        doRegister();
        neverRegistered = false;
        registered = true;

        // key2，调用invokeHandlerAddedIfNeeded()
        // 触发添加Handler的回调，其中pineline.addLast(ChannelInitializer)的处理就是在这一步完成的
        // 这一步之后pipeline里面应该是head<=>LoggineHandler<=>tail
        // 而ServerBootstrapAcceptor还没有加入到pipeline中，
        // 因为它设置了使用EventLoop的线程执行，当前线程就是EventLoop的线程
        // 所以，添加ServerBootstrapAcceptor会在当前任务执行完毕才会执行
        pipeline.invokeHandlerAddedIfNeeded();

        safeSetSuccess(promise);
        // 调用ChannelPineline的fireChannelRegistered()，实际是调用的各个ChannelHandler的channelRegistered()方法
        pipeline.fireChannelRegistered();
        // Channel是否已经激活，此时还未绑定到具体的地址，所以还未激活
        if (isActive()) {
            if (firstRegistration) {
                pipeline.fireChannelActive();
            } else if (config().isAutoRead()) {
                beginRead();
            }
        }
    } catch (Throwable t) {
        // 异常处理，可以跳过
        closeForcibly();
        closeFuture.setClosed();
        safeSetFailure(promise, t);
    }
}
```

这里有两个个非常重要的方法：

- doRegister ()，一看就是干正事的方法
- pipeline.invokeHandlerAddedIfNeeded ()，触发添加 Handler 的回调，其中 pineline.addLast (ChannelInitializer) 的处理就是在这一步完成的，有兴趣的同学可以跟踪看一下，这一块我们本节不详细展开

先来看 `doRegister()` 方法：

```java
// io.netty.channel.nio.AbstractNioChannel#doRegister
protected void doRegister() throws Exception {
    boolean selected = false;
    for (;;) {
        try {
            // key，将EventLoop中的Selector与Java原生的Channel绑定在一起，并返回这个SelectionKey
            // 注意，第三个参数是this，代表的是当前这个Netty中的Channel，我们这里就是NioServerSocketChannel
            // 它作为Selection的attachment绑定到SelectionKey上，与JavaChannel和Selector是同一个级别的
            selectionKey = javaChannel().register(eventLoop().unwrappedSelector(), 0, this);
            return;
        } catch (CancelledKeyException e) {
            // 异常处理，可以跳过
            if (!selected) {
                eventLoop().selectNow();
                selected = true;
            } else {
                throw e;
            }
        }
    }
}
```

这里其实就一行关键代码，将 Selector 与 Java 原生 Channel 绑定在一起，并将当前 Netty 的 Channel 通过 attachment 的形式绑定到 SelectionKey 上，到这里，你可能会有疑问：为什么要把 Netty 的 Channel 当作附件放到 SelectionKey 中呢？后面你会知道的，相信我。

所以，整个注册的过程主要就干了三个事：

1. 把 Channel 绑定到一个 EventLoop 上；
2. 把 Java 原生 Channel、Netty 的 Channel、Selector 绑定到 SelectionKey 中；
3. 触发 Register 相关的事件；

至此，`initAndRegister()` 方法内部就分析完成了，我们再来看看另一个重要方法 `doBind0()`:

```java
// 1. io.netty.bootstrap.AbstractBootstrap#doBind0
private static void doBind0(
    final ChannelFuture regFuture, final Channel channel,
    final SocketAddress localAddress, final ChannelPromise promise) {

    // 异步执行
    channel.eventLoop().execute(new Runnable() {
        @Override
        public void run() {
            if (regFuture.isSuccess()) {
                // key，调用Channel的bind()方法，因为在线程池里面，所以这里要打一个断点
                channel.bind(localAddress, promise).addListener(ChannelFutureListener.CLOSE_ON_FAILURE);
            } else {
                promise.setFailure(regFuture.cause());
            }
        }
    });
}
// 2. 调用Channel的bind()方法 io.netty.channel.AbstractChannel#bind(java.net.SocketAddress, io.netty.channel.ChannelPromise)
@Override
public ChannelFuture bind(SocketAddress localAddress, ChannelPromise promise) {
    // 调用的是pipeline的bind()方法
    return pipeline.bind(localAddress, promise);
}
// 3. 调用的是pipeline的bind()方法io.netty.channel.DefaultChannelPipeline#bind(java.net.SocketAddress, io.netty.channel.ChannelPromise)
@Override
public final ChannelFuture bind(SocketAddress localAddress, ChannelPromise promise) {
    // 从尾开始调用，也就是outbound
    return tail.bind(localAddress, promise);
}
// 4. 此时pipeline中的Handler为head<=>LoggingHandler<=>ServerBootstrapAcceptor<=>tail，出站的pineple实际为tail=>LoggingHandler=>head，下面我只贴主要代码
// 5. io.netty.handler.logging.LoggingHandler#bind
@Override
public void bind(ChannelHandlerContext ctx, SocketAddress localAddress, ChannelPromise promise) throws Exception {
    if (logger.isEnabled(internalLevel)) {
        logger.log(internalLevel, format(ctx, "BIND", localAddress));
    }
    ctx.bind(localAddress, promise);
}
// 6. io.netty.channel.DefaultChannelPipeline.HeadContext#bind
@Override
public void bind(
    ChannelHandlerContext ctx, SocketAddress localAddress, ChannelPromise promise) {
    // 最后调用的是HeadContext这个Handler中unsafe的bind()方法
    unsafe.bind(localAddress, promise);
}
// 7. io.netty.channel.AbstractChannel.AbstractUnsafe#bind
@Override
public final void bind(final SocketAddress localAddress, final ChannelPromise promise) {
    // 省略其它代码

    boolean wasActive = isActive();
    try {
        // key，绑定地址
        doBind(localAddress);
    } catch (Throwable t) {
        safeSetFailure(promise, t);
        closeIfClosed();
        return;
    }
	// 成功激活，调用pipeline.fireChannelActive()方法
    if (!wasActive && isActive()) {
        invokeLater(new Runnable() {
            @Override
            public void run() {
                pipeline.fireChannelActive();
            }
        });
    }
    // 设置promise为成功状态
    safeSetSuccess(promise);
}
// 8. 绕了一圈，最后又回到了NioServerChannel的doBind()方法 io.netty.channel.socket.nio.NioServerSocketChannel#doBind
@SuppressJava6Requirement(reason = "Usage guarded by java version check")
@Override
protected void doBind(SocketAddress localAddress) throws Exception {
    // 根据不同的JDK版本调用不同的方法
    if (PlatformDependent.javaVersion() >= 7) {
        // 我使用的JDK8版本，所以走到这里了
        javaChannel().bind(localAddress, config.getBacklog());
    } else {
        javaChannel().socket().bind(localAddress, config.getBacklog());
    }
}
```

可以看到，`doBind0()` 最后也是通过 Java 原生 Channel 的 bind () 方法来实现的。

最后，我们来总结一下整个服务启动的过程，服务启动主要是通过两个主要的大方法来完成的：

1. initAndRegister ()，初始化并注册什么呢？
   - channelFactory.newChannel()
     - 通过反射创建一个 NioServerSocketChannel
     - 将 Java 原生 Channel 绑定到 NettyChannel 中
     - 注册 Accept 事件
     - 为 Channel 分配 id
     - 为 Channel 创建 unsafe
     - 为 Channel 创建 ChannelPipeline（默认是 head<=>tail 的双向链表）
   - init(channel)
     - 把 ServerBootstrap 中的配置设置到 Channel 中
     - 添加 ServerBootstrapAcceptor 这个 Handler
   - register(channel)
     - 把 Channel 绑定到一个 EventLoop 上
     - 把 Java 原生 Channel、Netty 的 Channel、Selector 绑定到 SelectionKey 中
     - 触发 Register 相关的事件
2. doBind0 ()，到底绑定的是什么？
   - 通过 Java 原生 Channel 绑定到一个本地地址上

好了，经过本节的学习，我想你一定会发现很多新的问题，比如：

1. ChannelInitializer 是怎么实现的？
2. ch.eventLoop ().execute () 这种写法是在干什么？
3. ServerBootstrapAcceptor 是干什么的？
4. Netty 使用的还是 Java 原生的 Channel，那么，Selector 在哪里用的？

等等。

能发现问题是好事，有些问题会在后面的章节中涉及，有些问题需要你自己解决，我相信你一定可以做到的。



 ### 后记

本节，我们一起学习了 Netty 服务启动的过程，通过源码的阅读，可以看到，Netty 源码的调用链也是非常长的，在源码阅读的过程中，肯定会发现一些新的问题，随着我们源码阅读的不断深入，这些问题我们也会一一攻破。

下一节，我们将一起学习 Netty 中连接建立过程的源码剖析，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f1805890001d7af18450993.png)





<div style="page-break-after:always;"></div>

 ## 13 Netty服务如何接收新的连接


![img](https://img3.sycdn.imooc.com/5f0595830001a3ac06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)合理安排时间，就等于节约时间。——培根![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了服务启动过程的源码剖析，简单回顾一下，服务启动的时候会创建 ServerSocketChannel，并将之与 ChannelPipeline、EventLoop、Selector、Java 原生 Channel 进行绑定，同时通过 Java 原生 Channel 绑定到一个本地地址。

那么，如果有新连接进来，服务是如何接收（或接受，Accept）的呢？

本节，我们就来深入学习服务接收连接的源码剖析。



 ### 问题

经过上一节的学习，我们知道，服务启动的时候会往 NioServerSocketChannel 对应的 ChannelPipeline 后面添加一个叫做 ServerBootstrapAcceptor 的 ChannelHandler，那么，今天的问题是：

1. ServerBootstrapAcceptor 的作用是什么？
2. 接收连接的过程是否也要跟 Java 原生 Channel 打交道？
3. Selector 又是在哪里使用到的？

带着这几个问题进入今天的探索吧。



 ### 调试技巧

上一节，有我们自己编写的 main () 方法为基础，我们把第一个断点打在 main () 方法中，跟着断点一步一步调试即可剖析出整个服务启动过程的源码，本节的主题为服务接收新连接，断点该打在哪里呢？又该如何调试呢？

针对这个问题，我给出我的解决方案，有更好方案的同学，也可留言或者私聊我贡献给大家。

我们知道，Netty 中将 ChannelHandler 分成 inbound 和 outbound 两种类型，既然是接收新连接，那肯定是 inbound，所以，我们先从 ChannelInboundHandler 这个接口出发，分析它有哪些方法，简单瞄一眼，大致发现有三种可能跟接收新连接有关系的：

- channelRegistered ()/channelUnregistered ()，服务启动的时候有看到 Register 相关的调用
- channelActive ()/channelInactive ()，服务启动绑定完地址的时候有看到 Active 相关的调用
- channelRead ()/channelReadComplete ()，暂未看到在哪里使用的

简单分析一下，上面两种类型在服务启动的时候都有见过它们的源码，所以，不太可能是在接收新连接的时候调用的，因此，只剩下 channelRead ()/channelReadComplete () 这两个方法是有极大可能是在接收新连接的时候调用的，根据名称也能大概猜测是这样的。

所以，我们只需要找到一个 ChannelInboundHandler，把断点打在它的 channelRead () 方法中，就能大概率的跟踪到接收新连接的过程。

通过上一节的分析，我们知道，服务启动完成后，只有一个 Channel，也就是 NioServerSocketChannel，而它对应的 ChannelPipeline 中是有四个 Handler 的，即 head<=>LoggingHandler<=>ServerBootstrapAcceptor<=>tail，所以，我们只要把断点打在这四个 Handler 中的任意一个的 channelRead () 方法中即可。

> 确切地说应该是 ChannelHandlerContext，本系列课程，不严格区分 ChannelHandler 和 ChannelHandlerContext 的语义，大家根据上下文很容易理解即可。但是，要记住 ChannelPipeline 中包含的是 ChannelHandlerContext 的双向链表，而 ChannelHandlerContext 中才是具体的 ChannelHandler。

本节，我们就把断点打在 HeadContext 的 channelRead () 方法中。

> HeadContext，即是一个 ChannelHandlerContext，又是一个 ChannelInboundHandler，同时也是 ChannelOutboundHandler。



 ### 服务接收新连接过程

OK，在启动服务之前，请先将上一节的所有断点取消掉，待服务启动完成后，再在 HeadContext 的 channelRead () 方法中打一个断点，然后，进入今天的源码剖析阶段。

打开 XSHELL，输入 `telnet localhost 8007`，回车，可以看到，服务端成功停在了 HeadContext 的 channelRead () 方法的断点处：

![图片描述](https://img1.sycdn.imooc.com/5f180b030001beb319200913.png)
好了，下面要讲我的独家秘技了 —— **观察线程栈**。观察线程栈，会发现一些非常熟悉的字眼，比如 “NioEventLoop”、“run”、“processSelectedKeys”，如果你看不出这么明显的字眼，说明前面的 NIO 部分没有好好学习哦。

> 为了照顾大部分同学，我们再回顾下 NIO 编程的大致过程：
>
> - 先是启动 ServerSocketChannel，并注册 Accept 事件；
> - 轮询调用 Selector 的 select () 方法，select () 方法还有两个兄弟 ——selectNow ()，select (timeout)；
> - 调用 Selector 的 selectedKeys () 方法，拿到轮询到的 SelectionKey；
> - 遍历这些 selectedKeys，处理它们感兴趣到的事件；
> - 如果是 Accept 事件，则从 SelectionKey 中取出 ServerSocketChannel，并 accept () 出来一个 SocketChannel；
> - 把这个 SocketChannel 也注册到 Selector 上，并注册 Read 事件；

所以，这里我们大胆猜测，Netty 底层接收新连接跟 Java 原生 Channel 是一致的，而且它的 select 是在 NioEventLoop 的 run () 方法中，并在获取到 SelectedKeys 之后，调用了 processSelectedKeys () 方法处理这些 SelectionKey。

至于，我们的猜测对不对呢？打开 NioEventLoop 的 run () 方法看一看：

```java
// io.netty.channel.nio.NioEventLoop#run
@Override
protected void run() {
    int selectCnt = 0;
    // 死循环，还记得NIO中的死循环吗？
    for (;;) {
        try {
            int strategy;
            try {
                strategy = selectStrategy.calculateStrategy(selectNowSupplier, hasTasks());
                switch (strategy) {
                    case SelectStrategy.CONTINUE:
                        continue;
                    case SelectStrategy.BUSY_WAIT:
                    case SelectStrategy.SELECT:
                        long curDeadlineNanos = nextScheduledTaskDeadlineNanos();
                        if (curDeadlineNanos == -1L) {
                            curDeadlineNanos = NONE; // nothing on the calendar
                        }
                        nextWakeupNanos.set(curDeadlineNanos);
                        try {
                            if (!hasTasks()) {
                                // key1，select()相关的方法
                                strategy = select(curDeadlineNanos);
                            }
                        } finally {
                            nextWakeupNanos.lazySet(AWAKE);
                        }
                    default:
                }
            } catch (IOException e) {
                rebuildSelector0();
                selectCnt = 0;
                handleLoopException(e);
                continue;
            }

            selectCnt++;
            cancelledKeys = 0;
            needsToSelectAgain = false;
            final int ioRatio = this.ioRatio;
            boolean ranTasks;
            if (ioRatio == 100) {
                try {
                    if (strategy > 0) {
                        // key2，处理SelectionKey
                        processSelectedKeys();
                    }
                } finally {
                    ranTasks = runAllTasks();
                }
            } else if (strategy > 0) {
                final long ioStartTime = System.nanoTime();
                try {
                    // key2，处理SelectionKey
                    processSelectedKeys();
                } finally {
                    final long ioTime = System.nanoTime() - ioStartTime;
                    ranTasks = runAllTasks(ioTime * (100 - ioRatio) / ioRatio);
                }
            } else {
                ranTasks = runAllTasks(0);
            }
		// 省略其他代码
    }
}
```

从这个方法中，我们可以发现一些关键信息：

- 有个死循环，跟 NIO 编程一模一样；
- 找到了一个看起来像是 select () 的调用 select (curDeadlineNanos)；
- 找到了一个看起来像是处理 SelectionKey 的方法 processSelectedKeys ()；

至于是不是呢，让我们先来看看 `select(curDeadlineNanos)` 方法：

```java
// io.netty.channel.nio.NioEventLoop#select
private int select(long deadlineNanos) throws IOException {
    if (deadlineNanos == NONE) {
        // 无限期阻塞
        return selector.select();
    }
    long timeoutMillis = deadlineToDelayNanos(deadlineNanos + 995000L) / 1000000L;
    // 不阻塞的selectNow()和阻塞一段时间的select(timeout)
    return timeoutMillis <= 0 ? selector.selectNow() : selector.select(timeoutMillis);
}
```

可以看到，这里把 select () 的三兄弟都考虑在内了，根据传进来的超时时间判断调用哪个 select () 方法。

再看看 `processSelectedKeys()` 方法：

```java
// io.netty.channel.nio.NioEventLoop#processSelectedKeys
private void processSelectedKeys() {
    if (selectedKeys != null) {
        // 我们这里有新连接进来，肯定不为空
        processSelectedKeysOptimized();
    } else {
        processSelectedKeysPlain(selector.selectedKeys());
    }
}
private void processSelectedKeysOptimized() {
    // 遍历SelectionKey
    for (int i = 0; i < selectedKeys.size; ++i) {
        final SelectionKey k = selectedKeys.keys[i];
        // 优化GC
        selectedKeys.keys[i] = null;
        // 取出SelectionKey中的附件，还记得附件是什么吗？
        // 上一节，服务启动的时候把Selector、Java原生Channel、Netty的Channel绑定在一起了
        // 其中，Netty的Channel是通过attachment绑定到SelectionKey中的
        // 所以，针对新连接建立的过程，这里取出来的就是Netty中的NioServerSocketChannel
        final Object a = k.attachment();

        if (a instanceof AbstractNioChannel) {
            // 处理之
            processSelectedKey(k, (AbstractNioChannel) a);
        } else {
            @SuppressWarnings("unchecked")
            NioTask<SelectableChannel> task = (NioTask<SelectableChannel>) a;
            processSelectedKey(k, task);
        }

        if (needsToSelectAgain) {
            selectedKeys.reset(i + 1);
                selectAgain();
                i = -1;
            }
        }
    }
}
private void processSelectedKey(SelectionKey k, AbstractNioChannel ch) {
    final AbstractNioChannel.NioUnsafe unsafe = ch.unsafe();
    
    // 省略异常处理等其他代码

    try {
        int readyOps = k.readyOps();
        
        // 如果是Connect事件
        if ((readyOps & SelectionKey.OP_CONNECT) != 0) {
            int ops = k.interestOps();
            ops &= ~SelectionKey.OP_CONNECT;
            k.interestOps(ops);
            unsafe.finishConnect();
        }
        // 如果是Write事件
        if ((readyOps & SelectionKey.OP_WRITE) != 0) {
            ch.unsafe().forceFlush();
        }
        // 如果是Read事件或者Accept事件
        if ((readyOps & (SelectionKey.OP_READ | SelectionKey.OP_ACCEPT)) != 0 || readyOps == 0) {
            unsafe.read();
        }
    } catch (CancelledKeyException ignored) {
        unsafe.close(unsafe.voidPromise());
    }
}
```

可以看到，这里的写法也是跟我们的 NIO 编程保持一致的，针对不同的事件使用不同的逻辑进行处理，不同的是，Netty 中具体的处理逻辑交给了 Channel 的 unsafe 来处理，对于接收新连接的过程，这里的 unsafe 无疑就是 NioServerSocketChannel 中的 unsafe 了。

```java
// io.netty.channel.nio.AbstractNioMessageChannel.NioMessageUnsafe#read
@Override
public void read() {
    assert eventLoop().inEventLoop();
    final ChannelConfig config = config();
    final ChannelPipeline pipeline = pipeline();
    final RecvByteBufAllocator.Handle allocHandle = unsafe().recvBufAllocHandle();
    allocHandle.reset(config);

    boolean closed = false;
    Throwable exception = null;
    try {
        try {
            do {
                // key1，读取消息
                int localRead = doReadMessages(readBuf);
                if (localRead == 0) {
                    break;
                }
                if (localRead < 0) {
                    closed = true;
                    break;
                }

                allocHandle.incMessagesRead(localRead);
            } while (allocHandle.continueReading());
        } catch (Throwable t) {
            exception = t;
        }

        int size = readBuf.size();
        for (int i = 0; i < size; i ++) {
            readPending = false;
            // key2，触发channelRead()
            pipeline.fireChannelRead(readBuf.get(i));
        }
        readBuf.clear();
        allocHandle.readComplete();
        pipeline.fireChannelReadComplete();

        if (exception != null) {
            closed = closeOnReadError(exception);
            pipeline.fireExceptionCaught(exception);
        }

        if (closed) {
            inputShutdown = true;
            if (isOpen()) {
                close(voidPromise());
            }
        }
    } finally {
        if (!readPending && !config.isAutoRead()) {
            removeReadOp();
        }
    }
}
}
```

从这个方法中我们可以捕捉到两个关键方法：

- doReadMessages (readBuf)，读取消息，如何读取？读取的内容是什么？
- pipeline.fireChannelRead (readBuf.get (i))，触发 ChannelHandler 的 channelRead () 方法，最终由谁处理？

我们先来看第一个方法 `doReadMessages(readBuf)`:

```java
// io.netty.channel.socket.nio.NioServerSocketChannel#doReadMessages
@Override
protected int doReadMessages(List<Object> buf) throws Exception {
    // key1，看起来跟Java原生Channel有关系
    SocketChannel ch = SocketUtils.accept(javaChannel());

    try {
        if (ch != null) {
            // key2，构造了一个Netty的NioSocketChannel，并把Java原生SocketChannel传入
            buf.add(new NioSocketChannel(this, ch));
            return 1;
        }
    } catch (Throwable t) {
        logger.warn("Failed to create a new channel from an accepted socket.", t);

        try {
            ch.close();
        } catch (Throwable t2) {
            logger.warn("Failed to close a socket.", t2);
        }
    }

    return 0;
}
// io.netty.util.internal.SocketUtils#accept
public static SocketChannel accept(final ServerSocketChannel serverSocketChannel) throws IOException {
    try {
        return AccessController.doPrivileged(new PrivilegedExceptionAction<SocketChannel>() {
            @Override
            public SocketChannel run() throws IOException {
                // 调用Java原生的aacept()方法创建一个SocketChannel
                return serverSocketChannel.accept();
            }
        });
    } catch (PrivilegedActionException e) {
        throw (IOException) e.getCause();
    }
}
```

可以，Netty 最终还是调用的 Java 原生的 SeverSocketChannel 的 accept () 方法来创建一个 SocketChannel，并把这个 SocketChannel 绑定到 Netty 自己的 NioSocketChannel 中，还记得上一节创建 NioServerSocketChannel 的过程吗？

NioSocketChannel 的创建过程也是一样的，我就不贴源码了，简单再回顾一下：

- 将 Java 原生 Channel 配置成非阻塞 `ch.configureBlocking(false)`；
- 设置感兴趣的事件为 Read 事件，NioServerSocketChannel 感兴趣的事件为 Accept 事件；
- 分配 id；
- 创建 unsafe；
- 创建 ChannelPipeline；

好了，到这里 SocketChannel 就创建好了，但是它的 pipeline 中还是只有 head 和 tail 两个 Handler，还无法处理消息，那么，ChannelPipeline 的初始化在哪里呢？

这就轮到 `pipeline.fireChannelRead(readBuf.get(i))` 这行代码来发挥作用了，这里的 pipeline 实际上是 NioServerSocketChannel 对应的 ChannelPipeline，通过上一节的分析我们知道，服务启动完成后这个 ChannelPipeline 中的双向链表为 `head<=>LoggingHandler<=>ServerBootstrapAcceptor<=>tail`，很显然，只有 ServerBootstrapAcceptor 这个 ChannelHandler 会往子 ChannelPipeline 中添加子 ChannelHandler，所以，我们直接看 ServerBootstrapAcceptor 的 channelRead () 方法即可。

```java
// io.netty.bootstrap.ServerBootstrap.ServerBootstrapAcceptor#channelRead
@Override
@SuppressWarnings("unchecked")
public void channelRead(ChannelHandlerContext ctx, Object msg) {
    // 这里的msg就是上面的readBuf.get(i)，也就是NioSocketChannel，也就是子Channel
    final Channel child = (Channel) msg;
    // 添加子ChannelHandler，这里同样也是以ChannelInitializer的形式添加的
    child.pipeline().addLast(childHandler);
    // 设置子Channel的配置等信息
    setChannelOptions(child, childOptions, logger);
    setAttributes(child, childAttrs);

    try {
        // 将子Channel注册到workerGroup中的一个EventLoop上
        childGroup.register(child).addListener(new ChannelFutureListener() {
            @Override
            public void operationComplete(ChannelFuture future) throws Exception {
                if (!future.isSuccess()) {
                    forceClose(child, future.cause());
                }
            }
        });
    } catch (Throwable t) {
        forceClose(child, t);
    }
}
```

这里的代码跟上一节中 `initAndRegister()` 方法中的逻辑是完全一样的，我们就不再赘述了。

好了，今天的源码剖析基本就讲完了，让我们来总结一下服务接收新连接的过程：

1. Netty 中轮询的方法是写在 NioEventLooop 中的；
2. Netty 底层也是通过 Java 原生 ServerSocketChannel 来接收新连接的；
3. Netty 将接收到的 SocketChannel 包装成了 NioSocketChannel，并给它分配 ChannelPipeline 等元素；
4. Netty 中通过 ServerBootstrapAcceptor 这个 ChannelHandler 来初始化 NioSocketChannel 的配置并将其注册到 EventLoop 中；
5. 注册到 EventLoop 中同样也会与这个 EventLoop 中的 Selector 绑定，Netty 的 NioSocketChannel 同样地也是以附件的形式绑定在 SelectionKey 中；

至此，一个 SocketChannel 才算真正建立完成，也就可以接收消息了。



 ### 后记

本节，我们一起学习了 Netty 中服务接收新连接过程的源码剖析，相对于上一节，你可能会发现，本节的内容似乎要简单不少，对的，万事开头难，源码剖析也是一样，一开始入门会比较困难，一旦入门了，越往后越简单。

通过本节的剖析，我们知道了 Netty 中接收新连接的过程跟 Java 原生 NIO 是同出一辙，或者说是对 Java 原生 NIO 的增强，那么，既然连接已经就绪，如何接收消息呢？且听下回分解。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f180ae50001631315560631.png)





<div style="page-break-after:always;"></div>

 ## 14 Netty服务如何接收新的数据


![img](https://img1.sycdn.imooc.com/5f0595ce0001862706400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)知识犹如人体的血液一样宝贵。——高士其![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了服务接收新连接过程的源码剖析，发现一个很有趣的现象，其实，Netty 底层还是使用的 Java 原生的 NIO 来操作的。

那么，接收新数据也是一样吗？如果是，那么数据如何转化成 Netty 的 ByteBuf 呢？

所以，今天，我们就来一探 Netty 是如何接收新数据的。



 ### 问题

我们知道，Java 原生 NIO 从 SocketChannel 中取出来的数据是存储在 ByteBuffer 里面的，也就是下面这样的代码：

```java
if (selectionKey.isReadable()) {
    // 强制转换为SocketChannel
    SocketChannel socketChannel = (SocketChannel) selectionKey.channel();
    // 创建Buffer用于读取数据
    ByteBuffer buffer = ByteBuffer.allocate(1024);
    // 将数据读入到buffer中（第二阶段阻塞）
    int length = socketChannel.read(buffer);
    // 处理数据。。。
}
```

那么，今天的问题是：

1. 如果 Netty 底层使用的是 Java 原生的 SocketChannel，那么她是如何处理数据的？
2. 数据又是如何在 ChannelPipeline 中传递的？
3. 如何在控制台中打印出客户端传递过来的数据？

好了，带着这些问题进入今天的探索吧。



 ### 服务接收新数据过程

上一节，我们说接收新连接的处理主要是在 NioEventLoop 的 run () 方法中，里面有个方法叫做 `processSelectedKey()`，它里面对于四种事件都有相应的判断并交给 Channel 的 Unsafe 属性来处理，代码如下：

```java
private void processSelectedKey(SelectionKey k, AbstractNioChannel ch) {
    final AbstractNioChannel.NioUnsafe unsafe = ch.unsafe();
    
    // 省略异常处理等其他代码

    try {
        int readyOps = k.readyOps();
        
        // 如果是Connect事件
        if ((readyOps & SelectionKey.OP_CONNECT) != 0) {
            int ops = k.interestOps();
            ops &= ~SelectionKey.OP_CONNECT;
            k.interestOps(ops);
            unsafe.finishConnect();
        }
        // 如果是Write事件
        if ((readyOps & SelectionKey.OP_WRITE) != 0) {
            ch.unsafe().forceFlush();
        }
        // 如果是Read事件或者Accept事件
        if ((readyOps & (SelectionKey.OP_READ | SelectionKey.OP_ACCEPT)) != 0 || readyOps == 0) {
            unsafe.read();
        }
    } catch (CancelledKeyException ignored) {
        unsafe.close(unsafe.voidPromise());
    }
}
```

可以看到，Accept 事件和 Read 事件的处理其实是在同一行代码，所以，我们只需要在 `unsafe.read()` 这一行打上一个断点即可，不过，为了更精确，我们这里使用条件断点，在 IDEA 中设置如下（在断点上右击）：
![图片描述](https://img1.sycdn.imooc.com/5f1f8028000132f716260383.png)

让我们清除其它的断点，启动服务，并通过 XSHELL 连接到服务，可以发现，此时程序并不会停留在我们的断点处，因为此时是 Accept 事件，我们在 XSHELL 中发现一串字符串，比如 “12345”，此时程序才会停留在断点处，让我们跟踪到这个 unsafe 内部：

```java
// io.netty.channel.nio.AbstractNioByteChannel.NioByteUnsafe#read
@Override
public final void read() {
    final ChannelConfig config = config();
    if (shouldBreakReadReady(config)) {
        clearReadPending();
        return;
    }
    final ChannelPipeline pipeline = pipeline();
    // ByteBuf的分配器
    final ByteBufAllocator allocator = config.getAllocator();
    final RecvByteBufAllocator.Handle allocHandle = recvBufAllocHandle();
    allocHandle.reset(config);

    ByteBuf byteBuf = null;
    boolean close = false;
    try {
        do {
            // key1，通过allocator创建一个ByteBuf，如何创建的？
            byteBuf = allocHandle.allocate(allocator);
            // key2，读取数据到ByteBuf中，如何读取？
            allocHandle.lastBytesRead(doReadBytes(byteBuf));
            if (allocHandle.lastBytesRead() <= 0) {
                byteBuf.release();
                byteBuf = null;
                close = allocHandle.lastBytesRead() < 0;
                if (close) {
                    readPending = false;
                }
                break;
            }

            allocHandle.incMessagesRead(1);
            readPending = false;
            // key3，触发channelRead()
            pipeline.fireChannelRead(byteBuf);
            byteBuf = null;
        } while (allocHandle.continueReading());

        allocHandle.readComplete();
        // key4，触发channelReadComplete()
        pipeline.fireChannelReadComplete();

        if (close) {
            closeOnRead(pipeline);
        }
    } catch (Throwable t) {
        handleReadException(pipeline, byteBuf, t, close, allocHandle);
    } finally {
        if (!readPending && !config.isAutoRead()) {
            removeReadOp();
        }
    }
}
```

这个方法中有四个关键的信息：

- 通过 allocator 创建一个 ByteBuf，如何创建的呢？默认的又是什么呢？这个比较简单，默认地，通过各种参数判断当前操作系统是否允许池化、Unsafe、堆外这三个指标，当然，这些参数也可以通过启动参数来控制。我的系统默认创建的是 PooledUnsafeDirectByteBuf，你也可以看看你的是哪个。
- 读取数据到 ByteBuf 中，我们知道，Netty 底层包装了 Java 原生的 SocketChannel，那这里是如何读取的呢？
- 触发 ChannelPipeline 中的 ChannelHandler 的 channelRead () 方法。
- 触发 ChannelPipeline 中的 ChannelHandler 的 channelReadComplete () 方法，与上述同理，本文不详细展开。

首先，让我们看看 `doReadBytes(byteBuf)` 这个方法内部：

```java
// io.netty.channel.socket.nio.NioSocketChannel#doReadBytes
@Override
protected int doReadBytes(ByteBuf byteBuf) throws Exception {
    final RecvByteBufAllocator.Handle allocHandle = unsafe().recvBufAllocHandle();
    // 设置可读取的长度
    allocHandle.attemptedBytesRead(byteBuf.writableBytes());
    // key，调用ByteBuf的writeBytes()方法
    // 第一个参数是Java原生的SocketChannel，第二个参数是可读取的长度
    return byteBuf.writeBytes(javaChannel(), allocHandle.attemptedBytesRead());
}
// io.netty.buffer.AbstractByteBuf#writeBytes(java.nio.channels.ScatteringByteChannel, int)
@Override
public int writeBytes(ScatteringByteChannel in, int length) throws IOException {
    // 保证容量足够，里面有扩容的逻辑
    ensureWritable(length);
    // key，调用setBytes()方法
    // 第一个参数是写入的位置，第二参数是SocketChannel，第三个参数可写入的长度
    int writtenBytes = setBytes(writerIndex, in, length);
    if (writtenBytes > 0) {
        writerIndex += writtenBytes;
    }
    return writtenBytes;
}
// io.netty.buffer.PooledByteBuf#setBytes(int, java.nio.channels.ScatteringByteChannel, int)
@Override
public final int setBytes(int index, ScatteringByteChannel in, int length) throws IOException {
    try {
        // key，调用Java原生SocketChannel的read()方法
        // read()方法的参数是Java原生的ByteBuffer
        return in.read(internalNioBuffer(index, length));
    } catch (ClosedChannelException ignored) {
        return -1;
    }
}
```

跟踪到最后，果然不出我们所料，Netty 底层在读取数据的时候依然是调用的 Java 原生的 SocketChannel 的 read () 方法，将数据读取到了 ByteBuffer 中，也就是这里的 `internalNioBuffer(index, length)` 返回的是一个 Java 原生的 ByteBuffer，所以，此时，我们是不是可以大胆猜测，Netty 的 ByteBuf 是对 Java 原生 ByteBuffer 的包装呢？

为了验证我们的猜想，让我们再前进一步，深入到 `internalNioBuffer(index, length)` 内部：

```java
// io.netty.buffer.PooledByteBuf#internalNioBuffer(int, int)
@Override
public final ByteBuffer internalNioBuffer(int index, int length) {
    checkIndex(index, length);
    return _internalNioBuffer(index, length, false);
}    
final ByteBuffer _internalNioBuffer(int index, int length, boolean duplicate) {
    index = idx(index);
    // duplicate为false，所以使用的是第二个
    ByteBuffer buffer = duplicate ? newInternalNioBuffer(memory) : internalNioBuffer();
    buffer.limit(index + length).position(index);
    return buffer;
}
protected final ByteBuffer internalNioBuffer() {
    // this.tmpNioBuf
    ByteBuffer tmpNioBuf = this.tmpNioBuf;
    if (tmpNioBuf == null) {
        this.tmpNioBuf = tmpNioBuf = newInternalNioBuffer(memory);
    }
    return tmpNioBuf;
}
```

可以看到，最后返回的实际上是 `this.tmpNioBuf`，它的类型的是 ByteBuffer，果然，Netty 的 ByteBuf 底层果然是包装了 Java 原生的 ByteBuffer。
![图片描述](https://img1.sycdn.imooc.com/5f1f803e00011a4013560392.png)

所以，Netty 并不神秘，我们一层一层揭开它的面纱，让她裸露在我们面前。

好了，让我们再来看看第二个问题，数据如何在 ChannelPipeline 中传递的？

让我们跟踪到上面代码中的 `pipeline.fireChannelRead(byteBuf)` 内部：

```java
// 1. io.netty.channel.DefaultChannelPipeline#fireChannelRead
@Override
public final ChannelPipeline fireChannelRead(Object msg) {
    // 从HeadContext开始调用
    AbstractChannelHandlerContext.invokeChannelRead(head, msg);
    return this;
}
// 2. io.netty.channel.AbstractChannelHandlerContext#invokeChannelRead
static void invokeChannelRead(final AbstractChannelHandlerContext next, Object msg) {
    final Object m = next.pipeline.touch(ObjectUtil.checkNotNull(msg, "msg"), next);
    EventExecutor executor = next.executor();
    // 判断当前线程是不是在EventLoop中
    if (executor.inEventLoop()) {
        next.invokeChannelRead(m);
    } else {
        executor.execute(new Runnable() {
            @Override
            public void run() {
                next.invokeChannelRead(m);
            }
        });
    }
}
// 3. io.netty.channel.AbstractChannelHandlerContext#invokeChannelRead
private void invokeChannelRead(Object msg) {
    if (invokeHandler()) {
        try {
            // 调用里面的ChannelHandler的channelRead()方法
            ((ChannelInboundHandler) handler()).channelRead(this, msg);
        } catch (Throwable t) {
            notifyHandlerException(t);
        }
    } else {
        fireChannelRead(msg);
    }
}
// 4. io.netty.channel.DefaultChannelPipeline.HeadContext#channelRead
@Override
public void channelRead(ChannelHandlerContext ctx, Object msg) {
    // 调用ChannelHandlerContext的fireChannelRead()方法
    // 触发下一个Context中Handler的调用
    ctx.fireChannelRead(msg);
}
// 5. io.netty.channel.AbstractChannelHandlerContext#fireChannelRead
@Override
public ChannelHandlerContext fireChannelRead(final Object msg) {
    // 寻找下一个可用的ChannelHandlerContext
    invokeChannelRead(findContextInbound(MASK_CHANNEL_READ), msg);
    return this;
}
// 5.1 io.netty.channel.AbstractChannelHandlerContext#findContextInbound
private AbstractChannelHandlerContext findContextInbound(int mask) {
    AbstractChannelHandlerContext ctx = this;
    do {
        ctx = ctx.next;
    } while ((ctx.executionMask & mask) == 0);
    return ctx;
}
// 6. io.netty.channel.AbstractChannelHandlerContext#invokeChannelRead
// 又回到了上面第2步
static void invokeChannelRead(final AbstractChannelHandlerContext next, Object msg) {
    final Object m = next.pipeline.touch(ObjectUtil.checkNotNull(msg, "msg"), next);
    EventExecutor executor = next.executor();
    if (executor.inEventLoop()) {
        next.invokeChannelRead(m);
    } else {
        executor.execute(new Runnable() {
            @Override
            public void run() {
                next.invokeChannelRead(m);
            }
        });
    }
}
```

从这段代码中我们可以得出以下几点重要内容（对于入站消息）：

- ChannelPipeline 是从 HeadContext 开始执行的；
- 同一个 Channel 的所有 ChannelHandler 的执行都会放在 EventLoop 中执行，所以它们是线程安全的；
- 调用 `ctx.fireChannelRead(msg);` 即可触发下一个 ChannelHandler 的执行；

对于我们的 EchoServer，它里面有四个 Handler，即 head<=>LoggingHandler<=>EchoServerHandler<=>tail，EchoServerHandler 中 channelRead () 方法为：

```java
public class EchoServerHandler extends ChannelInboundHandlerAdapter {
    @Override
    public void channelRead(ChannelHandlerContext ctx, Object msg) {
        // 读取数据后写回客户端
        ctx.write(msg);
    }
}
```

我们并没有调用 `ctx.fireChannelRead(msg);`，所以流程并不会走到 tail 这个 Context。

让我们用一个图来表示这个过程：
![图片描述](https://img1.sycdn.imooc.com/5f1f80560001d1be10320269.png)

> HeadContext，不仅是一个 ChannelHandlerContext，也是一个 ChannelInboundHandler，同时也是一个 ChannelOutboundHandler。
>
> TailContext，不仅是一 ChannelHandlerContext，同时也是一个 ChannelInboundHandler。

可以看到，流程到 EchoServerHandler 就终止了，因为 EchoServerHandler 中并没有调用 ChannelHandlerContext 的 fireChannelRead () 方法，所以，不会再调用到下一个 ChannelHandlerContext。

正常来说，一条消息也不会走到 TailContext，为什么呢？让我们来看看 TailContext 的 channelRead () 方法：

```java
// io.netty.channel.DefaultChannelPipeline.TailContext#channelRead
@Override
public void channelRead(ChannelHandlerContext ctx, Object msg) {
    onUnhandledInboundMessage(ctx, msg);
}
// io.netty.channel.DefaultChannelPipeline#onUnhandledInboundMessage
protected void onUnhandledInboundMessage(ChannelHandlerContext ctx, Object msg) {
    onUnhandledInboundMessage(msg);
    if (logger.isDebugEnabled()) {
        logger.debug("Discarded message pipeline : {}. Channel : {}.",
                     ctx.pipeline().names(), ctx.channel());
    }
}
// io.netty.channel.DefaultChannelPipeline#onUnhandledInboundMessage
protected void onUnhandledInboundMessage(Object msg) {
    try {
        logger.debug(
            "Discarded inbound message {} that reached at the tail of the pipeline. " +
            "Please check your pipeline configuration.", msg);
    } finally {
        // 释放ByteBuf的引用
        ReferenceCountUtil.release(msg);
    }
}
```

可以看到，如果一条消息走到了 TailContext，它的最终下场是只打印了几行日志，也就是被丢弃了。那为什么还要这个 TailContext？主要作用有两点：

- 实现 ChannelPipeline 的完整性，有头有尾
- 对资源做一个回收，可以看到，最后一行释放了 ByteBuf 的引用，对于池化的 ByteBuf，可以让它们重新回到池中，对于非池化的 ByteBuf，可以释放它们占用的内存

好了，对于如何读取新数据以及数据如何在 ChannelPipeline 中传递，我们都弄明白了，让我们再看看第三个问题，如何在控制台中打印出客户端传递过来的消息呢？

其实，也很简单，如果你的记忆还比较清晰的话，应该还记得我们前面介绍编解码方式的时候有提到过一对编解码，叫做 StringEncoder/StringDecoder，我们这里只需要在 ChannelPipeline 中加入这两个编解码，即可把客户端传过来的消息对应的 ByteBuf 转化成 String 类型，这样在 EchoServerHandler 中就可以直接打印到控制台了，让我们来试试吧：

```java
public final class EchoServer {
    public static void main(String[] args) throws Exception {
        // 省略其它代码
        serverBootstrap.childHandler(new ChannelInitializer<SocketChannel>() {
            @Override
            public void initChannel(SocketChannel ch) throws Exception {
                ChannelPipeline p = ch.pipeline();
                // 可以添加多个子Handler
                p.addLast(new LoggingHandler(LogLevel.INFO));
                // 添加String类型的编解码
                p.addLast(new StringDecoder());
                // 因为还要写回客户端，所以还要加上StringEncoder
                p.addLast(new StringEncoder());

                p.addLast(echoServerHandler);
            }
        });
    }
}
public class EchoServerHandler extends ChannelInboundHandlerAdapter {
    // 省略其它代码
    @Override
    public void channelRead(ChannelHandlerContext ctx, Object msg) {
        // 如果上面解码成功才会打印
        if (msg instanceof String) {
            System.out.println("接收到的消息为：" + msg);
        }
        // 读取数据后写回客户端
        ctx.write(msg);
    }
}
```

重启服务器，使用 XSHELL 重新连接到服务器，并发送 “12345”，可以看到控制台中成功打印出来，说明我们的代码修改正确了，并且客户端也回显了发送的内容，完美 ^^

```java
接收到的消息为：12345
```

至此，本节的内容就讲完啦。



 ### 后记

本节，我们一起学习了 Netty 接收新数据过程的源码剖析，通过不断的探寻底层的源码和原理，我们发现，揭开了 Netty 的神秘面纱之后，其实，她也很简单，底层都是对 Java 原生 NIO 的包装和优化，不断地提升用户体验，创造更美好的东西供大家使用。

本节我们只讲了 Netty 接收新数据的过程，那么，Netty 发送数据的过程又是怎样的呢？让我们下回见。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f1f806a0001bfb613950638.png)





<div style="page-break-after:always;"></div>

 ## 15 Netty服务如何写出数据


![img](https://img4.sycdn.imooc.com/5f0595c100012d9f06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才就是长期劳动的结果。——牛顿![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了 Netty 接收新数据过程的源码剖析，我们又发现了一个有趣的现象，Netty 的 ByteBuf 竟然也是对 Java 原生 ByteBuffer 的包装。

经过前面的学习，我想你一定迫不及待地想知道 Netty 中写出数据的过程了吧，也有可能，你自己已经根据我们前面的调试方法自己看了，也有可能，睿智的你已经猜测 Netty 中写出数据，肯定也是调用 Java 原生 SocketChannel 的写出数据。

那么，是不是如你所猜测呢？让我们进入今天的学习吧。



 ### 问题

我们知道，Java 原生 NIO 写出数据是从 ByeBuffer 中写出的，也就是下面这样的代码：

```java
private static void send(SocketChannel socketChannel, String msg) {
    try {
        ByteBuffer writeBuffer = ByteBuffer.allocate(1024);
        writeBuffer.put(msg.getBytes());
        writeBuffer.flip();
        // 调用SocketChannel的写出方法
        socketChannel.write(writeBuffer);
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

那么，今天的问题是：

1. Netty 底层是不是调用的 SocketChannel 的 write () 方法呢？
2. 写出数据在 ChannelPipeline 中的传递顺序是怎样的？
3. 写出为什么还有一个叫做 `flush` 的过程？之前写出的数据又在哪里呢？

好了，让我们带着这些问题进入今天的探索吧。



 ### 服务写出数据过程

今天的内容调试起来比较简单，我们继续使用 EchoServer 这个案例，为了便于讲解，我们先把 StringDecoder/StringEncoder 相关的内容注释掉，直接在 EchoServerHandler 的 channelRead () 方法中打个断点即可：

```java
public class EchoServerHandler extends ChannelInboundHandlerAdapter {
    // 省略其它代码
    @Override
    public void channelRead(ChannelHandlerContext ctx, Object msg) {
        // 读取数据后写回客户端
        // key1，断点在此处
        ctx.write(msg);
    }
    @Override
    public void channelReadComplete(ChannelHandlerContext ctx) {
        // key2，这里也需要个断点
        ctx.flush();
    }
}
```

不过，一般来说，服务端发送数据不会在每次 write () 的时候就发送出去，而是先缓存起来，等到一定量之后或者显式地说明要发送的时候再真正地发送出去，这样能在一定程度上提高效率。

就像快递公司一般都会在各个地方设置网点一样，快递小哥并不是收取完快递就给你发出去了，而是，先集成存放在网点，等达到一定量之后，或者到晚上八九点钟之后，再装车发送出去。快递小哥往网点投放快递就类似于 write (msg) 的过程，而装车拉走就类似于 flush () 的过程。

![图片描述](https://img1.sycdn.imooc.com/5f1f812d0001d6e410350472.png)
所以，上面的代码，如果仅仅调用了 `ctx.write(msg)`，客户端可能并不能及时地收取到消息，我们还需要调用一个叫做 `ctx.flush()` 的方法，才能真正地把数据发送给客户端。为了与读取消息的过程一致，我们这里把 `ctx.flush()` 方法的调用放在了 `channelReadComplete()` 方法中，因此，这里也需要打个断点。

好了，让我们先跟踪第一个方法 ——`ctx.write(msg)` 吧。

清除其它断点，只保留这两个断点，启动服务，使用 XSHELL 模拟客户端发送一条消息过来，我们还是以 `12345` 为例，可以发现，断点成功停留在了 `ctx.write(msg)` 这一行，跟踪进去看看：

```java
// 1. io.netty.channel.AbstractChannelHandlerContext#write
@Override
public ChannelFuture write(Object msg) {
    return write(msg, newPromise());
}
// 2. io.netty.channel.AbstractChannelHandlerContext#write
@Override
public ChannelFuture write(final Object msg, final ChannelPromise promise) {
    // 第二个参数为flush，这里传入的是false
    // 也就是默认不进行真正地发送
    write(msg, false, promise);

    return promise;
}
// 3. io.netty.channel.AbstractChannelHandlerContext#write
private void write(Object msg, boolean flush, ChannelPromise promise) {
    // 检查参数，可以跳过
    ObjectUtil.checkNotNull(msg, "msg");
    try {
        if (isNotValidPromise(promise, true)) {
            ReferenceCountUtil.release(msg);
            // cancelled
            return;
        }
    } catch (RuntimeException e) {
        ReferenceCountUtil.release(msg);
        throw e;
    }
    // key1，寻找下一个可用的outbound类型的ChannelHandlerContext
    // 在ChannelPipeline中也就是prev指针标记的那个
    // 这里找到的就是LoggingHandler对应的那个ChannelHandlerContext
    final AbstractChannelHandlerContext next = findContextOutbound(flush ?
                                                                   (MASK_WRITE | MASK_FLUSH) : MASK_WRITE);
    // touch()可以先不管，可以把这里返回的对象看作与msg是一个对象
    final Object m = pipeline.touch(msg, next);
    EventExecutor executor = next.executor();
    if (executor.inEventLoop()) {
        if (flush) {
            next.invokeWriteAndFlush(m, promise);
        } else {
            // key2，flush为false，所以走到了这里
            // 调用context的invokeWrite()方法
            next.invokeWrite(m, promise);
        }
    } else {
        final WriteTask task = WriteTask.newInstance(next, m, promise, flush);
        if (!safeExecute(executor, task, promise, m, !flush)) {
            task.cancel();
        }
    }
}
// 4. io.netty.channel.AbstractChannelHandlerContext#invokeWrite
void invokeWrite(Object msg, ChannelPromise promise) {
    if (invokeHandler()) {
        invokeWrite0(msg, promise);
    } else {
        write(msg, promise);
    }
}
// 5. io.netty.channel.AbstractChannelHandlerContext#invokeWrite0
private void invokeWrite0(Object msg, ChannelPromise promise) {
    try {
        // 调用Handler的write()方法
        ((ChannelOutboundHandler) handler()).write(this, msg, promise);
    } catch (Throwable t) {
        notifyOutboundHandlerException(t, promise);
    }
}
// 6. io.netty.handler.logging.LoggingHandler#write
@Override
public void write(ChannelHandlerContext ctx, Object msg, ChannelPromise promise) throws Exception {
    if (logger.isEnabled(internalLevel)) {
        logger.log(internalLevel, format(ctx, "WRITE", msg));
    }
    // 又调回了第2步中的方法，继续寻找下一个可用的outbound类型的ChannelHandlerContext
    ctx.write(msg, promise);
}
```

所以，到这里，第 2 个问题我们倒是先解决了，数据在 ChannelPipeline 中的传递，也是通过 ChannelHandlerContext 进行的，每次寻找下一个可用的 outbound 类型的 ChannelHandlerContext，调用它里面的 ChannelHandler 的 write () 方法，然后，在 ChannelHandler 里面调用 `ctx.write(msg, promise)` 才能让这个链往下传递，继续寻找下一个可用的 outbound 类型的 ChannelHandlerContext。F

因此，我们可以把上一节的图补全为下面这样：
![图片描述](https://img1.sycdn.imooc.com/5f1f814400018d0710350283.png)
为了便于理解，我特意把箭头区分成两种颜色，并标上数字：

- 红色表示接收数据的过程，蓝色表示写出数据的过程；
- 1 表示调用 ctx.fireChannelRead (msg) 方法，触发下一个 ChannelHandlerContext 的调用；
- 2 表示调用 next.invokeChannelRead (m) 方法，调用到下一个 ChannelHandlerContext；
- 3 表示调用 ((ChannelInboundHandler) handler ()).channelRead (this, msg) 方法，调用 ChannelHandler 的 channelRead () 方法；
- 4 表示调用 ctx.write (msg) 或者 ctx.write (msg, promise) 方法，触发下一个 ChannelHandlerContext 的调用；
- 5 表示调用 next.invokeWrite (m, promise) 方法，调用到下一个 ChannelHandlerContext；
- 6 表示调用 ((ChannelOutboundHandler) handler ()).write (this, msg, promise) 方法，调用 ChannelHandler 的 write () 方法；

所以，对于接收数据，如果需要数据在 ChannelPipeline 中传递，就调用 `ctx.fireChannelRead(msg)` 方法；对于写出数据，如果需要数据在 ChannelPipeline 中传递，就调用 `ctx.write(msg)` 或者 `ctx.write(msg, promise)` 方法。

通过上面的图，我们知道， 最后一定会走到 ChannelPipeline 的 HeadContext 类的 write () 方法，所以，直接在这个方法中打一个断点，或者慢慢一步一步走到这里都可以：

```java
// io.netty.channel.DefaultChannelPipeline.HeadContext#write
@Override
public void write(ChannelHandlerContext ctx, Object msg, ChannelPromise promise) {
    // 调用unsafe的write()方法
    unsafe.write(msg, promise);
}
// io.netty.channel.AbstractChannel.AbstractUnsafe#write
@Override
public final void write(Object msg, ChannelPromise promise) {
    assertEventLoop();
    // key，看起来像是一个缓存的东西
    ChannelOutboundBuffer outboundBuffer = this.outboundBuffer;
    if (outboundBuffer == null) {
        safeSetFailure(promise, newClosedChannelException(initialCloseCause));
        ReferenceCountUtil.release(msg);
        return;
    }

    int size;
    try {
        // 过滤消息
        msg = filterOutboundMessage(msg);
        // 计算消息的大小
        size = pipeline.estimatorHandle().size(msg);
        if (size < 0) {
            size = 0;
        }
    } catch (Throwable t) {
        safeSetFailure(promise, t);
        ReferenceCountUtil.release(msg);
        return;
    }

    // key，添加到缓存中
    outboundBuffer.addMessage(msg, size, promise);
}
// io.netty.channel.ChannelOutboundBuffer#addMessage
public void addMessage(Object msg, int size, ChannelPromise promise) {
    Entry entry = Entry.newInstance(msg, size, total(msg), promise);
    // 典型的单链表添加元素的过程
    if (tailEntry == null) {
        flushedEntry = null;
    } else {
        Entry tail = tailEntry;
        tail.next = entry;
    }
    tailEntry = entry;
    if (unflushedEntry == null) {
        unflushedEntry = entry;
    }

    incrementPendingOutboundBytes(entry.pendingSize, false);
}
```

所以，`ctx.write()` 方法最终只是把消息添加到了一个叫做 `ChannelOutboundBuffer` 的缓存中，并没有真正地发送出去。

那么，我们要怎么寻找在哪里真正发送数据出去的呢？

好了，我们在 EchoServerHandler 中打的第二个断点要登场了，`ctx.flush();` 的调用过程跟 `ctx.write(msg)` 是类似的，我们就不再赘述了，直接来到 HeadContext 的 `flush()` 方法。

```java
// io.netty.channel.DefaultChannelPipeline.HeadContext#flush
@Override
public void flush(ChannelHandlerContext ctx) {
    unsafe.flush();
}
// io.netty.channel.AbstractChannel.AbstractUnsafe#flush
@Override
public final void flush() {
    assertEventLoop();

    ChannelOutboundBuffer outboundBuffer = this.outboundBuffer;
    if (outboundBuffer == null) {
        return;
    }
    outboundBuffer.addFlush();
    // key，不知道大家发现没，这种带0结尾的一般也是干正事的方法
    flush0();
}
// io.netty.channel.nio.AbstractNioChannel.AbstractNioUnsafe#flush0
@Override
protected final void flush0() {
    if (!isFlushPending()) {
        super.flush0();
    }
}
// io.netty.channel.AbstractChannel.AbstractUnsafe#flush0
protected void flush0() {
    // 省略其它代码

    try {
        doWrite(outboundBuffer);
    } catch (Throwable t) {
        // // 省略其它代码
    } finally {
        inFlush0 = false;
    }
}
// io.netty.channel.socket.nio.NioSocketChannel#doWrite
@Override
protected void doWrite(ChannelOutboundBuffer in) throws Exception {
    SocketChannel ch = javaChannel();
    int writeSpinCount = config().getWriteSpinCount();
    do {
        if (in.isEmpty()) {
            clearOpWrite();
            return;
        }

        // Ensure the pending writes are made of ByteBufs only.
        int maxBytesPerGatheringWrite = ((NioSocketChannelConfig) config).getMaxBytesPerGatheringWrite();
        // key1，从ChannelOutboundBuffer中取出ByteBuffer
        // 前面分析write()的时候放里面放的实际是ByeBuf
        // 因为ByteBuf实际上是对ByteBuffer的包装
        // 所以这里取出来的时候直接就转换成ByteBuffer了
        ByteBuffer[] nioBuffers = in.nioBuffers(1024, maxBytesPerGatheringWrite);
        int nioBufferCnt = in.nioBufferCount();

        // Always us nioBuffers() to workaround data-corruption.
        // See https://github.com/netty/netty/issues/2761
        switch (nioBufferCnt) {
            case 0:                
                writeSpinCount -= doWrite0(in);
                break;
            case 1: {
                // 我们只写了一条数据，所以实际是走到了这里
                ByteBuffer buffer = nioBuffers[0];
                int attemptedBytes = buffer.remaining();
                // key2，调用SocketChannel的write()方法写出数据
                final int localWrittenBytes = ch.write(buffer);
                if (localWrittenBytes <= 0) {
                    incompleteWrite(true);
                    return;
                }
                adjustMaxBytesPerGatheringWrite(attemptedBytes, localWrittenBytes, maxBytesPerGatheringWrite);
                in.removeBytes(localWrittenBytes);
                --writeSpinCount;
                break;
            }
            default: {
                long attemptedBytes = in.nioBufferSize();
                // key2，调用SocketChannel的write()方法写出数据
                final long localWrittenBytes = ch.write(nioBuffers, 0, nioBufferCnt);
                if (localWrittenBytes <= 0) {
                    incompleteWrite(true);
                    return;
                }
                adjustMaxBytesPerGatheringWrite((int) attemptedBytes, (int) localWrittenBytes,
                                                maxBytesPerGatheringWrite);
                in.removeBytes(localWrittenBytes);
                --writeSpinCount;
                break;
            }
        }
    } while (writeSpinCount > 0);

    incompleteWrite(writeSpinCount < 0);
}
```

这里有两个关键方法：

- 先从 ChannelOutboundBuffer 中取出 ByteBuffer；
- 再通过 Java 原生的 SocketChannel 写出数据。

至此，写出数据过程的源码剖析就讲完了，让我们再来总结一下：

1. 调用 ctx.write () 方法时，只是把数据添加到 ChannelOutboundBuffer 缓存中；
2. 调用 ctx.flush () 方法时，才把数据从 ChannelOutboundBuffer 取出来；
3. 调用 Java 原生的 SocketChannel 把数据发送出去。



 ### 后记

本节，我们一起学习了 Netty 中服务写出数据过程的源码剖析，通过阅读源码，我们知道，Netty 中写出数据实际上分成了两步：ctx.write () 和 ctx.flush ()，write () 的时候只是把数据添加到缓存中，flush () 才真正把数据发送出去，之所以要分成两步，也是基于效率来考虑的，大家可以类比快递网点的生活案例进行对比，如果没有网点，则需要接收到快递就装车拉走，将要耗费巨大的人力物力财力。

到这里，数据流向角度的源码分析就快结束了，下一节，我们将看看 Netty 是如何做到优雅关闭的，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f1f815a0001735c14780681.png)







<div style="page-break-after:always;"></div>

 ## 16 Netty服务如何优雅关闭


![img](https://img4.sycdn.imooc.com/5f0595dc00018ee006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)不安于小成，然后足以成大器；不诱于小利，然后可以立远功。——方孝孺![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了服务写出数据的源码剖析，我们发现，Netty 中将写出数据分成了两个部分，第一部分先缓存起来，第二部分再通过 Java 原生的 SocketChannel 发送出去。

今天，我们再来学习一个新的概念 —— 如何优雅地关闭服务。

好了，开始今天的学习吧。



 ### 问题

在 Netty 的编码模板中，我们一般会在 try…finally… 中写上这么一段代码：

```java
try {
    // 省略其他代码
    // 9. 等待服务端监听端口关闭，这里会阻塞主线程
    f.channel().closeFuture().sync();
} finally {
    // 10. 优雅地关闭两个线程池
    bossGroup.shutdownGracefully();
    workerGroup.shutdownGracefully();
}
```

通过 NioEventLoopGroup 的 shutdownGracefully () 来关闭服务器，那么，今天的问题来了：

1. shutdownGracefully () 内部的逻辑是怎样的？
2. 进行了哪些资源的释放？
3. NioEventLoopGroup 如何知道所有的 EventLoop 都优雅关闭了呢？

好了，让我们带着这些问题进入今天的探索吧。



 ### 优雅关闭服务过程

正常来说，服务是不会走到第 10 步的，除非出现异常，因为第 9 步的 sync () 会阻塞 main 线程。

所以，我们这里调试的时候可以先把第 9 步注释掉，让程序能够走到第 10 步，这样便于我们调试。

假设我们已经这样做了，程序断点在了 `bossGroup.shutdownGracefully();` 这一行，让我们跟踪到这个方法内部看看：

```java
// io.netty.util.concurrent.AbstractEventExecutorGroup#shutdownGracefully
@Override
public Future<?> shutdownGracefully() {
    // 调用重载方法
    // 第一个参数为静默周期，默认2秒
    // 第二个参数为超时时间，默认15秒
    return shutdownGracefully(DEFAULT_SHUTDOWN_QUIET_PERIOD, DEFAULT_SHUTDOWN_TIMEOUT, TimeUnit.SECONDS);
}
// io.netty.util.concurrent.MultithreadEventExecutorGroup#shutdownGracefully
@Override
public Future<?> shutdownGracefully(long quietPeriod, long timeout, TimeUnit unit) {
    for (EventExecutor l: children) {
        // 调用孩子的shutdownGracefully()
        // 这里的EventExecutor无疑就是NioEventLoop
        l.shutdownGracefully(quietPeriod, timeout, unit);
    }
    // 返回的是NioEventLoopGroup的terminationFuture
    return terminationFuture();
}
```

可以看到，内部其实是调用了每个 NioEventLoop 的 shutdownGracefully () 方法，最后返回了 NioEventLoopGroup 的 terminationFuture。

我们先看看 NioEventLoop 的 shutdownGracefully () 方法：

```java
// io.netty.util.concurrent.SingleThreadEventExecutor#shutdownGracefully
@Override
public Future<?> shutdownGracefully(long quietPeriod, long timeout, TimeUnit unit) {
    // 参数检验
    ObjectUtil.checkPositiveOrZero(quietPeriod, "quietPeriod");
    if (timeout < quietPeriod) {
        throw new IllegalArgumentException(
            "timeout: " + timeout + " (expected >= quietPeriod (" + quietPeriod + "))");
    }
    ObjectUtil.checkNotNull(unit, "unit");

    // 其它线程正在执行关闭，直接返回
    if (isShuttingDown()) {
        return terminationFuture();
    }

    boolean inEventLoop = inEventLoop();
    boolean wakeup;
    int oldState;
    for (;;) {
        // 再次检查其它线程正在执行关闭，直接返回
        if (isShuttingDown()) {
            return terminationFuture();
        }
        int newState;
        wakeup = true;
        oldState = state;
        // 我们是在main线程中执行的
        // 所以不在EventLoop中
        if (inEventLoop) {
            newState = ST_SHUTTING_DOWN;
        } else {
            switch (oldState) {
                case ST_NOT_STARTED:
                case ST_STARTED:
                    // 显然，我们的程序已经启动了
                    // 所以，新状态为ST_SHUTTING_DOWN
                    newState = ST_SHUTTING_DOWN;
                    break;
                default:
                    newState = oldState;
                    wakeup = false;
            }
        }
        // key1，更新状态成功，退出循环
        if (STATE_UPDATER.compareAndSet(this, oldState, newState)) {
            break;
        }
    }
    // key2，修改NioEventLoop的属性标识
    gracefulShutdownQuietPeriod = unit.toNanos(quietPeriod);
    gracefulShutdownTimeout = unit.toNanos(timeout);

    if (ensureThreadStarted(oldState)) {
        return terminationFuture;
    }

    // key3，添加一个空任务，唤醒EventLoop
    if (wakeup) {
        taskQueue.offer(WAKEUP_TASK);
        if (!addTaskWakesUp) {
            wakeup(inEventLoop);
        }
    }

    // key4，返回NioEventLoop的terminationFuture
    return terminationFuture();
}
// io.netty.channel.nio.NioEventLoop#wakeup
@Override
protected void wakeup(boolean inEventLoop) {
    if (!inEventLoop && nextWakeupNanos.getAndSet(AWAKE) != AWAKE) {
        selector.wakeup();
    }
}
```

这个方法就结束了，让我们整理下这个方法的主要逻辑：

- 修改状态为 ST_SHUTTING_DOWN；
- 修改两个属性，一个是静默周期，一个是超时时间；
- 往队列中放了一个空任务，并唤醒 NioEventLoop，实际上是唤醒的 selector，也就是 selector.select () 的位置；
- 返回 NioEventLoop 的 terminationFuture，这个 terminationFuture 怎么跟 NioEventLoopGroup 的 terminationFuture 联系起来的呢？或者说，NioEventLoopGroup 怎么知道所有的 NioEventLoop 都关闭成功了呢？

可以看到，这个方法中并没有对 “优雅关闭” 做什么实质的处理，那么，真正关闭的处理逻辑在哪里呢？

经过前面的学习，我们知道，NioEventLoop 相当于一个线程，它的 run () 方法中有对 selector 的轮询，而这里又唤醒了 selector，所以，我们大胆猜测，处理逻辑应该是在 NioEventLoop 的 run () 方法中，让我们再仔细研究一下这个 run () 方法：

```java
@Override
protected void run() {
    int selectCnt = 0;
    // 轮询
    for (;;) {
        try {
            int strategy;
            try {
                // 策略，这里面会检测如果有任务，调用的是selectNow()，也就是不阻塞
                strategy = selectStrategy.calculateStrategy(selectNowSupplier, hasTasks());
                switch (strategy) {
                    case SelectStrategy.CONTINUE:
                        continue;
                    case SelectStrategy.BUSY_WAIT:
                    case SelectStrategy.SELECT:
                        long curDeadlineNanos = nextScheduledTaskDeadlineNanos();
                        if (curDeadlineNanos == -1L) {
                            curDeadlineNanos = NONE; // nothing on the calendar
                        }
                        nextWakeupNanos.set(curDeadlineNanos);
                        try {
                            if (!hasTasks()) {
                                // 如果没有任务，才会调用这里的select()，默认是阻塞的
                                // 通过前面的唤醒，唤醒的是这里的select()
                                strategy = select(curDeadlineNanos);
                            }
                        } finally {
                            nextWakeupNanos.lazySet(AWAKE);
                        }
                    default:
                }
            
                // 省略其他内容
        }
        try {
            // 判断是否处于关闭中
            if (isShuttingDown()) {
                // key1，关闭什么？
                closeAll();
                // key2，确定关闭什么？
                if (confirmShutdown()) {
                    return;
                }
            }
        } catch (Throwable t) {
            handleLoopException(t);
        }
    }
}
```

针对优雅关闭的时候，肯定不能让 run () 方法阻塞在 select () 上，所以前面向队列中添加了一个空任务，当有任务的时候，它调用的就是 selectNow () 方法，selectNow () 方法不管有没有读取到任务都会直接返回，不会产生任何阻塞，最后，程序逻辑会走到 `isShuttingDown()` 这个判断的地方，这里有两个比较重要的方法：

- closeAll ()，关闭了什么？
- confirmShutdown ()，确定关闭了什么？

我们先来看看 `closeAll()` 这个方法，这里有个调试技巧，请看源码：

```java
// io.netty.channel.nio.NioEventLoop#closeAll
private void closeAll() {
    // 再次调用selectNow()方法
    selectAgain();
    // selector中所有的SelectionKey
    Set<SelectionKey> keys = selector.keys();
    Collection<AbstractNioChannel> channels = new ArrayList<AbstractNioChannel>(keys.size());
    for (SelectionKey k: keys) {
        // 最好在这里打个断点，因为有些NioEventLoop里面是没有绑定Channel的，所以没有Channel需要关闭
        // 在这里打个断点，NioServerSocketChannel对应的NioEventLoop肯定会到这里
        // 这里取出来的附件就是NioServerSocketChannel
        Object a = k.attachment();
        if (a instanceof AbstractNioChannel) {
            // 把要关闭的Channel加到集合中
            channels.add((AbstractNioChannel) a);
        } else {
            // NioTask当前版本没有地方使用
            k.cancel();
            @SuppressWarnings("unchecked")
            NioTask<SelectableChannel> task = (NioTask<SelectableChannel>) a;
            invokeChannelUnregistered(task, k, null);
        }
    }

    // 遍历集合
    for (AbstractNioChannel ch: channels) {
        // key，调用Channel的unsafe进行关闭
        ch.unsafe().close(ch.unsafe().voidPromise());
    }
}
```

`closeAll()` 方法中主要就是对 Channel 进行关闭，这些 Channel 的关闭最后又是调用他们的 unsafe 进行关闭的，让我们跟踪到 unsafe 里面看看到底做了哪些操作：

```java
// io.netty.channel.AbstractChannel.AbstractUnsafe#close
@Override
public final void close(final ChannelPromise promise) {
    assertEventLoop();

    ClosedChannelException closedChannelException = new ClosedChannelException();
    // 调用重载方法
    close(promise, closedChannelException, closedChannelException, false);
}
// io.netty.channel.AbstractChannel.AbstractUnsafe#close
private void close(final ChannelPromise promise, final Throwable cause,
                   final ClosedChannelException closeCause, final boolean notify) {
    if (!promise.setUncancellable()) {
        return;
    }

    // 使用closeInitiated防止重复关闭
    // closeInitiated初始值为false，所以这个大if可以跳过
    if (closeInitiated) {
        // 省略不相关代码
        return;
    }

    // 下面的逻辑只会执行一次
    closeInitiated = true;

    final boolean wasActive = isActive();
    // 写出数据时的缓存
    final ChannelOutboundBuffer outboundBuffer = this.outboundBuffer;
    // 置为空表示不允许再写出数据了
    this.outboundBuffer = null;
    // 默认为空
    Executor closeExecutor = prepareToClose();
    if (closeExecutor != null) {
        // 对于NioServerSocketChannel，默认为空，不会走到这，省略这段代码
    } else {
        try {
            // key，一看就是干正事的方法
            doClose0(promise);
        } finally {
            if (outboundBuffer != null) {
                // todo 未发送的数据将失败，为什么不让它们发送出去呢？
                outboundBuffer.failFlushed(cause, notify);
                outboundBuffer.close(closeCause);
            }
        }
        if (inFlush0) {
            invokeLater(new Runnable() {
                @Override
                public void run() {
                    // 触发channelInactive()和channelDeregister()方法
                    fireChannelInactiveAndDeregister(wasActive);
                }
            });
        } else {
            // 触发channelInactive()和channelDeregister()方法
            fireChannelInactiveAndDeregister(wasActive);
        }
    }
}
private void doClose0(ChannelPromise promise) {
    try {
        // 干正事的方法
        doClose();
        // 将closeFuture设置为已关闭
        closeFuture.setClosed();
        // 将promise设置为已成功
        safeSetSuccess(promise);
    } catch (Throwable t) {
        closeFuture.setClosed();
        safeSetFailure(promise, t);
    }
}
@Override
protected void doClose() throws Exception {
    // 关闭Java原生的Channel，我们这里为ServerSocketChannel
    javaChannel().close();
}
// io.netty.channel.nio.AbstractNioChannel#doDeregister
// 这个方法是在fireChannelInactiveAndDeregister()中调用的
@Override
protected void doDeregister() throws Exception {
    // 取消SelectionKey
    eventLoop().cancel(selectionKey());
}
```

总结一下，`close()` 的过程关闭了哪些资源：

- 写出数据的缓存置空，不允许再写出数据；
- 缓存中未发送的数据将失败；
- 关闭 Java 原生的 Channel；
- closeFuture 置为关闭状态；
- 取消 Channel 关联的 SelectionKey；
- 调用 channelInactive () 和 channelDeregister () 方法；

到这里，整个 `closeAll()` 就完了，我们再来看看 `confirmShutdown()`：

```java
protected boolean confirmShutdown() {
    // 不是正在关闭，返回false
    if (!isShuttingDown()) {
        return false;
    }

    if (!inEventLoop()) {
        throw new IllegalStateException("must be invoked from an event loop");
    }

    // 取消定时任务
    cancelScheduledTasks();

    // 设置优雅关闭服务的开始时间
    if (gracefulShutdownStartTime == 0) {
        gracefulShutdownStartTime = ScheduledFutureTask.nanoTime();
    }

    // 运行所有任务和所有shudown的钩子任务
    if (runAllTasks() || runShutdownHooks()) {
        // 有任何一个任务运行，都会进入这里
        // 已经关闭了，返回true
        if (isShutdown()) {
            return true;
        }

        // 如果静默周期为0，返回true
        if (gracefulShutdownQuietPeriod == 0) {
            return true;
        }
        // 否则添加一个空任务，返回false
        taskQueue.offer(WAKEUP_TASK);
        return false;
    }

    // 没有任何任务运行
    final long nanoTime = ScheduledFutureTask.nanoTime();

    // 如果已经关闭，或者超时了，返回true
    if (isShutdown() || nanoTime - gracefulShutdownStartTime > gracefulShutdownTimeout) {
        return true;
    }

    // 如果当前时间减去上一次运行的时间在静默周期以内
    if (nanoTime - lastExecutionTime <= gracefulShutdownQuietPeriod) {
        // 添加一个空任务，并休眠100ms
        taskQueue.offer(WAKEUP_TASK);
        try {
            Thread.sleep(100);
        } catch (InterruptedException e) {
            // Ignore
        }
        // 返回false
        return false;
    }

    // 超过了静默周期，返回true
    return true;
}
```

这里首先要明确返回值的意义，请看下面简化版的 `run()` 方法，如果 `confirmShutdown()` 返回 true，将跳出循环，那么，这个 run () 方法也就结束了，如果返回 false，将重新执行这里面的逻辑，直到返回 true。

```java
protected void run() {
    for(;;) {
        if (isShuttingDown()) {
            closeAll();
            if (confirmShutdown()) {
                return;
            }
        }
    }
}
```

静默周期的存在，会使得 Netty 尽量运行完所有的任务直到超时。如果真的没有任务了，或者超时了，会怎样呢？程序将进入下面的这个方法：

```java
// io.netty.util.concurrent.SingleThreadEventExecutor#doStartThread
private void doStartThread() {
    assert thread == null;
    // key1，这里是真正启动线程的地方
    executor.execute(new Runnable() {
        @Override
        public void run() {
            thread = Thread.currentThread();
            if (interrupted) {
                thread.interrupt();
            }

            boolean success = false;
            updateLastExecutionTime();
            try {
                // key2，这个run()方法就是之前NioEventLoop中的run()方法
                SingleThreadEventExecutor.this.run();
                success = true;
            } catch (Throwable t) {
                logger.warn("Unexpected exception from an event executor: ", t);
            } finally {
                for (;;) {
                    int oldState = state;
                    if (oldState >= ST_SHUTTING_DOWN || STATE_UPDATER.compareAndSet(
                        SingleThreadEventExecutor.this, oldState, ST_SHUTTING_DOWN)) {
                        break;
                    }
                }

                if (success && gracefulShutdownStartTime == 0) {
                    if (logger.isErrorEnabled()) {
                        logger.error("Buggy " + EventExecutor.class.getSimpleName() + " implementation; " +
                                     SingleThreadEventExecutor.class.getSimpleName() + ".confirmShutdown() must " +
                                     "be called before run() implementation terminates.");
                    }
                }

                try {
                    // 再次执行confirmShutdown()直到没有任务或者超时
                    for (;;) {
                        if (confirmShutdown()) {
                            break;
                        }
                    }

                    // 修改状态为ST_SHUTDOWN，之后不能再添加任何任务
                    for (;;) {
                        int oldState = state;
                        if (oldState >= ST_SHUTDOWN || STATE_UPDATER.compareAndSet(
                            SingleThreadEventExecutor.this, oldState, ST_SHUTDOWN)) {
                            break;
                        }
                    }

                    // 最后一次运行confirmShutdown()方法，把剩余的任务全部运行完
                    confirmShutdown();
                } finally {
                    try {
                        // 执行cleanup()方法
                        cleanup();
                    } finally {
                        // 移除所有的threadLocal
                        FastThreadLocal.removeAll();

                        // 更新状态为ST_TERMINATED
                        STATE_UPDATER.set(SingleThreadEventExecutor.this, ST_TERMINATED);
                        // threadLock标识减一，将触发某些事件
                        threadLock.countDown();
                        // 销毁的任务数，为什么还会有任务呢？
                        // 时刻考虑并发特性，其它线程有可能在上面最后一次运行confirmShutdown()之后又往当前线程添加了任务
                        int numUserTasks = drainTasks();
                        if (numUserTasks > 0 && logger.isWarnEnabled()) {
                            logger.warn("An event executor terminated with " +
                                        "non-empty task queue (" + numUserTasks + ')');
                        }
                        // key，NioEventLoop的terminationFuture已成功
                        terminationFuture.setSuccess(null);
                    }
                }
            }
        }
    });
}
```

这个方法中有几个关键的地方：

- 多次执行 confirmShutdown () 方法，确保所有的任务都尽量完成；
- 执行 cleanup () 方法，又清理什么呢？
- 移除所有的 ThreadLocal 相关的资源；
- 最终状态设置为 ST_TERMINATED；
- threadLock 的值减一，它是一个 CountDownLatch，应该触发什么事件呢？
- NioEventLoop 的 terminationFuture 已成功完成，它又如何与 NioEventLoopGroup 的 termination 扯上关系？

我们着重看一下上面打问号的三个地方，先来看看 `cleanup()` 这个方法：

```java
// io.netty.channel.nio.NioEventLoop#cleanup
@Override
protected void cleanup() {
    try {
        selector.close();
    } catch (IOException e) {
        logger.warn("Failed to close a selector.", e);
    }
}
```

其实很简单，它关闭了 selector。

再来看看 threadLock 这个变量，它的作用是什么，在上面它调用了 `countDown()` 方法，那么，一定存在某个地方有个 `await()` 方法等着我们，让我们找找看，果不其然，在下面这个地方找到了它：

```java
// io.netty.util.concurrent.SingleThreadEventExecutor#awaitTermination
@Override
public boolean awaitTermination(long timeout, TimeUnit unit) throws InterruptedException {
    ObjectUtil.checkNotNull(unit, "unit");
    if (inEventLoop()) {
        throw new IllegalStateException("cannot await termination of the current thread");
    }

    threadLock.await(timeout, unit);

    return isTerminated();
}
public boolean isTerminated() {
    return state == ST_TERMINATED;
}
```

这个方法的作用就是等待终止，它在哪里调用的呢？大胆猜测，它是在它的父亲，也就是 NioEventLoopGroup，那里调用的，找找看有没有类似的方法，还真有：

```java
// io.netty.util.concurrent.MultithreadEventExecutorGroup#awaitTermination
@Override
public boolean awaitTermination(long timeout, TimeUnit unit)
    throws InterruptedException {
    long deadline = System.nanoTime() + unit.toNanos(timeout);
    // 循环每一个NioEventLoop，等待它们终止
    loop: for (EventExecutor l: children) {
        for (;;) {
            long timeLeft = deadline - System.nanoTime();
            if (timeLeft <= 0) {
                break loop;
            }
            if (l.awaitTermination(timeLeft, TimeUnit.NANOSECONDS)) {
                break;
            }
        }
    }
    // 返回整个Group的终止状态
    return isTerminated();
}
```

那么，这个 Group 的等待终止方法又是在哪里调用的呢？源码中并没有调用的地方，它其实是留给用户自己调用的，比如，我们可以在主线程中调用这个方法，判断 Group 完全终止后做些什么事情。

最后，我们再来看看父亲的 terminationFuture 怎么跟孩子的 terminationFuture 关联起来的。

通过前面的分析，我们知道，NioEventLoopGroup 的 terminationFuture 是在其 shutdownGracefully () 中返回的，而 NioEventLoop 的 terminationFuture 是在其 shutdownGracefully () 方法中返回的，且它们的返回值并没有显式地联系起来，那么，它们到底有没有联系呢？又是怎样联系起来的呢？

让我们先找一下 NioEventLoop 的 terminationFuture 在何时置为完成的，通过上面的分析，发现是在 doStartThread () 这个方法中，当所有资源全部释放完毕之后，将其 terminationFuture 置为完成的，那么，父亲的 terminationFuture 正常来说应该需要等到所有孩子的 terminationFuture 完成之后才能置为完成，它在哪里呢？这个有点难找，最后，找到是在下面这个构造方法里面：

```java
protected MultithreadEventExecutorGroup(int nThreads, Executor executor,
                                        EventExecutorChooserFactory chooserFactory, Object... args) {
    // 省略其他代码

    // 创建一个监听器
    final FutureListener<Object> terminationListener = new FutureListener<Object>() {
        @Override
        public void operationComplete(Future<Object> future) throws Exception {
            // 每个孩子完成时，terminatedChildren加一
            // 如果等于孩子数量，说明全部完成了
            if (terminatedChildren.incrementAndGet() == children.length) {
                terminationFuture.setSuccess(null);
            }
        }
    };

    // 给每个孩子都添加上这个监听器
    for (EventExecutor e: children) {
        e.terminationFuture().addListener(terminationListener);
    }

    // 省略其他代码
}
```

在 `MultithreadEventExecutorGroup` 的构造方法中，给每个孩子都添加了一个监听器，当孩子完成时，完成数量加一，直到等于孩子数量，则把父亲的 terminationFuture 设置为已成功完成，所以，两者的 terminationFuture 是有关系的。

等等，其实还没完，细心的同学会发现，中间有一个注释我打了一个 `todo` 标识：

```java
// io.netty.channel.AbstractChannel.AbstractUnsafe#close
private void close(final ChannelPromise promise, final Throwable cause,
                   final ClosedChannelException closeCause, final boolean notify) {
    // 省略其他代码
    if (closeExecutor != null) {
        // 对于NioServerSocketChannel，默认为空，不会走到这，省略这段代码
    } else {
        try {
            // key，一看就是干正事的方法
            doClose0(promise);
        } finally {
            if (outboundBuffer != null) {
                // todo 未发送的数据将失败，为什么不让它们发送出去呢？
                outboundBuffer.failFlushed(cause, notify);
                outboundBuffer.close(closeCause);
            }
        }
    }
    // 省略其他代码
}
```

为什么 “优雅关闭”，却不把缓存中的消息发送出去呢？我百思不得其解，为了验证源码没有错，我们可以做如下实验：

将 EchoServerHandler 中 channelReadComplete () 方法中的 `ctx.flush()` 方法注释掉，然后取消所有断点，只保留 main () 方法中 `bossGroup.shutdownGracefully()` 处的打点，启动服务器，当断点停留在此处的时候，使用 XSHELL 连接到服务端，并发送 “12345” 字符串，此时，按 F9 放开断点，服务端将优雅停机，观察客户端是否收到 “12345” 这条消息：
![图片描述](https://img1.sycdn.imooc.com/5f1f81a800018bcf05630274.png)

很遗憾，客户端确实没有收到 “12345” 这条消息，说明，我们源码读得没错，Netty 优雅停机时确实不会把未发送的消息继续发送完。

好了，到这里，今天所有的问题就都解决完了，让我们来总结一下 “优雅关闭服务” 的过程：

1. 优雅关闭服务分成两个部分，调用 shutdownGracefully ()，只是修改一些状态和属性的值，并唤醒 NioEventLoop 中的 select () 方法；
2. 真正的处理逻辑在 NioEventLoop 的 run () 方法中；
3. 关闭的关键方法又分为 closeAll () 和 confirmShutdown () 两个方法；
4. closeAll () 中主要是对 Channel 的关闭，跟 Channel 相关的资源释放都在这里，比如缓存消息的失败、SelectionKey 的取消、Java 原生 Channel 的关闭等；
5. confirmShutdown () 中主要是对队列中的任务或者钩子任务进行处理，主要是通过一个叫做静默周期的参数来控制尽量执行完所有任务，但是，也不能无限期等待，所以，还有一个超时时间进行控制；
6. 接着，程序的逻辑来到了真正启动线程的地方，也就是 doStartThread () 方法，它里面有个非常重要的方法 cleanup ()，并清理了所有 ThreadLocal 相关的资源，最后把 NioEventLoop 的状态设置为 ST_TERMINATED；
7. cleanup () 方法中主要是对 Selector 进行关闭；
8. 然后，我们分析了 NioEventLoopGroup 与 NioEventLoop 在程序终止时相关的联系，包括 threadLock 和 terminationFuture 等；
9. 最后，我们验证了 Netty 中的优雅关闭服务的时候确实不会真正发送缓存中的内容。



 ### 后记

今天的代码量有点大，且很绕，其中牵涉到很多的线程切换、ChannelFuture 的状态切换等，并不像之前的源码剖析那么顺畅，请大家保持耐心，文章只能起到引领的作用，具体的源码还是要大家亲自跑一遍才能理解里面的弯弯绕绕。

至此，从数据流向的角度来剖析源码的全部章节就讲完了，从下一章开始，我们将从 Netty 核心知识的角度来剖析源码，彼时，我们将会讲解很多 Java 中的高阶技巧，敬请期待！



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f1f81ee0001cd8416051238.png)




<div style="page-break-after:always;"></div>

 # 第 3 章 源码剖析——核心知识

 ## 17 如何从源码的角度深入剖析ByteBuffer


![img](https://img2.sycdn.imooc.com/5f0595e70001d1d306400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)生活的理想，就是为了理想的生活。——张闻天![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

前面的章节，我们一起从数据流向的角度剖析了 Netty 的源码，包括服务的启动、接收新的连接或数据、写出数据、关闭服务等。

然而，从数据流向的角度只能窥见 Netty 很小一部分的源码，比如，你只看见了调用一个方法就能创建符合要求的 ByteBuf 却不知为何如此简单，你只看见了 Netty 使用了线程池却不知线程池用的是什么队列，你只看见了 Netty 到处都在使用 Promise 却不知 Promise 为何物。

所以，从本节开始，我们将从 Netty 核心知识的角度来剖析源码，同时，我们也会一起学习很多 Java 中的高阶技巧。

在前面的章节，我们多多少少地介绍过一些 ByteBuffer、ByteBuf 相关的知识，但是它们还不全面，所以，本节，我想先从 Java 原生的 ByteBuffer 入手，来更好地过渡到 Netty 的源码设计。



 ### 问题

我们知道，Netty 之所以如此高效，很大一部分原因得益于其对直接内存的高效使用，所以，今天，我想问：

1. Java 中的 ByteBuffer 有直接内存的实现吗？
2. Java 中如何使用直接内存？又如何释放直接内存呢？
3. Java 中 ByteBuffer 的直接内存实现又是如何管理直接内存的？

好了，让我们带着这些问题进入今天的探索吧。



 ### Buffer 的分类

经过前面的学习，我们知道，Buffer 按照不同的维度有不同的分类，大体上有两种主要的维度，按照数据类型分为 ByteBuffer、CharBuffer、ShortBuffer、IntBuffer、LongBuffer、FloatBuffer、DoubleBuffer 等，按照内存实现可以分为堆内存实现和直接内存实现。其实，还有另一种不太常见的维度，按照读写的维度分为只读和可读写，一般来说，只读的 Buffer 后面以 `R` 结尾，比如 HeapByteBufferR，这种比较少见，有兴趣的同学可以自己看看相关的源码。

今天我们的主角是堆内存实现和直接内存实现，它们分别是怎么实现的呢？有什么区别吗？

不过，在正式介绍之前，我想讲另外一个非常有意思的类，我把它称作 Java 中的魔法类 ——Unsafe。



 ### 不安全的 Unsafe

看过并发集合或者原子类源码的同学，应该对 Unsafe 这个类印象比较深刻，像我们经常使用的 `CAS` 操作，底层就是使用 Unsafe 来实现的，比如，AtomicInteger 中的 compareAndSet () 方法：

```java
public final boolean compareAndSet(int expect, int update) {
    return unsafe.compareAndSwapInt(this, valueOffset, expect, update);
}
```

然而，Unsafe 的功能远远不止 `CAS` 这一种操作，有兴趣的同学可以看看这篇文章【[死磕 java 魔法类之 Unsafe 解析](https://mp.weixin.qq.com/s/0s-u-MysppIaIHVrshp9fA)】，今天，我们再介绍一种 Unsafe 不太常见的功能 —— 操作直接内存。

Unsafe 操作直接内存是通过下面几个方法实现的：

```java
// 分配内存
public native long allocateMemory(long var1);
// 释放内存
public native void freeMemory(long var1);
// 设置内存值
public native void setMemory(Object var1, long var2, long var4, byte var6);
// 设置某种类型的值，比如putInt()
public native void putXxx(long var1, xxx var3);
// 获取某种类型的值，比如getInt()
public native xxx getXxx(long var1);
```

比如，我们可以使用 Unsafe 来实现一个直接内存实现的 `int` 数组。

```java
public class DirectIntArray {
    // 一个int等于4个字节
    private static final int INT = 4;
    private long size;
    private long address;

    private static Unsafe unsafe;
    static {
        try {
            // Unsafe类有权限访问控制，只能通过反射获取其实例
            Field f = Unsafe.class.getDeclaredField("theUnsafe");
            f.setAccessible(true);
            unsafe = (Unsafe) f.get(null);
        } catch (NoSuchFieldException e) {
            e.printStackTrace();
        } catch (IllegalAccessException e) {
            e.printStackTrace();
        }
    }

    public DirectIntArray(long size) {
        this.size = size;
        // 参数字节数
        address = unsafe.allocateMemory(size * INT);
    }

    // 获取某位置的值
    public int get(long i) {
        if (i >= size) {
            throw new ArrayIndexOutOfBoundsException();
        }
        return unsafe.getInt(address + i * INT);
    }

    // 设置某位置的值
    public void set(long i, int value) {
        if (i >= size) {
            throw new ArrayIndexOutOfBoundsException();
        }
        unsafe.putInt(address + i * INT, value);
    }

    // 数组大小
    public long size() {
        return size;
    }

    // 释放内存
    public void freeMemory() {
        unsafe.freeMemory(address);
    }

    public static void main(String[] args) {
        // 创建数组并赋值
        DirectIntArray array = new DirectIntArray(4);
        array.set(0, 1);
        array.set(1, 2);
        array.set(2, 3);
        array.set(3, 4);
        // 下面这行数组越界了
//        array.set(5, 5);

        int sum = 0;
        for (int i = 0; i < array.size(); i++) {
            sum += array.get(i);
        }
        // 打印10
        System.out.println(sum);

        // 最后别忘记释放内存
        array.freeMemory();
    }
}
```

最后，一定别忘了释放内存，这是操作直接内存的一个非常 “不安全的” 地方，谨记！

好了，有了上面的介绍，相信你对 Java 中如何操作直接内存一定有了非常清晰的认识，其实，也是非常简单的。

下面，我们就正式地来揭开 Java 中堆内存和直接内存两种方式实现的 ByteBuffer 的神秘面纱。



 ### 宏观分析 ByteBuffer

> 学习源码一般遵循着先宏观再微观的原则。宏观上，一般先看继承体系，类的基本结构等，通过这种方式一般能找到一到两个突破口。微观上，一般根据宏观找到的突破口，进入调试，调试，调试。很多同学看源码喜欢干看，其实是不对的，一定要调试，不调试就无法掌握细节。
> ![图片描述](https://img1.sycdn.imooc.com/5f1f821400012d9f04500487.png)

从继承体系上，ByteBuffer 是一个抽象类，它继承自 Buffer 抽象类，它有两个主要实现类 ——HeapByteBuffer 和 DirectByteBuffer，其中 DirectByteBuffer 和 ByteBuffer 之间还有一个 MappedByteBuffer，另外，这两个实现类分别还有自己的只读模式，即 HeapByteBufferR 和 DirectByteBufferR。

> MappedByteBuffer 是做什么的呢？本节的知识点不涉及到这个类，有兴趣的同学可以自己探索。

从类的基本结构上，ByteBuffer 包含两个非常重要的方法：

```java
// 创建一个直接内存实现的ByteBuffer
public static ByteBuffer allocateDirect(int capacity) {
    return new DirectByteBuffer(capacity);
}
// 创建一个堆内存实现的ByteBuffer
public static ByteBuffer allocate(int capacity) {
    if (capacity < 0)
        throw new IllegalArgumentException();
    return new HeapByteBuffer(capacity, capacity);
}
```

这两个方法就是我们微观分析时需要使用到的突破口。

另外，还包含一些操作 ByteBuffer 的方法，主要是 put () 和 get ()，以及切片、子集等，与数组或者集合 list 的操作方法比较类似，这里就不一一列举了。

有了上面的突破口，我们就可以正式进入微观分析阶段了，即调试。



 ### 微观分析 ByteBuffer



 #### 堆内存实现的 ByteBuffer——HeapByteBuffer

既然要调试，当然要写调试用例啦，我这里也准备了一个调试用例：

```java
public class ByteBufferTest {
    public static void main(String[] args) {
        // 1. 创建一个堆内存实现的ByteBuffer
        ByteBuffer buffer = ByteBuffer.allocate(12);
        // 2. 写入值
        buffer.putInt(1);
        buffer.putInt(2);
        buffer.putInt(3);

        // 3. 切换为读模式
        buffer.flip();

        // 4. 读取值
        System.out.println(buffer.getInt());
        System.out.println(buffer.getInt());
        System.out.println(buffer.getInt());
    }
}
```

OK，我们要开始调试了，你准备好了么？！Let’s go!

让我们把断点打在 `ByteBuffer buffer = ByteBuffer.allocate(12);` 这行，跟踪进去：

```java
// 1. 创建堆内存实现的ByteBuffer
public static ByteBuffer allocate(int capacity) {
    if (capacity < 0)
        throw new IllegalArgumentException();
    return new HeapByteBuffer(capacity, capacity);
}
// 2. HeapByteBuffer的构造方法
HeapByteBuffer(int cap, int lim) {            // package-private
    // lim = cap = 12
    // 创建了一个12大小的byte数组
    // 调用父构造方法
    super(-1, 0, lim, cap, new byte[cap], 0);
}
// 3. ByteBuffer的构造方法
ByteBuffer(int mark, int pos, int lim, int cap,   // package-private
           byte[] hb, int offset)
{
    // 调用父构造方法
    // pos = 0，默认创建的就是写模式
    // lim = cap = 12
    super(mark, pos, lim, cap);
    // byte数组hb（heap buffer），为上面传过来的new byte[cap]
    this.hb = hb;
    this.offset = offset;
}
// 4. Buffer的构造方法
Buffer(int mark, int pos, int lim, int cap) {       // package-private
    if (cap < 0)
        throw new IllegalArgumentException("Negative capacity: " + cap);
    // 三个非常重要的变量：capacity、limit、position
    this.capacity = cap;
    limit(lim);
    position(pos);
    if (mark >= 0) {
        if (mark > pos)
            throw new IllegalArgumentException("mark > position: ("
                                               + mark + " > " + pos + ")");
        this.mark = mark;
    }
}
```

整个创建的过程非常简单，主要包含以下逻辑：

1. 创建了一个 byte 数组保存在 hb 这个变量中；
2. 给几个重要的变量赋值，比如 capacity、limit、position，还有一个 mark，感兴趣的同学可以自己看看这个变量的作用；
3. 默认创建的 ByteBuffer 为写模式，因为 position 从 0 开始且 capacity=limit = 数组大小；

还记得写模式吗？还记得 capacity、limit、position 这三个重要的属性吗？让我们把前面的图再拿出来回顾一下。
![图片描述](https://img1.sycdn.imooc.com/5f1f83320001a6d110300419.png)

> 在上面的左图中，limit=capacity=8，表示的是数组的大小，而数组的下标是从 0 开始的，所以这里指向了数组最大位置的下一个位置。position 表示的是下一次写入的位置，从 0 开始，与数组的下标保持一致，所以，这里的 position 最大只能等于 8，也就是 limit 的值，当等于 8 时再写入，就溢出了（8 这个位置不会写入数据）。

OK，到这里 ByteBuffer 我们就创建好了，所谓堆内存的实现方式，就是使用的 Java 自带的 byte 数组来实现的，让我们再来看看写入 putInt () 这个方法是如何实现的。

```java
// 写入一个int类型的数值
public ByteBuffer putInt(int x) {
    // 调用Bits工具类的putInt()方法，Bits是位的意思
    // 堆内存的实现中使用大端法来存储数据
    Bits.putInt(this, ix(nextPutIndex(4)), x, bigEndian);
    return this;
}
// 移动position到下一个位置
// 因为一个int占4个字节，所以这里往后移动4位
final int nextPutIndex(int nb) {                    // package-private
    // 判断有没有越界
    if (limit - position < nb)
        throw new BufferOverflowException();
    int p = position;
    position += nb;
    // 注意，这里返回的是移动前的位置，初始值为0
    return p;
}
// 计算写入的偏移量，初始值为0
protected int ix(int i) {
    return i + offset;
}
// java.nio.Bits#putInt(java.nio.ByteBuffer, int, int, boolean)
static void putInt(ByteBuffer bb, int bi, int x, boolean bigEndian) {
    // 堆内存使用的是大端法，更符合人们的习惯
    if (bigEndian)
        // 大端法
        putIntB(bb, bi, x);
    else
        putIntL(bb, bi, x);
}
// java.nio.Bits#putIntB(java.nio.ByteBuffer, int, int)
static void putIntB(ByteBuffer bb, int bi, int x) {
    // 把一个int拆分成4个byte，分别写入
    // int3(int x) { return (byte)(x >> 24); }
    bb._put(bi    , int3(x));
    // int2(int x) { return (byte)(x >> 16); }
    bb._put(bi + 1, int2(x));
    // int1(int x) { return (byte)(x >>  8); }
    bb._put(bi + 2, int1(x));
    // int0(int x) { return (byte)(x      ); }
    bb._put(bi + 3, int0(x));
}
// java.nio.HeapByteBuffer#_put
void _put(int i, byte b) {                  // package-private
    // 最终变成了修改byte数组
    hb[i] = b;
}
```

写入方法无非就是根据当前 position 的位置往后写入一个 int 大小的数据，写入的时候会把 int 拆分成 4 个 byte 分别写入，而最终其实就是修改前面创建的 byte 数组。

OK，同样地，读取方法应该就是先根据当前 position 计算读取的偏移量，再从数组中读取 4 个字节的数据，最后再拼装成一个 int 类型返回。这块的代码相对来说都比较简单，我们就不一一细看了。

综上所述，HeapByteBuffer 内部使用 byte 数组来存储数据，并根据 position 来写入或者读取数据，既然使用的是 Java 中的类型，自然使用的是堆内存。



 #### 直接内存实现的 ByteBuffer——DirectByteBuffer

上面我们简单介绍了 HeapByteBuffer，它主要是使用 byte 数组来实现的，那么，DirectByteBuffer 是如何实现的呢？通过上面我们讲解的 Unsafe，结合 HeapByteBuffer 的实现，你能自己实现一个 DirectByteBuffer 吗，就像直接内存实现的 DirectIntArray 一样？

建议先想好这几个问题，再接着看下面的源码分析。

同样地，我们还是使用上面的调试用例，只不过改动一个方法：

```java
public class ByteBufferTest {
    public static void main(String[] args) {
        // 创建一个直接内存实现的ByteBuffer
        ByteBuffer buffer = ByteBuffer.allocateDirect(12);
        // 写入值
        buffer.putInt(1);
        buffer.putInt(2);
        buffer.putInt(3);

        // 切换为读模式
        buffer.flip();

        // 读取值
        System.out.println(buffer.getInt());
        System.out.println(buffer.getInt());
        System.out.println(buffer.getInt());
    }
}
```

问题无处不在，在 DirectIntArray 的使用中，我们是手动调用 freeMemory () 来释放内存的，DirectByteBuffer 的使用过程中如何释放内存，保证内存不泄漏？

在 `ByteBuffer buffer = ByteBuffer.allocateDirect(12);` 这行打一个断点，一步一步跟踪进去：

```java
public static ByteBuffer allocateDirect(int capacity) {
    // 创建直接内存实现的ByteBuffer
    return new DirectByteBuffer(capacity);
}
DirectByteBuffer(int cap) {                   // package-private
    // 调用父构造方法，设置position/limit/capacity/mark这几个值
    // 与HeapByteBuffer类似，只不过没有创建hb那个数组
    super(-1, 0, cap, cap);
    // 是否页对齐，默认为否
    boolean pa = VM.isDirectMemoryPageAligned();
    // 每页大小
    int ps = Bits.pageSize();
    long size = Math.max(1L, (long)cap + (pa ? ps : 0));
    // 先预订内存，如果内存不够，会进行清理，并尝试几次
    Bits.reserveMemory(size, cap);

    long base = 0;
    try {
        // key1，重点来了，调用unsafe的allocateMemory()方法来分配内存
        base = unsafe.allocateMemory(size);
    } catch (OutOfMemoryError x) {
        Bits.unreserveMemory(size, cap);
        throw x;
    }
    // key2，初始化这片内存的值为0
    unsafe.setMemory(base, size, (byte) 0);
    // 根据是否页对齐计算实际的地址
    if (pa && (base % ps != 0)) {
        // Round up to page boundary
        address = base + ps - (base & (ps - 1));
    } else {
        // 默认不页对齐，所以地址就等于allocateMemory()返回的地址
        address = base;
    }
    // key3，Cleaner是什么？干什么的？有什么作用？
    cleaner = Cleaner.create(this, new Deallocator(base, size, cap));
    att = null;
}
```

> 看源码有个准则，一定要学会抓重点，对于看不懂的东西可以先记下并跳过，比如，DirectByteBuffer 的构造方法中其实牵涉到很多高阶知识，像页对齐、弱引用 / 虚引用（在 reserveMemory () 方法中）等相关的东西，这部分东西非常复杂且难以理解，先记下来，等把整体流程理清楚了，再回头深究这一块的东西，其实也是遵循着从宏观到微观的方法论，宏观使你了解整体流程，微观才能使你的知识体系得到升华。

好了，针对 DirectByteBuffer 的构造方法，整体流程与 HeapByteBuffer 是比较类似的，只不过不是创建一个 byte 数组来保存数据，而是调用 unsafe 来分配内存并保存数据，总结下来有三个非常重要的地方：

1. `base = unsafe.allocateMemory(size);`，调用 unsafe 的 allocateMemory () 方法来分配内存
2. `unsafe.setMemory(base, size, (byte) 0);`，初始化这片内存的值为 0，为什么要进行初始化？如果不初始化，之前这块内存可能被别的程序使用过，会残留一些数据，对当前的数据造成影响，这是我们写 DirectIntArray 没有考虑到的。
3. `cleaner = Cleaner.create(this, new Deallocator(base, size, cap));`，这行代码是干什么的？看着似乎跟清理内存有关，这个我们等会再看，先来看看如何写入数据和读取数据。

经过上面的折腾，我们终于创建好了一个 DirectByteBuffer，接下来，我们来一起看看如何写入数据和读取数据吧。

写入数据调用的是 `buffer.putInt(1);` 这个方法，同样地，调试跟踪进去：

```java
// 写入一个int类型的数值
public ByteBuffer putInt(int x) {
    // 1 << 2 = 4，一个int占4个字节
    putInt(ix(nextPutIndex((1 << 2))), x);
    return this;
}
// 计算下一个position的位置并返回当前position的值
final int nextPutIndex(int nb) {                    // package-private
    if (limit - position < nb)
        throw new BufferOverflowException();
    int p = position;
    position += nb;
    // 返回移动前的值
    return p;
}
// 计算偏移量，在address的基础上加上position的值
private long ix(int i) {
    return address + ((long)i << 0);
}
private ByteBuffer putInt(long a, int x) {
    // unaligned不是之前讲的那个页对齐
    // 这里是跟CPU架构相关的一个参数
    if (unaligned) {
        int y = (x);
        // 在windows系统中内存值使用的是小端法，所以直接内存使用的是小端法
        // 因此，这里要转换一下
        // 调用unsafe的putInt()方法修改直接内存中对应地址的值
        unsafe.putInt(a, (nativeByteOrder ? y : Bits.swap(y)));
    } else {
        Bits.putInt(a, x, bigEndian);
    }
    return this;
}
```

写入方法无非就是根据当前 position 的位置往后写入一个 int 大小的数据，写入的时候会调用 unsafe 的 putInt () 方法在内存中对应地址的位置直接写入值，而不是像 HeapByteBuffer 那样修改 byte 数组对应位置的值。

OK，同样地，读取方法应该就是先根据当前 position 计算读取的偏移地址，再调用 unsafe 的 getInt () 方法在内存中对应地址的位置读取一个 int 大小的数据，这块的代码相对来说都比较简单，我们就不一一细看了。

综上所述，DirectByteBuffer 底层使用的是 Unsafe 来分配一块直接内存，并在写入数据和读取数据的时候使用 Unsafe 对应的方法来操作直接内存，了解了其原理，是不是也很简单呢？

好了，到这里 DirectByteBuffer 的基本原理我们已经看透 80% 了，为什么是 80% 呢？

还记得前面我们使用 DirectIntArray 的时候最后要调用 freeMemory () 来清理内存吗？

是的，在 DirectByteBuffer 这里，我们并没有看到清理内存的相关代码，那肯定是有问题的，哎不对，上面好像有个 Cleaner，看着像是清理什么东西，那么，它是不是清理内存的呢？让我们再仔细研究一下。

```java
cleaner = Cleaner.create(this, new Deallocator(base, size, cap));
```

这里新建了一个叫作 `Deallocator` 的对象，所谓 `Deallocator`，它等于 `De + allocator`，在英语中，`De` 前缀一般表示相反的意思，比如，increse 是升高的意思，而 decrease 是下降的意思，所以，allocate 是分配的意思，deallocate 应该是解除分配的意思，也就是清理的意思，变成名词就是 deallocator，可以理解为清理器的意思。

到底是不是我们理解的意思呢？直接上代码：

```java
private static class Deallocator implements Runnable {

    private static Unsafe unsafe = Unsafe.getUnsafe();

    private long address;
    private long size;
    private int capacity;

    // 构造方法传入allocate的时候返回的地址，以及容量等参数
    private Deallocator(long address, long size, int capacity) {
        assert (address != 0);
        this.address = address;
        this.size = size;
        this.capacity = capacity;
    }

    public void run() {
        if (address == 0) {
            // Paranoia
            return;
        }
        // 调用unsafe的freeMemory释放内存
        unsafe.freeMemory(address);
        address = 0;
        // 取消预订的内存
        Bits.unreserveMemory(size, capacity);
    }

}
```

Deallocator 实现了 Runnable 接口，Runnable 接口是什么？大家都比较熟悉了，它是线程执行的任务。那么，这个任务是在什么时候执行的呢？又干了什么呢？我们先来看第二个问题，从上面的代码中可以看到它调用了 unsafe 的 freeMemory () 方法来释放内存，所以，这个任务的作用就是清理内存。

但是，这个任务又是在什么时候执行的呢？或者说，在哪里执行的呢？还是回到创建的地方，也就是下面这行代码：

```java
cleaner = Cleaner.create(this, new Deallocator(base, size, cap));
```

这里创建了一个 Cleaner 的对象，跟踪进去看看 Cleaner 类（前方高能，请系好安全带！）：

```java
// 虚引用
public class Cleaner extends PhantomReference<Object> {
    private static final ReferenceQueue<Object> dummyQueue = new ReferenceQueue();
    private static Cleaner first = null;
    private Cleaner next = null;
    private Cleaner prev = null;
    private final Runnable thunk;

    private static synchronized Cleaner add(Cleaner var0) {
        // 省略部分代码，将var0添加到Cleaner链表中
        return var0;
    }

    private static synchronized boolean remove(Cleaner var0) {
        // 省略部分代码，将var0从链表中移除
    }

    private Cleaner(Object var1, Runnable var2) {
        // 调用父类的构造方法
        // ★Cleaner这个虚引用引用的对象是var1，也就是Deallocaotr对象
        // 先记住上面这句话！！！
        super(var1, dummyQueue);
        // var2即上面创建的Deallocator对象
        this.thunk = var2;
    }

    public static Cleaner create(Object var0, Runnable var1) {
        // 创建一个Cleaner对象，并返回这个对象
        // 它里面封装了一个任务
        return var1 == null ? null : add(new Cleaner(var0, var1));
    }

    public void clean() {
        // 从链表中移除当前对象
        if (remove(this)) {
            try {
                // 执行任务
                this.thunk.run();
            } catch (final Throwable var2) {
                AccessController.doPrivileged(new PrivilegedAction<Void>() {
                    public Void run() {
                        if (System.err != null) {
                            (new Error("Cleaner terminated abnormally", var2)).printStackTrace();
                        }

                        System.exit(1);
                        return null;
                    }
                });
            }

        }
    }
}
```

可见，Cleaner 继承自一个叫作 PhantomReference 的类，PhantomReference 是什么呢？

PhantomReference 翻译过来叫作虚引用，它还有三个兄弟，一个叫作强引用，一个叫作软引用，还有一个叫作弱引用。

**强引用**，使用最普遍的引用。如果一个对象具有强引用，它绝对不会被 gc 回收。如果内存空间不足了，gc 宁愿抛出 OutOfMemoryError，也不是会回收具有强引用的对象。

**软引用**（SoftReference），如果一个对象只具有软引用，则内存空间足够时不会回收它，但内存空间不够时就会回收这部分对象。只要这个具有软引用对象没有被回收，程序就可以正常使用。因此，可以使用软引用来做缓存使用，有效减少 OOM 的出现。

**弱引用**（WeakReference），如果一个对象只具有弱引用，则不管内存空间够不够，当 gc 扫描到它时就会回收它。因此，弱引用也可用来作为缓存使用。

**虚引用**（PhantomReference），如果一个对象只具有虚引用，那么它就和没有任何引用一样，任何时候都可能被 gc 回收。虚引用主要用来跟踪对象被垃圾回收的活动。

让我们总结一下这四个兄弟的区别：

| 类型   | 被回收时间     | 用途                     | 举例                          |
| :----- | :------------- | :----------------------- | :---------------------------- |
| 强引用 | 不会被回收     | 对象正常状态             | Object object = new Object(); |
| 软引用 | 内存不足时     | 缓存                     | 很少使用                      |
| 弱引用 | 执行垃圾回收时 | 缓存                     | WeakHashMap、TheadLocal       |
| 虚引用 | 任何时候       | 跟踪对象被垃圾回收的活动 | Cleaner                       |

软（弱、虚）引用通常和一个引用队列（ReferenceQueue）一起使用，当 gc 回收这个软（弱、虚）引用引用的对象时，会把这个软（弱、虚）引用本身放到这个引用队列中。（先记住这句话）

好了，关于强软弱虚引用的概念就介绍到这里，通过上面 Cleaner 的源码，我们发现，Deallocator 的 run () 方法实际上是在 Cleaner 的 clean () 方法中调用的，那么，这个 clean () 方法又是在哪里调用的呢？其实，它是在 Reference 中调用的，Reference 中有一个线程会一直扫描这些软弱虚引用，可以先看我下面删减后的代码，再看其完整代码：

```java
public abstract class Reference<T> {
    // 引用的对象
    private T referent;         /* Treated specially by GC */
    // 引用队列
    volatile ReferenceQueue<? super T> queue;
    
    @SuppressWarnings("rawtypes")
    volatile Reference next;

    // JVM内部使用，当引用的对象被gc清理时，放到这里
    transient private Reference<T> discovered;  /* used by VM */

    static private class Lock { }
    private static Lock lock = new Lock();

    // 通过discover来为其赋值
    private static Reference<Object> pending = null;

    // 处理线程
    private static class ReferenceHandler extends Thread {
        // 省略部分代码

        public void run() {
            // 死循环
            while (true) {
                tryHandlePending(true);
            }
        }
    }

    static boolean tryHandlePending(boolean waitForNotify) {
        Reference<Object> r;
        Cleaner c;
        try {
            synchronized (lock) {
                if (pending != null) {
                    r = pending;
                    // 判断是否为Cleaner对象
                    c = r instanceof Cleaner ? (Cleaner) r : null;
                    // pending从discovered赋值而来
                    pending = r.discovered;
                    r.discovered = null;
                } else {
                    if (waitForNotify) {
                        lock.wait();
                    }
                    return waitForNotify;
                }
            }
        } catch (OutOfMemoryError x) {
            Thread.yield();
            return true;
        } catch (InterruptedException x) {
            return true;
        }

        // 如果是Cleaner对象，则执行其clean()方法
        if (c != null) {
            c.clean();
            return true;
        }

        ReferenceQueue<? super Object> q = r.queue;
        // 入队
        if (q != ReferenceQueue.NULL) q.enqueue(r);
        return true;
    }

    // 在静态块中创建上述线程
    static {
        ThreadGroup tg = Thread.currentThread().getThreadGroup();
        for (ThreadGroup tgn = tg;
             tgn != null;
             tg = tgn, tgn = tg.getParent());
        // 创建这个线程
        Thread handler = new ReferenceHandler(tg, "Reference Handler");
        handler.setPriority(Thread.MAX_PRIORITY);
        // 守护线程
        handler.setDaemon(true);
        // 启动线程
        handler.start();

        SharedSecrets.setJavaLangRefAccess(new JavaLangRefAccess() {
            @Override
            public boolean tryHandlePendingReference() {
                return tryHandlePending(false);
            }
        });
    }

    // 省略其他代码

}
```

通过上面的分析，我们总结一下虚引用及其引用的对象被清理的过程：

1. 引用的对象被 gc 清理；
2. 虚引用进入 discovered 队列；
3. discovered 队列中的虚引用被赋值给 pending 队列；
4. 如果虚引用是 Cleaner，则执行其 clean () 方法；
5. 如果引用队列不为空，则进入引用队列 ReferenceQueue；

比如，我们拿 DirectByteBuffer 为例，来描述一下整个过程：

1. 首先，DirectByteBuffer 本身是一个堆内存中的对象，它里面有一个属性叫作 address，address 保存的是直接内存的地址，操作 DirectByteBuffer 的时候实际上是对 address 指向地址的操作，当然，这种操作是通过 unsafe 来执行的；
2. 其次，Cleaner 是一个虚引用，它引用的对象是 DirectByteBuffer，并注册了 Deallocator 这个任务，是通过 `Cleaner.create(this, new Deallocator(base, size, cap))` 这行代码实现的；
3. 再次，当 DirectByteBuffer 不具有强引用时，随时都可能被 gc 从堆内存清理掉，此时，JVM 会把上面绑定的 Cleaner 对象放到 Reference 的 discovered 队列上；
4. 然后，Reference 中的线程 ReferenceHandler 不断轮循，把 discovered 队列中的虚引用赋值到 pending 队列中，并且，这个虚引用如果是 Cleaner 对象，会执行它的 clean () 方法，且会把这个虚引用加入到 ReferenceQueue 队列中；
5. 最后，执行 clean () 方法的时候将会执行到 Deallocator 的 run () 方法，在这里调用 unsafe 的 freeMemory () 清理掉直接内存；

整个过程就是这样，比较绕，且牵涉到很多虚（软弱）引用相关的知识点，望多多体会。

其实，总结来说，在 DirectByteBuffer 的使用过程中，直接内存的回收还是 gc 控制的，只不过是一种间接控制。

好了，到这里 DirectByteBuffer 的整个源码就剖析完成了，你有没有 Get 到呢？



 ### 后记

本节，我们从宏观和微观两个角度剖析了 ByteBuffer 在 Java 中的实现方式，并从源码层面对 HeapByteBuffer 和 DirectByteBuffer 做了非常深入的挖掘，特别是 DirectByteBuffer，它牵涉到很多 Java 中的高阶知识，相信通过本节的学习，你一定能够见识到很多未曾见过的知识，并且会发现很多自己感兴趣的点，比如大端法小端法、Unsafe、强软弱虚引用等，如果你对哪个点特别感兴趣，请死磕到底。

既然 Java 原生的 DirectByteBuffer 都已经这么牛 X 了，Netty 还能对它做出哪些更牛 X 的改造呢？下一节，我们不见不散。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f1f835500016b8119762146.png)





<div style="page-break-after:always;"></div>

 ## 18 Netty的ByteBuf是如何支持堆内存非池化实现的


![img](https://img1.sycdn.imooc.com/5f0595f20001aed506400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)虚心使人进步，骄傲使人落后。——毛泽东![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起再次深入学习了 Java 原生的 ByteBuffer，并从源码级别对其进行了完整的剖析，ByteBuffer 从实现方式上分成 HeapByteBuffer 和 DirectByteBuffer 两种内存实现方式，HeapByteBuffer 底层使用 byte 数组存储数据，DirectByteBuffer 底层使用 unsafe 操作直接内存。通过源码的学习，我们还进一步掌握了很多 Java 中的高阶知识，有了很大的收获。

如果说 Java 中 ByteBuffer 的实现方式用精巧来形容，那么，Netty 中的 ByteBuf 可以用精妙来形式，它有哪些妙之处呢？我想用一词概括它的精妙之处 —— 高效易用。



 ### 问题

通过上一节的学习，我们知道，Java 原生的 Buffer 有三种不同的分类方式：按数据类型、按内存实现方式、按读写方式，可以分成不同的 Buffer。那么，今天，我想问：

1. Netty 中的 ByteBuf 有没有兄弟类呢，即 CharBuf 等？
2. Netty 中的 ByteBuf 有哪些分类方式？
3. Netty 中的 ByteBuf 各种实现方式的底层原理是什么？

掌握这几个问题，相信你一定对 ByteBuf 有一个全面的认识。

今天的学习，我们还是遵循上一节的方法 —— 从宏观到微观，一步一步深入剖析，好了，让我们进入今天的学习吧。



 ### 宏观分析 ByteBuf



 #### 继承体系

![图片描述](https://img1.sycdn.imooc.com/5f276c350001bf4113780487.png)

从继承体系上看，ByteBuf 有八个主要实现类，这八个实现类又可以按三个维度来划分：

1. 内存实现方式：Heap 和 Direct；
2. 池化与否：Pooled 和 Unpooled；
3. Unsafe 与否：Unsafe 和 Safe（类名不带 Unsafe 的即为 Safe）；

> ByteBuf 并没有类似于 CharBuf、IntBuf 这样的兄弟类。

经过上一节的学习，内存实现方式这个维度我们都比较熟悉了，另外两个维度对于我们可能就比较懵了：

1. 池化，这里的池跟线程池、数据库连接池是一样的概念吗？ByteBuf 如何池化？
2. Unsafe，这里的 Unsafe 跟 Java 原生的 Unsafe 有关系吗？上一节不是说 DirectByteBuffer 底层就是通过 Unsafe 操作直接内存实现的吗？这里的 Unsafe 又是几个意思？

先把这些问题记录下来，一步一步来，我们再来看看 ByteBuf 这个类的结构。



 #### 类结构

类结构主要包含字段和方法，ByteBuf 作为一个抽象类，没有任何字段，大致浏览一下它的方法，主要可以分成三大类：

1. writeXxx ()/readXxx ()：写入、读取数据
2. setXxx ()/getXxx ()：根据索引写入、读取数据
3. 其它：返回 ByteBuf 的状态、遍历等方法，比如返回容量、是否可读等方法

在这些方法中，有一个方法比较亮眼，即：

```java
public abstract ByteBufAllocator alloc();
```

OK，这是我们找到的一个突破口，从类名 `ByteBufAllocator` 可以看出它是 ByteBuf 的分配器，什么是分配器呢？它类似于我们常说的工厂模式，用来创建 ByteBuf 的地方。

此时，我们需要简单浏览一下 ByteBufAllocator 的继承体系和类结构，即宏观分析一下。



 ##### ByteBufAllocator 的继承体系

![图片描述](https://img1.sycdn.imooc.com/5f276c48000186e310410287.png)

我们可以把上图分解成左右两个部分来看，左半边是以 Pooled/Unpooled 为划分标准，右半边是以 Heap/Direct 为划分标准，这是跟 ByteBuf 本身的分类方式差不多嘛？实际上是不是这样呢？

很遗憾，并不是这样，再仔细观察一下右边两个类的名字，一个是以 Preferred 开头，一个是以 Prefer 开头，可见这两个类不是出自同一人之手，或者不是同一人同一时间写的。

通过这个切入点，再仔细观察一下，会发现 UnpooledByteBufAllocator 和 PooledByteBufAllocator 位于核心库 netty-buffer 中，而 PreferHeapByteBufAllocator 位于核心库 netty-transport 中，而 PreferredDirectByteBufAllocator 位于库 transport-native-unix-common 中。

再大概浏览一下四个类中的代码，可以发现，UnpooledByteBufAllocator 和 PooledByteBufAllocator 类中默认都是偏向于使用 Direct 的方式创建 ByteBuf，而 PreferHeapByteBufAllocator 和 PreferredDirectByteBufAllocator 中保存了 ByteBufAllocator 的实例，其实真正干活还是交给 UnpooledByteBufAllocator 或者 PooledByteBufAllocator 类来实现的，这是设计模式中的装饰器模式的用法。

```java
// 使用池化技术
public class PooledByteBufAllocator extends AbstractByteBufAllocator implements ByteBufAllocatorMetricProvider {
    public static final PooledByteBufAllocator DEFAULT =
            new PooledByteBufAllocator(PlatformDependent.directBufferPreferred());
    // 省略其它代码
}
// 不使用池化技术
public final class UnpooledByteBufAllocator extends AbstractByteBufAllocator implements ByteBufAllocatorMetricProvider {
    public static final UnpooledByteBufAllocator DEFAULT =
            new UnpooledByteBufAllocator(PlatformDependent.directBufferPreferred());
    // 省略其它代码
}
// 更偏向于使用堆内存
public final class PreferHeapByteBufAllocator implements ByteBufAllocator {
    private final ByteBufAllocator allocator;
    // 省略其它代码
}
// 更偏向于使用直接内存
public final class PreferredDirectByteBufAllocator implements ByteBufAllocator {
    private ByteBufAllocator allocator;
    // 省略其它代码
}
```

所以，我大胆猜测，一开始 Netty 的作者只提供了 UnpooledByteBufAllocator 和 PooledByteBufAllocator 这两种创建 ByteBuf 的分配器，而 PreferHeapByteBufAllocator 和 PreferredDirectByteBufAllocator 是后面写的，且不是同一个作者写的，或者不是同一时间写的。

好了，我们再来看看 ByteBufAllocator 这个接口的结构。



 ##### ByteBufAllocator 的结构

这里我列出几个比较重要的方法，还有一个常量：

```java
public interface ByteBufAllocator {
    // 默认的分配器，除非显式地配成unpooled，否则使用pooled
    ByteBufAllocator DEFAULT = ByteBufUtil.DEFAULT_ALLOCATOR;
    
    // 创建一个ByteBuf，看具体的实现方式决定创建的是direct的还是heap的
    ByteBuf buffer();
    ByteBuf buffer(int initialCapacity);
    ByteBuf buffer(int initialCapacity, int maxCapacity);

    // 创建一个heap类型的ByteBuf
    ByteBuf heapBuffer();
    ByteBuf heapBuffer(int initialCapacity);
    ByteBuf heapBuffer(int initialCapacity, int maxCapacity);

    // 创建一个direct的ByteBuf
    ByteBuf directBuffer();
    ByteBuf directBuffer(int initialCapacity);
    ByteBuf directBuffer(int initialCapacity, int maxCapacity);
    
	// 省略其它方法
 }
```

有这几个方法，完全够我们使用了，通过观察可以发现，每种方法都提供了三种重载方式，且参数的变化是跟容量相关的，所以，我们是否可以大胆猜测：其实，ByteBuf 是支持扩容的呢？

支不支持扩容呢？下面进入我们的微观分析阶段。



 ### 微观分析 ByteBuf

通过宏观分析，我们知道 ByteBuf 有 8 个主要实现类，我们又知道，可以通过 ByteBufAllocator 来创建不同类型的 ByteBuf，但是，并没有看到跟 Unsafe 相关的代码，这是一个问题，等待我们去挖掘。

所以，我们先从简单的 Unpooled 和 Heap 入手，这样怎么写调试用例呢？其实很简单，请看：

```java
public class ByteBufTest {
    public static void main(String[] args) {
        // 1. 参数是preferDirect，即是否偏向于使用直接内存
        UnpooledByteBufAllocator allocator = new UnpooledByteBufAllocator(false);
        
        // 2. 创建一个非池化基于堆内存的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer();
        
        // 3. 写入数据
        byteBuf.writeInt(1);
        byteBuf.writeInt(2);
        byteBuf.writeInt(3);

        // 4. 读取数据
        System.out.println(byteBuf.readInt());
        System.out.println(byteBuf.readInt());
        System.out.println(byteBuf.readInt());
    }
}
```

这个调试用例，我将分成 4 个部分来进行源码级别的剖析：

1. 创建 ByteBufAllocator 的过程；
2. 创建 heapByteBuf 的过程；
3. 写入数据的过程；
4. 读取数据的过程；

首先，让我们看看创建 ByteBufAllocator 的过程：

```java
// 参数1preferDirect表示是否偏向于使用直接内存
// 这里我们传的是false
public UnpooledByteBufAllocator(boolean preferDirect) {
    this(preferDirect, false);
}
// 参数2表示是否禁用内存泄漏检测，先跳过
public UnpooledByteBufAllocator(boolean preferDirect, boolean disableLeakDetector) {
    this(preferDirect, disableLeakDetector, PlatformDependent.useDirectBufferNoCleaner());
}
// 参数3表示是否尝试没有Cleaner的构造方法，这个是什么意思呢？
public UnpooledByteBufAllocator(boolean preferDirect, boolean disableLeakDetector, boolean tryNoCleaner) {
    super(preferDirect);
    this.disableLeakDetector = disableLeakDetector;
    noCleaner = tryNoCleaner && PlatformDependent.hasUnsafe()
        && PlatformDependent.hasDirectBufferNoCleanerConstructor();
}
// 调用父类的构造方法
protected AbstractByteBufAllocator(boolean preferDirect) {
    // 如果偏向于直接内存且平台有Unsafe，则默认使用直接内存
    // 这里的Unsafe是Java原生的Unsafe吗？
    directByDefault = preferDirect && PlatformDependent.hasUnsafe();
    emptyBuf = new EmptyByteBuf(this);
}
```

这段代码看着是不是很费劲？那就对了。这段代码主要是用来判断当前运行的 JDK 平台是否支持相关的功能，比如直接内存，并不是说这里传了 `preferDirect=true`，最后就一定会创建直接内存形式的 ByteBuf 给到我们。说句不好听的，你喜欢是你的事，支不支持是我的事。

为什么会有平台是否支持的判断呢？归纳起来主要有三个原因：

1. JDK 各版本之间并不完全兼容。比如低版本的 JDK 可能就不支持使用直接内存。
2. 不同的设备支持的功能不一样。我们知道，Java 程序是 `write once, run anywhere`，这其实是各个平台级别的 JDK 底层给我们做了很多兼容，有的平台可能就不支持直接内存，比如安卓可能就不支持直接内存。
3. 不同类型的 JDK 支持的功能不一样。目前比较主流的有两大阵营 ——OracleJDK 和 OpenJDK，OracleJDK 是功能最齐全的，OpenJDK 相对来说会缺失一些功能。

所以，Netty 把这些细节都给我们考虑在内了，它会检测当前运行的平台是否支持某些功能，然后做出最好的优化让程序可以继续运行。比如，我们如果直接使用 Java 原生的方法创建了一个 DirectByteBuffer，可能换一个平台就无法运行，但是，使用 Netty 不会出现这种情况，它可能会退化成 HeapByteBuffer，让程序可以继续运行。如果这部分判断让我们自己来写呢，那肯定是不现实的，我们不可能把每个平台不同设备不同类型的 JDK 全部研究一遍。

然而，它是怎么检测的呢？比如 `PlatformDependent.hasUnsafe()` 这个方法内部到底做了哪些判断呢？让我们一起来看一看：

```java
public static boolean hasUnsafe() {
    return UNSAFE_UNAVAILABILITY_CAUSE == null;
}
```

这里只是简单地判断了一下 `UNSAFE_UNAVAILABILITY_CAUSE` 是否为 null，这个变量又是什么？

在 IDEA 中，按住 CTRL 键鼠标点击一下，可以定位到这个变量声明的地方：

```java
public final class PlatformDependent {
    private static final Throwable UNSAFE_UNAVAILABILITY_CAUSE = unsafeUnavailabilityCause0();
	// 省略其它代码
}
```

OK，可以看到，这里是通过一个方法返回的，跟踪进去：

```java
// 返回不支持Unsafe的原因
private static Throwable unsafeUnavailabilityCause0() {
    // 如果是安卓，直接抛出不支持的异常
    if (isAndroid()) {
        logger.debug("sun.misc.Unsafe: unavailable (Android)");
        return new UnsupportedOperationException("sun.misc.Unsafe: unavailable (Android)");
    }

    // 如果是IKVM.NET，直接抛出不支持的异常
    if (isIkvmDotNet()) {
        logger.debug("sun.misc.Unsafe: unavailable (IKVM.NET)");
        return new UnsupportedOperationException("sun.misc.Unsafe: unavailable (IKVM.NET)");
    }

    // 通过PlatformDependent0.getUnsafeUnavailabilityCause()判断是否支持Unsafe
    Throwable cause = PlatformDependent0.getUnsafeUnavailabilityCause();
    // 如果有原因，直接返回
    if (cause != null) {
        return cause;
    }

    try {
        // 再判断是否有Unsafe
        boolean hasUnsafe = PlatformDependent0.hasUnsafe();
        logger.debug("sun.misc.Unsafe: {}", hasUnsafe ? "available" : "unavailable");
        return hasUnsafe ? null : PlatformDependent0.getUnsafeUnavailabilityCause();
    } catch (Throwable t) {
        logger.trace("Could not determine if Unsafe is available", t);
        // Probably failed to initialize PlatformDependent0.
        return new UnsupportedOperationException("Could not determine if Unsafe is available", t);
    }
}
```

最后，到 `PlatformDependent0` 这个类中，实际上，是在它的静态块中进行判断的（删减了许多代码）：

```java
// io.netty.util.internal.PlatformDependent0#getUnsafeUnavailabilityCause
static Throwable getUnsafeUnavailabilityCause() {
    // 这个变量是在下面这个静态块中赋值的
    return UNSAFE_UNAVAILABILITY_CAUSE;
}
static {
    // 是否显式地关闭unsafe，通过参数io.netty.noUnsafe控制
    if ((unsafeUnavailabilityCause = EXPLICIT_NO_UNSAFE_CAUSE) != null) {
        direct = null;
        addressField = null;
        unsafe = null;
        internalUnsafe = null;
    } else {
        // 创建一个Java原生的DirectByteBuffer后面使用
        direct = ByteBuffer.allocateDirect(1);

        // 尝试获取Unsafe的字段theUnsafe
        final Field unsafeField = Unsafe.class.getDeclaredField("theUnsafe");

        // 尝试获取copyMemory()方法
        finalUnsafe.getClass().getDeclaredMethod(
            "copyMemory", Object.class, long.class, Object.class, long.class, long.class);

        // 尝试获取DirectByteBuffer中的address字段（实际是在其父类Buffer中）
        // 这个address是专门用来存储直接内存的地址的
        final Field field = Buffer.class.getDeclaredField("address");
        final long offset = finalUnsafe.objectFieldOffset(field);
        final long address = finalUnsafe.getLong(direct, offset);
        
        // 上面方法的返回值
        UNSAFE_UNAVAILABILITY_CAUSE = unsafeUnavailabilityCause;
    }
    // 省略其它代码
}
```

首先，会检测我们是否显式地关闭了 Unsafe，即通过参数 `io.netty.noUnsafe` 控制的，其实，Netty 中很多场景都是可以通过参数显式地控制的，但是，一般我们也没有必要去修改默认配置，因为 Netty 给我们的默认配置已经足够好了。

然后，会尝试反射访问 Unsafe 中的属性 `theUnsafe` 和方法 `copyMemory`，其中，`theUnsafe` 是我们获得 Unsafe 实例的唯一方法，因为这个类是 Java 核心类，有非常严格的权限控制，我们只能通过这种方式获得其实例。

最后，会反射获取 DirectByteBuffer 中的 `address` 属性，这个 `address` 是定义在其父类 Buffer 中的。

如果上面三步都成功了，才能宣判我们可以正确地使用 Unsafe 了，当然了，这个 Unsafe 就是 Java 原生的那个 Unsafe。

另外，前面看到的 `PlatformDependent.hasDirectBufferNoCleanerConstructor()` 最终也是在这个静态块中判断的，原理都差不多，无非是通过反射判断某个方法或者属性存不存在，有兴趣的同学可以研究下。

好了，接下来，我们来看看创建 HeapByteBuffer 的过程吧，即 `ByteBuf byteBuf = allocator.heapBuffer();`:

```java
@Override
public ByteBuf heapBuffer() {
    // DEFAULT_INITIAL_CAPACITY = 256
    // DEFAULT_MAX_CAPACITY = Integer.MAX_VALUE = 2147483647
    return heapBuffer(DEFAULT_INITIAL_CAPACITY, DEFAULT_MAX_CAPACITY);
}
@Override
public ByteBuf heapBuffer(int initialCapacity, int maxCapacity) {
    if (initialCapacity == 0 && maxCapacity == 0) {
        return emptyBuf;
    }
    // 检查这两个容量是否合规
    validate(initialCapacity, maxCapacity);
    return newHeapBuffer(initialCapacity, maxCapacity);
}
@Override
protected ByteBuf newHeapBuffer(int initialCapacity, int maxCapacity) {
    // 根据是否可以使用Unsafe创建不同的类型
    return PlatformDependent.hasUnsafe() ?
        new InstrumentedUnpooledUnsafeHeapByteBuf(this, initialCapacity, maxCapacity) :
    new InstrumentedUnpooledHeapByteBuf(this, initialCapacity, maxCapacity);
}
```

看到这里你可能会有一些疑问：

1. 原来 Unsafe 是在最后一步这里才真正用到，但是，Unsafe 不是用来操作直接内存的吗？我们这里创建的是基于堆内存的，它有什么意义呢？
2. 为什么创建的不是我们上面介绍的 8 种类型呢，而是它们的子类？
3. 这里有两个容量，难道 Netty 中的 ByteBuf 可以支持扩容？

OK，我们先回答第二个问题，为什么创建的是 InstrumentedUnpooledHeapByteBuf 或者 InstrumentedUnpooledUnsafeHeapByteBuf 类的对象呢？

首先，我们要理解 `Instrumented` 这个单词的含义，直接查它的意思是指`乐器、仪器、工具`，这个词更偏向于指法律、艺术、科学方面的工具或者器械，不过，这些可能还是跟我们这里的意思没有太大关系，最后，我找到了一段对这个单词的英文解释：

> the semantic role of the entity (usually inanimate) that the agent uses to perform an action or start a process

正所谓是，每个单词都认识，连一起就都不认识了，其实，也不用全认识，认识一个单词即可 ——`agent`—— 代理的意思，这个代理跟 Proxy 比较类似，不过有一点区别，像我们常用的代理（Proxy）都是方法级别的，而这个代理（Agent/Instrument）一般是指类级别的代理，它会代理整个类。好吧，还是比较懵，那就当成一样的吧也无所谓。

> 其实，在 Java 和 Spring 中也分别有 Instrument 一说，在 Spring 中，也可以把它看成是 AOP 的一种方式，有兴趣的同学可以面向搜索引擎学习一下。

问题又来了，为什么要使用 Instrument 做一层代理呢？那肯定是对原有功能进行了一些增强，至于做了哪些增强，我们接着看。

因为我使用的是 win8 JDK8，天生就是支持 Unsafe 的，所以，在我的电脑上创建的就是 InstrumentedUnpooledUnsafeHeapByteBuf 的对象，让我们继续跟下去：

```java
InstrumentedUnpooledUnsafeHeapByteBuf(UnpooledByteBufAllocator alloc, int initialCapacity, int maxCapacity) {
    // 调用父类的构造方法
    super(alloc, initialCapacity, maxCapacity);
}
public UnpooledUnsafeHeapByteBuf(ByteBufAllocator alloc, int initialCapacity, int maxCapacity) {
    // 调用父类的构造方法
    super(alloc, initialCapacity, maxCapacity);
}
public UnpooledHeapByteBuf(ByteBufAllocator alloc, int initialCapacity, int maxCapacity) {
    // 这个父类构造方法里没什么重要的东西，不断续往里跟了
    super(maxCapacity);

    // 检查两个容量
    if (initialCapacity > maxCapacity) {
        throw new IllegalArgumentException(String.format(
            "initialCapacity(%d) > maxCapacity(%d)", initialCapacity, maxCapacity));
    }

    this.alloc = checkNotNull(alloc, "alloc");
    // 调用allocateArray创建了一个byte数组，并保存起来
    setArray(allocateArray(initialCapacity));
    // 初始化readIndex和writeIndex为0
    setIndex(0, 0);
}
// InstrumentedUnpooledUnsafeHeapByteBuf#allocateArray
// 这个方法就是做了增强的方法
@Override
protected byte[] allocateArray(int initialCapacity) {
    byte[] bytes = super.allocateArray(initialCapacity);
    // 增强的地方
    ((UnpooledByteBufAllocator) alloc()).incrementHeap(bytes.length);
    return bytes;
}
```

到这里就比较清楚了，UnpooledUnsafeHeapByteBuf 底层还是使用的 Java 原生的 byte 数组来实现的，至于这里增强的方法，其实是加入了监控，打开 InstrumentedUnpooledUnsafeHeapByteBuf 这个类，你会发现，它里面还有另一个方法叫作 freeArray ()，它做的增强即：当创建 byte 数组的时候记录下来分配的堆内存大小，当释放 byte 数组的时候将其占用的堆内存大小相应减少。这样就起来了监控的目的，即 Netty 可以监控进程中所有的 UnpooledUnsafeHeapByteBuf 到底占用了多少堆内存，方便出问题时进行排查，当然，也可以用于提前发现内存泄漏等问题。

OK，经过前面的过程，我们终于创建了一个 UnpooledUnsafeHeapByteBuf 对象，接下来我们再来看看写入数据的过程吧，即 `byteBuf.writeInt(1);` 这行代码，继续跟踪进去：

```java
@Override
public ByteBuf writeInt(int value) {
    // 一个int等于4个字节
    // 检查是否可写，里面会做扩容相关的操作，
    // 最终会调用allocateArray()分配一个新的数组，并把旧数组的数据拷贝到新数组
    // 且调用freeArray()把旧数组释放，当然，此时也会改变上面提到的监控的数值
    ensureWritable0(4);
    // 在写索引的位置开始写入值
    _setInt(writerIndex, value);
    // 写索引加4
    writerIndex += 4;
    return this;
}
@Override
protected void _setInt(int index, int value) {
    // 调用UnsafeByteBufUtil工具类修改array数组index位置的值
    UnsafeByteBufUtil.setInt(array, index, value);
}
static void setInt(byte[] array, int index, int value) {
    // 我的电脑UNALIGNED=true
    if (UNALIGNED) {
        // 又到了PlatformDependent这个类中
        PlatformDependent.putInt(array, index, BIG_ENDIAN_NATIVE_ORDER ? value : Integer.reverseBytes(value));
    } else {
        PlatformDependent.putByte(array, index, (byte) (value >>> 24));
        PlatformDependent.putByte(array, index + 1, (byte) (value >>> 16));
        PlatformDependent.putByte(array, index + 2, (byte) (value >>> 8));
        PlatformDependent.putByte(array, index + 3, (byte) value);
    }
}
public static void putInt(byte[] data, int index, int value) {
    // 继续到PlatformDependent0这个类中
    PlatformDependent0.putInt(data, index, value);
}
static void putInt(byte[] data, int index, int value) {
    // 调用Unsafe的putInt()方法直接修改对象的属性
    // 数组本身就是一种特殊的对象，它也有对象头等属性
    // 所以，需要一个偏移量，BYTE_ARRAY_BASE_OFFSET=16
    UNSAFE.putInt(data, BYTE_ARRAY_BASE_OFFSET + index, value);
}
// native方法
// 这个putInt()跟上一节修改直接内存的putInt()不是同一个方法
// 上一节的putInt(long var1, int var3)第一个参数是内存地址
// 本节的putInt()第一个参数是对象，第二参数是在对象中的偏移量
public native void putInt(Object var1, long var2, int var4);
```

好了，到这里就比较清晰了，UnpooledUnsafeHeapByteBuf 底层是使用的 Unsafe 来修改数组中的值，为了与 Java 原生 HeapByteBuffer 对比，我们把上一节 HeapByteBuffer 写入数据的最终方法拿过来再对比一下：

```java
// 写入一个int类型的数值
public ByteBuffer putInt(int x) {
    // 调用Bits工具类的putInt()方法，Bits是位的意思
    // 堆内存的实现中使用大端法来存储数据
    Bits.putInt(this, ix(nextPutIndex(4)), x, bigEndian);
    return this;
}
// java.nio.Bits#putInt(java.nio.ByteBuffer, int, int, boolean)
static void putInt(ByteBuffer bb, int bi, int x, boolean bigEndian) {
    // 堆内存使用的是大端法，更符合人们的习惯
    if (bigEndian)
        // 大端法
        putIntB(bb, bi, x);
    else
        putIntL(bb, bi, x);
}
// java.nio.Bits#putIntB(java.nio.ByteBuffer, int, int)
static void putIntB(ByteBuffer bb, int bi, int x) {
    // 把一个int拆分成4个byte，分别写入
    // int3(int x) { return (byte)(x >> 24); }
    bb._put(bi    , int3(x));
    // int2(int x) { return (byte)(x >> 16); }
    bb._put(bi + 1, int2(x));
    // int1(int x) { return (byte)(x >>  8); }
    bb._put(bi + 2, int1(x));
    // int0(int x) { return (byte)(x      ); }
    bb._put(bi + 3, int0(x));
}
// java.nio.HeapByteBuffer#_put
void _put(int i, byte b) {                  // package-private
    // 最终变成了修改byte数组
    hb[i] = b;
}
```

可以看到，Java 原生的 HeapByteBuffer 并没有使用 Unsafe，而是把一个 int 类型拆分成了 4 个 byte 类型，再分别修改 byte 数组对应位置的值，而 Netty 中是直接使用 Unsafe 来修改 byte 数组的值，它是直接修改那一片内存区域的值，不需要拆分等操作，所以，相对来说，更高效一些。

> 其实呢，Netty 中也有 Java 这样的实现，即不带 Unsafe 的 UnpooledHeapByteBuf 类，它的底层就是像 Java 这样把一个 int 拆分成 4 个 byte，并修改数组下标的方式来实现的，有兴趣的同学可以自己看看相关的源码。

同样地，我们可以想像得到，读取数据的过程肯定也是使用 Unsafe 来操作的，我们直接给出代码，就不赘述了：

```java
@Override
public int readInt() {
    // 检查可读
    checkReadableBytes0(4);
    // 在读索引的位置读取数据
    int v = _getInt(readerIndex);
    // 读索引加4
    readerIndex += 4;
    return v;
}
@Override
protected int _getInt(int index) {
    // 调用UnsafeByteBufUtil工具类
    return UnsafeByteBufUtil.getInt(array, index);
}
static int getInt(byte[] array, int index) {
    // 在我的电脑UNALIGNED=true
    if (UNALIGNED) {
        // 调用PlatformDependent
        int v = PlatformDependent.getInt(array, index);
        return BIG_ENDIAN_NATIVE_ORDER ? v : Integer.reverseBytes(v);
    }
    return PlatformDependent.getByte(array, index) << 24 |
        (PlatformDependent.getByte(array, index + 1) & 0xff) << 16 |
        (PlatformDependent.getByte(array, index + 2) & 0xff) <<  8 |
        PlatformDependent.getByte(array, index + 3) & 0xff;
}
public static int getInt(byte[] data, int index) {
    // 调用PlatformDependent0
    return PlatformDependent0.getInt(data, index);
}
static int getInt(byte[] data, int index) {
    // 调用Unsafe的getInt()方法
    return UNSAFE.getInt(data, BYTE_ARRAY_BASE_OFFSET + index);
}
// 第一个参数是对象，第二个参数是在对象中的偏移量
public native int getInt(Object var1, long var2);
```

好了，到这里对于 UnpooledUnsafeHeapByteBuf 的源码级别的剖析就结束了。



 ### 后记

本节，我们一起从宏观上对 ByteBuf 做了一个全面的剖析，并从微观上深入剖析了其一个子类 UnpooledUnsafeHeapByteBuf，到这里，你可能还有一些疑问的，比如，Netty 是怎么利用直接内存的，等等。嗯，有问题是好事，别急，我们一步一步来，先从简单的入手，再慢慢过渡到更难的级别。

下一节，我们将一起学习 `Netty是如何使用直接内存的`这个问题，不见不散。



 ### 思维导图

本次的思维导图和以往不太一样，大家可以在分类方式后面不断联想并提出一些问题。

![图片描述](https://img1.sycdn.imooc.com/5f276c7000015c4620261217.png)





<div style="page-break-after:always;"></div>

 ## 19 Netty的ByteBuf是如何支持直接内存非池化实现的


![img](https://img2.sycdn.imooc.com/5f0595ff000144d706400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)对自己不满是任何真正有才能的人的根本特征之一。——契诃夫![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起从宏观上对 ByteBuf 做了一个全面的剖析，并从微观上深入剖析了其一个子类 UnpooledUnsafeHeapByteBuf，可以发现，其底层使用的是 Java 原生的数组，并使用 Unsafe 直接更新数组中的内容。

那么，如果是 UnpooledDirectByteBuf 和 UnpooledUnsafeDirectByteBuf，它们底层又是怎样的呢？针对 UnpooledDirectByteBuf 这个类，难道不使用 Unsafe 也能操作直接内存？

本节，我们就来将这些问题解决。



 ### 问题

1. UnpooledDirectByteBuf 不使用 Unsafe 吗？
2. UnpooledUnsafeDirectByteBuf 的实现跟 DirectByteBuffer 是否完全一致？
3. 上面两者如何释放内存？



 ### 微观剖析 UnpooledDirectByteBuf

我们先从带 Unsafe 的开始，因为在 Netty 中默认就是开启 Unsafe 的。



 #### 调试用例

调试用例还是延用上一节的，略作修改：

```java
public class ByteBufTest {
    public static void main(String[] args) {
        // 参数是preferDirect，即是否偏向于使用直接内存
        ByteBufAllocator allocator = new UnpooledByteBufAllocator(true);

        // 创建一个非池化基于直接内存的ByteBuf
        ByteBuf byteBuf = allocator.directBuffer();

        // 写入数据
        byteBuf.writeInt(1);
        byteBuf.writeInt(2);
        byteBuf.writeInt(3);

        // 读取数据
        System.out.println(byteBuf.readInt());
        System.out.println(byteBuf.readInt());
        System.out.println(byteBuf.readInt());

        // 记得释放内存哦
        ReferenceCountUtil.release(byteBuf);
    }
}
```

在这个调试用例中，我们分配了一个直接内存实现的 ByteBuf，并进行了写入数据和读取数据的操作，另外，还多了一步操作，即释放内存。至于为什么要手动释放内存呢？我们待会儿说。

> 其实在学习 `Netty核心组件剖析`这一节，我们就说过，入站事件的处理最好继承自 SimpleChannelInboundHandler 而不是 ChannelInboundHandlerAdapter，因为 SimpleChannelInboundHandler 内部调用了 `ReferenceCountUtil.release(byteBuf)` 方法，会帮我们自动清理垃圾。



 #### 创建分配器

在创建分配器这里，我们把 preferDirect 这个参数由 false 改为了 true，当然了，不改也没有关系，因为后面使用的是 allocator.directBuffer () 这个方法，它同样会创建直接内存实现的 ByteBuf。

不过，这里有个要注意的点，即下面这个构造方法：

```java
public UnpooledByteBufAllocator(boolean preferDirect, boolean disableLeakDetector, boolean tryNoCleaner) {
    super(preferDirect);
    this.disableLeakDetector = disableLeakDetector;
    noCleaner = tryNoCleaner && PlatformDependent.hasUnsafe()
            && PlatformDependent.hasDirectBufferNoCleanerConstructor();
}
```

> noCleaner 的判断可以参考上一节 hasUnsafe () 分析，它们最终是在同一个静态块中判断的。

这个方法中尝试去获取 Java 原生的 DirectByteBuffer 中是否包含没有 Cleaner（NoCleaner）的构造方法，即下面这个方法：

```java
private DirectByteBuffer(long addr, int cap) {
    super(-1, 0, cap, cap);
    address = addr;
    cleaner = null;
    att = null;
}
```

> 我是 win8 OracleJDK，所以是有这个方法的，因此，noCleaner 等于 true。

为什么要看有没有这个方法呢？因为 Netty 想干一件大事 —— 自己控制内存的释放。

在前面的章节，我们分析过，原生 DirectByteBuffer 是依赖于 Cleaner 来做垃圾清理的，本质是将直接内存的释放与 JVM 本身的 GC 关联起来，通过虚引用的清理间接地控制直接内存的释放，那么，Netty 为什么还要多此一举，自己去控制直接内存的释放呢？其实，Netty 这么做是有道理的，把所有类型的 ByteBuf 抽象到同一个高度，主要是为了与后面所说的池化的 ByteBuf 保持一致。通过观察，可以发现，所有的 ByteBuf 都继承自 AbstractReferenceCountedByteBuf 类，所以，都可以调用其 release () 方法释放内存，包括前面说过的 UnpooledUnsafeHeapByteBuf。



 #### 创建直接内存实现的 ByteBuf

通过前面的操作，已经创建好了一个分配器，接下来，我们就使用这个分配器来创建一个直接内存实现的 ByteBuf，同样地，我们还是使用调试大法直接跟踪到 `allocator.directBuffer()` 代码内部：

```java
@Override
public ByteBuf directBuffer() {
    // 调用重载方法，传入默认的初始容量和最大容量
    return directBuffer(DEFAULT_INITIAL_CAPACITY, DEFAULT_MAX_CAPACITY);
}
@Override
public ByteBuf directBuffer(int initialCapacity, int maxCapacity) {
    if (initialCapacity == 0 && maxCapacity == 0) {
        return emptyBuf;
    }
    // 检查初始容量和最大容量
    validate(initialCapacity, maxCapacity);
    // 调用另一个方法新建
    return newDirectBuffer(initialCapacity, maxCapacity);
}
@Override
protected ByteBuf newDirectBuffer(int initialCapacity, int maxCapacity) {
    final ByteBuf buf;
    // 如果支持Unsafe
    if (PlatformDependent.hasUnsafe()) {
        // 根据noCleaner的值判断使用哪个子类
        // 我的电脑noCleaner=true，所以使用的是InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf
        buf = noCleaner ? new InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf(this, initialCapacity, maxCapacity) :
        new InstrumentedUnpooledUnsafeDirectByteBuf(this, initialCapacity, maxCapacity);
    } else {
        // 不支持Unsafe的情况使用这个子类
        buf = new InstrumentedUnpooledDirectByteBuf(this, initialCapacity, maxCapacity);
    }
    return disableLeakDetector ? buf : toLeakAwareBuffer(buf);
}
// 省略N层构造方法
public UnpooledDirectByteBuf(ByteBufAllocator alloc, int initialCapacity, int maxCapacity) {
    super(maxCapacity);
    // 省略参数检查
    
    this.alloc = alloc;
    // 调用allocateDirect()方法
    setByteBuffer(allocateDirect(initialCapacity), false);
}
// InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf#allocateDirect
@Override
protected ByteBuffer allocateDirect(int initialCapacity) {
    // 调用父类的
    ByteBuffer buffer = super.allocateDirect(initialCapacity);
    // 监控增强
    ((UnpooledByteBufAllocator) alloc()).incrementDirect(buffer.capacity());
    return buffer;
}
// UnpooledUnsafeNoCleanerDirectByteBuf#allocateDirect
@Override
protected ByteBuffer allocateDirect(int initialCapacity) {
    // 调用到PlatformDependent
    return PlatformDependent.allocateDirectNoCleaner(initialCapacity);
}
public static ByteBuffer allocateDirectNoCleaner(int capacity) {
    assert USE_DIRECT_BUFFER_NO_CLEANER;
    // 记录内存使用情况
    incrementMemoryCounter(capacity);
    try {
        // 调用到PlatformDependent0
        return PlatformDependent0.allocateDirectNoCleaner(capacity);
    } catch (Throwable e) {
        decrementMemoryCounter(capacity);
        throwException(e);
        return null;
    }
}
static ByteBuffer allocateDirectNoCleaner(int capacity) {
    // 调用UNSAFE分配内存，并把地址传给newDirectBuffer()方法
    return newDirectBuffer(UNSAFE.allocateMemory(Math.max(1, capacity)), capacity);
}
static ByteBuffer newDirectBuffer(long address, int capacity) {
    ObjectUtil.checkPositiveOrZero(capacity, "capacity");
    try {
        // 调用DirectByteBuffer的DirectByteBuffer(long addr, int cap)构造方法
        return (ByteBuffer) DIRECT_BUFFER_CONSTRUCTOR.newInstance(address, capacity);
    } catch (Throwable cause) {
        if (cause instanceof Error) {
            throw (Error) cause;
        }
        throw new Error(cause);
    }
}
```

所以，针对非池化且使用直接内存的情况下，Netty 默认创建的就是一个不使用 Cleaner 清理垃圾的 DirectByteBuffer，没错，Netty 底层使用的就是 Java 原生的 DirectByteBuffer，这个也可以在 UnpooledDirectByteBuf 的属性中找到：

```java
public class UnpooledDirectByteBuf extends AbstractReferenceCountedByteBuf {
    ByteBuffer buffer;
}
```

既然使用的是 Java 原生的 DirectByteBuffer，那么写入数据和读取数据肯定是与其保持一致的，这两个方法我们就不再分析了，有兴趣地同学可以使用调试大法跟踪一下。

那么，问题来了：Netty 既然不使用 Cleaner 来自动清理垃圾，那它怎么实现垃圾清理呢？



 #### 释放内存

这就是 `ReferenceCountUtil.release(byteBuf);` 这行代码的作用了，同样地，我们跟踪进去瞧一瞧：

```java
// ReferenceCountUtil#release
public static boolean release(Object msg) {
    if (msg instanceof ReferenceCounted) {
        // 转换成ReferenceCounted
        return ((ReferenceCounted) msg).release();
    }
    return false;
}
// AbstractReferenceCountedByteBuf#release()
@Override
public boolean release() {
    // updater.release(this)将其引用计数减一
    // 默认的引用计数为2
    // 如果减到1的话表示可以清理掉了，此时会返回true
    return handleRelease(updater.release(this));
}
private boolean handleRelease(boolean result) {
    // 如果减到1的话，就把它清理掉
    if (result) {
        deallocate();
    }
    return result;
}
@Override
protected void deallocate() {
    ByteBuffer buffer = this.buffer;
    if (buffer == null) {
        return;
    }
    // 将对DirectByteBuffer的引用置为空，方便GC清理this.buffer引用的对象
    this.buffer = null;

    if (!doNotFree) {
        // 调用freeDirect
        freeDirect(buffer);
    }
}
// InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf#freeDirect
@Override
protected void freeDirect(ByteBuffer buffer) {
    int capacity = buffer.capacity();
    // 调用父类
    super.freeDirect(buffer);
    // 监控增强
    ((UnpooledByteBufAllocator) alloc()).decrementDirect(capacity);
}
@Override
protected void freeDirect(ByteBuffer buffer) {
    // 调用到PlatformDependent
    PlatformDependent.freeDirectNoCleaner(buffer);
}
public static void freeDirectNoCleaner(ByteBuffer buffer) {
    assert USE_DIRECT_BUFFER_NO_CLEANER;

    int capacity = buffer.capacity();
    // 调用到PlatformDependent
    PlatformDependent0.freeMemory(PlatformDependent0.directBufferAddress(buffer));
    decrementMemoryCounter(capacity);
}
static void freeMemory(long address) {
    // 调用Unsafe释放直接内存
    UNSAFE.freeMemory(address);
}
```

可以看到，最终是调用的 Unsafe 的 freeMemory () 方法来释放内存的，这与 DirectByteBuffer 的最终结果又是一致的（Deallocator 中调用了 Unsafe 的 freeMemory () 方法）。

所以，我们总结归纳一下整个过程：

1. 在创建分配器 UnpooledByteBufAllocator 的时候会查找 DirectByteBuffer 中是否包含 NoCleaner 的构造方法；
2. 在创建 UnpooledDirectByteBuf 的时候默认创建的是其子类 InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf，这个类将不使用 Cleaner 来清理垃圾，同时，它的底层使用的是 Java 原生的 DirectByteBuffer，且包含 Unsafe；
3. 在清理内存的时候需要手动调用 `ReferenceCountUtil.release(byteBuf);` 方法；
4. 最终也是调用 Unsafe 的 freeMemory () 来释放内存；



 #### 其它

在上面分析的过程中，我们发现 InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf 类还有两个兄弟类：

- InstrumentedUnpooledUnsafeDirectByteBuf
- InstrumentedUnpooledDirectByteBuf

从名字上也可以看出，前者不包含 `NoCleaner`，那可能就是使用的 Cleaner 来清理垃圾，后者不包含 `Unsafe`，那可能就是不使用 Unsafe 来操作直接内存了吧，具体是不是这样呢？我们简单快速地过一下源码。



 ##### InstrumentedUnpooledUnsafeDirectByteBuf

直接打开这个类：

```java
private static final class InstrumentedUnpooledUnsafeDirectByteBuf extends UnpooledUnsafeDirectByteBuf {
    InstrumentedUnpooledUnsafeDirectByteBuf(
        UnpooledByteBufAllocator alloc, int initialCapacity, int maxCapacity) {
        super(alloc, initialCapacity, maxCapacity);
    }

    @Override
    protected ByteBuffer allocateDirect(int initialCapacity) {
        ByteBuffer buffer = super.allocateDirect(initialCapacity);
        ((UnpooledByteBufAllocator) alloc()).incrementDirect(buffer.capacity());
        return buffer;
    }

    @Override
    protected void freeDirect(ByteBuffer buffer) {
        int capacity = buffer.capacity();
        super.freeDirect(buffer);
        ((UnpooledByteBufAllocator) alloc()).decrementDirect(capacity);
    }
}
```

与其它 `Instrumented` 开头的增强类几乎没有任何区别，其实，真正区别的地方在于它们的父类，通过观察可以发现，InstrumentedUnpooledUnsafeNoCleanerDirectByteBuf 继承自 UnpooledUnsafeNoCleanerDirectByteBuf ，而 InstrumentedUnpooledUnsafeDirectByteBuf 继承自 UnpooledUnsafeDirectByteBuf，所以，真正的区别还是位于它们的父类中，我们以 `allocateDirect()` 这个方法为例，跟踪到它的父类中：

```java
// UnpooledDirectByteBuf#allocateDirect
protected ByteBuffer allocateDirect(int initialCapacity) {
    // 这不是`再谈ByteBuffer`中我们的调试用例使用的方法么？！
    return ByteBuffer.allocateDirect(initialCapacity);
}
// ByteBuffer#allocateDirect
public static ByteBuffer allocateDirect(int capacity) {
    // 直接创建了DirectByteBuffer，包含Cleaner的
    return new DirectByteBuffer(capacity);
}
```

OK，到这里就很清晰了，也就是说，如果 DirectByteBuffer 中不包含 `NoCleaner` 的构造方法，就使用与 Java 原生一样的方式，创建一个包含 Cleaner 的 DirectByteBuffer。



 ##### InstrumentedUnpooledDirectByteBuf

同样地，如果没有 Unsafe，直接看其父类 UnpooledDirectByteBuf 的 allocateDirect () 方法：

```java
// UnpooledDirectByteBuf#allocateDirect
protected ByteBuffer allocateDirect(int initialCapacity) {
    return ByteBuffer.allocateDirect(initialCapacity);
}
// ByteBuffer#allocateDirect
public static ByteBuffer allocateDirect(int capacity) {
    return new DirectByteBuffer(capacity);
}
```

纳尼，与上面的那个 InstrumentedUnpooledUnsafeDirectByteBuf 一样的处理逻辑，是的，你没有看错，就是一样的。

其实，也不完全一样，仔细观察一下，InstrumentedUnpooledUnsafeDirectByteBuf 的父类 UnpooledUnsafeDirectByteBuf 是继承自 InstrumentedUnpooledDirectByteBuf 的父类 UnpooledDirectByteBuf 的，它里面加了一个属性 `memoryAddress`：

```java
public class UnpooledUnsafeDirectByteBuf extends UnpooledDirectByteBuf {
    long memoryAddress;
}
```

Netty 这里的意思并不是说不支持 Unsafe 就甩锅给 JDK，而是说 Netty 支不支持使用 Unsafe，如果可以使用，那么，它就可以使用 Unsafe 来操作直接内存，如果不支持使用 Unsafe，那它也只能交给 JDK 自己来处理了。

> Netty 支不支持使用 Unsafe 是通过参数 `io.netty.noUnsafe` 来控制，默认为 false，也就是可以使用 Unsafe。

好了，到这里，UnpooledDirectByteBuf 和 UnpooledUnsafeDirectByteBuf 的分析就结束了。



 ### 后记

今天，我们一起学习了 UnpooledDirectByteBuf 和 UnpooledUnsafeDirectByteBuf 的实现细节，总的来说，它们底层都是使用 Java 原生的 DirectByteBuffer，不同之处在于，默认情况下，Netty 是自己控制直接内存的释放，即使用 DirectByteBuffer 的 NoCleaner 构造方法，且支持使用 Unsafe。如果 DirectByteBuffer 没有 NoCleaner 方法，则使用包含 Cleaner 的构造方法，同时也支持使用 Unsafe。如果显式地说明了不支持使用 Unsafe 的话，那么最后只能交给 JDK 自己来处理了。

后面，我们将学习池化相关的概念，简单地说，Netty 中包含两种池化 —— 内存池和对象池，它们有怎样的区别和联系呢，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f28bdcd00018a4424610477.png)







<div style="page-break-after:always;"></div>

 ## 20 jemalloc内存分配器是什么


![img](https://img3.sycdn.imooc.com/5f05960b0001c88906400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才免不了有障碍，因为障碍会创造天才。——罗曼·罗兰![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

前面的章节，我们一起学习了 Netty 中非池化的四种 ByteBuf，今天，我们本来是要学习池化的 ByteBuf 的，但是，直接看着代码讲池化，特别是内存池，可能无法理解，所以，本节，我们先讲讲 Netty 使用的内存分配器 ——jemalloc，理解了底层原理，我们才能如虎添翼，飞速奔跑。

好了，进入今天的学习吧。



 ### jemalloc



 #### 基础知识

所谓内存池，是指应用程序向操作系统（或 JVM）申请一块内存，自己管理这一块内存，对象的创建和销毁都从这块内存中分配和回收，这么一块内存就可以称作内存池，对应地，管理这块内存的工具就称作内存分配器。同时，对于申请对象的不同又可以分为堆内存池和直接内存池，如果是向 JVM 申请的内存，那就是堆内存池，如果是向操作系统申请的内存，那就是直接内存池。

那么，有哪些内存分配器呢？

业界比较著名的有三个内存分配器：

1. ptmalloc，Doug Lea 编写的分配器，支持每个线程（per-thread，简称 pt）的 arena，glibc 的默认分配器。

> Doug Lea 大神还有个分配器叫作 dlmalloc，dl 即其名之缩写。

1. tcmalloc，Google 的分配器，它加入了线程缓存（thread cache，简称 tc），Google 声称其比 ptmalloc 快 6 倍。
2. jemalloc，Jason Evans 的分配器，je 即其名之缩写，借鉴了很 tcmalloc 的优秀设计，声称比 tcmalloc 更快，且 CPU 核数越多优势越大，当然，算法也更复杂。

其它的分配器还有 nedmalloc、Hoard、TLSF 等。

目前，jemalloc 已经广泛运用在 facebook、Mozilla、FreeBSD 等公司的产品上，那么，它有怎样的优势呢？

简单总结一下，主要有三大优势：

- 快速分配和回收
- 内存碎片少
- 支持性能分析

当然了，以上说的都是原生的 jemalloc，我们今天要讲的是 Netty 中的 jemalloc，它是原生 jemalloc 在 Java 中的一种实现方式，并根据 Java 语言自身的特点做了一些删减和优化，关于原生的 jemalloc 可以点击文后的`原生jemalloc相关链接`学习了解。



 #### Netty 中的 jemalloc

![图片描述](https://img1.sycdn.imooc.com/5f2a0e350001972510330529.png)

我们先从宏观方面对 Netty 中的内存池有个全面的了解，在 Netty 中，主要包含上面这些组件：

- PoolArena
- PoolChunkList
- PoolChunk
- PoolSubpage
- PoolThreadCache

我们一一来分析。



 ##### PoolArena

根据内存方式的不同，PoolArena 分成 HeapArena 和 DirectArena 两个子类，在创建 PooledByteBufAllocator 的时候会分别初始化这两种类型的 PoolArena 数组，数组默认大小为核数的 2 倍，同时也会根据可以使用的内存大小动态调整。

```java
public class PooledByteBufAllocator extends AbstractByteBufAllocator implements ByteBufAllocatorMetricProvider {    
	private final PoolArena<byte[]>[] heapArenas;
    private final PoolArena<ByteBuffer>[] directArenas;
}
```

> 核数也可以通过 JVM 启动参数 `io.netty.availableProcessors` 配置，因为如果使用低版本的 JDK 且部署在 docker 容器中，获取的是主机的核数，而不是 docker 容器分配的核数。

PoolArena 中存储着 2 种类型的数据结构，分别为 2 个 PoolSubPage [] 数组和 6 个 PoolChunkList：

```java
abstract class PoolArena<T> implements PoolArenaMetric {
	private final PoolSubpage<T>[] tinySubpagePools;
    private final PoolSubpage<T>[] smallSubpagePools;

    private final PoolChunkList<T> q050;
    private final PoolChunkList<T> q025;
    private final PoolChunkList<T> q000;
    private final PoolChunkList<T> qInit;
    private final PoolChunkList<T> q075;
    private final PoolChunkList<T> q100;
}
```

为什么这么复杂呢？一切都是为了更好地利用内存。

实际上，所有的数据都存储在叫作 PoolChunk 的对象中，默认每个 PoolChunk 可以存储 16MB 的数据（chunkSize），每个 PoolChunk 内部又使用伙伴算法将这 16MB 拆分成 2048 个 Page，每个 Page 的大小（pageSize）为 `16MB/2048=8KB`。

如果分配的内存（规范化后的内存）小于 8KB，则把 Page 拆分成更小的内存块，并使用 PoolSubpage 管理这些更小的内存，每个 Page 的拆分标准根据这个 Page 首次被分配时的请求的大小决定：

- 如果小于 512B，则按照 16B 规范化，比如请求的大小为 30B，则规范化到 32B，然后 PoolSubpage 中的元素大小就是 32B，那么，这个 Page 就被拆分成了 `8KB/32B=256` 个更小的内存块。
- 如果大于等于 512B，则按照 `512B*(2^n)` 规范化，比如请求的大小为 996B，那就规范化到 1024B，也就是 1KB，然后这个 Page 就被拆分成了 `8KB/1KB=8` 个更小的内存块。

如果分配的内存大于等于 8KB，且小于等于 16MB，则按照 Page 的大小，也就是 8KB，进行规范化，然后再根据伙伴算法的规则进行内存的分配，什么是伙伴算法呢？我们待会讲。

如果分配的内存大于 16MB，则按照非池化的方式分配内存。

所以，为了区分以上几种情况，Netty 中定义了一个 SizeClass 类型的枚举，把这几种情况分别叫作 Tiny、Small、Normal、Huge，其中 Huge 不在这个枚举中。

如果要用一张图来表示的话，我觉得下面这张比较合适：
![图片描述](https://img1.sycdn.imooc.com/5f2a0e520001567709270792.png)

对于 Tiny 和 Small 类型，Netty 为了快速定位，定义了两个数组放在 PoolArena 中，分别是 tinySubpagePools 和 smallSubpagePools，它们的大小分别为 32 和 4，如果这两个数组对应的位置有值，说明之前出现过相同大小的内存块，那就快速定位到那个 PoolSubpage，使用它直接分配内存，而不用再从头查找，加快分配内存的速度。

前面我们说了，实际上，所有的数据都位于 PoolChunk 中，为了更好地管理这些 PoolChunk，Netty 将它们以双向链表的形式存储在 PoolChunkList 中，同时 PoolChunkList 本身也以双向链表的形式呈现。

在 PoolArena 中，定义了 6 个 PoolChunkList，分别是 qInit、q000、q025、q050、q075、q100，Netty 根据 PoolChunk 的使用率将它们放到不同类型的 PoolChunkList 中，它们代表的使用率分别为：

- qInit，内存使用率为 Integer.MIN_VALUE ~ 25%，当然不可能有负的使用率，所以最小应该是 0
- q000，内存使用率为 0 ~ 50%
- q025，内存使用率为 25% ~ 75%
- q050，内存使用率为 50% ~ 100%
- q075，内存使用率为 75% ~ 100%
- q100，内存使用率为 100% ~ Integer.MAX_VALUE，当然不可能有超过 100% 的使用率，所以最大应该是 100%

举个例子来说明，比如一个 Chunk 首次分配了大小为 512B 的内存，那么它的内存使用率就是 `512B/16MB` 不足 1%，向上取整为 1%，初始时放在 qInit 中，当其分配的总内存超过了 4MB 的时候，也就是达到 25% 了，这个 PoolChunk 就被移动到 q000 中，同样地，当其分配的内存超过 8MB 的时候，就移动到了 q025 中。反过来也是一样，当有对象释放内存时，这部分内存又会被回收到 PoolChunk 中待分配，这时候内存使用会降低，当降低到 4MB 时，也就是 q025 的下限，则会将这个 PoolChunk 移动到 q000 中。



 ##### PoolChunkList

正如前面所说，PoolChunkList 就是相近内存使用率的 PoolChunk 的集合，这些 PoolChunk 以双链表的形式存储在 PoolChunkList 中，而 PoolChunkList 本身也以双向链表的形式连在一起，为什么要以双向链表的形式存在呢？
![图片描述](https://img1.sycdn.imooc.com/5f2a0e66000124d610350253.png)

其实，这包含两个问题：

1. PoolChunk 以双向链表的形式存在，是为了删除元素（移动 PoolChunk）的时候更快，比如，要删除 chunk2，只要把它的 prev 和 next 连一起就行了，时间复杂度更低；
2. PoolChunkList 以双向链表的形式存在，是为了让 PoolChunk 在 PoolChunkList 之间移动更快，比如，一个 PoolChunk 不管是从 q025 到 q050，还是从 q050 回到 q025，都很快，时间复杂度都很低；

另外，在 Netty 中，当分配内存时，优先从 q050 中寻找合适的 PoolChunk 来分配内存，为什么先从 q050 开始呢？

```java
private void allocateNormal(PooledByteBuf<T> buf, int reqCapacity, int normCapacity) {
    if (q050.allocate(buf, reqCapacity, normCapacity) 
        || q025.allocate(buf, reqCapacity, normCapacity) 
        || q000.allocate(buf, reqCapacity, normCapacity) 
        || qInit.allocate(buf, reqCapacity, normCapacity) 
        || q075.allocate(buf, reqCapacity, normCapacity)) {
        return;
    }
    // 省略其它代码
}
```

因为 q050 中的 PoolChunk 的内存使用率都比 50% 多一点，这样更容易找到符合条件的 PoolChunk，又不至于使 PoolChunk 的利用率偏低。

我们举个例子，假如从 q075 中先寻找，如果要分配 4M 以上的内存就无法找到合适的 PoolChunk；假如从 q025 中先寻找，可能正好有内存使用率在 25% 以上的 PoolChunk，这时候就直接使用了，那么 q050 中的 PoolChunk 就很难被利用起来，也就是 q050 中的 PoolChunk 的剩余空间很难被利用起来，进而导致整体的利用率偏低，也就是内存碎片会变高。

那么，如果先从 q050 寻找合适的 PoolChunk 呢？这时 q025 和 q075 中的 PoolChunk 可能永远都不会被使用到，不过没关系，对于 q025 中的 PoolChunk 的内存使用率变为 0 的时候，它们自然就被释放了，而 q075 中的 PoolChunk 本身内存使用率就已经很高了，不用到它们反而更好，等它们的内存使用率降低的时候就又回到 q050 中了，此时就又来很容易地被利用起来。

因此，从 q050 开始寻找，能很大程度上增大整体的内存使用率，降低内存碎片的存在。



 ##### PoolChunk

前面我们说了，默认地，一个 PoolChunk 可以存储 16MB 的数据，PoolChunk 是真正存储数据的地方，何以见得？

```java
final class PoolChunk<T> implements PoolChunkMetric {
    // 数据存储的地方
    final T memory;
    // 满二叉树对应节点是否被分配，数组大小为4096
    private final byte[] memoryMap;
    // 满二叉树原始节点高度，数组大小为4096
    private final byte[] depthMap;
    // 管理更小的内存，数组大小为2048
    private final PoolSubpage<T>[] subpages;
    // 剩余的内存
    private int freeBytes;
    PoolChunk<T> prev;
    PoolChunk<T> next;
}
```

PoolChunk 本身是一个泛型类型，内部保存了一个叫作 memory 的变量，这个 memory 会根据分配的是堆内存还是直接内存而变换类型：

- 对于堆内存，memory 的类型为 byte []
- 对于直接内存，memory 的类型为 ByteBuffer，实际上为 DirectByteBuffer

所有的数据都存储在 memory 中，至于更小粒度的划分，比如 PoolSubpage，它们使用各种偏移量对 memory 进行分段处理，数据本身并不会复制到这些细粒度的类中。

> 在 Netty 中，并没有 PoolPage 或者 Page 这个类，Page 是一种抽象的说法，它表示的是 PoolChunk 中每 8KB 的数据块，它同样使用 PoolSubpage 来表示。

默认地，Netty 使用伙伴算法将 PoolChunk 分成 2048 个 Page，这些 Page 又向上形成一颗满二叉树：
![图片描述](https://img1.sycdn.imooc.com/5f2a0e7f0001f3be10290823.png)

结合上图，我们先来简单介绍一下 PoolChunk 中的几个变量：

- depthMap，保存着满二叉树原始的高度信息，比如 depthMap [1024]=10
- memoryMap，初始值等于 depthMap，随着节点的被分配，它的值会不断变化，更新子节点的值时，会同时更新其父节点的值，其父节点的值等于两个子节点值中的最小者。
- subpages，对应于上图中的 Page0、Page1、…、Page2047，在 Netty 中并没有 Page 的具体代码实现，它同样使用 PoolSubpage 来表示。只有分配的内存小于 8KB，才会使用 PoolSubpage 进行管理，在 PoolSubpage 创建之后，会加入到 PoolArena 中 tinySubpagePools [] 或 smallSubpagePools [] 对应位置的链表中，同时，在 PoolSubpage 代表的内存被分配完之后，会从对应的链表中删除，也就是说，在同一时刻，head 最多只会与一个 PoolSubpage 形成双向链表。
- freeBytes，PoolChunk 中剩余的内存，即可被使用的内存。

> 如果分配的内存大于等于 8KB，由 PoolChunk 自己管理。

为了更好地理解伙伴分配算法，我们来假想一种分配内存的情况，如果分配内存的顺序分别为 8KB、16KB、8KB，则会按以下顺序进行：

- 8KB，符合一个 Page 大小，所以从第 11 层（12-8KB/8KB）寻找节点，这里找到了 2048 这个节点，发现其 memoryMap [2048]=11=depthMap [2048]，可以被分配，然后到其对应的 Page [0] 中分配内存，分配之后将其 memoryMap [2048]=12，memoryMap [1024]=11=（2048 和 2049 中的最小者 11），memoryMap [512]=10=（1024 和 1025 中的最小者 10），…，memoryMap [1]=1；
- 16KB，符合两个 Page 大小，所以从第 10 层寻找节点（12-16KB/8KB），找到 1024 节点，发现其 memoryMap [1024]=11!=depthMap [1024]，不符合条件，继续寻找到 1025 节点，发现其 memoryMap [1025]=10=depthMap [1025]，符合条件，所以，到其对应的叶子节点 2050/2051 对应的 Page [2]/Page [3] 中分配内存，分配之后 memoryMap [2050]=12，memoryMap [2051]=12，memoryMap [1025]=12=（2050 和 2051 中的最小值 12），memoryMap [512]=11=（1024 和 1025 中的最小者 11），…，memoryMap [1]=1；
- 8KB，符合一个 Page 大小，所以从第 11 层（12-8KB/8KB）寻找节点，2048 已经不符合条件了，所以找到了 2049 这个节点，到其对应的 Page [1] 中分配内存，然后更新 memoryMap [2049]=12，memoryMap [1024]=12=（2048 和 2049 中的最小者 12），memoryMap [512]=12=（1024 和 1025 中的最小者 12），…，memoryMap [1]=1；

至此，三次内存都分配完毕，总共分配了 Page0~Page3 共 4 个 Page，从分配结果也可以看出，使用伙伴分配算法，能极大地保证分配连续的内存空间，并减少内存碎片的诞生。



 ##### PoolSubpage

前面我们说过，只有当分配的内存小于一个 Page 大小，即 8KB 时，才会使用 PoolSubpage 来进行管理，那么它是怎么管理的呢？

让我们先来看看它的几个关键字段：

```java
final class PoolSubpage<T> implements PoolSubpageMetric {
    // 对应满二叉树中的哪个节点
    private final int memoryMapIdx;
    // 在PoolChunk的memory中的偏移量
    private final int runOffset;
    // 表示每个小块的状态
    private final long[] bitmap;
    // 每个小块（元素）的大小
    int elemSize;
    // 最大的元素个数=8KB/elemSize
    private int maxNumElems;
    // 需要使用到几个long
    private int bitmapLength;
    // 可用的元素个数
    private int numAvail;
    // 双向链表的指针
    // 与PoolArena中的tinySubpagePoos或smallSubpagePools中的元素形成双向链表
    PoolSubpage<T> prev;
    PoolSubpage<T> next;
}
```

elemSize 表示每个元素的大小，这个大小是根据这个 Page 接收到的第一个请求的大小决定的。

比如，首次分配 30B 的内存，则会经历以下几个步骤：

1. 判断小于 512B，按 16B 向上规范化到 32B；
2. 在满二叉树的第 11 层寻找一个可用的节点，假如是 2049，即 memoryMapIdx=2049，它代表的是 Page1，Page1 这个节点在 PoolChunk 中对应到 memory 上的偏移量就是 8192（前面有个 Page0），所以，runOffset=8192；
3. 此时，会把 Page0 按 32B 分成（8KB/32B=256）个小块，所以，elemSize=32B，maxNumElems=256，numAvail=256；
4. 同时，这 256 个小块就需要 256 个 bit（位）来表示其每个小块的状态，也就是需要（256/64=4）个 long 类型来表示，所以，bitmapLength=4；
5. 然后，把这个 PoolSubpage 与 PoolArena 的 tinySubpagePools [1]（相当于 head）形成双向链表，因为 tinySubpagePools [0] 代表的是 16B 的内存，tinySubpagePools [1] 代表的是 32B 的内存；
6. 当分配完这 32B 之后，可用节点数减一，所以，numAvail=255；

当再次分配规范为 32B 内存的时候，就看 PoolArena 的 tinySubpagePools [1] 的 next 中有没有值，有值，就直接使用其分配内存了，而不用再重新走一遍上面的过程，从而加快分配内存的速度。



 ##### PoolThreadCache

前面讲了这么多，分配内存的速度已经足够快了，但是，还可以更快，那就是加入线程缓存 PoolThreadCache，那么，PoolThreadCache 在何时使用呢？

其实，这要结合回收内存一起使用，当回收内存时，先不还给 PoolChunk，而是使用本地线程缓存起来，当下一次再分配同样大小（规范化后的大小）的内存时，先尝试从本地线程缓存里面取，如果取到了就可以直接使用了。

那么，PoolThreadCache 可以缓存哪些类型的缓存呢？

在 Netty 中，除了 Huge，其它类型的内存都可以缓存，即 Tiny、Small、Normal，当然，根据堆内存和直接内存的不同，PoolThreadCache 中又分成了两大类：

```java
final class PoolThreadCache {
    // 堆内存的缓存
    private final MemoryRegionCache<byte[]>[] tinySubPageHeapCaches;
    private final MemoryRegionCache<byte[]>[] smallSubPageHeapCaches;
    private final MemoryRegionCache<byte[]>[] normalHeapCaches;
    // 直接内存的缓存
    private final MemoryRegionCache<ByteBuffer>[] tinySubPageDirectCaches;
    private final MemoryRegionCache<ByteBuffer>[] smallSubPageDirectCaches;
    private final MemoryRegionCache<ByteBuffer>[] normalDirectCaches;
}
```

PoolThreadCache 中使用了一个叫作 MemoryRegionCache 的类来做缓存，它内部维护了一个队列，当回收内存时，这块内存进入到这个队列中，当下次再分配同样大小（规范化后的大小）的内存时，从这个队列中取，关于 PoolThreadCache 的使用，我们下一节结合代码一起学习。



 ### 后记

今天，我们一起学习了 Netty 中 jemalloc 内存分配器实现的一些基本概念，有了这些概念，我们再去学习 Netty 的内存池，相信一定可以事半功倍的。

下一节，我们将通过调试大法把今天讲的这些概念全部连成线，从根本上理解 Netty 中内存池的实现原理，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f2a0e95000105fd25531601.png)



 ### 原生 jemalloc 相关链接

[1] [one malloc to rule them all](http://blog.reverberate.org/2009/02/one-malloc-to-rule-them-all.html)

[2] [Structures in jemalloc](https://medium.com/iskakaushik/eli5-jemalloc-e9bd412abd70)

[3] [A Scalable Concurrent malloc(3) Implementation for FreeBSD](https://www.bsdcan.org/2006/papers/jemalloc.pdf)

[4] [Scalable memory allocation using jemalloc](https://www.facebook.com/notes/facebook-engineering/scalable-memory-allocation-using-jemalloc/480222803919/)

[5] [ptmalloc,tcmalloc 和 jemalloc 内存分配策略研究](http://www.360doc.com/content/13/0915/09/8363527_314549128.shtml)





<div style="page-break-after:always;"></div>

 ## 21 Netty的内存池是如何实现的


![img](https://img4.sycdn.imooc.com/5f05962b0001a81106400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)人的影响短暂而微弱，书的影响则广泛而深远。——普希金![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了Netty中jemalloc的基本概念，并从原理层面对jemalloc做了一定的解析，本节，我们将从源码层面对Netty的内存池做一个全面的剖析。

因为内存池跟对象池往往纠缠在一起，所以，关于对象池相关的代码本节一律先跳过，免得把你弄晕。

好了，让我们开始今天的学习吧。



 ### 问题

对于今天的源码剖析，你可以带着下面这么几个问题：

1. PoolArena中的PoolSubpage数组和PoolChunk中的PoolSubpage数组有什么关联？
2. PoolThreadCache中的MemoryRegionCache数组与PoolSubpage是否有联系？
3. Netty内存池的整体结构是什么样的？
4. 如果让你来介绍Netty内存池，你如何来描述？



 ### 内存池源码剖析



 #### 调试用例

上一节，我们说了Netty根据请求的大小将其分成四类：Tiny、Small、Normal、Huge，这四类请求的分界线分别为512B、8KB、16MB，针对这四类请求，Netty的处理逻辑并不一样，但是，本节，我们并不打算把这四种全部讲解一遍，我们只讲解其中的一个——Tiny。

另外，为了加快分配内存的速度，Netty还使用了线程缓存，而线程缓存实际上是在有回收内存的情况下才有效，所以，我们设计的调试用例里面还应该包括回收内存的部分，即`ReferenceCountUtil.release(byteBuf)`。

好了，让我们看看今天的调试用例吧：

```java
public class ByteBufTest {
    public static void main(String[] args) {
        // 1. 创建池化的分配器
        ByteBufAllocator allocator = new PooledByteBufAllocator(false);
        // 2. 分配一个40B的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer(40);
        // 3. 写入数据
        byteBuf.writeInt(4);
        // 4. 读取数据
        System.out.println(byteBuf.readInt());
        // 5. 回收内存
        ReferenceCountUtil.release(byteBuf);
        // 6. 分配一个30B的ByteBuf
        ByteBuf byteBuf2 = allocator.heapBuffer(30);
        // 7. 再次分配一个40B的ByteBuf
        ByteBuf byteBuf3 = allocator.heapBuffer(40);
    }
}
```

我们先创建一个池化的分配器，使用其分配一个40B的ByteBuf，接着写入数据并读取数据，然后回收，理论上来说，这个40B的ByteBuf会进入线程缓存，接着再分配一个30B的ByteBuf，观察其是否会从线程缓存中获取，最后再分配一个40B的ByteBuf，观察其是否会从线程缓存中获取。



 #### 源码调试

本节的代码有点多，有些不太重要的我就直接跳过去了，希望大家能够亲自动手调试一下整个过程。



 ##### 1. 创建池化的分配器

让我们先在创建分配器那行打个断点，跟踪进去：

```java
public PooledByteBufAllocator(boolean preferDirect, int nHeapArena, int nDirectArena, 
                              int pageSize, int maxOrder,
                              int tinyCacheSize, int smallCacheSize, int normalCacheSize,
                              boolean useCacheForAllThreads, int directMemoryCacheAlignment) {
    super(preferDirect);
    // 这是一个ThreadLocal，用于存放线程缓存PoolThreadCache对象
    threadCache = new PoolThreadLocalCache(useCacheForAllThreads);
    // Tiny的缓存个数，默认512
    this.tinyCacheSize = tinyCacheSize;
    // Small的缓存个数，默认256
    this.smallCacheSize = smallCacheSize;
    // Normal的缓存个数，默认64
    this.normalCacheSize = normalCacheSize;
    // pageSize默认为8KB
    // maxOrder表示树的最大高度，默认为11
    // 计算每个Chunk的大小，默认为16MB
    chunkSize = validateAndCalculateChunkSize(pageSize, maxOrder);

    // ...

    // 计算每页大小的左移位数
    // pageSize=8KB=10 0000 0000 0000=1<<13
    // pageShifts表示pageSize是1左移13位得来的
    // 所以pageShifts为13
    int pageShifts = validateAndCalculatePageShifts(pageSize);

    // 初始化堆内存池heapArenas
    // 默认为CPU核数*2，同时根据堆内存大小调整
    if (nHeapArena > 0) {
        heapArenas = newArenaArray(nHeapArena);
        List<PoolArenaMetric> metrics = new ArrayList<PoolArenaMetric>(heapArenas.length);
        for (int i = 0; i < heapArenas.length; i ++) {
            // 创建HeapArena并加入到数组中
            PoolArena.HeapArena arena = new PoolArena.HeapArena(this,
                                                                pageSize, maxOrder, pageShifts, chunkSize,
                                                                directMemoryCacheAlignment);
            heapArenas[i] = arena;
            // 同时加入监控
            metrics.add(arena);
        }
        heapArenaMetrics = Collections.unmodifiableList(metrics);
    } else {
        heapArenas = null;
        heapArenaMetrics = Collections.emptyList();
    }

    // 初始化直接内存池directArenas
    // 默认为CPU核数*2，同时根据直接内存大小调整
    if (nDirectArena > 0) {
        directArenas = newArenaArray(nDirectArena);
        List<PoolArenaMetric> metrics = new ArrayList<PoolArenaMetric>(directArenas.length);
        for (int i = 0; i < directArenas.length; i ++) {
            // 创建DirectArena并加入到数组中
            PoolArena.DirectArena arena = new PoolArena.DirectArena(
                this, pageSize, maxOrder, pageShifts, chunkSize, directMemoryCacheAlignment);
            directArenas[i] = arena;
            // 同时加入监控
            metrics.add(arena);
        }
        directArenaMetrics = Collections.unmodifiableList(metrics);
    } else {
        directArenas = null;
        directArenaMetrics = Collections.emptyList();
    }
    // 监控
    metric = new PooledByteBufAllocatorMetric(this);
}
```

在PooledByteBufAllocator的构造方法中，主要是初始化一些属性，比如chunkSize、heapArenas和directArenas数组等，默认地，chunkSize为16M，heapArenas和directArenas数组大小为2倍的CPU核数，同时根据内存大小动态调整。



 ##### 2. 分配一个40B的ByteBuf

好了，上面我们已经创建好了一个池化的分配器，下面就来看看它是如何为我们分配一个40B的ByteBuf的，继续调试：

```java
// PooledByteBufAllocator#newHeapBuffer
@Override
protected ByteBuf newHeapBuffer(int initialCapacity, int maxCapacity) {
    // 先从ThreadLocal中获取一个PoolThreadCache线程缓存对象
    PoolThreadCache cache = threadCache.get();
    // 因为我们创建的是基于堆内存的ByteBuf，所以使用heapArena
    // 另外，在PoolThreadCache初始化的时候会绑定一个最少使用的heapArena
    // 所以这里是可以获取到的
    // 具体可参考PooledByteBufAllocator.PoolThreadLocalCache#initialValue()方法
    PoolArena<byte[]> heapArena = cache.heapArena;

    final ByteBuf buf;
    if (heapArena != null) {
        // 使用heapArena来分配
        buf = heapArena.allocate(cache, initialCapacity, maxCapacity);
    } else {
        buf = PlatformDependent.hasUnsafe() ?
            new UnpooledUnsafeHeapByteBuf(this, initialCapacity, maxCapacity) :
        new UnpooledHeapByteBuf(this, initialCapacity, maxCapacity);
    }

    return toLeakAwareBuffer(buf);
}
```

在这段代码中，首先从threadCache中获取了一个PoolThreadCache对象cache，再从这个cache中获取一个heapArena，这个heapArena是从allocator的heapArenas数组中取的一个最少使用的，在cache初始化的时候绑定进去的，为什么绑定的是最少使用的呢？

我们知道，heapArenas数组的大小是固定的，而线程是可能无限多的，每个线程都要绑定一个heapArena，那么，怎么绑定才能减少线程之间的竞争呢？答案很明显，绑定最少使用的那个heapArena。比如，heapArenas数组大小为16，而线程也正好为16，这样的话，线程之间完全没竞争关系，如果按照数组的顺序绑定，最后这16个线程都会绑定到同一个heapArena，竞争非常剧烈。

OK，我们继续跟踪到`heapArena.allocate()`中：

```java
// PoolArena#allocate(PoolThreadCache, int, int)
PooledByteBuf<T> allocate(PoolThreadCache cache, int reqCapacity, int maxCapacity) {
    // 使用对象池创建一个池化的ByteBuf，先不展开，跳过
    // PooledByteBuf中有一个memory字段用来存放数据
    // 从对象池中返回的这个buf，它的memory大小为0
    // 内存池的作用就是为了给这个memory分配空间
    PooledByteBuf<T> buf = newByteBuf(maxCapacity);
    // 继续深入
    allocate(cache, buf, reqCapacity);
    return buf;
}
// PoolArena#allocate(PoolThreadCache, PooledByteBuf<T>, int)
private void allocate(PoolThreadCache cache, PooledByteBuf<T> buf, final int reqCapacity) {
    // 将请求的大小规范化，这里40B会被规范化到48B
    final int normCapacity = normalizeCapacity(reqCapacity);
    // 判断是否小于8KB
    if (isTinyOrSmall(normCapacity)) { // capacity < pageSize
        int tableIdx;
        PoolSubpage<T>[] table;
        // 是否为Tiny，即小于512B
        boolean tiny = isTiny(normCapacity);
        if (tiny) { // < 512
            // 先尝试从线程缓存中分配内存
            if (cache.allocateTiny(this, buf, reqCapacity, normCapacity)) {
                // 分配成功则返回
                return;
            }
            // 计算48B在tinySubpagePools数组中的索引
            // 16、32、48，所以这里的索引是3
            tableIdx = tinyIdx(normCapacity);
            // PoolArena的tinySubpagePools数组，大小为32
            table = tinySubpagePools;
        } else {
            // 如果为Small，从这里走
            if (cache.allocateSmall(this, buf, reqCapacity, normCapacity)) {
                return;
            }
            tableIdx = smallIdx(normCapacity);
            table = smallSubpagePools;
        }

        // 获取头节点，head中不存放任何数据，仅用来加锁使用
        final PoolSubpage<T> head = table[tableIdx];

        // 分段锁的用法，减少锁竞争
        synchronized (head) {
            // 因为还没有分配过任何内存，所以next为空，先跳过这一段
            final PoolSubpage<T> s = head.next;
            // ...
            // 分配成功会返回
        }
        // 按PoolArena加锁，又是分段锁的用法
        // 这里就体会到了上面按最少使用去绑定PoolArena的魅力了吧
        // 减少了锁竞争
        synchronized (this) {
            // 这个方法名有点歧义
            // 并不是说按Normal的请求去处理
            allocateNormal(buf, reqCapacity, normCapacity);
        }

        incTinySmallAllocation(tiny);
        return;
    }
    // 如果是Normal请求
    if (normCapacity <= chunkSize) {
        // ...
    } else {
        // 如果是Huge请求
        allocateHuge(buf, reqCapacity);
    }
}
```

这段代码中运用了大量的分段锁技巧：

- PoolArena，每个线程绑定一个最少使用的PoolArena，充分减少锁竞争。
- tinySubpagePools，按16B分成32段，只有分配相同大小（规范后的大小）的请求时且还是两个线程绑定到同一个PoolArena的情况下才有锁竞争。

结合ConcurrentHashMap中分段锁的用法，我们归纳出来一个规律：**分段锁一般都是通过数组来实现的，通过某种规则将多个线程的操作分离到数组中不同的位置上，以便降低线程之间修改同一段数组的竞争，所以，有时候也叫作锁分离。**

比如，在ConcurrentHashMap中，是根据key值hash到不同的桶中进行处理。在PoolArena中，是通过线程绑定最小使用PoolArena来达到锁分离的目的。在tinySubpagePools中，是通过将请求分割成不同的段进行处理减少锁竞争。

OK，让我们继续跟踪到`allocateNormal()`内部：

```java
// PoolArena#allocateNormal
private void allocateNormal(PooledByteBuf<T> buf, int reqCapacity, int normCapacity) {
    // 先尝试从已有的PoolChunk中分配内存
    // 此时是第一次请求，所以，没有任何可用的PoolChunk
    if (q050.allocate(buf, reqCapacity, normCapacity) 
        || q025.allocate(buf, reqCapacity, normCapacity) 
        || q000.allocate(buf, reqCapacity, normCapacity) 
        || qInit.allocate(buf, reqCapacity, normCapacity) 
        || q075.allocate(buf, reqCapacity, normCapacity)) {
        return;
    }

    // key1, 创建一个新的PoolChunk
    PoolChunk<T> c = newChunk(pageSize, maxOrder, pageShifts, chunkSize);
    // key2, 使用这个PoolChunk分配内存
    boolean success = c.allocate(buf, reqCapacity, normCapacity);
    assert success;
    // 这新的PoolChunk加入到qInit中
    qInit.add(c);
}
```

这个方法中，有两个关键的地方：

- 创建PoolChunk，通过上一节的分析，我们知道，数据全部都是存储在PoolChunk的memory字段中的，那么，这个memory是如何创建的呢？
- 使用PoolChunk分配内存，如何分配？

我们先来看第一个问题：

```java
// PoolArena.HeapArena#newChunk
@Override
protected PoolChunk<byte[]> newChunk(int pageSize, int maxOrder, int pageShifts, int chunkSize) {
    return new PoolChunk<byte[]>(this, newByteArray(chunkSize), pageSize, maxOrder, pageShifts, chunkSize, 0);
}
// PoolArena.HeapArena#newByteArray
private static byte[] newByteArray(int size) {
    // 调用PlatformDependent
    return PlatformDependent.allocateUninitializedArray(size);
}    
public static byte[] allocateUninitializedArray(int size) {
    // 默认地，UNINITIALIZED_ARRAY_ALLOCATION_THRESHOLD=-1
    // 创建了一个大小为16MB的byte[]数组，在堆内存中
    return UNINITIALIZED_ARRAY_ALLOCATION_THRESHOLD < 0 || UNINITIALIZED_ARRAY_ALLOCATION_THRESHOLD > size ?
        new byte[size] : PlatformDependent0.allocateUninitializedArray(size);
}
// PoolChunk的构造方法
PoolChunk(PoolArena<T> arena, T memory, int pageSize, int maxOrder, int pageShifts, int chunkSize, int offset) {
    unpooled = false;
    this.arena = arena;
    // memory就是上面创建的byte[]数组
    this.memory = memory;
    // 8KB
    this.pageSize = pageSize;
    // 13
    this.pageShifts = pageShifts;
    // 11
    this.maxOrder = maxOrder;
    // 16MB
    this.chunkSize = chunkSize;
    // 0
    this.offset = offset;
    // 12，表示如果满二叉树中的节点更新到了12，则表示此节点已完全分配了
    unusable = (byte) (maxOrder + 1);
    // 24，用于计算满二叉树中的节点占用的空间大小，比如2048占用8K，而1024占用16K
    log2ChunkSize = log2(chunkSize);
    // -8192，表示subpage溢出的掩码
    subpageOverflowMask = ~(pageSize - 1);
    // 初始时可使用的内存等于PoolChunk的整个空间，即16MB
    freeBytes = chunkSize;

    assert maxOrder < 30 : "maxOrder should be < 30, but is: " + maxOrder;
    // 一个PoolChunk可以被分成多少页，1<<11=2048
    maxSubpageAllocs = 1 << maxOrder;

    // 创建memoryMap和depthMap，满二叉树，最后一层的节点数正好等于上面所有层的节点数
    // 所以它们的大小为2048*2=4096
    memoryMap = new byte[maxSubpageAllocs << 1];
    depthMap = new byte[memoryMap.length];
    int memoryMapIndex = 1;
    // 初始化memoryMap和depthMap中的元素为每个节点的高度
    for (int d = 0; d <= maxOrder; ++ d) {
        int depth = 1 << d;
        for (int p = 0; p < depth; ++ p) {
            memoryMap[memoryMapIndex] = (byte) d;
            depthMap[memoryMapIndex] = (byte) d;
            memoryMapIndex ++;
        }
    }
    // 一个PoolChunk可以被分割成2048个Page
    // Page在Netty中同样使用PoolSubpage来表示
    subpages = newSubpageArray(maxSubpageAllocs);
    cachedNioBuffers = new ArrayDeque<ByteBuffer>(8);
}
```

> 满二叉树非常适合用数组来存储，下层节点的个数正好是上层节点个数的两倍，所以，从数组下标为1的位置开始存储元素，那么它的两个子节点的下标正好是父节点下标的两倍及两倍加1，举个例子，节点6的子节点分别为节点12和节点13，反之，一个节点的父节点正好为其下标的一半，比如节点13的父节点为`13/2=6`。
> ![图片描述](https://img1.sycdn.imooc.com/5f2b61550001870c10340441.png)

这段代码主要创建了一个基于堆内存的byte[]数组并将其赋值给了PoolChunk的memory字段。同时，构建了两棵满二叉树memoryMap和depthMap，memoryMap用于保存节点分配的情况，depthMap用于存储节点的原始高度，当一个节点被完全分配后，它在memoryMap中的值将变成12（unusable）。并且，新建了一个大小为2048的PoolSubpage数组，当然了，这个数组暂未初始化，因为如果分配的内存大于等于一个Page大小（8KB）时，这个数组其实并没有什么用。

OK，到此，我们已经从堆内存拿到了一个16MB的byte[]数组，那么，PoolChunk是怎么把它分配给具体的PoolByteBuf的呢？继续跟踪`c.allocate()`方法:

```java
// buffer.PoolChunk#allocate
boolean allocate(PooledByteBuf<T> buf, int reqCapacity, int normCapacity) {
    final long handle;
    // 判断是否大于等于一个Page的大小，即8KB
    if ((normCapacity & subpageOverflowMask) != 0) { // >= pageSize
        // 调用allocateRun()处理
        handle =  allocateRun(normCapacity);
    } else {
        // key1，调用allocateSubpage()处理
        handle = allocateSubpage(normCapacity);
    }

    // 处理失败
    if (handle < 0) {
        return false;
    }
    ByteBuffer nioBuffer = cachedNioBuffers != null ? cachedNioBuffers.pollLast() : null;
    // key2，分配完毕，初始化前面创建的PooledByteBuf
    // 所有分配的信息都保存在handle中
    initBuf(buf, nioBuffer, handle, reqCapacity);
    return true;
}
```

这个方法主要包含两部分内容：

- 根据请求的大小调用不同的方法处理，如果请求大于8KB，交给allocateRun()方法处理，否则交给allocateSubpage()方法处理，它们都会返回一个叫作handle的long类型变量，这个handle里面就保存着分配内存的结果，这两个handle有什么区别呢？
- 使用上述返回的handle初始化前面创建的PooledByteBuf对象；

我们接着来看看两个分配的方法，先来一个简单点的分配方法——`allocateRun()`：

```java
// PoolChunk#allocateRun
// 这个方法仅用于分配大于等于8KB的内存
private long allocateRun(int normCapacity) {
    // 计算在满二叉树的哪层寻找节点
    // 假设normCapacity=8KB
    // d=11-(log2(8192)-13)=11-(13-13)=11
    int d = maxOrder - (log2(normCapacity) - pageShifts);
    // 在d层寻找到一个节点，这个节点的id
    // 比如，在11层找到了2048这个节点
    int id = allocateNode(d);
    if (id < 0) {
        return id;
    }
    // 整个PoolChunk的可用容量减去8192
    // runLength()用于计算节点占用的数据量
    // 比如2048这个节点，注意位运算与减法运算的优先级
    // runLength(2048)=1<<log2ChunkSize-depth(id)=1<<(24-11)=1<<13=8192
    freeBytes -= runLength(id);
    // 返回这个节点的id
    return id;
}
```

allocateRun()方法用于分配大于等于8KB的内存，最后返回的是找到的那个节点的id，当然，这里在allocateNode()方法中也会调用updateParentsAlloc(id)方法更新其及父节点在memoryMap中的值，这一块就不细说了。

再来看看第二个分配方法——`allocateSubpage()`：

```java
// PoolChunk#allocateSubpage
// 用于分配小于8KB的内存
private long allocateSubpage(int normCapacity) {
    // 根据规范化后的大小从PoolArena的tinySubpagePools或者smallSubpagePools中找到一个合适的元素作为head
    PoolSubpage<T> head = arena.findSubpagePoolHead(normCapacity);
    // 从第11层寻找一个合适的节点
    // 因为小于8KB，所以肯定是从叶子节点中寻找合适的节点
    int d = maxOrder;
    // 分段锁
    synchronized (head) {
        // 找到的节点id，比如2048
        int id = allocateNode(d);
        if (id < 0) {
            return id;
        }

        // 这个数组是PoolChunk中的数组，其实是Page数组，大小为2048
        final PoolSubpage<T>[] subpages = this.subpages;
        // 一页的大小，8192
        final int pageSize = this.pageSize;

        // 可用容量减去1页的大小
        // 这一页只要分配出去了内存，则表示这一页都被占用了
        // 后续只能分配跟第一次请求大小（规范后的大小）一样的内存
        freeBytes -= pageSize;

        // Page的索引，比如2048对应Page0
        int subpageIdx = subpageIdx(id);
        // 取出这个Page
        PoolSubpage<T> subpage = subpages[subpageIdx];
        if (subpage == null) {
            // 创建一个Page，并将其与PoolArena的head节点形成双向循环链表
            // runOffset()表示的是这个Page在PoolChunk中的偏移量
            // elemSize=normCapacity
            subpage = new PoolSubpage<T>(head, this, id, runOffset(id), pageSize, normCapacity);
            subpages[subpageIdx] = subpage;
        } else {
            subpage.init(head, normCapacity);
        }
        // 使用Page来分配内存
        return subpage.allocate();
    }
}
```

![图片描述](https://img1.sycdn.imooc.com/5f2b61760001f3be10290823.png)

跟PoolSubpage这块相关的内容可以结合上一节的图来学习，一定要时刻记住，PoolSubpage有两重身份，一重代表着Page，一重代表着更小的内存块。

可以发现，PoolChunk对于分配小于8KB的内存，最后还是交给PoolSubpage来干的，所以，我们继续往里跟踪：

```java
// PoolSubpage#allocate
long allocate() {
    if (elemSize == 0) {
        return toHandle(0);
    }

    if (numAvail == 0 || !doNotDestroy) {
        return -1;
    }
    // bitmap的每一bit（位）用于保存每一小块内存是否被分配了
    final int bitmapIdx = getNextAvail();
    // q表示在第几个long中，2的6次方=64，q=bimapIdx>>>6=bitmapIdx/64
    // 比如，130位对应于下标为130/64=2的long的第2位
    int q = bitmapIdx >>> 6;
    // r表示在这个long类型中的偏移量
    // 相当于bitmapIdx%64
    // 比如，130%64=2
    int r = bitmapIdx & 63;
    assert (bitmap[q] >>> r & 1) == 0;
    // 更新第q个long的第r位为1，表示已分配
    bitmap[q] |= 1L << r;

    // 如果可用内存为0了，就从PoorArena的tinySubpagePools或者smallSubpagePools对应的链表中移除
    if (-- numAvail == 0) {
        removeFromPool();
    }

    // 转换成handle
    return toHandle(bitmapIdx);
}
private long toHandle(int bitmapIdx) {
    // 为了与Normal类型的区分，加一个掩码
    // 比如，在Page0中分得了一小块内存，且是第一个元素
    // 那么handle=0x4000000000000000L|0|2048
    return 0x4000000000000000L | (long) bitmapIdx << 32 | memoryMapIdx;
}
```

关于bitmap，我举个例子助你来理解，比如，按48B分割一个Page，那么，可以分割成`8KB/48B=170.666=170`个小内存块，剩余那零点几就变成了内存碎片，一个long类型可以存储64个小内存块的状态信息，那么，170个就需要`170/64=2.656=3`个long类型来存储所有小内存块的状态信息，此时，要分配第130个48B，那么，就标记下标为2的long的第2位为1，当然，在此之前前面129位肯定都已经被分配了，所以它们对应的位都是1：
![图片描述](https://img1.sycdn.imooc.com/5f2b61920001332510290391.png)

好了，到这里内存就已经分配完毕了，那么，怎么把它跟PooledByteBuf关联起来呢？其实也很简单，只要把上面我们求得的那个handle跟PooledByteBuf绑定在一起我们就能准确地定位到是在哪个Page的哪一小块分配了多少的内存，这也就是初始化PooledByteBuf的功能，即：`initBuf()`：

```java
// PoolChunk#initBuf
void initBuf(PooledByteBuf<T> buf, ByteBuffer nioBuffer, long handle, int reqCapacity) {
    // 第几号节点
    int memoryMapIdx = memoryMapIdx(handle);
    // bitmapIdx索引
    int bitmapIdx = bitmapIdx(handle);
    // bitmapIdx=0表示的是Normal
    // 因为subpage方式的handle前面有个掩码，所以不会为0
    if (bitmapIdx == 0) {
        byte val = value(memoryMapIdx);
        assert val == unusable : String.valueOf(val);
        buf.init(this, nioBuffer, handle, runOffset(memoryMapIdx) + offset,
                 reqCapacity, runLength(memoryMapIdx), arena.parent.threadCache());
    } else {
        // 使用subpage初始化
        initBufWithSubpage(buf, nioBuffer, handle, bitmapIdx, reqCapacity);
    }
}
// PoolChunk#initBufWithSubpage(PooledByteBuf<T>, ByteBuffer, long, int, int)
private void initBufWithSubpage(PooledByteBuf<T> buf, ByteBuffer nioBuffer,
                                long handle, int bitmapIdx, int reqCapacity) {
    assert bitmapIdx != 0;

    // 第几号节点
    int memoryMapIdx = memoryMapIdx(handle);

    // 第几个Page
    PoolSubpage<T> subpage = subpages[subpageIdx(memoryMapIdx)];
    assert subpage.doNotDestroy;
    assert reqCapacity <= subpage.elemSize;

    // 调用PooledByteBuf自己的init方法
    // 第四个参数用于计算这一小块内存在整个PoolChunk中的偏移量
    buf.init(
        this, nioBuffer, handle,
        runOffset(memoryMapIdx) + (bitmapIdx & 0x3FFFFFFF) * subpage.elemSize + offset,
        reqCapacity, subpage.elemSize, arena.parent.threadCache());
}
// PooledByteBuf#init
void init(PoolChunk<T> chunk, ByteBuffer nioBuffer,
          long handle, int offset, int length, int maxLength, PoolThreadCache cache) {
    init0(chunk, nioBuffer, handle, offset, length, maxLength, cache);
}
// PooledByteBuf#init0
private void init0(PoolChunk<T> chunk, ByteBuffer nioBuffer,
                   long handle, int offset, int length, int maxLength, PoolThreadCache cache) {
    assert handle >= 0;
    assert chunk != null;

    // 属于哪个PoolChunk
    this.chunk = chunk;
    // 将chunk的memory赋值给buf
    memory = chunk.memory;
    tmpNioBuf = nioBuffer;
    // 哪个分配器
    allocator = chunk.arena.parent;
    // 绑定的PoolThreadCache，在释放内存的时候使用
    this.cache = cache;
    // handle，记录了哪个节点哪个位
    this.handle = handle;
    // 在整个chunk中的偏移量
    this.offset = offset;
    // 实际请求的大小，即40B
    this.length = length;
    // 最大长度，为规范化后的大小，即48B
    this.maxLength = maxLength;
}
```

OK，到这里整个PooledByteBuf就创建完毕了，既然PooledByteBuf中保存了PoolChunk的整个memory及操作的偏移量，那么，写入数据和读取数据的时候是不是只要按这个偏移量来操作就可以了呢？



 ##### 3. 写入数据

关于写入数据，我们快速的过一下源码：

```java
// 写入一个int类型
@Override
public ByteBuf writeInt(int value) {
    ensureWritable0(4);
    _setInt(writerIndex, value);
    writerIndex += 4;
    return this;
}
@Override
protected void _setInt(int index, int value) {
    // 调用Unsafe来写入数据
    // memory即chunk的memory
    UnsafeByteBufUtil.setInt(memory, idx(index), value);
}
protected final int idx(int index) {
    // 计算写入偏移量，等于memory的偏移量+writeIndex
    return offset + index;
}
```

可以看到，跟我们预期的完全一样，这里我再提一个问题：通过前面我们分析非池化的ByteBuf，我们知道，Netty中的ByteBuf是可以扩容的，而上面我们创建PooledByteBuf有个maxLength限制了最大可以使用的内存，那么，对于PooledByteBuf，它是如何扩容的呢？留给你自己来探索喽^^



 ##### 4. 读取数据

读取数据肯定是跟写入数据一样的处理方式，这里就不再赘述了。



 ##### 5. 回收内存

到目前为止，PoolThreadCache都没有派上用场，那么，它是没用吗？当然不是，只有回收内存的时候才考虑要不要把这部分内存放到PoolThreadCache中缓存起来，下面我们就来看看回收内存的整个过程，同样地，还是直接跟踪到源码里面：

```java
// ReferenceCountUtil#release(Object)
// 回收内存的工具方法
public static boolean release(Object msg) {
    if (msg instanceof ReferenceCounted) {
        return ((ReferenceCounted) msg).release();
    }
    return false;
}
// ...
// PooledByteBuf#deallocate
@Override
protected final void deallocate() {
    if (handle >= 0) {
        final long handle = this.handle;
        // 将handle置为-1
        this.handle = -1;
        // 将memory置为空
        memory = null;
        // 调用PoolArena的free()方法回收内存
        chunk.arena.free(chunk, tmpNioBuf, handle, maxLength, cache);
        tmpNioBuf = null;
        // 将chunk置为空
        chunk = null;
        // 对象池的方法，本节暂不涉及
        recycle();
    }
}
```

这里将PooledByteBuf中跟内存池有关的变量全部置为初始值，并交给PoolArena来free内存，所以，PoolArena可以看作是整个内存池的管家，所有的入口都在它这里，继续跟进：

```java
// PoolArena#free
// 注意，这个nioBuffer不是上面创建的那个PooledByteBuf
void free(PoolChunk<T> chunk, ByteBuffer nioBuffer, long handle, int normCapacity, PoolThreadCache cache) {
    // 非池化的，对于Huge来说使用的是非池化的方式
    if (chunk.unpooled) {
        int size = chunk.chunkSize();
        destroyChunk(chunk);
        activeBytesHuge.add(-size);
        deallocationsHuge.increment();
    } else {
        SizeClass sizeClass = sizeClass(normCapacity);
        // 使用PoolThreadCache来处理
        if (cache != null && cache.add(this, chunk, nioBuffer, handle, normCapacity, sizeClass)) {
            // 这里相当于线程缓存做了一层拦截，如果被拦截下来了，就不用释放了
            return;
        }

        freeChunk(chunk, handle, sizeClass, nioBuffer, false);
    }
}
// PoolThreadCache#add
boolean add(PoolArena<?> area, PoolChunk chunk, ByteBuffer nioBuffer,
            long handle, int normCapacity, SizeClass sizeClass) {
    // key1，PoolThreadCache中同样根据不同的请求大小分成不同的MemoryRegionCache
    MemoryRegionCache<?> cache = cache(area, normCapacity, sizeClass);
    if (cache == null) {
        return false;
    }
    // 存储在MemoryRegionCache中
    return cache.add(chunk, nioBuffer, handle);
}
// PoolThreadCache.MemoryRegionCache#add
public final boolean add(PoolChunk<T> chunk, ByteBuffer nioBuffer, long handle) {
    Entry<T> entry = newEntry(chunk, nioBuffer, handle);
    // key2，入队
    boolean queued = queue.offer(entry);
    if (!queued) {
        entry.recycle();
    }
    return queued;
}
```

整个流程很清晰，根据请求大小（规范化后的大小）从PoolThreadCache中找到一个对应的MemoryRegionCache，然后把这个PoolChunk的这个handle组成一个Entry放到队列中，这里有两个问题：

1. MemoryRegionCache的规则是什么？
2. 这个队列是阻塞队列吗？

我们先来看第一个问题，其实，MemoryRegionCache跟PoolArena中的tinySubpagePools和smallSubpagePools这两个数组有点类似，在PoolThreadCache中，存在三个类似的数组：tinySubPageHeapCaches、smallSubPageHeapCaches、normalHeapCaches，它们分别用来缓存Tiny、Small、Normal类型的请求，它们的大小分别是32、4、3，前两者跟PoolArena中的那两个数组大小完全一样，寻找的规则也是一模一样的，对于normalHeapCaches，有点区别，它只缓存Normal类型的三个段，即8KB、16KB、32KB，所以，PoolThreadCache最多只能缓存32KB大小的请求释放的内存，超过32KB的请求释放的内存则不再缓存。

接着来看看第二个问题，这个队列不是一个阻塞队列，它是一种叫作`MpscArrayQueue`，`mpsc`的全称叫作`Multiple producer single consumer`，即多生产者单消费者，它是Netty自己实现的一种队列，里面运用了很多Java中的高级技巧，效率比Java原生的阻塞队列或者并发安全的队列要高不少。

那么，Netty为什么要使用这种多生产者单消费者队列呢？

先埋个伏笔，我们后面详细介绍`MpscArrayQueue`队列。



 ##### 6. 分配一个30B的ByteBuf

如果分配一个30B的ByteBuf，它会走上面加到PoolThreadPool中的缓存吗？

我不打算跟代码，让我们一起来脑补“分配一个30B的ByteBuf”的整个过程：

1. 30B规范化之后等于32B，属于Tiny类型；
2. 尝试使用PoolThreadCache分配内存，发现存放32B的缓存MemoryRegionCache中并没有相关缓存，所以，走缓存失败；
3. 尝试从PoolArena的tinySubpagePools[1]中找到符合的PoolSubpage，发现并没有，所以，只能对整个PoolArena加锁了；
4. 尝试从PoolArena的6个chunkList中分配内存，发现在qInit中存在可用的PoolChunk，使用它分配内存；
5. 在这个PoolChunk中找到第2049号节点可以使用，使用它分配内存（2048节点已经被前面的48B的请求占用了）；
6. 2049节点对应Page1，它首次接收请求，所以新建一个PoolSubpage，它的elemSize=32B，同时，把这个PoolSubpage与PoolArena的tinySubpagePools[1]这个head形成双向链表，另外，整个Page按32B分割成了`8192/32=256`个小块内存，需要`256/64=4`个long类型存储每个小块内存的状态；
7. 当前这个请求是Page1的第一个请求，所以，它在Page1中的偏移量是0，但是它在整个PoolChunk中的偏移量为8192，所以，分配完毕返回的handle=0x4000000000000000L | 0 | 2049；
8. 调用PooledByteBuf的init()方法初始化，它的memory与48B那个是同一个PoolChunk的memory，但是它的偏移量为8192，容量为30B，最大容量为32B；
9. 虽然分配的是30B的容量，且最大容量为32B，但是依然可以写入超过32B容量的数据，当写入超过32B时，将进行扩容，扩容的逻辑咱们就不脑补了。

通过这种脑补法，发现48B和32B关联的是同一个PoolChunk的memory，那么，它们并发地写会不会有线程安全的问题呢？其实，并不会有，因为它们是对memory这个数组不同的段进行操作，之间不存在线程安全的问题，这也是锁分离思想的体现（大锁化小锁，小锁化无锁）。



 ##### 7. 再次分配一个40B的ByteBuf

让我们再一起使用脑补法看看再次分配一个40B的ByteBuf会怎样：

1. 40B规范化后为48B，属于Tiny类型；
2. 尝试使用PoolThreadCache分配内存，查看其tinySubPageHeapCaches[2]，发现它的队列里面有个可以使用的entry，将其出队（poll），这个entry里面存储了属于哪个PoolChunk，及handle，而handle里面存储了哪个节点（memoryMapIdx），及这小块内存的索引（bitmapIdx）；
3. 通过这个entry初始化PooledByteBuf。

OK，到这里整个内存池部分就讲解完毕了。



 ### 后记

本节，我们基于堆内存把整个内存池学习了一遍，其实这一块可以学习的东西还有很多，比如：

1. Small类型是如何分配内存的？
2. Normal类型是如何分配内存的？
3. Huge类型是如何分配内存的？
4. 如果换成直接内存，这四种类型又是怎么处理的？

另外，我留了两个思考题，大家可以尝试解答一下，见文后。



 ### 思维导图

今天的思维导图，我希望你能根据这几个步骤，把Netty的内存池描述清楚。
![图片描述](https://img1.sycdn.imooc.com/5f2b61b30001dd9210771060.png)



 ### 思考题一

```java
public class ByteBufTest {
    public static void main(String[] args) throws InterruptedException {
        // 参数是preferDirect，即是否偏向于使用直接内存
        ByteBufAllocator allocator = new PooledByteBufAllocator(false);
        // 分配一个40B的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer(40);
        // 写入数据
        byteBuf.writeInt(4);
        // 读取数据
        System.out.println(byteBuf.readInt());
        // 回收内存
        new Thread(()->ReferenceCountUtil.release(byteBuf)).start();
        // 休息1秒，保证完全释放
        Thread.sleep(1000);
        // 再次分配一个40B的ByteBuf
        ByteBuf byteBuf2 = allocator.heapBuffer(40);
    }
}
```

如上代码，第二次分配40B内存的时候是否可以使用到缓存？



 ### 思考题二

```java
public class ByteBufTest {
    public static void main(String[] args) throws InterruptedException {
        // 参数是preferDirect，即是否偏向于使用直接内存
        ByteBufAllocator allocator = new PooledByteBufAllocator(false);
        // 分配一个40B的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer(40);
        // 写入数据
        byteBuf.writeInt(4);
        // 读取数据
        System.out.println(byteBuf.readInt());
        // 回收内存
        ReferenceCountUtil.release(byteBuf);
        // 休息1秒，保证完全释放
        Thread.sleep(1000);
        new Thread(() -> {
            // 再次分配一个40B的ByteBuf
            ByteBuf byteBuf2 = allocator.heapBuffer(40);
            // 其它处理
        }).start();
    }
}
```

如上代码，第二次分配40B内存的时候是否可以使用到缓存？





<div style="page-break-after:always;"></div>

 ## 22 Netty的对象池又是如何实现的


![img](https://img3.sycdn.imooc.com/5f05963b000186cd06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)人的差异在于业余时间。——爱因斯坦![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了 Netty 内存池的知识，它主要采用 jemalloc 内存分配器来实现，不过，在 Netty 中，还有另外一种池化手段 —— 对象池，相比于内存池，对象池要简单不少，你知道它的实现原理吗？

今天，我们就来学习 Netty 对象池的相关概念及源码阅读。

好了，开始今天的学习吧。



 ### 问题

关于 Netty 对象池，我想问你几个问题：

1. Netty 对象池与内存池的区别与联系？
2. Netty 内存池中是否使用到了对象池？
3. Netty 对象池中是否使用到了内存池？
4. Netty 对象池实现的基本逻辑？



 ### Netty 对象池详解



 #### 调试用例

其实，在上一节，我们就见过了 Netty 对象池，只 是当时我们跳过去了，所以，本节，我们就简单一点，直接使用上一节的调试用例，然后跟踪源码到上一节跳过的地方：

```java
public class ByteBufTest {
    public static void main(String[] args) {
        // 1. 创建池化的分配器
        ByteBufAllocator allocator = new PooledByteBufAllocator(false);
        // 2. 分配一个40B的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer(40);
        // 3. 写入数据
        byteBuf.writeInt(4);
        // 4. 读取数据
        System.out.println(byteBuf.readInt());
        // 5. 回收内存
        ReferenceCountUtil.release(byteBuf);
        // 6. 分配一个30B的ByteBuf
        ByteBuf byteBuf2 = allocator.heapBuffer(30);
        // 7. 再次分配一个40B的ByteBuf
        ByteBuf byteBuf3 = allocator.heapBuffer(40);
    }
}
```

通过上一节的学习，我们知道，当分配 30B 内存的 ByteBuf 的时候是不会使用到内存池的，那么，它会使用到对象池吗？



 #### 源码剖析



 ##### 创建 40B 的 ByteBuf 对象

我们把断点打在 `ByteBuf byteBuf = allocator.heapBuffer(40);` 这一行，跟踪进去，看看第一次分配 ByteBuf 的时候发生了什么：

```java
// ...
// PoolArena#allocate(PoolThreadCache, int, int)
PooledByteBuf<T> allocate(PoolThreadCache cache, int reqCapacity, int maxCapacity) {
    // key，创建一个ByteBuf
    PooledByteBuf<T> buf = newByteBuf(maxCapacity);
    // 通过内存池给它分配内存，上一节的内容，本节不展开
    allocate(cache, buf, reqCapacity);
    return buf;
}
```

本节，我们的重点是学习这个 buf 到底是如何创建出来的，所以，下面那行关于内存池的内容我们就不展开了，继续跟进：

```java
// PoolArena.HeapArena#newByteBuf
@Override
protected PooledByteBuf<byte[]> newByteBuf(int maxCapacity) {
    return HAS_UNSAFE ? PooledUnsafeHeapByteBuf.newUnsafeInstance(maxCapacity)
        : PooledHeapByteBuf.newInstance(maxCapacity);
}
// PooledUnsafeHeapByteBuf#newUnsafeInstance
static PooledUnsafeHeapByteBuf newUnsafeInstance(int maxCapacity) {
    // key，通过RECYCLER得到一个buf，所以秘密在这个RECYCLE中
    PooledUnsafeHeapByteBuf buf = RECYCLER.get();
    // 重新使用，重置属性
    buf.reuse(maxCapacity);
    return buf;
}
final void reuse(int maxCapacity) {
    // 设置最大容量
    maxCapacity(maxCapacity);
    // 重置引用计数
    resetRefCnt();
    // 重置readIndex和writeIndex为0
    setIndex0(0, 0);
    // 重置mark为0
    discardMarks();
}
```

这段代码的关键是通过一个叫作 `RECYCLER` 的东西获得了一个 buf，这玩意是个什么东西呢？或者它是不是东西呢？其实，它是定义在 PooledUnsafeHeapByteBuf 类中的一个常量：

```java
final class PooledUnsafeHeapByteBuf extends PooledHeapByteBuf {
    // 第一个核心类——ObjectPool
    private static final ObjectPool<PooledUnsafeHeapByteBuf> RECYCLER = ObjectPool.newPool(
            // 第二个核心类——ObjectCreator
            new ObjectCreator<PooledUnsafeHeapByteBuf>() {
        @Override
        public PooledUnsafeHeapByteBuf newObject(Handle<PooledUnsafeHeapByteBuf> handle) {
            // 实际创建buf的地方
            return new PooledUnsafeHeapByteBuf(handle, 0);
        }
    });
}
```

可以看到，RECYCLER 是 ObjectPool 的一个对象，它里面封装了一个 ObjectCreator 对象，用来创建对象，当然，这里创建的就是 PooledUnsafeHeapByteBuf 对象了，且它的容量为 0，同时还有一个 handle 属性，这个 handle 不是我们上一节说的那个 handle 哈，上一节的 handle 是一个 long 类型的，里面存储了节点编号及 bitmapIdx 等相关信息，那么，今天这个 handle 是个什么东西呢？不急，我们慢慢来分析。

我们先不纠结于这个类，接着上面的代码继续跟踪：

```java
private static final class RecyclerObjectPool<T> extends ObjectPool<T> {
    // 第三个核心类——Recycler
    private final Recycler<T> recycler;

    RecyclerObjectPool(final ObjectCreator<T> creator) {
        // Recycler对象，包装creator
        recycler = new Recycler<T>() {
            // 第四个核心类——Handle
            // 注意这个方法，下面会用到
            @Override
            protected T newObject(Handle<T> handle) {
                // 通过creator创建对象
                return creator.newObject(handle);
            }
        };
    }

    @Override
    public T get() {
        // 调用recycler的get()方法
        return recycler.get();
    }
}
```

可以看到，这个 get () 方法最后是调用了 Recycler 的 get () 方法，继续跟进：

```java
// Recycler#get
public final T get() {
    // 每个线程最多可缓存的容量大小，默认为4KB
    if (maxCapacityPerThread == 0) {
        return newObject((Handle<T>) NOOP_HANDLE);
    }
    // 第五个核心类——Stack
    // 从threadLocal中获取一个对象，这个对象是Stack的对象
    Stack<T> stack = threadLocal.get();
    // 从栈中弹出一个元素，这个元素是DefaultHandle，它实现了Handle接口
    DefaultHandle<T> handle = stack.pop();
    if (handle == null) {
        // handle为空则创建之
        handle = stack.newHandle();
        // 并创建它里面的对象
        // newObject()方法即上面Recycler实现中的方法
        handle.value = newObject(handle);
    }
    // 返回创建的对象
    return (T) handle.value;
}
```

OK，到这里整个逻辑都比较清晰了，Netty 对象池底层是通过 ThreadLocal + Stack（栈）实现的，把 Stack 存储在线程本地变量中，这个栈里面存储的是 Handle，Handle 里面关联了 PooledByteBuf，当我们获取 PooledByteBuf 时，先尝试从线程本地变量的栈中取出一个 Handle，如果没有缓存，则新建一个 Handle 并初始化它里面的 PooledByteBuf，即 value。

> 确切地来说，这个 ThreadLocal 是 FastThreadLocal，它在 Java 原生 ThreadLocal 之上做了一些改进，使其性能更优越，我们后面再单独分析这个类。

直接在 Stack 里面存储 PooledByteBuf 它不香吗？为什么要存储 Handle，再用 Handle 来关联 PooledByteBuf 呢？

其实，Stack 直接存储 PooledByteBuf 作为元素也是可以的，中间加一层 Handle，是因为 Handle 需要存储一些状态信息，比如，是否被回收等，如果把这些信息放到 PooledByteBuf 中，显然会对 PooledByteBuf 本身造成侵略，而且，如果对象池中放到不是 PooledByteBuf，而是换成另一个类，那个类也要加上诸如是否被回收等状态信息，显然也是不合适的，所以，抽象出来一层 Handle 专门用来存储这些状态信息，再用 Handle 去关联真正缓存的对象，这样设计扩展性更好，代码解耦更彻底。

如果上面这样一大段文字看着比较费劲，那我们就把上面标记的那些核心类连起来看看：
![图片描述](https://img1.sycdn.imooc.com/5f30adaa00010b9009790809.png)

这是一个非标准的类图，我把组合、聚合、关联、依赖等几种关系统一弱化成了关联关系，即图中标有数字的那种箭头，而且，我并没有把所有的关联关系全部画出来，看着这张图，我们梳理一下整个流程：

1. 创建 buf 的入口是 PooledUnsafeHeapByteBuf 的 newUnsafeInstance () 方法；
2. newUnsafeInstance () 方法中调用了 RECYCLER（ObjectPool 的对象）的 get () 方法，而 RECYCLER 实际上是 RecyclerObjectPool 的对象；
3. RecyclerObjectPool 的 get () 方法中调用了 recycler（Recycler 的对象）的 get () 方法，而 recycler 实际上是 Recycler 的匿名实现类的对象，这个匿名实现类中实现了 newObject () 方法，newObject () 方法在下面会用到；
4. Recycler 的 get () 方法是真正干活的地方，内部主要做了四件事：
   - 从 threadLocal 中获取 Stack 对象；
   - 从 Stack 中弹出 DefaultHandle 对象；
   - 如果没有弹出任何元素，则创建一个 DefaultHandle，并调用 Recycler 的 newObject () 方法创建实际要缓存的对象；
   - 返回 DefaultHandle 中实际缓存的对象，即它的 value 值；
5. 在匿名 Recycler 的 newObject () 内部，又调用了了 ObjectCreator 的 newObject () 方法；
6. ObjectCreator 的 newObject () 方法的实现实际上是在 PooledUnsafeHeapByteBuf 初始化 RECYCLER 时实现的；
7. ObjectCreator 的 newObject () 方法中调用了 PooledUnsafeHeapByteBuf 的构造方法初始化了一个容量为 0 的 buf，且绑定了 DefaultHandle。

OK，到此从对象池中拿 buf 的过程剖析完毕，也就是说，第一次创建 buf 的时候实际上最后还是使用 buf 自己的构造方法创建了一个 0 容量的 buf，跟上一节的内容结合在一起，后面就是给这个 buf 分配内存了，我们就跳过啦，搞不清楚的同学可以把这两节的内容串在一起调试一遍。



 ##### 回收 ByteBuf 对象

对象池的作用无疑是重复利用资源，所以，如果没有回收对象，就体现不出它的价值了，所以，让我们看看回收对象的时候这个对象是怎么加入到对象池中的。

OK，让我们在 `ReferenceCountUtil.release(byteBuf);` 打一个断点，并跟踪进去（跳过了内存池相关的代码）：

```java
// PooledByteBuf#deallocate
@Override
protected final void deallocate() {
    if (handle >= 0) {
        final long handle = this.handle;
        this.handle = -1;
        memory = null;
        chunk.arena.free(chunk, tmpNioBuf, handle, maxLength, cache);
        tmpNioBuf = null;
        chunk = null;
        // 关键之处
        recycle();
    }
}
// PooledByteBuf#recycle
private void recycle() {
    recyclerHandle.recycle(this);
}
// Recycler.DefaultHandle#recycle
@Override
public void recycle(Object object) {
    if (object != value) {
        throw new IllegalArgumentException("object does not belong to handle");
    }

    Stack<?> stack = this.stack;
    if (lastRecycledId != recycleId || stack == null) {
        throw new IllegalStateException("recycled already");
    }

    stack.push(this);
}
```

OK，这一块的逻辑比较简单，最后就是把 buf 中绑定的 handle 入到 Stack 中，因为 handle 里面同样保存了 buf，所以，下一次再创建 buf 的时候就可以重复利用这个 buf 了。



 ##### 创建 30B 的 ByteBuf 对象

相信通过上面的源码分析，到这里就很简单了，我们直接脑补一下流程：

1. 通过 PooledUnsafeHeapByteBuf 的 newUnsafeInstance () 方法入口一直调到 Recycler 的 get () 方法；
2. 从 ThreadLocal 中获取 Stack；
3. 从 Stack 中弹出 Handle，正好有一个刚放进去的 Handle；
4. 直接返回 Handle 中的 value，即 buf；
5. 重置 buf 的属性，为我们重新使用；
6. 调用内存池相关逻辑为其分配内存；

可以看到，对象池跟分配多少字节的数据完全没有关系，那是内存池的事儿，所以，这里创建 30B 的 ByteBuf 对象一样可以重复利用前面缓存下来的 ByteBuf 对象。

到这里，对象池的源码剖析基本就结束了，既然这个对象池这么好用，我们能不能使用呢？答案当然是可以啦。



 #### 对象池的使用

其实，使用方法也非常简单，就像你看到的 PooledUnsafeHeapByteBuf 中的用法一样，只需要简单的三步就可以很容易使用 Netty 的对象池了：

1. 需要使用的类要与 handle 绑定；
2. 这个类的对象回收的时候调用 handler 的 recycle () 方法；
3. 定义一个 ObjectPool 对象，用它来创建这个类的对象；

比如，在游戏中有这么一个类叫作 `Player`，也就是玩家，假设玩家这个类的对象的创建过程是非常耗费资源的，那么，我们完全就可以把下线的玩家缓存到对象池中，等下次有上线的玩家，我们直接从对象池中拿一个 “玩家”，并重置它的属性给这次新上线的玩家复用是完全可以的，下面我们就来简单实现这么个逻辑。



 ##### 定义玩家类

```java
public class Player {

    // 定义对象池
    private static final ObjectPool<Player> RECYCLER = ObjectPool.newPool(
            handle -> new Player(handle));

    // 玩家属性
    private Long id;
    private String name;
    // ...

    // 绑定handle
    private ObjectPool.Handle<Player> handle;

    // 构造方法私有化
    private Player(ObjectPool.Handle<Player> handle) {
        this.handle = handle;
    }

    // 创建实例
    public static Player newInstance(Long id, String name) {
        Player player = RECYCLER.get();
        player.id = id;
        player.name = name;
        return player;
    }

    // 玩家下线
    public void offline() {
        handle.recycle(this);
    }

    // 打印
    @Override
    public String toString() {
        return String.format("id=%d, name=%s, classId=%s", id, name, super.toString());
    }
}
```

这个 Player 类比较简单，我们来测试一下。



 ##### 测试玩家类

```java
public class PlayerTest {
    public static void main(String[] args) {
        // 创建player1
        Player player1 = Player.newInstance(1L, "alan");
        // 打印player1
        System.out.println(player1);
        // player1下线
        player1.offline();

        // 创建player2
        Player player2 = Player.newInstance(2L, "alex");
        // 打印player2
        System.out.println(player2);
        // 二者是否相等
        System.out.println(player1 == player2);

        // 假设player1又上线了呢
        player1 = Player.newInstance(1L, "alan");
        // 打印player1
        System.out.println(player1);
        // 二者是否相等
        System.out.println(player1 == player2);
    }
}
```

你猜这个结果会如何？我直接给出我的运行结果了：

```
id=1, name=alan, classId=com.imooc.netty.core.$21.Player@300ffa5d
id=2, name=alex, classId=com.imooc.netty.core.$21.Player@300ffa5d
true
id=1, name=alan, classId=com.imooc.netty.core.$21.Player@37f8bb67
false
```

是不是很简单？！^^



 ##### 其它

其实，Netty 中对象池可不只是用在池化 ByteBuf 这里，在很多地方都有用到，比如，内存池里面的 PoolThreadCache 中用来做缓存的 MemoryRegionCache 中的队列中的元素 Entry：

```java
// io.netty.buffer.PoolThreadCache.MemoryRegionCache.Entry
static final class Entry<T> {
    final Handle<Entry<?>> recyclerHandle;
    PoolChunk<T> chunk;
    ByteBuffer nioBuffer;
    long handle = -1;

    Entry(Handle<Entry<?>> recyclerHandle) {
        this.recyclerHandle = recyclerHandle;
    }

    void recycle() {
        chunk = null;
        nioBuffer = null;
        handle = -1;
        recyclerHandle.recycle(this);
    }
}

@SuppressWarnings("rawtypes")
private static Entry newEntry(PoolChunk<?> chunk, ByteBuffer nioBuffer, long handle) {
    Entry entry = RECYCLER.get();
    entry.chunk = chunk;
    entry.nioBuffer = nioBuffer;
    entry.handle = handle;
    return entry;
}

@SuppressWarnings("rawtypes")
private static final ObjectPool<Entry> RECYCLER = ObjectPool.newPool(new ObjectCreator<Entry>() {
    @SuppressWarnings("unchecked")
    @Override
    public Entry newObject(Handle<Entry> handle) {
        return new Entry(handle);
    }
});
```

另外，还有 `io.netty.channel.AbstractChannelHandlerContext.WriteTask`，等等，有兴趣的同学可以翻翻源码看看。



 ### 后记

今天，我们一起学习了 Netty 中的对象池，可以发现，对象池的实现相比于内存池的实现不要太简单，是吧？！

但是，它真的如此简单么？我留了两道思考题，你能解答出来吗？见文后。

在今天的内容中，我们提到了对象池底层使用到了一个叫作 `FastThreadLocal` 的类，它是比 Java 原生的 ThreadLocal 效率更高的实现，它有哪些神奇之处呢？我们下一节一起来剖析之，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f30adc30001f76511100507.png)



 ### 思考题一

```java
public class ByteBufTest {
    public static void main(String[] args) throws InterruptedException {
        // 参数是preferDirect，即是否偏向于使用直接内存
        ByteBufAllocator allocator = new PooledByteBufAllocator(false);
        // 分配一个40B的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer(40);
        // 写入数据
        byteBuf.writeInt(4);
        // 读取数据
        System.out.println(byteBuf.readInt());
        // 回收内存
        new Thread(()->ReferenceCountUtil.release(byteBuf)).start();
        // 休息1秒
        Thread.sleep(1000);
        // 再次分配一个40B的ByteBuf
        ByteBuf byteBuf2 = allocator.heapBuffer(30);
    }
}
```

如上代码，创建 30B 的 ByteBuf 时是否可以使用到对象池中的缓存？



 ### 思考题二

```java
public class ByteBufTest {
    public static void main(String[] args) throws InterruptedException {
        // 参数是preferDirect，即是否偏向于使用直接内存
        ByteBufAllocator allocator = new PooledByteBufAllocator(false);
        // 分配一个40B的ByteBuf
        ByteBuf byteBuf = allocator.heapBuffer(40);
        // 写入数据
        byteBuf.writeInt(4);
        // 读取数据
        System.out.println(byteBuf.readInt());
        // 回收内存
        ReferenceCountUtil.release(byteBuf);
        // 休息1秒，保证完全释放
        Thread.sleep(1000);
        new Thread(() -> {
            // 再次分配一个40B的ByteBuf
            ByteBuf byteBuf2 = allocator.heapBuffer(30);
            // 其它处理
        }).start();
    }
}
```

如上代码，创建 30B 的 ByteBuf 时是否可以使用到对象池中的缓存？







<div style="page-break-after:always;"></div>

 ## 23 Netty的FastThreadLocal到底快在哪里


![img](https://img1.sycdn.imooc.com/5f0596480001e04206400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才就是这样，终身努力，便成天才。——门捷列夫![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

前面几节，我们一起学习了 Netty 中的内存池和对象池相关的知识，不管是内存池还是对象池，它们底层都有使用一种叫作线程本地缓存的东西，我们知道，在 Java 中有 ThreadLocal 可以存储线程本地变量，但是，在 Netty 中，并没有使用 Java 原生的 ThreadLocal，而是创建了一个新的类 ——FastThreadLocal，从名字上就可以看出，它很快，那么，它究竟是不是真的正如其名，很 Fast 呢？它相比于 Java 原生的 ThreadLocal，除了快还有哪些特性呢？

今天，就让我们一起来学习 Netty 中鼎鼎大名的快男 ——FastThreadLocal。



 ### 问题

关于 FastThreadLocal 的学习，我想问你这么几个问题：

1. Java 原生的 ThreadLocal 是如何实现的？有什么缺点？
2. FastThreadLocal 是如何实现的？有什么优点和缺点？
3. FastThreadLocal 有哪些使用的姿势？
4. FastThreadLocal 一定比 ThreadLocal 快吗？
5. FastThreadLocal 除了快还有什么优势？



 ### ThreadLocal 简介

在正式介绍 FastThreadLocal 之前，让我们先从 Java 原生的 ThreadLocal 开始说起。

在 ThreadLocal 体系中，有三个特别重要的类：Thread、ThreadLocal、ThreadLocalMap，其中 ThreadLocalMap 是 ThreadLocal 的内部类。
![图片描述](https://img1.sycdn.imooc.com/5f31f7db0001d56b10320210.png)

Thread，线程类，就是我们创建线程的那个类，这里面有一个字段叫作 `threadLocals`，它的类型是 ThreadLocalMap。

ThreadLocal，线程本地类，用于存放线程本地变量，每一个 ThreadLocal 中存储的值在每一个线程中都有一个副本，这个副本是保存在 Thread 的 `threadLocals` 中的。

ThreadLocalMap，它是一种使用线性探测法实现的哈希表，可以理解成就是一个 HashMap，不过这个哈希表的 key 是 ThreadLocal，value 是 ThreadLocal 存储的值，这么来说可能比较难理解，我用个伪代码来表示一下：

```java
ThreadLocalMap<ThreadLocal, Object> map = new ThreadLocalMap<>();
ThreadLocal threadLocal = new ThreadLocal();
User user = new User();
map.put(threadLocal, user);
```

当然，实际使用肯定是不能这样用的，这里仅用于描述 ThreadLocalMap 的组成结构。

什么是线性探测法呢？

使用线性探测法的哈希表使用数组存储元素，每次添加元素的时候，如果 hash 到的位置已经有元素了，则向后移动一位检测是否有元素，如果还有元素，继续往后移直到一个没有元素的位置把当前要添加的元素放在那个位置。比如，对于一个容量为 8 的哈希表，我们依次放入 2、10、3、4、11 这么几个元素：
![图片描述](https://img1.sycdn.imooc.com/5f31f7ea00017ac910300215.png)

整个过程是这样的：

1. 2%8=2，所以放在下标为 2 的位置；
2. 10%8=2，所以放在下标为 2 的位置，但是下标 2 的位置有元素了，往后移一位，到下标为 3 的位置，没有元素，所以 10 放在了下标为 3 的位置；
3. 3%8=3，所以放在下标为 3 的位置，但是下标 3 的位置有元素了，往后移一位，到下标为 4 的位置，没有元素，所以 3 放在了下标为 4 的位置；
4. 4%8=4，所以放在下标为 4 的位置，但是下标 4 的位置有元素了，往后移一位，到下标为 5 的位置，没有元素，所以 4 放在了下标为 5 的位置；
5. 11%8=3，所以放在下标为 3 的位置，但是下标 3 的位置有元素了，往后移一位，到下标为 4 的位置，也有元素了，继续后移，到下标为 5 的位置，依然有元素，继续后移，到下标为 6 的位置，没有元素，所以 11 放在了下标为 6 的位置；

可以看到，使用线性探测法实现的哈希表非常容易出现哈希冲突，且解决冲突的过程时间复杂度非常高，最高可以达到 O (n) 的时间复杂度。

既然线性探测法性能这么差，为什么 ThreadLocal 还要使用线性探测法呢？我认为原因有两点：

1. ThreadLocal 是 JDK1.2 就加入的类，比较早，那时候性能还不是主要的关注点；
2. 线程本地变量并不会存在很多，比如，使用 Spring 的情况下，一个线程也就差不多 30 多个 ThreadLocal 变量，所以，对性能影响并不是特别明显；

> 关于哈希表的更多内容，可以参考这篇文章[《哈希表》](https://mp.weixin.qq.com/s/lS2w-RhK7FEgqG6xfc_L0w)。

另外，ThreadLocalMap 中的 Entry 是一个弱引用，它引用的对象就是它的 key 值，即 ThreadLocal 变量，所以，当这个 key 不具有强引用时，下一次垃圾回收时，这个弱引用本身会进入到引用队列中，等待被回收，关于弱引用的相关知识，可以参考《再谈 ByteBuffer》那一章的讲解。

那么，我们该如何使用 ThreadLocal 呢？

让我们来看看 ThreadLocal 的作者怎么说：

> ThreadLocal instances are typically *private static* fields in classes that wish to associate state with a thread (e.g., a user ID or Transaction ID).

作者告诉我们，我们应该把 ThreadLocal 作为类的静态私有变量来使用，让我们看一个例子：

```java
public class ThreadLocalTest {
    // threadLocal1
    private static ThreadLocal<String> STRING_THREAD_LOCAL = ThreadLocal.withInitial(() -> Thread.currentThread().getName());
    // threadLocal2
    private static ThreadLocal<Long> LONG_THREAD_LOCAL = ThreadLocal.withInitial(() -> Thread.currentThread().getId());
    // threadLocal3
    private static ThreadLocal<User> USER_THREAD_LOCAL = new ThreadLocal<>();

    public static void main(String[] args) {
        // thread1
        new Thread(() -> {
            User user = new User(1L, "test001");
            USER_THREAD_LOCAL.set(user);
            
            System.out.println("001：threadName: " + STRING_THREAD_LOCAL.get());
            System.out.println("001：threadId: " + LONG_THREAD_LOCAL.get());
            System.out.println("001：" + USER_THREAD_LOCAL.get());
        }, "thread-001").start();

        // thread2
        new Thread(() -> {
            User user = new User(2L, "test002");
            USER_THREAD_LOCAL.set(user);
            
            System.out.println("002：threadName: " + STRING_THREAD_LOCAL.get());
            System.out.println("002：threadId: " + LONG_THREAD_LOCAL.get());
            System.out.println("002：" + USER_THREAD_LOCAL.get());
        }, "thread-002").start();
    }

    static class User {
        Long id;
        String name;

        public User(Long id, String name) {
            this.id = id;
            this.name = name;
        }

        @Override
        public String toString() {
            return "id=" + id + ", name=" + name;
        }
    }

}
```

在这个示例中，我们创建了三个 ThreadLocal，他们的值分别为 String、Long、User，然后在 main () 方法中分别创建了两个 Thread，那么，在这两个 Thread 生命周期结束之前，这三个 ThreadLocal 分别是怎么存储的呢？
![图片描述](https://img1.sycdn.imooc.com/5f31f7ff00011c4110330529.png)

在调用 ThreadLocal 的 set ()/setInitialValue () 等方法时，会获取到 Thread 中的 `threadLocals` 这个 Map，然后调用它的 set () 方法（类似于 HashMap 的 put () 方法）把当前 ThreadLocal 本身作为 key，添加到这个 Map 中，最终的存储结构如上图所示。

可以看到，每一个 ThreadLocal 在每一个线程中都保存了一份，而且它们对应的 value 不同。

那么，在生产中，是否可以使用到 ThreadLocal 呢？

答案是当然的，比如一些具有状态的大对象的创建，我们完全可以使用 ThreadLocal 来保存，使得每一个线程都有一个不同的副本，各副本之间的状态不会产生影响，比如经典的就是 SimpleDateFormat、Random 等对象的使用。另外，在诸如 Spring 等 Web 应用场景中，我们也可以使用 ThreadLocal 来保存用户信息，比如，前置拦截器中获取一次用户信息把它保存在 ThreadLocal 中，这样在后面的调用过程中都可以直接拿来使用（无异步调用），在后置拦截器中再把这个用户信息清除即可。此外，还有分布式 ID 的追踪等场景。

既然，ThreadLocal 这么好用，那么，Netty 为什么还要自己造一个 FastThreadLocal 呢？

这就要归结于 ThreadLocal 本身的一些缺陷了，它有哪些缺陷呢？我归纳了一下，主要是以下两点：

- 存储数据的 ThreadLocalMap 使用的是线性探测法，效率低下；
- 使用结束未及时 remove () 掉 ThreadLocal 中的值，容易造成内存泄漏，这种情况只能依靠下一次调用 ThreadLocal 的时候来清除无用的数据，可以参考 ThreadLocal 的 set ()/get ()/remove () 中的相关代码；

那么，Netty 是如何改造 ThreadLocal 的呢？下面我们就来一起学习 FastThreadLocal 这个非常 Fast 的 ThreadLocal。



 ### FastThreadLocal 简介

在 Netty 中，为了配合 FastThreadLocal 的使用，还定义了另外两个非常重要的类 ——InternalThreadLocalMap 和 FastThreadLocalThread。

我们先来看看 InternalThreadLocalMap 类。

**InternalThreadLocalMap**，它是对原生 ThreadLocalMap 的优化，它不再使用线性探测法实现，而是显式地给每个 ThreadLocal 分配一个 index，使用这个 index 定位 ThreadLocal 在数组中的精确位置，可以让时间复杂度降低到 O (1)，这个性能提升是很明显的，比如，我们同样放入 2、10、3、4、11 这么几个元素：
![图片描述](https://img1.sycdn.imooc.com/5f31f81a00019f8a10270241.png)

整个过程非常简单，每个元素创建的时候都给它分配一个 index，对于 2、10、3、4、11，它们的索引分别是 1、2、3、4、5，这样，它们在放入数组的时候直接按这个 index 作为下标去数组对应的位置即可，也不会出现 hash 冲突，当索引大小达到了数组长度扩容就好了。

不过，这样使用也有个问题，就是当一个元素回收的时候，它的 index 并不会回收，也就是数组对应的位置不能重复利用，但是，这又不是一个问题，因为上面也说过了，ThreadLocal 一般作为类的静态属性来使用，正常情况下，是永远不会被回收的，所以，在 ThreadLocal 的使用场景下，这样的 Map 完全没有问题。

我们再来看看 FastThreadLocalThread 类。

**FastThreadLocalThread**，它是对 Thread 的包装，目的是为了配合 FastThreadLocal 的使用。它里面封装了一个 InternalThreadLocalMap 字段，这样的话，以前使用 Thread 的 `threadLocals` 存储元素就变成了使用这个 InternalThreadLocalMap 来存储元素，以达到上面说的利用 InternalThreadLocalMap 高性能。

另外，FastThreadLocalThread 中的构造方法还对任务进行了包装，使得线程任务运行结束的时候可以自动清理掉本线程相关的本地变量。

OK，讲了这么多，怎么能没有源码呢？



 ### FastThreadLocal 源码剖析



 #### 调试用例

调试用例非常简单，FastThreadLocal 的使用基本上与 ThreadLocal 完全一致，所以，我们只需要拿上面 ThreadLocal 的使用简单修改即可，这也是 Netty 比较厉害的地方：

```java
public class FastThreadLocalTest {

    private static FastThreadLocal<User> USER_THREAD_LOCAL = new FastThreadLocal<>();

    public static void main(String[] args) {
        // thread1
        new FastThreadLocalThread(() -> {
            User user = new User(1L, "test001");
            USER_THREAD_LOCAL.set(user);

            System.out.println("001：" + USER_THREAD_LOCAL.get());
        }, "thread-001").start();

        // thread2
        new FastThreadLocalThread(() -> {
            User user = new User(2L, "test002");
            USER_THREAD_LOCAL.set(user);

            System.out.println("002：" + USER_THREAD_LOCAL.get());
        }, "thread-002").start();
    }
}
```

为了简单一点，我们这个用例中只保留一个线程本地变量。然后，进入调试模式，在 USER_THREAD_LOCAL 声明的地方打个断点，并跟踪进去：

```java
// 创建一个FastThreadLocal
public FastThreadLocal() {
    // 给它一个index
    index = InternalThreadLocalMap.nextVariableIndex();
}
// InternalThreadLocalMap#nextVariableIndex
public static int nextVariableIndex() {
    // static final AtomicInteger nextIndex = new AtomicInteger();
    // 这个index是从一个AtomicInteger中获取的
    int index = nextIndex.getAndIncrement();
    if (index < 0) {
        nextIndex.decrementAndGet();
        throw new IllegalStateException("too many thread-local indexed variables");
    }
    return index;
}
```

可以看到，在 FastThreadLocal 创建的时候给它分配了一个 index，这个 index 是从一个 AtomicInteger 中获取的，理论上来说，index 的值应该从 0 开始，但是 FastThreadLocal 中有一个常量字段 `variablesToRemoveIndex`，它会在 FastThreadLocal 加载的时候就从 AtomicInteger 中拿走了第一个值 0，所以，实际上，FastThreadLocal 中的 index 是从 1 开始的。

此时，我们就创建好了一个 FastThreadLocal，让我们再把断点打在创建第一个 FastThreadLocalThread 的地方，并跟踪进去：

```java
public FastThreadLocalThread(Runnable target, String name) {
    // 1. 包装任务
    // 2. 调用父类Thread的构造方法
    super(FastThreadLocalRunnable.wrap(target), name);
    cleanupFastThreadLocals = true;
}
```

可以看到，在创建 FastThreadLocalThread 的时候对其任务进行了再包装，那么，这个包装后的任务长啥样呢？让我们看看 FastThreadLocalRunnable 这个类：

```java
final class FastThreadLocalRunnable implements Runnable {
    // 原始任务
    private final Runnable runnable;

    private FastThreadLocalRunnable(Runnable runnable) {
        this.runnable = ObjectUtil.checkNotNull(runnable, "runnable");
    }

    @Override
    public void run() {
        // 对原始任务的run()方法进行了包装
        try {
            runnable.run();
        } finally {
            // run()结束后清理掉FastThreadLocal
            FastThreadLocal.removeAll();
        }
    }

    // 包装方法
    static Runnable wrap(Runnable runnable) {
        return runnable instanceof FastThreadLocalRunnable ? runnable : new FastThreadLocalRunnable(runnable);
    }
}
```

这里的包装也非常简单，只是对原始任务的 run () 方法进行包装，使其运行完毕后，清理掉 FastThreadLocal，那么，这个清理到底清理了什么呢？我们后面再看。

OK，包装任务并调用父类 Thread 的构造方法之后，我们的 FastThreadLocalThread 就创建完毕了，此时，执行它的 start () 方法，将进入到线程的 run () 方法中，所以，我们现在在 Thread 的 run () 方法中打一个断点：

```java
// Thread#run
@Override
public void run() {
    // 不为空，是上面传进来的包装后的任务
    if (target != null) {
        target.run();
    }
}
// FastThreadLocalRunnable#run
@Override
public void run() {
    try {
        // 1. 运行原始任务
        runnable.run();
    } finally {
        // 2. 清理工作
        FastThreadLocal.removeAll();
    }
}
```

这里运行到了 FastThreadLocalRunnable 这个类里面，这里主要干两件事，一是运行原始任务，即我们传进去的 Runnable，二是清理工作。此时，继续跟踪将进入 main () 方法中我们传入的 Runnable 中，即下面这块代码：

```java
new FastThreadLocalThread(() -> {
    User user = new User(1L, "test001");
    USER_THREAD_LOCAL.set(user);

    System.out.println("001：" + USER_THREAD_LOCAL.get());
}, "thread-001").start();
```

在我们的 Runnable 中主要对 USER_THREAD_LOCAL 进行了 set () 和 /get () 方法的调用，我们先跟踪到 set () 方法中：

```java
// FastThreadLocal#set(V)
public final void set(V value) {
    // 如果value不等于UNSET，就把它set进去
    // 初始化时InternalThreadLocalMap中的数组的每个元素都会被初始化为UNSET
    if (value != InternalThreadLocalMap.UNSET) {
        // 1. 获取存储元素的InternalThreadLocalMap
        InternalThreadLocalMap threadLocalMap = InternalThreadLocalMap.get();
        // 2. 设置值
        setKnownNotUnset(threadLocalMap, value);
    } else {
        remove();
    }
}
```

在 set () 方法里面，首先，获取到当前线程存储本地变量的 Map，然后，往这个 Map 中设置值。我们先来看看是如何获取到当前线程对应的 Map 的：

```java
public static InternalThreadLocalMap get() {
    Thread thread = Thread.currentThread();
    // 判断当前线程是不是FastThreadLocalThread
    if (thread instanceof FastThreadLocalThread) {
        // 如果是，使用fastGet
        return fastGet((FastThreadLocalThread) thread);
    } else {
        // 如果否，使用slowGet
        return slowGet();
    }
}
// fast
private static InternalThreadLocalMap fastGet(FastThreadLocalThread thread) {
    // 这个Map是存储在FastThreadLocalThread中的，变量名为threadLocalMap
    InternalThreadLocalMap threadLocalMap = thread.threadLocalMap();
    if (threadLocalMap == null) {
        // 初始化Map
        thread.setThreadLocalMap(threadLocalMap = new InternalThreadLocalMap());
    }
    return threadLocalMap;
}
// slow
private static InternalThreadLocalMap slowGet() {
    // UnpaddedInternalThreadLocalMap是InternalThreadLocalMap的父类
    // 里面存储了一个Java原生的ThreadLocal，它的值是InternalThreadLocalMap
    // 这里是把这个Map取出来
    // 也就是说，如果当前线程对象不是FastThreadLocalThread
    // 就使用Java原生的ThreadLocal来存储一个InternalThreadLocalMap
    // 跟Netty相关的本地变量还是存储在InternalThreadLocalMap中
    ThreadLocal<InternalThreadLocalMap> slowThreadLocalMap = UnpaddedInternalThreadLocalMap.slowThreadLocalMap;
    InternalThreadLocalMap ret = slowThreadLocalMap.get();
    if (ret == null) {
        // 初始化Map
        ret = new InternalThreadLocalMap();
        slowThreadLocalMap.set(ret);
    }
    return ret;
}
```

获取存储本地线程变量的 Map 分为两种情况：

1. 如果当前线程是 FastThreadLocalThread，则直接取 FastThreadLocalThread 的 threadLocalMap 属性即可；
2. 如果当前线程不是 FastThreadLocalThread，则在 UnpaddedInternalThreadLocalMap 中保存一个 ThreadLocal，在这个 ThreadLocal 里面保存了一个线程本地变量 InternalThreadLocalMap，再把 Netty 相关的线程本地变量放到这个 Map 中，这里的逻辑有点绕，请仔细体会。

OK，此时，我们拿到了这个 Map，再看看是怎么把值设置进去的呢？

```java
// FastThreadLocal#setKnownNotUnset
private void setKnownNotUnset(InternalThreadLocalMap threadLocalMap, V value) {
    // 取当前FastThreadLocal的索引index
    if (threadLocalMap.setIndexedVariable(index, value)) {
        // key，将当前FastThreadLocal添加到待清理的Set中
        addToVariablesToRemove(threadLocalMap, this);
    }
}
// InternalThreadLocalMap#setIndexedVariable
public boolean setIndexedVariable(int index, Object value) {
    // 存储元素的数组
    Object[] lookup = indexedVariables;
    // 容量还够
    if (index < lookup.length) {
        // 直接找到数组的位置把值设置进去，时间复杂度为O(1)
        Object oldValue = lookup[index];
        lookup[index] = value;
        return oldValue == UNSET;
    } else {
        // 容量不够，先扩容再设置值
        expandIndexedVariableTableAndSet(index, value);
        return true;
    }
}
private void expandIndexedVariableTableAndSet(int index, Object value) {
    // 旧数组
    Object[] oldArray = indexedVariables;
    // 旧容量
    final int oldCapacity = oldArray.length;
    
    // 找到大于index的最小的2次方
    // 比如，index=3，则为4
    // index=16，则为32
    // 因为数组下标是从0开始的，16个元素的数组最大的下标为15，所以16需要32个元素的数组
    // 如何实现取大于等于自己的最小2次方呢？只需要把这里改成 index-1 即可
    // 有兴趣的同学可以看看HashMap的tableSizeFor()方法
    int newCapacity = index;
    newCapacity |= newCapacity >>>  1;
    newCapacity |= newCapacity >>>  2;
    newCapacity |= newCapacity >>>  4;
    newCapacity |= newCapacity >>>  8;
    newCapacity |= newCapacity >>> 16;
    newCapacity ++;

    // 创建新数组，并把旧数组的元素全部拷贝过来
    Object[] newArray = Arrays.copyOf(oldArray, newCapacity);
    // 把新数组不包含旧数组的后面部分都初始化为UNSET
    Arrays.fill(newArray, oldCapacity, newArray.length, UNSET);
    // 设置当前的值
    newArray[index] = value;
    // 把新数组赋值给InternalThreadLocalMap存储元素的数组
    indexedVariables = newArray;
}
```

设置值这里也分成两种情况：

1. 容量足够，直接把数组对应下标位置的值设置成新值即可，时间复杂度为 O (1)；
2. 容量不够，先扩容，再设置新值；

扩容这里有个疑问：为什么使用 index 作为基准来扩容，而不是直接扩容为旧数组容量的 2 倍呢？

我举个例子你就明白了，在 Netty 中，默认这个数组的容量是 32，假设我们有 100 个 FastThreadLocal 变量，且它们都没有 set () 过任何值，此时，这个数组大小依然是 32，现在如果要设置第 100 个 FastThreadLocal 的值呢？根据前面的逻辑，我们知道，它的 index 为 100，那么，此时，如果按旧数组的容量扩容为 2 倍，依然无法承载 index 为 100 的这个元素，所以，需要按 index 作为基准来进行扩容。

到这里，元素就已经添加到 Map 中了。在上面，我们看到在添加成功之后，还有一步操作是把当前 ThreadLocal 添加到待清理的 Set 中，这里是怎么实现的呢？让我们跟踪进去看看：

```java
private static void addToVariablesToRemove(InternalThreadLocalMap threadLocalMap, FastThreadLocal<?> variable) {
    // variablesToRemoveIndex是FastThreadLocal中的常量，它的值为0
    // 它对应的值同样存储在InternalThreadLocalMap中，是下标为0的元素
    // 这里也就解释了为什么FastThreadLocal的index是从0开始的了，因为被variablesToRemoveIndex占用了
    Object v = threadLocalMap.indexedVariable(variablesToRemoveIndex);
    // 0号元素是一个Set
    Set<FastThreadLocal<?>> variablesToRemove;
    if (v == InternalThreadLocalMap.UNSET || v == null) {
        // 初始化这个Set
        variablesToRemove = Collections.newSetFromMap(new IdentityHashMap<FastThreadLocal<?>, Boolean>());
        // 设置到0号元素中
        threadLocalMap.setIndexedVariable(variablesToRemoveIndex, variablesToRemove);
    } else {
        variablesToRemove = (Set<FastThreadLocal<?>>) v;
    }

    // 把当前FastThreadLocal添加到这个Set中
    variablesToRemove.add(variable);
}
```

这里把当前 FastThreadLocal 添加到了 InternalThreadLocalMap 中数组的 0 号元素对应的 Set 中了，添加到这里干什么呢？

让我们的代码继续前进，这里 set 完元素之后，在我们的 Runnable 中，下一步就是 get () 方法的调用了，里面的代码比较简单，就交给你自己了。

在 get () 方法获取到值且打印完成之后，我们的 Runnable 任务就完成了，此时，会再次回到 FastThreadLocalRunnable 的 run () 方法中，也就是下面这个方法：

```java
@Override
public void run() {
    try {
        // 1. 运行原始任务
        runnable.run();
    } finally {
        // 2. 清理工作
        FastThreadLocal.removeAll();
    }
}
```

在我们的 Runnable 任务运行完毕后，相当于当前线程的生命周期已经趋近于结束，所以，这里有个 finally，里面会执行清理工作，那么，都清理了什么东西呢？跟踪进去：

```java
public static void removeAll() {
    // 获取Map，getIfSet()方法跟上面的get()方法类似，只是内部不会再做初始化的操作
    InternalThreadLocalMap threadLocalMap = InternalThreadLocalMap.getIfSet();
    if (threadLocalMap == null) {
        // 如果为空，说明还未初始化，线程任务没有操作本地变量，直接返回就好了
        return;
    }

    try {
        // 从0呈元素取出待清理的FastThreadLocal
        Object v = threadLocalMap.indexedVariable(variablesToRemoveIndex);
        // 已初始化过
        if (v != null && v != InternalThreadLocalMap.UNSET) {
            // 转换为Set
            @SuppressWarnings("unchecked")
            Set<FastThreadLocal<?>> variablesToRemove = (Set<FastThreadLocal<?>>) v;
            // 转换为数组
            FastThreadLocal<?>[] variablesToRemoveArray =
                variablesToRemove.toArray(new FastThreadLocal[0]);
            // 遍历数组
            for (FastThreadLocal<?> tlv: variablesToRemoveArray) {
                // 1. 调用FastThreadLocal的remove()方法
                tlv.remove(threadLocalMap);
            }
        }
    } finally {
        // 2. 调用InternalThreadLocalMap的remove()方法
        InternalThreadLocalMap.remove();
    }
}
```

这里的逻辑比较简单，会把所有存储在待清理 Set 中的所有 FastThreadLocal 全部清除，即调用它们的 remove () 方法，同时，在最后会统一调用 InternalThreadLocalMap 的 remove () 方法，这两个 remove () 方法有什么区别呢？

```java
// 1. FastThreadLocal#remove
public final void remove(InternalThreadLocalMap threadLocalMap) {
    if (threadLocalMap == null) {
        return;
    }
    // 从Map中移除，这里是重置为UNSET元素
    Object v = threadLocalMap.removeIndexedVariable(index);
    // 从待清理的Set中移除
    removeFromVariablesToRemove(threadLocalMap, this);

    if (v != InternalThreadLocalMap.UNSET) {
        try {
            // 执行钩子方法
            onRemoval((V) v);
        } catch (Exception e) {
            PlatformDependent.throwException(e);
        }
    }
}
// 2. InternalThreadLocalMap#remove
public static void remove() {
    Thread thread = Thread.currentThread();
    if (thread instanceof FastThreadLocalThread) {
        // 移除Map本身
        ((FastThreadLocalThread) thread).setThreadLocalMap(null);
    } else {
        // 从ThreadLocal中移除Map本身
        slowThreadLocalMap.remove();
    }
}
```

可以看到，第一个 remove () 方法是把当前 FastThreadLocal 从 threadLocalMap 和待清理 Set 中移除，并执行钩子方法 onRemoval ()；第二个 remove () 方法是把 threadLocalMap 本身移除，当然，这里根据 Thread 的类型判断是从 FastThreadLocalThread 中移除还是从 ThreadLocal 中移除。

在上面，我们提到了一个钩子方法 onRemoval ()，它是干什么的呢？它实际上是一个空方法，这是 Netty 为我们预留的一个方法，我们可以继承自 FastThreadLocal 并实现 onRemoval () 方法，在移除 FastThreadLocal 的时候做一些我们自己的逻辑，比如清理我们自定义的资源等。其实，在 JDK 中，也有很多这种钩子方法，比如线程池 ThreadPoolExecutor.runWorker () 方法的逻辑，HashMap.putVal () 方法的逻辑（LinkedHashMap 就是使用这些钩子方法实现的），等等。



 #### 其它

其实，到这里，FastThreadLocal 的源码剖析过程基本结束了，但是，细心的同学可能会发现，InternalThreadLocalMap 还有个父类叫作 UnpaddedInternalThreadLocalMap，从名字可以看出多了一个 Unpadded，这个单词是什么意思呢？

Unpadded，顾名思义，它是 Padded 的反义词，Padded 表示的是缓存行补齐，用于消除伪共享带来的性能问题，它的补齐是通过声明下面一堆 long 类型变量来实现的。

```java
public final class InternalThreadLocalMap extends UnpaddedInternalThreadLocalMap {  
    public long rp1, rp2, rp3, rp4, rp5, rp6, rp7, rp8, rp9;
}
```

但是，在 InternalThreadLocalMap 中，并没有明确的证据表明这些变量能消除伪共享。经过查询相关的 issue 发现，在早期，添加这些变量确实会补齐缓存行，但是，后面 InternalThreadLocalMap 和 UnpaddedInternalThreadLocalMap 这两个类分别添加了 cleanerFlags 和 arrayList 这两个变量，而这里的 long 类型并没有对应的修改，导致现在是超出缓存行的状态，当然，这不是主要问题，主要问题是，添加这些变量是为了防止哪个变量伪共享的，我们也不得而知。

为了更好地验证这些变量是否真的能够消除伪共享，我做了测试，测试结果是在我的机器上添加这些变量并没有明显的性能提升，同学们也可以在自己的机器上测试下，具体的测试方法见文后。

> 关于伪共享的问题，我们这里就不展开了，有兴趣的同学可以看看这篇文章《[伪共享](https://mp.weixin.qq.com/s/rd13SOSxhLA6TT13N9ni8Q)》。



 ### 开篇回顾

在开篇，我们提了几个问题，这里根据源码的剖析结果再回顾一下：

1. FastThreadLocal 有哪些使用的姿势？

   FastThreadLocal 正常来说是跟 FastThreadLocalThread 联合使用的，但是，Netty 为了兼容性，也可以跟普通的 Thread 一起使用，只是会使用一种 slow 的方式来运行，这个 slow () 主要体现在 InternalThreadLocalMap 的存储上，使用 FastThreadLocalThread 时，它是存储在 FastThreadLocalThread 中的，使用普通的 Thread 时，它是存储在 Java 原生的 ThreadLocal 中的。

2. FastThreadLocal 一定比 ThreadLocal 快吗？

   不一定，当 FastThreadLocal 与普通 Thread 一起使用的时候，可能会比直接使用 ThreadLocal 还慢，这得根据 ThreadLocal 值的多少和 InternalThreadLocalMap 中值的多少来判断，比如，ThreadLocal 只存储了 InternalThreadLocalMap 一个值而 InternalThreadLocalMap 中存储了 100 个值 和 ThreadLocal 存储了 100 个值而 InternalThreadLocalMap 中只存储了一个值，这两种场景的结果肯定不一样。

3. FastThreadLocal 除了快还有什么优势？

   FastThreadLocal 除了快还能帮助我们自动清理相关资源，这是通过包装 Runnable 来实现的。

其它问题，诸如 ThreadLocal、FastThreadLocal 的实现以及优缺点等，我们这里就不一一解答了。



 ### 后记

本节，我们一起学习了 Netty 中的一个快类 ——FastThreadLocal，从使用上来说，它与使用 Java 原生的 ThreadLocal 并无明显区别，从实现上来说，它也完全兼容与普通 Thread 的联合使用。这也正是 Netty 的魅力所在。

另外，细心的同学会发现，它的相关代码完全遵循面向对象的思想，领域划分非常明确，比如，上文提到的两个 remove () 方法。

下一节，我们将学习内存池中使用到的另一个非常精彩的类 ——MpscArrayQueue—— 多生产者单消费者队列，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f31f8430001193121601268.png)



 ### 关于 InternalThreadLocalMap 的测试



 #### 测试用例

```java
public class InternalThreadLocalMapPaddingTest {

    /**
     * 单线程运行20次
     */
    @Test
    public void testPadding() {
        List<FastThreadLocal<Boolean>> list = new ArrayList<FastThreadLocal<Boolean>>();
        for (int i = 0; i < 1000000; i++) {
            list.add(new FastThreadLocal<Boolean>());
        }

        Boolean value = Boolean.TRUE;
        for (int j = 0; j < 20; j++) {
            long start = System.currentTimeMillis();
            for (int i = 0; i < 1000000; i++) {
                FastThreadLocal<Boolean> fastThreadLocal = list.get(i);
                fastThreadLocal.set(value=!value);
            }
            for (int i = 0; i < 1000000; i++) {
                FastThreadLocal<Boolean> fastThreadLocal = list.get(i);
                fastThreadLocal.get();
            }
            FastThreadLocal.removeAll();
            long end = System.currentTimeMillis();
            System.out.println(end - start);
        }

    }

    /**
     * 多线程运行20个线程
     */
    @Test
    public void testPaddingMultiThread() throws InterruptedException {
        final List<FastThreadLocal<Boolean>> list = new ArrayList<FastThreadLocal<Boolean>>();
        for (int i = 0; i < 100000; i++) {
            list.add(new FastThreadLocal<Boolean>());
        }

        final CountDownLatch countDownLatch = new CountDownLatch(20);
        for (int k = 0; k < 20; k++) {
            new FastThreadLocalThread(new Runnable() {
                @Override
                public void run() {
                    long start = System.currentTimeMillis();
                    Boolean value = Boolean.TRUE;
                    for (int i = 0; i < 100000; i++) {
                        FastThreadLocal<Boolean> fastThreadLocal = list.get(i);
                        fastThreadLocal.set(value=!value);
                    }
                    for (int i = 0; i < 100000; i++) {
                        FastThreadLocal<Boolean> fastThreadLocal = list.get(i);
                        fastThreadLocal.get();
                    }
                    FastThreadLocal.removeAll();
                    long end = System.currentTimeMillis();
                    System.out.println(end - start);

                    countDownLatch.countDown();
                }
            }).start();
        }
        countDownLatch.await();
        System.out.println("finished");
    }

}
```



 #### 测试方法

下载 netty 源码，把这个类放到 netty-common 工程的 test 下面，通过修改 InternalThreadLocalMap 源码，即把 `public long rp1, rp2, rp3, rp4, rp5, rp6, rp7, rp8, rp9;` 注释掉，对比注释前后的运行时间，记住多运行几次观察结果。

另外，在 64 位机器上，还有个指针压缩的概念，可以通过参数 `-XX:+UseCompressedOops` 和 `-XX:-UseCompressedOops` 来启用和禁用指针压缩，然后再结合上面的注释前后进行对比，观察结果。



 #### 测试结论

在我的机器上，测试发现，注释前后与是否启用指针压缩，都没有带来明显的性能提升，试想，测试用例中使用了 1000000 和 100000 个 FastThreadLocal 都没有明显的提升，那么，实际生产中最多也就几十几百个 FastThreadLocal，更是可以忽略不计了。

当然，以上测试结论仅限于我的机器，linux 和其它电脑并没有测试过，所以，这个结论并不严谨，仅作参考。







<div style="page-break-after:always;"></div>

 ## 24 Netty的队列有何不一样


![img](https://img3.sycdn.imooc.com/5f0596550001361906400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)人的差异在于业余时间。——爱因斯坦![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了 Netty 中的快男 ——FastThreadLocal，通过源码剖析，我们知道，如果使用不当，FastThreadLocal 也可能会变成慢男，不过，这都不是事儿，因为我们只要记住跟着 FastThreadLocalThread 一起使用就可以了，这个原则很简单。

其实呢，追踪一下常用的 Spring 等框架，会发现正常运转的情况下，一个线程最多也就三四十个 ThreadLocal 变量，那么，Netty 为何还要大费周章搞一个 FastThreadLocal 呢？这是由于 Netty 的使用场景导致的，不管是对象池还是内存池，亦或者是前面讲到的请求处理的过程，都大量使用了线程本地变量，且操作频繁，而 Java 原生的 ThreadLocal 使用的是线性探测法实现的哈希表，使得哈希冲突的概率太大且解决冲突的方式也不友好，且解决冲突之后更容易引起哈希冲突，所以，Netty 必须定义一个全新的 ThreadLocal 用来存储本地变量，简单点说，就是 Java 原生的 ThreadLocal 太慢了，无法应对 Netty 这种多缓存高频率的场景。

上面我们提到了 “场景” 两个字，其实，在 Netty 中，很多地方都针对特定的场景使用了特定的技术，比如，我们今天要说的一揽子队列 ——MpscArrayQueue、MpscChunkedArrayQueue、MpscUnboundedArrayQueue、MpscAtomicArrayQueue、MpscGrowableAtomicArrayQueue、MpscUnboundedAtomicArrayQueue 等。

可以发现，这些队列都有统一的前缀 `Mpsc-`，它是什么意思呢？这些队列又是使用在什么样的场景呢？相比于 Java 原生的队列，这些队列又有哪些好处呢？它们又是怎么实现的呢？

让我们带着这些问题进入今天的学习吧。



 ### Java 原生队列回顾

首先，我们来回顾下 Java 原生的队列，也就是下面这张图，它覆盖了 Java 中所有的原生队列：

![图片描述](https://img1.sycdn.imooc.com/5f31f8a3000134ad20210650.png)
对于这些 Java 原生的队列，我把它们分成这么几大类：

1. 非并发安全的队列
   - LinkedList，没错，你没看错，LInkedList 确实实现了 Queue 接口，可以把它当作一个队列来使用；
   - PriorityQueue，优先级队列，使用 “堆” 这种数据结构实现的队列，主要用于堆排序、中位数、99% 位数等场景；
2. 阻塞队列
   - ArrayBlockingQueue，最简单的阻塞队列，使用数组实现，有界，使用一个 ReentrantLock 及两个 Condition 控制并发安全，效率低下；
   - LinkedBlockingQueue，使用链表实现，有界或无界，使用两个 ReentrantLock 分别控制入队和出队，效率相对 ArrayBlockingQueue 要高一些；
   - SynchronizedQueue，俗称无缓冲队列，里面不存储任何元素，所有入队的元素都移交给另一个线程来处理，如果放入元素时没有线程来消费，那么，调用者线程会阻塞；同样地，如果取元素时没有生产者放入元素，那么消费线程也会阻塞；
   - PriorityBlockingQueue，优先级队列的阻塞模式，可在多线程环境中用于堆排序、中位数、99% 位数等场景；
   - LinkedTransferQueue，这是个强大的阻塞队列，它使用了一种叫作 “双重队列” 的数据结构，而且它相当于是 LinkedBlockingQueue、SynchronousQueue（公平模式）、ConcurrentLinkedQueue 三者的集合体，且比它们更高效；
   - DelayQueue，延时队列，它在优先级队列的基础上加入了 “延时” 的概念，出队时，如果堆顶的元素还没有到期，是不会出队的，主要运用在定时任务的场景中，比如，Java 的定时任务线程池 ScheduledThreadPoolExecutor，不过它是自己又实现了一遍延时队列，叫作 DelayedWorkQueue，而没有使用现成的 DelayQueue。
3. 并发安全的队列
   - ConcurrentLinkedQueue，它是并发安全的队列却不是阻塞队列，内部使用 自旋 + CAS 实现，是一种无锁队列，但是它无法使用在线程池中。

> 阻塞队列一定是并发安全的队列，关于以上所有队列的源码分析，可以参考文末链接解锁。

大部分情况下，使用 Java 原生的队列就能够达到我们的要求了，但是，对于一些特殊的场景，使用 Java 原生的队列性能就略显低下，所以，又衍生了一些第三方的框架专门实现特定的队列，来提高特定场景下的性能问题。

这些第三方框架中比较著名的有两个：Disruptor 和 jctools。

Disruptor，基于环形数组和 LMAX 架构实现，性能杠杠滴。

jctools，它把队列分成四种使用场景：

- SPSC，单生产者单消费者
- MPSC，多生产者单消费者
- SPMC，单生产者多消费者
- MPMC，多生产者多消费者

针对这四种场景 jctools 又实现了各种口味不同的队列，比如，我们今天的主角 ——MPSC 队列，没错，Netty 中使用的就是 jctools 中的 MPSC 队列，而且 Netty 只使用了 MPSC 这一种队列，更过分地，在 Netty 打包的时候使用了一个叫作 "shade" 的 maven 插件，直接把使用到的 jctools 中代码打包到了 Netty 的 `io.netty.util.internal.shaded.org.jctools.queues` 包下面，而没有使用到的其它的代码并没有打包过来，所以，在 `io.netty.util.internal.shaded.org.jctools.queues` 包下面只能看到跟 MPSC 队列相关的代码。

> shade 插件的全称为 maven-shade-plugin，参数 minimizeJar 用于控制只打包用到的类文件，详情见 netty-common 工程的 pom.xml 文件的插件部分。

今天，我们就从这些 MPSC 队列中挑一个来讲解，看看它的实现原理以及源码，挑来挑去挑谁呢，就 MpscArrayQueue 吧，因为它相对来说比较简单，看懂了它，其它的都不在话下，好了，开始喽 ^^



 ### MpscArrayQueue

按照我们以往的套路，对于这样的单个类，最适合使用从宏观到微观的分析方法，所以，我们先来看看 MpscArrayQueue 的继承体系。



 #### 继承体系

![图片描述](https://img1.sycdn.imooc.com/5f31f8f80001caf109871387.png)

纳尼！What！什么！点解咁复杂！没错，就是这么复杂，让我们把这些类分个类：

- -Pad 结尾的类，它们里面全都是一堆的 long 型变量，是用来避免伪共享的；
- -Field 结尾的类，它们里面存储着主要的字段，这些字段通过 - Pad 结尾的类通过 long 型变量隔开，以达到避免伪共享的目的；
- ConcurrentCircularArrayQueue，数据存储的地方，从名字可以看出，它也是通过环形数组实现的；
- MpscArrayQueue，对外暴露的可使用的类，里面不包含任何字段；
- 其它，最上层的就是一些接口了，可以看到，最终，MpscArrayQueue 是实现了 Java 原生的 Queue 接口的；

既然，是通过继承这种手段来避免伪共享的，那么，我们把这些字段压缩到一个类中看看长什么样子呢？

```java
public class FakeMpscArrayQueue<E> {
    long p01, p02, p03, p04, p05, p06, p07;
    long p10, p11, p12, p13, p14, p15, p16, p17;
    // 掩码，用来计算数组下标，加1就成了容量
    protected final long mask;
    // 存储数据的环形数组
    protected final E[] buffer;
    long p00, p01, p02, p03, p04, p05, p06, p07;
    long p10, p11, p12, p13, p14, p15, p16;
    // 生产者索引，有volatile
    private volatile long producerIndex;
    long p01, p02, p03, p04, p05, p06, p07;
    long p10, p11, p12, p13, p14, p15, p16, p17;
    // 生产者索引的最大值，有volatile
    private volatile long producerLimit;
    long p00, p01, p02, p03, p04, p05, p06, p07;
    long p10, p11, p12, p13, p14, p15, p16;
    // 消费者索引，无volatile
    protected long consumerIndex;
    long p01, p02, p03, p04, p05, p06, p07;
    long p10, p11, p12, p13, p14, p15, p16, p17;
}
```

既然，这里又提到了伪共享，那我们就简单介绍下伪共享到底是何方神圣。



 #### 题外话 —— 伪共享

在现在的 CPU 架构下，一般地，一台计算机都有多个 CPU 核心，叫作多核 CPU，这些 CPU 都要从一块叫作内存的地方读取数据，经过加工处理，再写回到内存中，如果每次读写数据都跟内存进行交互，太慢了，你可以想像成内存跟硬盘的关系，所以，为了加快 CPU 的处理速度，人们就给 CPU 安上了缓存，一般地，现代处理器都具有三级缓存，这三缓存也有个关系，越接近 CPU 的缓存越快越贵容量越小，越远离 CPU 的缓存越慢越便宜容量越大。

比如，对于一台 4 核 CPU 的计算机，它的缓存布局可能是这样的：
![图片描述](https://img1.sycdn.imooc.com/5f31fa48000118cc10320442.png)

这样，在处理数据的时候，CPU 就加载内存中的一小块数据到 CPU 缓存中，处理完毕并不用立马写回内存，等下次再读取或修改同一片内存区域的数据时，直接走缓存就好了，这样就极大地提高了数据处理的速度。刚才有提到每次加载一小块数据，那么，这个 “一小块” 是多大呢？通常地，现代 CPU 架构为 64 个字节。
![图片描述](https://img1.sycdn.imooc.com/5f3346430001831a10290157.png)

似乎很完美，试想这样一个问题，在内存中有两个相临的变量 x 和 y，一个线程一直在对 x 进行 ++ 操作，一个线程一直在对 y 进行 ++ 操作，会出现怎样地后果呢？
![图片描述](https://img1.sycdn.imooc.com/5f33466500018d6910310271.png)

假设两个变量初始值为 0，各自增 100 次，因为是两个不同的线程处理，所以这两个线程可能处于不同的 CPU 核中，根据上面的理论，CPU 每次加载 64 字节的数据到缓存中，所以，x 和 y 始终一起被加载到不同的缓存中，那么，各自修改完了如何写回主内存呢？发现没法写回了是不是？因为写回也是整个缓存行一起写回的，不管先写回哪个，都会被后写回的覆盖。

为了解决这种问题，有两种策略：

1. 给这个缓存行对应的内存块加锁，每次读写数据的时候都从主内存重新读取，写完之后立马写回主内存，多个线程处理同一块内存区域数据的时候排队进行，这样数据肯定就准确了；
2. 把 x 和 y 分隔开，不要让它们相临，让它们始终不会同时被加载到同一个缓存行中，只需要在它们之间补足 64 字节，它们自然就被隔开了，永远不会加载到同一个缓存行中；

两种方案都是可行的。

对于第一种方案，相当于缓存行永远失效，形同虚设了，这种锁又有另外一个名字 —— 内存屏障（Memory Barrier）或者内存栅栏 （Memory Fence），在现代 CPU 架构下，内存屏障主要分为读屏障（Load Memory Barrier）和写屏障（Store Memory Barrier）：

- 读屏障，每次都从主内存读取最新的数据；
- 写屏障，将缓存写入到主内存；

内存屏障还有个重要的功能，防止重排序，即不会把内存屏障前后的指令进行重排序。

使用内存屏障这种技术，又引来了新的问题，每次对 x 的操作，同时对 y 产生了影响，反之亦然，相当于 x 和 y 变成了一种共生的状态，但是实际上他们却没有任何关系，这种不同线程对同一块内存区域（缓存行）的不同变量的操作产生了互相影响的现象，就叫作**伪共享**（False Sharing）。为了解决伪共享带来的问题，就引出了第二种方案。

对于第二种方案，这样的玩法叫作加 Padding，在两个变量之间加一系列无用的变量，使得两个变量永远不会被加载到同一个缓存行，但是，它也有个问题，试想如果两个线程同时修改 x，它就无法处理了，此时，就只能使用第一种方案了。

在 Java 中，这种加 Padding 的玩法主要有三种实现方式：

- 变量前后添加 N 个 long 类型，N 的取值有两种说法，一种是 7，一种是 15，因为内存布局是按 8 字节对齐的，所以加上 7 个 long 正好等于 64 字节，也就是一个缓存行的大小，可以保证这个变量与其它变量分隔开，15 的说法是为了避免相邻扇区预取导致的伪共享冲突，在 Disruptor 框架中使用的是 7，在 jctools 中使用的是 15；
- 使用继承且在父子类中加上 padding，这样是为了防止内存布局重排序，比如，下面这个类，会把 byte 类型的 b 存储在 long 类型的前面，因为对象头占用 12 字节（压缩后），byte 类型占用 1 字节，这样只需要被 3 个字节就可以了，如果不做这种重排序，对象头需要补齐 4 个字节，而 byte 类型需要补齐 7 个字节，造成空间浪费；

```java
 class MemoryLayout{
     private long a;
     private byte b;
 }
```

- 使用 @sun.misc.Contended 注解，不过这是 Java8 新增的注解，所以，无法兼容之前的版本，现在大部分开源框架还没有使用这个注解；

好了，针对伪共享的问题，我们就简单介绍这么多内容，还是回到正题。



 #### 回归正题

如果把避免伪共享添加的这些字段去掉，那么，MpscArrayQueue 就只剩下这么几个字段了：

```java
public class FakeMpscArrayQueue<E> {
    // 掩码，用来计算数组下标，加1就成了容量
    protected final long mask;
    // 存储数据的环形数组
    protected final E[] buffer;
    // 生产者索引，有volatile
    private volatile long producerIndex;
    // 生产者索引的最大值，有volatile
    private volatile long producerLimit;
    // 消费者索引，无volatile
    protected long consumerIndex;
}
```

可以发现，producerIndex 和 producerLimit 加了 volatile，而 consumerIndex 却没有，这是为什么呢？请记住我们的场景是 MPSC，多生产者单消费者，所以，生产者的索引修改必须立马对其它线程可见，而只有一个消费者，它并不需要对别的线程立马可见，当然，生产者在特定情况下也是需要 consumerIndex 的最新值的，比如，环形数组的头性相接了，它是怎么实现的呢？让我们跟着源码来一起学习吧。



 #### 源码剖析



 ##### 调试用例

这一节的用例就比较好写了，因为 MpscArrayQueue 实现了 Queue 接口，所以，我们只要按其它的队列一样来写用例就可以了：

```java
public class MpscArrayQueueTest {

    public static final MpscArrayQueue<String> QUEUE = new MpscArrayQueue<>(5);

    public static void main(String[] args) {
        // 入队，如果队列满了则会抛出异常
        QUEUE.add("1");
        // 入队，返回是否成功
        QUEUE.offer("2");
        QUEUE.offer("3");
        QUEUE.offer("4");

        // 存储了多少元素
        System.out.println("队列大小：" + QUEUE.size());
        // 容量，可以存储多少元素，会按2次方对齐，所以这里为8
        System.out.println("队列容量" + QUEUE.capacity());

        // 出队，如果队列为空则会抛出异常
        System.out.println("出队：" + QUEUE.remove());
        // 出队，如果队列为空返回null
        System.out.println("出队：" + QUEUE.poll());
        // 查看队列头元素，如果队列为空则会抛出异常
        System.out.println("查看队列头元素：" + QUEUE.element());
        // 查看队列头元素，如果队列为空则返回null
        System.out.println("查看队列头元素：" + QUEUE.peek());
    }
}
```

接口 Queue 中对于入队、出队、查看队首元素各定义了两种方法，一类是抛出异常，一类是返回特定值：

|              | 抛出异常  | 返回特定值 |
| :----------- | :-------- | :--------- |
| 入队         | add(e)    | offer(e)   |
| 出队         | remove()  | poll()     |
| 查看队首元素 | element() | peek()     |

其中，抛出异常的方法最终也还是调用的返回特定值的方法，而查看队首元素跟出队方法是比较类似的，所以，这里我们主要看 offer (e)、poll () 这两个方法的源码实现。



 ##### 入队 offer (e)

好了，让我们先来看看入队方法 offer (e) 的实现，在 `QUEUE.offer("2");` 处打一个断点，此时，已经入队一个元素了，跟踪进去：

```java
// 入队
@Override
public boolean offer(final E e)
{
    // 空值检查
    if (null == e)
    {
        throw new NullPointerException();
    }

    // 掩码
    final long mask = this.mask;
    // 生产者的最大的索引值，初始时为传入的容量，即5
    long producerLimit = lvProducerLimit(); // LoadLoad
    long pIndex;
    do
    {
        // 生产者索引
        pIndex = lvProducerIndex(); // LoadLoad
        // 如果生产者索引达到了最大值，防止追尾
        if (pIndex >= producerLimit)
        {
            // 消费者索引，以volatile的形式获取，保证获取的是最新的值
            final long cIndex = lvConsumerIndex(); // LoadLoad
            // 修改为当前消费者的索引加上数组的大小
            producerLimit = cIndex + mask + 1;

            // 如果依然达到了最大值，则返回false，表示队列满了，再放元素就追尾了
            if (pIndex >= producerLimit)
            {
                return false; // FULL :(
            }
            else
            {
                // 否则更新最大索引为新值
                soProducerLimit(producerLimit);
            }
        }
    }
    // CAS更新生产者索引，更新成功了则跳出循环，说明数组中这个下标被当前这个生产者占有了
    // 此时即使更新索引成功了，数组中依然还没有放入元素
    // 如果更新失败，说明其它生产者（线程）先占用了这个位置，重新来过
    while (!casProducerIndex(pIndex, pIndex + 1));
    // 计算这个索引在数组中的下标偏移量
    final long offset = calcElementOffset(pIndex, mask);
    // 将元素放到这个位置
    soElement(buffer, offset, e); // StoreStore
    // 入队成功
    return true; // AWESOME :)
}
// lv=load valatile
// 读取producerLimit
protected final long lvProducerLimit()
{   // producerLimit本身就是volatile修饰的
    // 所以不用像下面的consumerIndex一样通过UNSAFE.getLongVolatile()一样来读取
    return producerLimit;
}
// 读取producerIndex
public final long lvProducerIndex()
{
    // producerIndex本身就用volatile修饰了
    return producerIndex;
}
// 读取consumerIndex
public final long lvConsumerIndex()
{   // 以volatile的形式加载consumerIndex
    // 此时，可以把consumerIndex想像成前面加了volatile
    // 会从内存读取最新的值
    return UNSAFE.getLongVolatile(this, C_INDEX_OFFSET);
}
// so=save ordered
// 保存producerLimit
protected final void soProducerLimit(long newValue)
{
    // 这个方法会加StoreStore屏障
    // 会把最新值直接更新到主内存中，但其它线程不会立即可见
    // 其它线程需要使用volatile语义才能读取到最新值
    // 这相当于是一种延时更新的方法，比volatile语义的性能要高一些
    UNSAFE.putOrderedLong(this, P_LIMIT_OFFSET, newValue);
}
// 修改数组对应偏移量的值
public static <E> void soElement(E[] buffer, long offset, E e)
{
    // 与上面同样的方法，比使用下标更新数组元素有两个优势
    // 1. 使用Unsafe操作内存更新更快
    // 2. 使用putOrderedObject会直接更新到主内存，而使用下标不会立马更新到主内存
    UNSAFE.putOrderedObject(buffer, offset, e);
}
// CAS更新producerIndex
protected final boolean casProducerIndex(long expect, long newValue)
{
    // CAS更新
    return UNSAFE.compareAndSwapLong(this, P_INDEX_OFFSET, expect, newValue);
}
```

这段入队的方法看似简单，实则蕴含大量的底层知识和优化技巧，让我们来看几个问题：

- 为什么需要 producerLimit，拿 producerIndex 与 consumerIndex 直接比较行不行？
- 很多方法后面写了 LoadLoad、StoreStore，它们是什么意思？
- Unsafe 的新方法 putOrderedObject () 和 getLongVolatile ()？

我们先来看第一个问题：**为什么要使用 producerLimit 呢？**

其实不使用 producerLimit 也是可以的，只不过这样的话，就需要每次都使用 volatile 语义获取 consumerIndex 的值，再用这个值加上数组的大小，就是 producerIndex 能达到的最大值，这跟把 consumerIndex 声明为 volatile 就没有什么分别了，也就无法达到提高性能的目的了。使用 producerLimit 的好处是明显的，差不多一轮才需要获取一次 consumerIndex 的值，相当于减少了消费端的竞争。

接着看看第二个问题：**LoadLoad、StoreStore 是什么意思？**

可以把 LoadLoad 看成是读屏障，表示每次都从主内存读取最新值，StoreStore 看成是写屏障，每次都把最新值写入到主内存。如果一个线程使用 StoreStore 屏障把最新值写入主内存，另一个线程只需要使用 LoadLoad 屏障就可以读取到最新值了，它们俩往往结合着来使用。

最后一个问题：**Unsafe 的新方法 putOrderedObject () 和 getLongVolatile ()？**

其实，在 Unsafe 中有五组相似的方法：

- putOrderedXxx ()，使用 StoreStore 屏障，会把最新值更新到主内存，但不会立即失效其它缓存行中的数据，是一种延时更新机制；
- putXxxVolatile ()，使用 StoreLoad 屏障，会把最新值更新到主内存，同时会把其它缓存行的数据失效，或者说会刷新其它缓存行的数据；
- putXxx (obj, offset)，不使用任何屏障，更新对象对应偏移量的值；
- getXxxVolatile ()，使用 LoadLoad 屏障，会从主内存获取最新值；
- getXxx，不使用任何屏障，读取对象对应偏移量的值；

从性能方面来说的话，putOrderedXxx () 用得好的话，性能会比 putXxxVolatile () 高一些，但是，如果用的不好的话，可能会出现并发安全的问题，所以，个人请谨慎使用，即使使用了，也要做好并发安全的测试。

OK，基础知识也补齐了，如果还看不懂，不要紧，先跳过去，我们再来看看出队方法，等看完出队方法了，我们使用脑补法来模拟一下入队出队的实现。



 ##### 出队 poll ()

同样地，在 `System.out.println("出队：" + QUEUE.poll());` 这行打一个断点，并跟踪进去：

```java
// 出队
@Override
public E poll()
{
    // 读取consumerIndex的值，注意这里是lp不是lv
    final long cIndex = lpConsumerIndex();
    // 计算在数组中的偏移量
    final long offset = calcElementOffset(cIndex);
    // 存储元素的数组
    final E[] buffer = this.buffer;

    // 取元素，前面通过StoreStore写入的，这里通过LoadLoad取出来的就是最新值
    E e = lvElement(buffer, offset); // LoadLoad
    if (null == e)
    {
        // 有一种例外，还记得上面入队的时候吗？
        // 是先更新了producerIndex的值，再把更新元素到数组中的。
        // 如果在两者之间，进行了消费，则此处是无法获取到元素的
        // 所以需要进入下面的判断
        // 判断consumerIndex是否等于producerIndex
        // 只要两则不相等，就可以再消费元素
        if (cIndex != lvProducerIndex())
        {
            // 使用死循环来取元素，直到取到为止
            do
            {
                e = lvElement(buffer, offset);
            }
            while (e == null);
        }
        else
        {
            // 如果两个索引相等了，说明没有元素了，返回null
            return null;
        }
    }

    // 更新取出的位置元素为null，注意是sp，不是so
    spElement(buffer, offset, null);
    // 修改consumerIndex的索引为新值，使用StoreStore屏障，直接更新到主内存
    soConsumerIndex(cIndex + 1); // StoreStore
    // 返回出队的元素
    return e;
}
// lp=load plain，简单读取
protected final long lpConsumerIndex()
{
    return consumerIndex;
}
// sp=store plain，简单存储
public static <E> void spElement(E[] buffer, long offset, E e)
{
    UNSAFE.putObject(buffer, offset, e);
}
```

时刻要记住消费者只有一个，所以，消费端完全不需要使用任何锁或者 CAS 操作，但是，生产者端是有可能读取 consumerIndex 的值的，所以，使用 StoreStore 屏障修改它的值即可。

还有一种例外，是生产者端先更新 producerIndex，再更新数组元素，这里使用死循环不断读取直到读取到为止。

入队出队的代码都分析完毕了，可以看到，整体的逻辑非常少，我算了下，入队出队两者加一起的主体逻辑都不到 100 行，但是，里面蕴含了大量的底层知识，为了更好地理解这种队列，我决定使用脑补法来模拟一下入队出队的过程。



 ##### 脑补入队出队过程

为了简单点，我们假设队列的长度为 4，一共入队 5 个元素，并出队 2 个元素，2 个生产者：
![图片描述](https://img1.sycdn.imooc.com/5f3346aa0001761a10290353.png)

假设入队的过程为 1、4 同时请求入队，3 入队，2、5 同时请求入队，连续出队 4 次，6 入队，让我们分析下整个过程：

1. 初始时，pIndex=0，cIndex=0，pLimit=4；（p=producer，c=consumer，下同)
2. 1、4 同时请求入队，两者拿到 pIndex 都是 0，pLimit 都是 4，所以，都判断为小于 pLimit，可以入队，但是在 CAS 更新 pIndex 的时候必然会一个成功一个失败，假设生产者 1 成功了，1 成功入队，4 入队失败，进入循环，重新读取 pIndex 为 1（因为 pIndex 为 volatile，所以 CAS 更新为 1 后立即对生产者 2 可见），判断依然小于 pLimit，可以入队，CAS 更新 pIndex 为 2；
3. 3 请求入队，没人跟它竞争，直接入队成功，pIndex 被更新为 3；
4. 2、5 同时请求入队，两者拿到的 pIndex 都是 3，pLimit 都是 4，所以，都判断为小于 pLimit，可以入队，但是在 CAS 更新 pIndex 的时候必然会有一个成功一个失败，假设生产者 2 成功了，5 成功入队，2 入队失败，进入循环，重新读取 pIndex 为 4，等于 pLimit 了（重新计算 pLimit 还是 4），所以直接返回 false，2 入队失败了；
5. 出队，此时，读取到 cIndex 为 0，读取数组下标为 0 位置的元素，也就是 1，更新下标 0 处元素为 null，并更新 cIndex 为 1，因为使用的是 StoreStore 屏障，所以，主内存中的 cIndex 也为 1；
6. 出队，出队，出队，同样地，最后，主内存中的 cIndex 为 4；
7. 6 请求入队，此时，读取到的 pIndex 为 4，pLimit 也为 4，pIndex 大于等于了 pLimit，重新读取 cIndex 的值为 4，并重新计算 pLimit 为 8，再判断 pIndex 小于 pLimit 了，更新主内存中的 pLimit 为新值 8，CAS 更新 pIndex 的值为 5 成功，6 入队成功，且在数组下标为 0 的位置。

整个过程就是这样，咦，6 是怎么跑到下标为 0 的位置的？

这个其实是通过计算偏移量算出来的，即下面这段代码：

```java
public static long calcElementOffset(long index, long mask)
{
    // REF_ARRAY_BASE，基础地址，数组在内存中的地址
    // REF_ELEMENT_SHIFT，可以简单地看作一个元素占用多少字节
    // 64位系统中一个引用对象占用64位，也就是8字节，但是压缩模式下占用4字节
    // index & mask 计算数组下标
    // 比如数组大小为4，mask就为3，pIndex为4时，4&3=100&11=0
    return REF_ARRAY_BASE + ((index & mask) << REF_ELEMENT_SHIFT);
}
```

好了，到这里，关于 MpscArrayQueue 的剖析就结束了，开篇我们说了，它还有很多兄弟类 ——MpscChunkedArrayQueue、MpscUnboundedArrayQueue、MpscAtomicArrayQueue、MpscGrowableAtomicArrayQueue、MpscUnboundedAtomicArrayQueue，相信有了本节的基础，分析这些类对你来说不是什么难事了。

> 带 Atomic 的类，是表示在 Netty 无法使用 Unsafe 的情况下使用 Atomic 原子类来做替代方案。



 ### 后记

本节，我们一起回顾了 Java 原生队列，并从源码级别剖析了一个 MPSC 队列 ——MpscArrayQueue，从中学到了很多 Java 底层的知识，相信有了本节的学习，下次再看到跟 Unsafe、伪共享相关的代码，你一定能够自己剖析地很好。

其实，Netty 中不仅使用了非常高效的 jctools 提供的队列，它还对 Java 原生的很多功能做了增强，比如前面学过的 ByteBuf、即将学到的 Future、线程池等等。

下一节，我们就来一起学习 Netty 增强的 Future，提前告诉你，Netty 虽然增强了 Future，但是它一不小心就搞出了个 Bug 呢，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3202950001511f19161671.png)



 ### 特别说明

在上一节中，InternalThreadLocalMap 中也使用了 padding 来消除伪共享，但是，那个用法实在不知道它是为了保护哪个变量被伪共享，而且，经过测试，也没发现加这段 padding 有明显的性能提升。

所以，正确的用法是本节介绍的这种用法，大家后面自己使用的时候也可以参考本节的用法，或者使用 Java8 的新注解 @sun.misc.Contended 来实现。



 ### 参考链接

[死磕 java 集合之 LinkedList 源码分析](https://mp.weixin.qq.com/s/Vy83PNpXvKCM9YG6CiTwBQ)

[死磕 java 集合之 PriorityQueue 源码分析](https://mp.weixin.qq.com/s/kGKS7WXWbf-ME1_Hr3Fpgw)

[死磕 java 集合之 ArrayBlockingQueue 源码分析](https://mp.weixin.qq.com/s/EN7qY1w4e8C0ZXiP7i82TA)

[死磕 java 集合之 LinkedBlockingQueue 源码分析](https://mp.weixin.qq.com/s/y6PoK3UbVLwdZoauLX8nsQ)

[死磕 java 集合之 SynchronousQueue 源码分析](https://mp.weixin.qq.com/s/dv_jT0-FuB-e2lDOXuqAwg)

[死磕 java 集合之 PriorityBlockingQueue 源码分析](https://mp.weixin.qq.com/s/AfSwIRbI-YjhMegv9qHazw)

[死磕 java 集合之 LinkedTransferQueue 源码分析](https://mp.weixin.qq.com/s/OZ8tbFqvD9lWEgdvtJ5wog)

[死磕 java 集合之 DelayQueue 源码分析](https://mp.weixin.qq.com/s/IOTwwgaOdMpZl-6QM0HlVQ)

[死磕 java 集合之 ConcurrentLinkedQueue 源码分析](https://mp.weixin.qq.com/s/DcirxmnxtS54fNbRYoimYA)

[杂谈 什么是伪共享？](https://mp.weixin.qq.com/s/rd13SOSxhLA6TT13N9ni8Q)





<div style="page-break-after:always;"></div>

 ## 25 Netty的Future是如何做到简捷易用的


![img](https://img3.sycdn.imooc.com/5f059664000169c206400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)受苦的人，没有悲观的权利。——尼采![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了 Netty 中使用到的队列，它是对 Java 原生队列的增强，其实，Netty 对 Java 原生的增强还有很多，比如，本节将要讨论的 Future。

Java 原生提供了一个 Future 接口，可以用来获取线程池中任务执行的结果，但是，它只提供了简单的功能，不能实现诸如判断任务是否成功执行完毕、任务执行完后来个回调、手动设置任务执行的结果等功能。

为了实现这些功能，Netty 扩展了 Java 原生的 Future 接口，并增加了一些实用的方法，但是，一不小心，Netty 也搞出了一个小 bug，而且，到目前为止，这个 Bug 依然还未修复，你知道这个 bug 是什么吗？

今天，就让我们一起来学习 Netty 增强的 Future。



 ### Java 原生 Future

首先，让我们来回顾下 Java 原生的 Future。
![图片描述](https://img1.sycdn.imooc.com/5f34a7b9000174c011630287.png)

所谓 Future，是未来、将来的意思，在 Java 中，它是指在未来做些什么，它跟 Runnable 组合就变成了 RunnableFuture，它跟 Scheduled 组合就变成了 ScheduledFuture，它跟 ForkJoin 组合就变成了 ForkJoinTask，它跟 Completable 组合就变成了 CompletableFuture，在 JUC 包下面主要提供了上图中这几种实现，其实，远远不止这些，还有很多在内部类里面，我没有列出来，本节，我们主要看两个简单的实现：FutureTask 和 CompletableFuture。

> RecursiveAction 表示无返回值任务，RecursiveTask 表示有返回值任务，CountedCompleter 表示有回调的无返回值任务，它们三个都是用在 ForkJoinPool 中的，有兴趣的同学可以自己看下相关的源码。



 #### Future 接口

首先，我们先看看 Future 接口提供了哪些能力：

```java
package java.util.concurrent;

public interface Future<V> {
    /**
     * <p>After this method returns, subsequent calls to {@link #isDone} will
     * always return {@code true}.  Subsequent calls to {@link #isCancelled}
     * will always return {@code true} if this method returned {@code true}.
     */
    // 取消，请记住上面的话：
    //      在这个方法返回之后，后面的isDone()方法总是返回true。
    //      如果这个方法返回true，后面的isCancelled()方法总是返回true。
    boolean cancel(boolean mayInterruptIfRunning);
    // 判断是否已取消
    boolean isCancelled();
    // 判断是否已完成，已完成有多层含义：已正常完成、已异常完成、已取消
    boolean isDone();
    // 获取结果，可以设置等待时间
    V get() throws InterruptedException, ExecutionException;
    V get(long timeout, TimeUnit unit)
        throws InterruptedException, ExecutionException, TimeoutException;
}
```

Future 接口除了提供获取任务执行结果的方法外，还提供了取消任务、判断任务是否已取消、是否已完成的方法，不过，这里的 isDone () 方法其实代表了三种状态：已正常完成、已异常完成、已取消，这是有点混乱的地方。



 #### FutureTask

FutureTask，用于在未来获取线程池中任务执行的结果，它的主要方法就是 get ()，调用 get () 时，如果任务未执行完毕会阻塞当前线程直到任务执行完毕并返回，如果任务已执行完毕则会立即返回任务执行的结果。它的实现原理很简单，是很多异步框架实现同步的基本原理，比如，Dubbo 中同步调用的实现方式就是参考 FutureTask 的实现的。

那么，FutureTask 该如何使用呢？请看下面的例子：

```java
public class FutureTaskTest {

    // 创建一个线程池
    private static final ExecutorService THREAD_POOL = Executors.newFixedThreadPool(8);

    public static void main(String[] args) throws ExecutionException, InterruptedException {
        // 执行第一个任务
        Future<Integer> future1 = THREAD_POOL.submit(() -> {
            // 阻塞1秒
            LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(1));
            // 返回1
            return 1;
        });
        // 执行第二个任务
        Future<Integer> future2 = THREAD_POOL.submit(() -> {
            // 阻塞2秒
            LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(2));
            // 返回2
            return 2;
        });

        // 把两个任务执行的结果相加
        int result = future1.get() + future2.get();
        // 打印
        System.out.println("result=" + result);
    }
}
```

在这个例子中，我们创建了一个固定大小的线程池，提交了两个任务，一个阻塞 1 秒后返回 1，一个阻塞 2 秒后返回 2，在主线程中，我们调用两个 Future 的 get () 方法获取任务执行的结果，并把它们相加，最后，打印输出结果。

运行这段代码，我们会发现，大概会在 2 秒后打印结果，也就是主线程一共等待了 2 秒钟，具体来说，是在调用两个 Future.get () 的时候其中一个等待了 2 秒钟，这两个 get () 方法有个短板效应（好像不太准备，长板效应是不是好点 ^^），以最晚返回的为准。

在这两例子中，其实是有两次阻塞，第一次是 future1.get () 阻塞了 1 秒，返回之后，调用 future2.get ()，又阻塞了 1 秒，才返回。如果把 future1 和 future2 换下位置会怎样呢？那就只有一次阻塞了，因为调用 future2.get () 的时候阻塞了 2 秒，此时，再调用 future1.get () 的时候，future1 对应的任务早都执行完了，所以会立即返回，不会再次阻塞。

那么，这个 get () 方法的阻塞是如何实现的呢？

让我们先看看 FutureTask 有哪些属性：

```java
public class FutureTask<V> implements RunnableFuture<V> {
    // 状态
    private volatile int state;
    private static final int NEW          = 0;
    private static final int COMPLETING   = 1;
    private static final int NORMAL       = 2;
    private static final int EXCEPTIONAL  = 3;
    private static final int CANCELLED    = 4;
    private static final int INTERRUPTING = 5;
    private static final int INTERRUPTED  = 6;

    // 任务
    private Callable<V> callable;
    // 返回值（正常的返回值或者异常）
    private Object outcome;
    // 运行任务的线程（防止多个线程同时运行了这个任务）
    private volatile Thread runner;
    // 等待队列，即调用者，多个调用者组成队列
    private volatile WaitNode waiters;
}
```

FutureTask 主要有五个重要的属性：

- state，状态，状态有七种，对于一个正常结束的任务，它的状态会从 NEW 到 COMPLETING，最后变成 NORMAL，表示正常结束；对于一个异常结束的任务，它的状态会从 NEW 到 COMPLETING，再到 EXCEPTIONAL，表示异常结束；
- callable，任务，外部传入的待执行的任务，任务执行完了会把这个字段置空；
- outcome，任务执行的结果，如果任务正常执行完毕则返回值会存储在里面，如果任务异常执行完成则保存的是异常信息，当调用 get () 方法时，如果任务已结束则根据状态变量的值判断是抛出异常还是正常返回值；另外，可以看到这个变量没有使用 volatile 关键字修饰，因为它总是在 state 调用之后被调用，所以，state 的 volatile 相当于对它也起到了保护作用；
- runner，运行任务的线程，当有一个线程运行任务时，设置该值，当有其它线程也想运行该任务时，则会直接返回；
- waiters，等待队列，在任务未结束之前，调用 get () 方法的所有线程都将进入这个队列中等待，当任务完成时，会依次唤醒这些等待的线程。

根据这五个属性，让我们脑补一下 FutureTask 正常执行结束的流程：

1. 初始化时，state 变量的值为 NEW；
2. 此时，如果调用 get () 方法，检测到此时 state 为 NEW，新建一个 WaitNode 节点并入队，当然了，此时 waiters 只有一个节点，如果另一个线程也调用了 get () 方法，那个线程也会入队；
3. 轮到任务运行了，运行之前检查状态是不是 NEW，并把运行的线程设置到 runner 变量中，这样下一个线程如果要运行检测到 runner 中有值了，就不会再重复执行任务了；
4. 当任务运行完毕，将 state 设置为 COMPLETING，并把任务执行的结果设置到 outcome 中；
5. 因为是正常运行结束，所以，最后，将 state 修改为 NORMAL 状态；
6. 任务运行完毕，将 waiters 中阻塞的线程全部唤醒；
7. get () 方法返回结果，调用着获取到结果做后续业务处理；

> 上面只是我们脑补的过程，实际情况到底是不是这样呢？这不在本节的范围之内，有兴趣的同学可以参考下这篇文章：[死磕 java 线程系列之线程池深入解析 —— 未来任务执行流程](https://mp.weixin.qq.com/s/qxBfzP-uFe1gvnV87jkw7g)

好了，FutureTask 看完了，我们再来看看 CompletableFuture。



 #### CompletableFuture

CompletableFuture，使用它你可以在任务执行完毕之后执行一系列的回调，不管是正常还是异常结束。

那么，它该怎么使用呢？让我们来看一个例子：

```java
public class CompletableFutureTest {

    // 创建一个线程池
    private static Executor threadPool = Executors.newFixedThreadPool(5);

    public static void main(String[] args) throws IOException, ExecutionException, InterruptedException {
        // 执行一个有返回值的任务
        CompletableFuture<?> future = CompletableFuture.supplyAsync(() -> {
            LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(2));
            System.out.println("inner thread: " + Thread.currentThread().getName());
//            throw new RuntimeException();
            return "aaaaa";
            // 如果执行异常，会进入下面这个回调
        }, threadPool).exceptionally(e -> {
            System.out.println("exception: " + e + ", thread: " + Thread.currentThread().getName());
            return "bbbbb";
            // 执行一个有返回值的回调
        }).thenApplyAsync(s -> {
            System.out.println("result: " + s + ", thread: " + Thread.currentThread().getName());
            return "ccccc";
            // 执行一个无返回值的回调
        }, threadPool).thenAcceptAsync(s -> {
            System.out.println("result2: " + s + ", thread: " + Thread.currentThread().getName());
            // 再执行一个有返回值的回调
        }, threadPool).thenApplyAsync(s -> {
            System.out.println("result3: " + s + ", thread: " + Thread.currentThread().getName());
            return "ddddd";
        }, threadPool);

        System.out.println("completableFuture running!");

        // 调用get()方法
        System.out.println("get: " + future.get());

    }
}
```

在这个例子中，我有两个问题：

1. 这个 get () 方法获取的返回值到底是什么？
2. 如果把任务体中的抛出异常注释打开，并把下面一行注释掉，这个 get () 获取到的返回值又是什么？

运行一下这个程序，你会发现最终 get () 方法获取的返回值都是 `ddddd`，也就是说原始任务的返回值被吃掉了，这是这个类比较迷的一点。

另外，CompletableFuture 中的很多方法都有同步和异步两种方式，针对异步方式，你还可以设置使用哪个线程池来运行，如果没有指定线程池，默认使用的是 `ForkJoinPool.commonPool()` 来运行。

这个类里面大量使用了跟 ForkJoinPool 相关的代码，比如对任务或者回调的包装都是继承自 ForkJoinTask，它已经不是一个纯粹的类了，跟 ForkJoinPool 的耦合特别严重，这不是一个良好的编程范式，所以，这个类我不打算深入讲解。

既然，Java 原生提供了 CompletableFuture 这个可以支持回调的 Future，那么，Netty 为什么还要实现自己的 Future 呢？总结起来，原因大概有以下两点：

1. CompletableFuture 是 Java8 新加入的类， 对于早期的 Netty 无法吃到这个福利；
2. CompletableFuture 的实现过于复杂，且强耦合于 ForkJoinPool，这不是良好的设计，所以，Netty 并不打算使用它；

所以，下面就让我们看看 Netty 是如何实现自己的 Future 的。



 ### Netty 的 Future

Netty 的 Future 扩展自 Java 原生的 Future，而且又提供了一种可以修改结果的增强，叫作 Promise。

针对 Future 的学习，我们同样使用从宏观到微观的分析方法。



 #### 继承体系

![图片描述](https://img1.sycdn.imooc.com/5f34a83800013f3c17420600.png)

其实，Netty 中的 Future 远远不止这些，这个图中只列举了一部分 Future，还有诸如带进度条的 Future 等不常用的没有列进来。

上面这个图，我们可以分成几个部分来看：

- 左边，跟 Runnable 相关，表示的是任务，主要实现类有 PromiseTask、ScheduledFutureTask 等；
- 中间，主要是 Promise 相关，经典实现 DefaultPromise；
- 右边，跟 Complete 相关，表示完成，Netty 将完成分成两种状态，即 Succeeded 和 Failed，非常清晰；
- 最后一部分，跟 Channel 相关，它可以跟 Promise 和 Complete 任意组合；

可以看到，Netty 中 Future 的继承体系非常清晰，而且看一眼名字就大概知道是干什么的，除了结构清晰以外，还有另外一点值得说明的是，Netty 中所有 Future 子类的代码也是比较接近的，看懂了一个，其它的基本很容易就能看懂，而 Java 原生的 Future 体系，可以说，每一个 Future 的实现都不一样，这让人感到很痛苦。

好了，既然 Netty 的 Future 是对 Java 原生 Future 的增强，那我们就来看看它到底增强了哪些方法吧。



 #### 增强的方法

Netty 中 Future 的增强主要分成两级，一级是 Future，一级是 Promise。

我们先来看看 Future 这个接口：

```java
package io.netty.util.concurrent;

public interface Future<V> extends java.util.concurrent.Future<V> {
    // 返回是否成功
    boolean isSuccess();
    // 返回是否可取消
    boolean isCancellable();
    // 返回异常，如果有异常的话
    Throwable cause();
    // 添加或移除回调的监听器
    Future<V> addListener(GenericFutureListener<? extends Future<? super V>> listener);
    Future<V> addListeners(GenericFutureListener<? extends Future<? super V>>... listeners);
    Future<V> removeListener(GenericFutureListener<? extends Future<? super V>> listener);
    Future<V> removeListeners(GenericFutureListener<? extends Future<? super V>>... listeners);
    // 阻塞直到完成（内部调用await()方法），如果有异常则会抛出异常
    Future<V> sync() throws InterruptedException;
    Future<V> syncUninterruptibly();
    // 等待完成
    Future<V> await() throws InterruptedException;
    Future<V> awaitUninterruptibly();
    boolean await(long timeout, TimeUnit unit) throws InterruptedException;
    boolean await(long timeoutMillis) throws InterruptedException;
    boolean awaitUninterruptibly(long timeout, TimeUnit unit);
    boolean awaitUninterruptibly(long timeoutMillis);
    // 立即获取结果，如果还没有完成则返回null，不会阻塞
    V getNow();
    // 取消
    @Override
    boolean cancel(boolean mayInterruptIfRunning);
}
```

可以看到，Netty 的 Future 接口增加了很多语义比较明确的方法，比如判断是否成功完成、是否可取消、返回任务执行异常、明确的阻塞或者等待方法、立即获取结果的方法等，另外，最有用的要数 Listener 回调机制了，这是 Java 原生 Future 所欠缺的，虽然 Java 中的 CompletableFuture 也提供了回调机制，但是，使用 CompletableFuture 的回调连原始任务执行的结果都不知道了，显然是有问题的，而且里面耦合了太多 ForkJoinPool 的代码，也不符合 Netty 的极简原则。

好了，我们再看看另一级增强 ——Promise：

```java
public interface Promise<V> extends Future<V> {
    // 显式地将结果设置为成功，如果设置失败将抛出异常
    Promise<V> setSuccess(V result);
    // 尝试将结果设置为成功，如果设置失败将返回false
    boolean trySuccess(V result);
    // 显式地将结果设置为失败，如果设置失败将抛出异常
    Promise<V> setFailure(Throwable cause);
    // 尝试将结果设置为失败，如果设置失败将返回false
    boolean tryFailure(Throwable cause);
    // 设置为不可取消
    boolean setUncancellable();
    // 以下为Future接口方法的重新定义（重写）
    @Override
    Promise<V> addListener(GenericFutureListener<? extends Future<? super V>> listener);
    @Override
    Promise<V> addListeners(GenericFutureListener<? extends Future<? super V>>... listeners);
    @Override
    Promise<V> removeListener(GenericFutureListener<? extends Future<? super V>> listener);
    @Override
    Promise<V> removeListeners(GenericFutureListener<? extends Future<? super V>>... listeners);
    @Override
    Promise<V> await() throws InterruptedException;
    @Override
    Promise<V> awaitUninterruptibly();
    @Override
    Promise<V> sync() throws InterruptedException;
    @Override
    Promise<V> syncUninterruptibly();
}
```

Promise 的主要作用就是提供了显式修改结果的方法，它可以把结果修改为成功或者失败，另外，还提供了设置不可取消的方法，我们开篇说的小 bug 就出在这个 `setUncancellable()` 方法上，为什么这么说呢？让我们看个例子：

```java
public class DefaultPromiseIsDoneBugTest {

    public static void main(String[] args) {
        // 创建一个promise
        Promise<?> promise = GlobalEventExecutor.INSTANCE.newPromise();
        // 设置为不可取消
        promise.setUncancellable();
        // 调用取消的方法
        boolean cancel = promise.cancel(false);
        // 调用是否完成的方法
        boolean isDone = promise.isDone();
        // 打印
        System.out.println(cancel);
        System.out.println(isDone);
        System.out.println(promise.isCancelled());
    }

}
```

相信你也可以预测到这段代码运行的结果，没错，它返回的结果是三个 false，乍看之下，似乎没什么问题。确实没什么大问题 ，让我们再回顾一下 Java 原生的 Future 接口中 cancel () 方法的注释：

```java
public interface Future<V> {
    /**
     * <p>After this method returns, subsequent calls to {@link #isDone} will
     * always return {@code true}.  Subsequent calls to {@link #isCancelled}
     * will always return {@code true} if this method returned {@code true}.
     */
    // 取消，请记住上面的话：
    //      在这个方法返回之后，后面的isDone()方法总是返回true。
    //      如果这个方法返回true，后面的isCancelled()方法总是返回true。
    boolean cancel(boolean mayInterruptIfRunning);
}
```

Netty 的实现虽然没有太大问题，但明显违反了 Java 原来这个方法的语义。针对这个问题，Netty 官方也给出了回应：
![图片描述](https://img1.sycdn.imooc.com/5f34a858000115da09450523.png)

根据 Norman 的回复，在下个大版本中，Netty 的 Future 接口将不再继承自 Java 原生的 Future 接口，但是，会提供一些转换的方法。

好了，这只是一个小插曲，下面我们从源码层面分析一个 Future 家族的经典实现 ——DefaultPromise。



 #### DefaultPromise



 ##### 主要属性

关于源码解析，我们首先来看一下 DefaultPromise 的属性：

```java
public class DefaultPromise<V> extends AbstractFuture<V> implements Promise<V> {
    // ...省略常量
    // 任务执行的结果
    private volatile Object result;
    // 执行的线程
    private final EventExecutor executor;
    // 监听器，用于执行回调
    private Object listeners;
    // 等待者的数量，即阻塞的线程数量
    private short waiters;
    // 用于控制通知监听，因为是在synchronized内部使用，所以不用加volatile关键字
    private boolean notifyingListeners;
}
```

可以看到，与 Java 原生 FutureTask 不一样的地方主要有以下几点：

1. 没有 state 变量，只有一个 volatile 修饰的 result 用于存放结果，那么，它是怎么维护这些状态的呢？
2. 没有了阻塞线程组成的队列，只存储了阻塞线程的数量，那么，它是怎么通知等待线程的呢？
3. 可以绑定了一系列的监听器，但是，它却是个 Object 类型，是不是有点奇怪？
4. 绑定了一个 EventExecutor，它是在什么时候使用的呢？

让我们带着这些问题，继续前进。



 ##### 调试用例

其实，DefaultPromise 的调试用例还是比较难写的，需要有前面服务启动和数据流向的源码剖析的底子，然后，从中找出一些端倪，才能比较容易地写出来，下面是我写的调试用例：

```java
public class DefaultPromiseTest {

    public static void main(String[] args) throws InterruptedException, IOException {
        // 相当于一个线程池中的一个线程（单线程）
        EventExecutor eventExecutor = new DefaultEventExecutor();
        // 使用EventExecutor的newPromise()方法创建
        Promise<Integer> promise1 = eventExecutor.newPromise();
        // 使用构造方法创建，推荐使用上面那种方式创建Promise
        Promise<Integer> promise2 = new DefaultPromise<>(eventExecutor);

        GenericFutureListener<Future<? super Integer>> listener = future -> {
            // 成功执行完毕
            if (future.isSuccess()) {
                System.out.println("done success, result=" + future.get()+", thread=" + Thread.currentThread().getName());
            } else {
                // 失败了
                System.out.println("done exception, e=" + future.cause()+", thread=" + Thread.currentThread().getName());
            }
        };
        promise1.addListener(listener);
        promise2.addListener(listener);

        // 执行两个任务
        eventExecutor.execute(() -> calc(2, promise1));
        eventExecutor.execute(() -> calc(0, promise2));

        // sync，阻塞，如果有异常会抛出异常
        promise1.sync();
        // await，阻塞，不会抛出异常
        promise2.await();

        System.out.println("finish");

        System.in.read();
    }

    private static void calc(int num, Promise<Integer> promise) {
        try {
            // 阻塞1秒
            LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(1));
            // 注意除数
            int result = 100 / num;
            System.out.println("success, thread=" + Thread.currentThread().getName());
            // 成功执行完毕
            promise.setSuccess(result);
        } catch (Exception e) {
            System.out.println("exception caught, e=" + e + ", thread=" + Thread.currentThread().getName());
            // 执行异常
            promise.setFailure(e);
        }
    }
}
```

首先，我们要明确一个概念，不管是 Future 还是 Promise，它们本身什么都代表不了，它们只是用来存储任务运行的结果（正常结果或者异常结果），所以，它们必须和任务一起使用才有意义，至于怎么一起使用，主要有两种形式，一种是同时实现 Future 接口（或 Promise 接口）和 Runnabe 接口，这样的实现类一般都是以 `XxxTask` 命名，比如 `FutureTask`、`PromiseTask`，一种是不实现 Runnable 接口，这样的类一般不具有 run () 方法，必须以参数的形式传递到任务的 run () 方法里面，这样在任务执行完毕才能把结果赋值给它。

可以看到，在我们的调试用例中，DefaultPromise 没有实现 Runnable 接口，所以，它只能以参数的形式传递给任务的 run () 方法，在任务执行完毕把结果再赋值给它。而任务一般在哪里运行呢？任务必须在线程池中运行，更确切地说，是需要有一个线程来执行任务，所以，这里我们需要创建一个线程，而在 Netty 中，线程又是以 EventExecutor 的形式存在的（可以把 EventExecutor 理解为 Java 原生线程池中的 Worker），因此，我们这里使用了一个 EventExecutor 的子类来作为线程使用。另外，查看 DefaultPromise 的构造方法，也可以知道，必须传一个 EventExecutor 类型的参数。

OK，在这个调试用例中，我们先创建了一个 DefaultEventExecutor 来作为任务执行的线程使用，随后使用不同的方式创建了两个 Promise，然后，创建了一个监听器并绑定到两个 Promise 中，接着使用上面创建的 EventExecutor 分别执行两个任务，最后，使用两种不同的方式阻塞等待任务执行完毕。在这个用例中，两个任务完全执行完毕需要多长时间？1 秒吗？2 秒吗？答案是 2 秒，因为这两个任务是放到同一个线程中来执行的，变成了串行，每个任务阻塞 1 秒，所以，一共是 2 秒。

好了，调试用例解释完毕，下面就来深入部署 DefaultPromise 的源码。



 ##### 源码剖析

前面创建 DefaultEventExecutor 和 DefaultPromise 的部分直接跳过，到创建监听器这里。

这里使用 lambda 表达式的形式创建了一个 GenericFutureListener 的匿名类，这个类里面我们对任务执行的结果进行监听，这个结果当然就是存储在 Future 里面的，通过 Future 的 isSuccess () 方法判断任务是否执行成功，然后针对成功和失败分别打印不同的语句。

然后，把这个监听器分别添加到两个 Promise 中，跟踪到 addListener () 方法中：

```java
// io.netty.util.concurrent.DefaultPromise#addListener
@Override
public Promise<V> addListener(GenericFutureListener<? extends Future<? super V>> listener) {
    checkNotNull(listener, "listener");
    // 添加监听器的时候加锁
    synchronized (this) {
        addListener0(listener);
    }
    // 如果任务已经执行完毕，直接触发监听器
    if (isDone()) {
        notifyListeners();
    }

    return this;
}

private void addListener0(GenericFutureListener<? extends Future<? super V>> listener) {
    // listeners即我们前面说的那个Object对象
    if (listeners == null) {
        // 1. 如果为空，则把listener直接赋值给它
        listeners = listener;
    } else if (listeners instanceof DefaultFutureListeners) {
        // 3. 如果是DefaultFutureListeners，则调用其add()方法
        ((DefaultFutureListeners) listeners).add(listener);
    } else {
        // 2. 否则创建一个DefaultFutureListeners把两个listener都添加进去
        listeners = new DefaultFutureListeners((GenericFutureListener<?>) listeners, listener);
    }
}
```

可以看到，对于 `private Object listeners;`，这个 listeners 可能有两种类型，一种是 GenericFutureListener，一种是 DefaultFutureListeners。试想一下，连续添加多个 listener 时的逻辑：

- 添加第一个 listener 时，listeners 为空，直接把这个 listener 赋值给 listeners；
- 添加第二个 listener 时，listeners 不为空，且不为 DefaultFutureListeners 类型，创建一个 DefaultFutureListeners 对象，并把当前添加这个和上一个添加的 listener 都通过构造方法传递给 DefaultFutureListeners；
- 添加第三个 listener 时，listeners 不为空，且为 DefaultFutureListeners 类型，直接调用 DefaultFutureListeners 的 add () 方法把 listener 添加进去。

查看 DefaultFutureListeners 的内容，可以发现，DefaultFutureListeners 里面维护一了个 GenericFutureListener 数组，那么，Netty 为什么要如此不嫌麻烦地这么玩呢？直接把这个数组放到 DefaultPromise 中，它不香么？

我猜测 Netty 这么玩的主要原因是，如果把数组直接放到 DefaultPromise 中，则针对这个数组的添加元素、删除元素、扩容的方法都要写在 DefaultPromise 中，DefaultPromise 类就变得不再单纯了，所以，另外拿一个类维护这些信息会比较好一些。至于添加第一个元素的时候为什么不使用 DefaultFutureListeners，可能是 DefaultFutureListeners 比较重（相当于一个 ArrayList），而且大部场景下可能都只有一个 Listener，所以针对一个 Listener 的时候单独处理一下可能要好一些，就像 HashMap 中针对 Key 为 String 类型时会单独处理一样。

好了，经历过两次 addListener ()，我们创建的 Listener 已经成功添加到两个 Promise 中了，下面就是执行任务 `eventExecutor.execute(() -> calc(2, promise1));` 了，这里就不用跟踪进去了，直接在 calc () 方法中打一个断点，按 F9，程序自然会走到 calc () 方法中：

```java
private static void calc(int num, Promise<Integer> promise) {
    try {
        // 阻塞1秒
        LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(1));
        // 注意除数
        int result = 100 / num;
        System.out.println("success, thread=" + Thread.currentThread().getName());
        // 成功执行完毕
        promise.setSuccess(result);
    } catch (Exception e) {
        System.out.println("exception caught, e=" + e + ", thread=" + Thread.currentThread().getName());
        // 执行异常
        promise.setFailure(e);
    }
}
```

在 calc () 方法中，我们主要做了一个除法运算，除数是传进来的参数 num，大家应该知道，如果 num 为 0 的话，这里肯定会抛出异常，所以，这里我使用一个 try…catch… 分别处理成功和失败的结果，对于成功的结果，调用 Promise 的 setSuccess () 方法将结果设置进去，对于失败的结果，那就是异常喽，使用 Promise 的 setFailure () 将异常信息设置进去。

继续跟进到 setSuccess () 方法内部：

```java
@Override
public Promise<V> setSuccess(V result) {
    if (setSuccess0(result)) {
        return this;
    }
    throw new IllegalStateException("complete already: " + this);
}
private boolean setSuccess0(V result) {
    return setValue0(result == null ? SUCCESS : result);
}
private boolean setValue0(Object objResult) {
    if (RESULT_UPDATER.compareAndSet(this, null, objResult) ||
        RESULT_UPDATER.compareAndSet(this, UNCANCELLABLE, objResult)) {
        if (checkNotifyWaiters()) {
            notifyListeners();
        }
        return true;
    }
    return false;
}
```

这里就比较简单了，不过知识点还是挺多的。首先，通过 CAS 的方式设置 result 的值，然后检查有没有等待者，有的话就通知它们，最后检查有没有 listeners，有的话就通知它们。

这里的 CAS 使用了一种特殊的技巧，我们可以看下 `RESULT_UPDATER` 的定义：

```java
private static final AtomicReferenceFieldUpdater<DefaultPromise, Object> RESULT_UPDATER =
            AtomicReferenceFieldUpdater.newUpdater(DefaultPromise.class, Object.class, "result");
private volatile Object result;
```

上面这两条语句在运行结果上等于下面这一条语句：

```java
private AtomicReference<Object> resultReference = new AtomicReference<>();
```

但是上面的写法更优，原因在于上面的语句使用 一个静态变量 + 一个非静态变量 的形式更节约内存，我们举个例子，假如创建 10 个 DefaultPromise，使用上面的语句内存中一共有 一个静态变量 + 10 个 result 变量，而如果使用下面的语句内存中会存储 10 个 resultReference 变量，同时，每个 resultReference 变量内部还维护了一个 Object 变量，所以一共是 20 个变量，下面的语句更耗内存，这种用法在 Netty 中随处可见。

然后，就是通知等待者：

```java
private synchronized boolean checkNotifyWaiters() {
    if (waiters > 0) {
        notifyAll();
    }
    return listeners != null;
}
```

这里比较恶心的一点是，明明 waiters 和 listeners 没有半毛线关系，但是，却把它们俩的判断放在同一个方法中，而把监听器的通知放在了这个方法之外，这样写的目的是为了共用同一个 `synchronized`。这里通知等待者使用的就是 Object 对象的 notifyAll () 方法，它只能使用在 `synchronized` 关键字内部，没错，Netty 对于等待者的处理就是使用的 Java 原生的 `synchronized`，并没有使用其它任何的技巧，简单唯美。

最后，就是通知监听器，这里有点小复杂：

```java
private void notifyListeners() {
    EventExecutor executor = executor();
    // 判断运行任务的线程跟执行监听回调的线程是不是同一个
    if (executor.inEventLoop()) {
        // 这里也是有点迷的地方，为什么要把stackDepth直接放到FastThreadLocal的InternalThreadLocalMap类中？
        // 这种耦合有点过分了
        final InternalThreadLocalMap threadLocals = InternalThreadLocalMap.get();
        final int stackDepth = threadLocals.futureListenerStackDepth();
        if (stackDepth < MAX_LISTENER_STACK_DEPTH) {
            threadLocals.setFutureListenerStackDepth(stackDepth + 1);
            try {
                // 立即通知监听器
                notifyListenersNow();
            } finally {
                threadLocals.setFutureListenerStackDepth(stackDepth);
            }
            // 注意，这里有个return
            return;
        }
    }
    // 如果不是同一个线程，走这个逻辑，使用监听器线程执行回调
    safeExecute(executor, new Runnable() {
        @Override
        public void run() {
            notifyListenersNow();
        }
    });
}
private void notifyListenersNow() {
    Object listeners;
    // 加锁，拿到listeners，赋值给局部变量，并清空之
    synchronized (this) {
        if (notifyingListeners || this.listeners == null) {
            return;
        }
        // 设置标志，说明正在进行回调的执行
        notifyingListeners = true;
        listeners = this.listeners;
        this.listeners = null;
    }
    for (;;) {
        // 执行回调
        if (listeners instanceof DefaultFutureListeners) {
            notifyListeners0((DefaultFutureListeners) listeners);
        } else {
            notifyListener0(this, (GenericFutureListener<?>) listeners);
        }
        // 加锁，做了两件事：
        // 如果执行回调期间添加了新的监听器，则赋值给局部变量，再次执行回调
        // 如果没有，则退出for循环并重置标志位
        synchronized (this) {
            if (this.listeners == null) {
                notifyingListeners = false;
                return;
            }
            listeners = this.listeners;
            this.listeners = null;
        }
    }
}
```

这里使用了锁拆分的技术，将锁拆分为两段，并把比较耗时的回调执行的过程剥离出去，能很大程度上提高效率。

真正执行回调这里就比较简单了，直接调用我们上面定义的 lambda 表达式：

```java
// 有多个监听器
private void notifyListeners0(DefaultFutureListeners listeners) {
    GenericFutureListener<?>[] a = listeners.listeners();
    int size = listeners.size();
    for (int i = 0; i < size; i ++) {
        notifyListener0(this, a[i]);
    }
}
// 单个监听器
@SuppressWarnings({ "unchecked", "rawtypes" })
private static void notifyListener0(Future future, GenericFutureListener l) {
    try {
        l.operationComplete(future);
    } catch (Throwable t) {
        if (logger.isWarnEnabled()) {
            logger.warn("An exception was thrown by " + l.getClass().getName() + ".operationComplete()", t);
        }
    }
}
```

好了，最后，还有一个 await () 方法：

```java
@Override
public Promise<V> await() throws InterruptedException {
    // 如果已经完成了，直接返回
    if (isDone()) {
        return this;
    }
    // 线程中断了，抛出异常
    if (Thread.interrupted()) {
        throw new InterruptedException(toString());
    }
    // 检查死锁，防止等待的方法在EventLoop中执行
    checkDeadLock();
    // 加锁
    synchronized (this) {
        while (!isDone()) {
            // 等待者数量加1
            incWaiters();
            try {
                // 等待，调用的是Object的wait()方法
                wait();
            } finally {
                // 等待者数量减1
                decWaiters();
            }
        }
    }
    return this;
}
```

await () 方法中使用的是就是 Java 原生关键字 `synchronized` 锁 + wait () 方法实现的，没有使用其它任何的技巧，简单唯美。

好了，到这里，DefaultPromise 的源码就分析完毕了，相比于 Java 原生的 FutureTask，DefaultPromise 的实现主要使用了大量的 synchronized 关键字锁来实现主要逻辑流的控制，虽然简单，但还是有很多知识点值得我们学习的，比如锁拆分、CAS 的使用，等等。



 ### 后记

本节，我们一起学习了 Netty 中增强的 Future，并对其主要实现类 ——DefaultPromise—— 进行了深入剖析。

看了本节的内容，你可能还是有点懵，这玩意在 Netty 中到底该如何使用呢？别急，下一节我们还会见到它的身影。

下一节，我们将对 Netty 中的线程池做一个深入的剖析，你准备好了吗？



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f34a8740001138717122976.png)







<div style="page-break-after:always;"></div>

 ## 26 Netty的线程池有什么样的特性


![img](https://img4.sycdn.imooc.com/5f0596700001ae4706400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)立志是事业的大门，工作是登堂入室的旅程。——巴斯德![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了 Netty 对 Java 原生 Future 的增强，并剖析了其中一个主要实现类 ——DefaultPromise，当时，我们说，Promise 主要是运用在线程池中，它必须绑定一个线程一起运行才有意义。

那么，Netty 中的线程池又是怎样的呢？为什么 Java 原生线程池无法适用于 Netty 的使用场景呢？Netty 又对线程池做了哪些改进呢？

让我们带着这些问题进入今天的学习吧。



 ### Java 原生线程池

在正式讲解 Netty 线程池之前，同样地，我们先回顾一下 Java 原生的线程池。
![图片描述](https://img1.sycdn.imooc.com/5f35f17a0001c19506280487.png)

Java 原生的线程池主要有三种：ThreadPoolExecutor、ScheduledThreadPoolExecutor、ForkJoinPool。

ThreadPoolExecutor 是最古老的类，我们通常说的线程池，也是指这个类。

ScheduledThreadPoolExecutor 是用来执行定时任务的线程池。

ForkJoinPool 是 Java7 新增的类，它使用的是工作窃取的算法实现的一种高效的线程池，非常适合解决大任务不断地拆成小任务，小任务再最终合并成结果的场景，比如，归并排序，等等。

> 对于这三种线程池的源码解析，可以参考文末的链接自行学习。

Java 还提供了一个工具类 Executors 专门用于生成各种不同的线程池，不过阿里巴马开发者手册中，强制禁止使用此工具类创建线程池。

你知道 Executors 可以创建哪些线程池吗？
![图片描述](https://img1.sycdn.imooc.com/5f35f19a00011f9612750718.png)

Executors 主要提供了这么六种方法用来创建线程池，当然，针对每个方法可能还有重载方法，但是，为什么阿里巴巴又禁止使用呢？看完下面的分析，你可以想想这个问题。



 #### ThreadPoolExecutor

ThreadPoolExecutor，它是我们通常所说的线程池，也是我们拿来跟 Netty 进行对比的线程池，所以，我们今天主要讲一下这个线程池。



 ##### 主要属性

我们先来看一下 ThreadPoolExecutor 的主要属性：

```java
public class ThreadPoolExecutor extends AbstractExecutorService {
    // 控制变量
    private final AtomicInteger ctl = new AtomicInteger(ctlOf(RUNNING, 0));
    // 任务队列
    private final BlockingQueue<Runnable> workQueue;
}
```

ThreadPoolExecutor 的主要属性就是这么两个：

- ctl，控制变量，高 3 位存储的是线程池的状态，这些状态有 RUNNING、SHUTDOWN、STOP、TIDYING、TERMINATED，代表了线程池的生命周期，低 29 位存储的是工作线程的数量。

  ![图片描述](https://img1.sycdn.imooc.com/5f35f1bc000174a410270186.png)

- workQueue，任务队列，它是一个阻塞队列，即在多线程环境下是安全的，我认为叫作 `taskQueue` 可能更合适。



 ##### 构造方法

我们再来看一看 ThreadPoolExecutor 的构造方法：

```java
public ThreadPoolExecutor(int corePoolSize,
                          int maximumPoolSize,
                          long keepAliveTime,
                          TimeUnit unit,
                          BlockingQueue<Runnable> workQueue,
                          ThreadFactory threadFactory,
                          RejectedExecutionHandler handler) {
    ...
}
```

面试中也经常会问到：请你说一说线程池的参数？

针对 ThreadPoolExecutor，它的构造方法一共有七个参数：

- corePoolSize，核心线程数，默认情况下，这部分线程不会被销毁
- maximumPoolSize，最大线程数，最大可以创建多少个线程
- keepAliveTime，线程保持时间，线程等待多长时间还没有任务就销毁
- unit，线程保持时间的单位
- workQueue，任务队列，存放任务的队列
- threadFactory，创建线程的工厂
- handler，拒绝策略，当线程池无法再承载更多的任务时如何拒绝



 ##### 任务流转

上面介绍了七个参数，那么，当我们提交一个任务到线程池的时候，这个任务又经历了怎样的历程呢？也就是任务的流转，这部分逻辑主要是在 execute () 方法中：

```java
public void execute(Runnable command) {
    // 判空
    if (command == null)
        throw new NullPointerException();
    
    int c = ctl.get();
    // 工作线程的数量小于核心线程数时
    if (workerCountOf(c) < corePoolSize) {
        // 添加一个工作线程
        if (addWorker(command, true))
            return;
        c = ctl.get();
    }
    // 工作线程的数量达到核心线程数时，任务入队
    if (isRunning(c) && workQueue.offer(command)) {
        int recheck = ctl.get();
        if (! isRunning(recheck) && remove(command))
            reject(command);
        else if (workerCountOf(recheck) == 0)
            addWorker(null, false);
    }
    // 任务队列满了，添加一个工作线程
    else if (!addWorker(command, false))
        // 添加工作线程失败（达到了最大线程数），执行拒绝策略
        reject(command);
}
```

任务的流转主要分为五个阶段：

- 当工作线程数小于核心线程数时，直接创建一个工作线程来执行任务；
- 当工作线程数达到核心线程数时，尝试入队，入队成功则进入任务队列中，等待被执行；
- 如果入队失败，表示队列满了，则尝试创建一个工作线程来执行任务；
- 如果创建工作线程失败，则执行拒绝策略；
- 对于在任务队列中等待的任务，待有空闲线程时，它们会从队列中被提取出来执行。

让我们用一张图来描述这整个过程：
![图片描述](https://img1.sycdn.imooc.com/5f35f1e20001f57607170776.png)

通过代码，可以看到，在 execute () 的方法中，只涉及到了 3 个参数，另外四个是在哪里使用的呢？

- maximuPoolSize，最大线程数，这个是在 addWorker () 方法中使用到的，如果达到了最大线程数，则会创建失败；
- threadFactory，线程工厂，这个也是在 addWorker () 方法中，具体点是在 new Worker () 的构造方法中，用来创建一个线程与 Worker 对象进行绑定；
- keepAliveTime 和 unit，线程保持时间，这一对参数是在 getTask () 方法中，表示从任务队列中取任务时，阻塞多长时间没有取到任务则结束阻塞，此时返回的任务为 null，工作线程会自然消亡。

从任务的流转过程来看，似乎很完美，但是，这个线程池有什么缺陷呢？



 ##### 缺点

其实，对于我们日常的工作来说，Java 原生的线程池对于我们来说已经足够完美，但是，对于追求高性能的 Netty 看来，性能这块还是有点欠缺啊。

这里说的性能主要体现在任务队列的设计上，我们想像一下，当线程数量特别多的时候，多个线程都去竞争这一个队列，势必会导致性能的下降。

那么，有没有更好的设计呢？有，ForkJoinPool，它使用工作窃取的算法，将队列分成了全局队列和线程私有队列，总体性能有了很大的提高。

但是，Netty 的场景似乎又不太一样，它特殊在哪里呢？让我们一起进入 Netty 的世界探寻它的线程池吧。



 ### Netty 线程池

Netty 线程池，是对 Java 原生线程池的一种增强，它的实现方式与 Java 原生线程池完全不一样，它的实现方式更适用于 Netty 的场景 —— 事件循环机制，所以，它的线程池又叫作事件循环线程池，即 EventLoopGroup。

同样地，对于 Netty 线程池的分析，我们也遵循从宏观到微观的分析方法。



 #### 继承体系

![图片描述](https://img1.sycdn.imooc.com/5f35f21400010b2d10550813.png)

我们可以把这个图分为上下两部分，上半部分是 Java 原生的接口，包括线程池的接口以及迭代器的接口，下半部分是 Netty 扩展的接口。

Netty 主要扩展了两层接口：

- 第一层是 EventExecutorGroup，它扩展了 Java 原生的 ScheduledExecutorService 接口和 Iterable 接口，说明它同时具有定时执行任务的能力，以及迭代的能力，是不是很奇怪，它迭代的是什么？对于 EventExecutorGroup，目前，它只有一个纯的实现类 DefaultEventExecutorGroup，而且还没有被使用到。
- 第二层是 EventLoopGroup，它扩展了 EventExecutorGroup，同时，它添加了一些跟 Channel 绑定的方法，说明它是一个跟网络请求息息相关的接口，目前，Netty 中使用的都是基于 EventLoopGroup 的线程池。

既然，目前，Netty 都没有使用到只跟 EventExecutorGroup 相关的实现类，那么，把 EventExecutorGroup 和 EventLoopGroup 合并行不行呢？其实，也是可以的，不过，这样就破坏了接口隔离的原则，而且，对于以后的扩展也是不友好的，比如，在后面的版本中，就是需要某种线程池，它不是处理网络请求的，这时候我们只要实现 EventExecutorGroup 就可以了，而不再需要实现 EventLoopGroup。

同样地，针对这两层线程池的接口，Netty 也扩展出了两个工作线程的接口：
![图片描述](https://img1.sycdn.imooc.com/5f35f226000195c208750987.png)

从图中可以看到，这两个工作线程的接口就是 EventExecutor 和 EventLoop，它们类似于 Java 原生线程池中的 Worker，它们本身不是线程，但是，它们维护了一个线程用来执行任务。

不过，你可能也发现了，EventExecutor 竟然继承自 EventExecutorGroup，且 EventLoop 继承自 EventLoopGroup，为什么设计得如此复杂呢？

那是因为，在 Netty 看来，EventExecutor 它就是一种特殊的 EventExecutorGroup，可以理解成，它是只包含一个线程的线程池，所以，在 Netty 中，你可以把任何 EventExecutor 的实现当作单线程的线程池使用，类似于 Executors 工具类提供 newSingleThreadExecutor () 方法，同样地，EventLoop 也是一样的道理。



 #### 调试用例

从继承体系中，我们想找到蛛丝马迹来编写调试用例是不太容易的，此时，我们打开 EventLoop 和 EventLoopGroup 的实现类，会发现，除了 DefaultEventLoop 和 DefaultEventLoopGroup，其它的实现类都是跟 Channel 强相关的，里面都是为了处理 Channel 的 IO 事件，其实，它们也正是为了不同平台而编写的多路利用的事件处理器。如果一上来就看这些类，我们势必要迷失在 Netty 的线程池中而不能自拔，所以，我们选择足够简单的 DefaultEventLoop 和 DefaultEventLoopGroup 来作为我们的研究对象，编写调试用例。

既然，它就是线程池，那我们就按线程池的写法来写调试用例就好了，下面是我写的调试用例：

```java
public class DefaultEventLoopGroupTest {
    public static void main(String[] args) {
        DefaultEventLoopGroup eventLoopGroup = new DefaultEventLoopGroup(5);

        for (int i = 0; i < 10; i++) {
            eventLoopGroup.execute(() -> {
                System.out.println("thread: " + Thread.currentThread().getName());
            });
        }
    }
}
```

是不是很简单？我们定义了固定数量为 5 的线程池，然后，用它执行 10 条任务。



 #### 源码剖析



 ##### 创建 DefaultEventLoopGroup

让我们来看这段代码的运行逻辑，在创建 DefaultEventLoopGroup 的位置打一个断点，跟踪进去：

```java
public DefaultEventLoopGroup(int nThreads) {
    this(nThreads, (ThreadFactory) null);
}
// 省略中间的构造方法
protected MultithreadEventExecutorGroup(int nThreads, Executor executor,
                                        EventExecutorChooserFactory chooserFactory, Object... args) {
    if (nThreads <= 0) {
        throw new IllegalArgumentException(String.format("nThreads: %d (expected: > 0)", nThreads));
    }

    if (executor == null) {
        // key1，使用了一个叫作ThreadPerTaskExecutor
        executor = new ThreadPerTaskExecutor(newDefaultThreadFactory());
    }
    // 初始化工作线程数组
    children = new EventExecutor[nThreads];

    for (int i = 0; i < nThreads; i ++) {
        boolean success = false;
        try {
            // key2，创建工作线程
            children[i] = newChild(executor, args);
            success = true;
        } catch (Exception e) {
            throw new IllegalStateException("failed to create a child event loop", e);
        } finally {
            if (!success) {
                // 创建失败的处理，相当于回滚
                // 省略这部分代码
            }
        }
    }

    // key3，创建选择器
    chooser = chooserFactory.newChooser(children);

    // 省略其它代码
}
```

在构造方法中，主要是初始化一些属性，这里有三个比较重要的点：

1. 在 key1 处创建一个 ThreadPerTaskExecutor，并在创建 key2 处创建工作线程的时候当作参数传进去了，这个 ThreadPerTaskExecutor 是什么，它的作用是什么？
2. key2 处的 EventExecutor 是如何创建的？
3. key3 处的选择器的作用是什么？

我们先说第三点吧，这个选择器是什么呢？其实，它是 DefaultEventLoopGroup 用来选择哪一个 DefaultEventLoop 来执行任务时使用的，在 Netty 内部，有两种选择器，分别为 `PowerOfTwoEventExecutorChooser` 和 `GenericEventExecutorChooser`，它们本质上来说没有什么区别，主要的区别在于如果数量为 2 的 N 次方，会使用 PowerOfTwoEventExecutorChooser 按 `&` 操作来计算下一个 EventExecutor，而 GenericEventExecutorChooser 则按 `%` 运算来计算下一个 EventExecutor，本质上都是取模运算，显然直接使用 `&` 操作效率更高一些，这是 Netty 优化到极致的一个表现：

```java
private static final class PowerOfTwoEventExecutorChooser implements EventExecutorChooser {
    private final AtomicInteger idx = new AtomicInteger();
    private final EventExecutor[] executors;
    @Override
    public EventExecutor next() {
        // &操作，减法操作优先级高于&操作
        // 轮询地获取EventExecutor（DefaultEventLoop）
        return executors[idx.getAndIncrement() & executors.length - 1];
    }
}

private static final class GenericEventExecutorChooser implements EventExecutorChooser {
    private final AtomicInteger idx = new AtomicInteger();
    private final EventExecutor[] executors;
    // &操作
    @Override
    public EventExecutor next() {
        return executors[Math.abs(idx.getAndIncrement() % executors.length)];
    }
}
```

好了，我们再回头看第一点，ThreadPerTaskExecutor，从名字看表示每个任务一个线程的执行器，请看它的真面目：

```java
public final class ThreadPerTaskExecutor implements Executor {
    private final ThreadFactory threadFactory;

    public ThreadPerTaskExecutor(ThreadFactory threadFactory) {
        this.threadFactory = ObjectUtil.checkNotNull(threadFactory, "threadFactory");
    }

    @Override
    public void execute(Runnable command) {
        // 使用线程工厂创建一个线程并启动这个线程
        threadFactory.newThread(command).start();
    }
}
```

这个类非常简单，只有一个 execute () 方法，在被调用的时候使用线程工厂创建一个线程并启动这个线程，所以，它有一个问题，就是 execute () 方法每被调用一次就创建一个线程，这也是它的名字的由来，来一个任务创建一个线程。

好了，我们接着看第二点，EventExecutor 是如何被创建的，这里是调用了 newChild () 的方法，这个方法实际上是位于 DefaultEventLoopGroup 中：

```java
// io.netty.channel.DefaultEventLoopGroup#newChild
@Override
protected EventLoop newChild(Executor executor, Object... args) throws Exception {
    return new DefaultEventLoop(this, executor);
}
// 省略中间的构造方法
protected SingleThreadEventExecutor(EventExecutorGroup parent, Executor executor,
                                    boolean addTaskWakesUp, int maxPendingTasks,
                                    RejectedExecutionHandler rejectedHandler) {
    super(parent);
    this.addTaskWakesUp = addTaskWakesUp;
    this.maxPendingTasks = Math.max(16, maxPendingTasks);
    // key1, 包装了一下传进来的ThreadPerTaskExecutor
    // 注意第二个参数
    this.executor = ThreadExecutorMap.apply(executor, this);
    // key2, 任务队列，默认使用的是LinkedBlockingQueue
    taskQueue = newTaskQueue(this.maxPendingTasks);
    // 拒绝策略
    rejectedExecutionHandler = ObjectUtil.checkNotNull(rejectedHandler, "rejectedHandler");
}
// 创建任务队列（默认的），子类可重写此方法
protected Queue<Runnable> newTaskQueue(int maxPendingTasks) {
    return new LinkedBlockingQueue<Runnable>(maxPendingTasks);
}
```

这段代码，最终，创建了一个 DefaultEventLoop，且这个 DefaultEventLoop 绑定了一个 executor 和一个任务队列，请注意这里的包含的信息：

1. executor，它是被包装之后的 ThreadPerTaskExecutor，如果被多次执行，那就会创建多个线程，所以，这个 executor 是不是只能执行一次 execute () 方法呢？
2. taskQueue，这个 DefaultEventLoop 包含一个任务队列，如果上面的 1 成立，也就是说一个 DefaultEventLoop 只有一个线程，那这个任务队列就是这个线程独享的，所以，它的出队操作不存在竞争，还记得我们前面介绍的多生产者单消费者队列 ——MpscArrayQueue 吗？

我们先卖个关子，直接看任务的执行流程。



 ##### 任务的执行流程

待上面的 DefaultEventLoopGroup 创建完毕后，程序又回到的 main () 方法中，我们在任务执行的地方跟踪进去，请注意每个方法的类名：

```java
// io.netty.util.concurrent.AbstractEventExecutorGroup#execute
@Override
public void execute(Runnable command) {
    // 调用选择器选择一个DefaultEventLoop
    // 根据上面选择器的源码，可知，使用的是轮询方式
    next().execute(command);
}
// io.netty.util.concurrent.SingleThreadEventExecutor#execute
@Override
public void execute(Runnable task) {
    ObjectUtil.checkNotNull(task, "task");
    // 调用下面的私有方法
    execute(task, !(task instanceof LazyRunnable) && wakesUpForTask(task));
}
// io.netty.util.concurrent.SingleThreadEventExecutor#execute
private void execute(Runnable task, boolean immediate) {
    // 当前线程是main，所以不在eventLoop中
    boolean inEventLoop = inEventLoop();
    // 添加任务到当前这个DefaultEventLoop的任务队列中
    // 如果添加失败会执行拒绝策略
    addTask(task);
    // 非不在，所以进入条件
    if (!inEventLoop) {
        // 启动线程
        startThread();
        // 省略其它代码
    }

}
```

到这里还很好理解，先把任务扔到一个队列中，再启动一个线程来运行它，关键是这个线程是如何启动的，继续跟踪到 startThread () 方法中：

```java
// io.netty.util.concurrent.SingleThreadEventExecutor#startThread
private void startThread() {
    // 如果当前DefaultEventLoop的状态是未启动，才执行下面的内容
    // 也就是说对于一个DefaultEventLoop来说，这个判断下方的内容只会执行一次
    // 也就是说一个DefaultEventLoop只会创建一个线程！
    if (state == ST_NOT_STARTED) {
        // 原子更新状态变量，又使用到了前面介绍过的AtomicIntegerFieldUpdater这种方式
        if (STATE_UPDATER.compareAndSet(this, ST_NOT_STARTED, ST_STARTED)) {
            boolean success = false;
            try {
                // 又一层调用
                doStartThread();
                success = true;
            } finally {
                if (!success) {
                    STATE_UPDATER.compareAndSet(this, ST_STARTED, ST_NOT_STARTED);
                }
            }
        }
    }
}
```

好了，到这里大致的逻辑已经很清晰了，通过上面的注释，一个 DefaultEventLoop 不管执行多少次任务，只会启动一个线程，我们再接着看 doStartThread () 的内部逻辑，这个方法有七八十行，我把干扰代码都删除了：

```java
// io.netty.util.concurrent.SingleThreadEventExecutor#doStartThread
private void doStartThread() {
    assert thread == null;
    // 这个executor是什么？
    // 它就是上面我们没介绍的被包装之后的ThreadPerTaskExecutor
    executor.execute(new Runnable() {
        @Override
        public void run() {
            try {
                // SingleThreadEventExecutor.this表示的是DefaultEventLoop对象
                // 所以，会调用到DefaultEventLoop的run()方法
                SingleThreadEventExecutor.this.run();
                success = true;
            } catch (Throwable t) {
            } finally {
            }
        }
    });
}
```

好烦啊，这里又把任务包装了一层，然后，调用了被包装之后的 ThreadPerTaskExecutor 的 execute () 方法，好了，下面就是揭开这个包装类真面目的时候了，上面 execute () 方法指向的是下面我加了标记的那行：

```java
public final class ThreadExecutorMap {
    // 一个FastThreadLocal，存储着一个EventExecutor
    private static final FastThreadLocal<EventExecutor> mappings = new FastThreadLocal<EventExecutor>();
    // 第一个参数是ThreadPerTaskExecutor
    // 第二个参数是DefaultEventLoop
    public static Executor apply(final Executor executor, final EventExecutor eventExecutor) {
        ObjectUtil.checkNotNull(executor, "executor");
        ObjectUtil.checkNotNull(eventExecutor, "eventExecutor");
        // 返回一个Executor的匿名对象
        return new Executor() {
            @Override
            public void execute(final Runnable command) {
                // ***************这行****************
                // 调用下面的apply
                // 这个executor就是真正的ThreadPerTaskExecutor了
                executor.execute(apply(command, eventExecutor));
            }
        };
    }
    // 第一个参数是任务
    // 第二个参数是DefaultEventLoop
    public static Runnable apply(final Runnable command, final EventExecutor eventExecutor) {
        ObjectUtil.checkNotNull(command, "command");
        ObjectUtil.checkNotNull(eventExecutor, "eventExecutor");
        return new Runnable() {
            @Override
            public void run() {
                // 设置DefaultEventLoop到FastThreadLocal中
                // 这样任务执行的过程中，都可以随时获取到这个DefaultEventLoop
                setCurrentEventExecutor(eventExecutor);
                try {
                    command.run();
                } finally {
                    // 执行完了移除
                    setCurrentEventExecutor(null);
                }
            }
        };
    }
    private static void setCurrentEventExecutor(EventExecutor executor) {
        mappings.set(executor);
    }
}
```

这里不管是对 ThreadPerTaskExecutor 的包装还是对任务的包装，都是为了找个地方把 DefaultEventLoop 存储到线程本地变量中去，以便任务在执行的过程中随时可以使用 DefaultEventLoop。

好了，程序接着走就到 ThreadPerTaskExecutor 的 execute () 方法中了：

```java
// io.netty.util.concurrent.ThreadPerTaskExecutor#execute
@Override
public void execute(Runnable command) {
    threadFactory.newThread(command).start();
}
```

这里就调用线程工厂创建一个线程了，当然，这个线程自然是 FastThreadLocalThread，然后，启动这个线程。

此时，这个任务已经被包装了 N 层了，所以，在跳过这行之前，先在 main () 方法中任务内部打一个断点，即下面的 System.out.println () 处：

```java
public class DefaultEventLoopGroupTest {
    public static void main(String[] args) {
        DefaultEventLoopGroup eventLoopGroup = new DefaultEventLoopGroup(5);

        for (int i = 0; i < 10; i++) {
            eventLoopGroup.execute(() -> {
                System.out.println("thread: " + Thread.currentThread().getName());
            });
        }
    }
}
```

然后，按 F9 就行了，因为到目前为止我们还在 main 线程中，而任务已经扔到队列中了，线程马上也要启动了，按完 F9，断点自然就停在了上面这个断点处，我们看看调用栈：
![图片描述](https://img1.sycdn.imooc.com/5f35f2420001a6c208060171.png)

图中，1 的位置即上面断点处，2 是没有分析到的地方，3、4 是已经分析过的地方，5 是在 FastTheadLocalThread 那章分析过的，6 是 Thread 的 run () 方法。好了，我们来看看 2 处的代码：

```java
// io.netty.channel.DefaultEventLoop#run
@Override
protected void run() {
    for (;;) {
        // 从队列中取任务
        Runnable task = takeTask();
        if (task != null) {
            // 执行任务
            task.run();
            updateLastExecutionTime();
        }

        if (confirmShutdown()) {
            break;
        }
    }
}
```

这个 run () 方法位于 DefaultEventLoop 中，可以看到，这是一个死循环，不断地从任务队列中取任务，然后执行，一直重复着这个动作。

结合我们前面的分析，一个 DefaultEventLoop 只会启动一个线程，而这个 DefaultEventLoop 又有自己专属的队列，所以，我们很容易就可以得出下面的线程模型：
![图片描述](https://img1.sycdn.imooc.com/5f35f25500010ad710270584.png)

在这个图中，我加入了 Provider 的概念，它就是任务的生产者，生产者可以有多个，所以，这就衍生出了一种多生产单消费者的任务队列，根据我们前面的学习，把这里的任务队列直接换成 MPSC 家族的队列是不是就能极大地提高效率呢？

没错，你可以看看 NioEventLoop 中重写的 newTaskQueue () 方法：

```java
// io.netty.channel.nio.NioEventLoop#newTaskQueue(int)
@Override
protected Queue<Runnable> newTaskQueue(int maxPendingTasks) {
    return newTaskQueue0(maxPendingTasks);
}
private static Queue<Runnable> newTaskQueue0(int maxPendingTasks) {
    return maxPendingTasks == Integer.MAX_VALUE ? PlatformDependent.<Runnable>newMpscQueue()
        : PlatformDependent.<Runnable>newMpscQueue(maxPendingTasks);
}
```

但是，这种线程模型有个致命的缺陷 —— 千万不要在任务中执行耗时的操作，否则这个线程对应的任务队列中的任务将全部都会处于排队状态，即使整个线程池中有其它空闲的线程，它们也不会从不是自己的任务队列中挪任务过来执行。关于这一点，你可以使用下面的例子证明：

```java
public class DefaultEventLoopGroupTest {
    public static void main(String[] args) {
        DefaultEventLoopGroup eventLoopGroup = new DefaultEventLoopGroup(2);

        for (int i = 0; i < 10; i++) {
            if (i%2 == 0) {
                eventLoopGroup.execute(() -> {
                    System.out.println("thread: " + Thread.currentThread().getName());
                });
            } else {
                eventLoopGroup.execute(() -> {
                    LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(1));
                    System.out.println("thread: " + Thread.currentThread().getName());
                });
            }
        }
    }
}
```

运行此程序，你会发现，一号线程早早地就执行完毕了所有 5 个任务，而二号线程则是 1 秒执行一个任务，一号线程是不会借二号线程的任务执行的，这也是 Netty 线程池与 ForkJoinPool 线程池的最大区别。

不过，这都不是个问题，Netty 线程池这样设计的目的也不是给我们的耗时业务使用的，如果有耗时的业务逻辑处理，请使用自定义的线程池进行处理，千万不要使用 Netty 的线程池。

好了，到这里，关于 Netty 的线程基本上就分析完毕了，有了这节的基础，相信你去看 NioEventLoop 的代码一定也会非常轻松的 ^^



 ### 后记

本节，我们从宏观和微观两个层面深入剖析了 Netty 的线程池，我们一定要记住一点：Netty 的线程池中坚决不允许执行耗时操作。

随着本节内容的结束，所有源码的分析就到这里了，但是，这只是一个起点，有了关于 ByteBuf、内存池、对象池、FastThreadLocal、MpscArrayQueue、Future、线程池的这些源码分析，我希望你可以回过头再把服务启动过程、数据接收写出过程的源码再仔细分析一遍，这样才能真正地达到从源码级别理解 Netty。

从下一节开始，我们将进入实战课程，在实战课程中，我将通过一个游戏项目，带你手把手地写一个服务端 Netty 应用程序，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f35f26a0001244018722028.png)




<div style="page-break-after:always;"></div>

 # 第 4 章 项目实战

 ## 27 软件开发的基本步骤，无套路不欢


![img](https://img4.sycdn.imooc.com/5f05967b0001481006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)劳动是一切知识的源泉。——陶铸![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

在前面的章节中，我们一起学习了 Netty 的发展历程，熟悉了它的核心组件，并从源码级别对它做了完整的剖析，通过这些学习，我们发现，Netty 确实做的很不错，不管是性能、效率，还是易用性，甚至是可学习性，它都做得很完美，将简单化做到了极致。

这里我们提到了易用性，前面也见识过了 Netty 的基本使用案例，确实非常简单，那么，在互联网级应用中，Netty 是否还是这么简单易用呢？

从本节开始，我将以游戏为背景介绍 Netty 是如何在互联网应用中落地的，但是，在正式介绍实战项目之前，我想先介绍一下软件开发的基本步骤，或者说是套路。



 ### 软件开发的基本步骤

在学校有学过软件设计或者系统设计的同学，对于软件开发的基本步骤都比较了解，不过，我想根据实际的情况对学校教过的知识再做一些补充，使这个体系更加完整健壮。
![图片描述](https://img1.sycdn.imooc.com/5f39e0950001050810320316.png)

上面这张图涵盖了从 产品 -> 研发 -> 测试 -> 运维 的整个产品开发周期的全图谱，这也是目前互联网公司软件开发的基本步骤，作为系统架构师，需要对每一个环节进行把关，才能做出健壮的产品。



 #### 需求分析

对于需求分析，我将它分成三个部分：

1. 需求收集
2. 详细分析
3. 可行性分析

首先，在当前的互联网环境下，基本上能想到的产品都有人做过了，而且，很多公司已经帮我们培养好了用户习惯，所以，需求收集，简单来说，就是看看竞品是怎么做的，直接抄是最方便的，这也是很多研发同学吐槽产品经理的地方，但是，事实就是如此。比如，老板让你做一个类似阿里云的东西，难道你真的傻傻地在脑海中构造一幅蓝图？

当然，收集的需求不仅仅包括业务侧需求，还应该包括研发侧需求，在很多公司，第一个版本急于上线，会落下很多研发债务，这部分债务在后期也是需要通过研发经理转换为研发侧需求的，比如性能测试、安全整改等。

对于收集到的需求，下一步就是进行需求的详细分析，哪些需求是有意义的，哪些需求是锦上添花的，哪些需求是可有可无的，这一块光靠产品经理可能就无法想全面了，这时候就需要架构师出马，对于产品收集的需求进行详细的分析，并给出合理的建议。

经过第二步，可能砍掉了一些不合理的需求，但是，不想当将军的研发不是好研发，所以，最后一步，一定要站在老板的角度想问题，也就是可行性分析，研发关注的是实现需求和个人成长，而老板关心的永远只有一个字 —— 钱，所以，可行性分析最重要的点就是能不能带来收益，能带来多少收益，投入产出比是多少，只有当产出大于投入时，这才是一条好的需求，才是值得做的。



 #### 系统设计

经过了需求分析，拿到了完整的需求，架构师就要开始做系统设计了，通常来说，架构师会从下面几个方面来做系统设计：

1. 技术选型；
2. 领域模型设计；
3. 接口设计；
4. 部署架构设计；

首先，技术选型，对于大部分互联网公司，做的产品都是基于 RESTful 的应用，所以，一般都会选择 springboot 或者 springcloud 作为他们的后端架构，但是，对于游戏或者证券类的应用，因为需要实时刷新，此时，再使用 spring 家族的技术就很难做到了，对于这部分应用，如果后端是 Java 的话，我是非常建议使用 Netty 的。

对于 Netty 应用，我想在技术选型这里再扩展几个点：

1. 网络协议选型；
2. 数据协议设计；
3. 编解码设计；

网络协议选型，是基于 Http，还是基于 TCP，还是基于 WebSocket，亦或者是 UDP？如果有自己的 APP 端，使用 Socket 没问题，如果后面又要做小程序呢，又要做 Web 应用呢？所以，通常的做法，我建议使用 WebSocket，这样不管后面增加多少种前端，后端的网络协议基本不需要修改。

数据协议设计，有没有比较通用的数据协议设计呢？从大的方面来说，有，现在比较流行的做法基本上都是分成请求头和请求体，从小的方面来说，又没有，因为具体的字段还是要根据业务场景来定义，比如，对于游戏场景，为了保证消息的时序性，我们一般会添加类似 requestId 或者 sequenceId 的字段。

编解码设计，这一块就是我们前面介绍过的内容了，对于编解码，通常分为协议层的编解码（一次编解码）和 Java 对象的编解码（二次编解码，序列化），协议层的编解码，我们通常采用 长度 + 内容 的方式，对于 Java 对象的编解码，一般可以选择 JSON 或者 Protobuf，不过，对于游戏，我们通常还是会选择 Protobuf 的。

好了，对于技术选型这一块我们就先说这么多，选好了技术，下一步就是根据业务来做领域模型的设计了。

领域模型设计，通常也叫作数据库设计或者数据结构设计，简单点讲，就是把业务抽象成 Java 可以操作的对象，这些对象有可能会存储在数据库中，如果是基于领域模型设计的话，它们还会有一些行为（方法），不过，现在大部分的场景都是使用的 MVC 设计，行为逐渐被抽离到了 Service 层。

领域模型设计好了，就轮到接口设计了，通常来说，架构师是不会干接口设计这个活的，因为实在太多了，对于一个正常的系统来说，基本上都会有几百个接口，如果都依赖架构师来设计，就太延误工期了，所以，通常来说，架构师会分好模块，扔给下面的研发人员来设计，再收集上来，大概看一遍，没问题即可。

最后，就是部署架构设计了，这一块也是架构师需要提前想好的，是单机，还是多机，还是微服务，当然，这一块也会跟第一部分的技术选型有一定的关系。对于现在的大部分互联网应用来说，通常设计成服务无状态即可，这样如果一个节点无法支撑业务量，加一个节点就行了，非常简单，但是，对于游戏应用来说，情况就不太一样了，游戏为了追求性能，很多数据是存储在内存中的，所以，它是有状态的，这样又该如何扩展呢？这个问题，我们后面详细聊。



 #### 系统实现

系统设计完，就可以着手实现了，其实，在接口设计完就可以实现了，这一步没啥好说的，就是 coding、coding、再 coding，但是，对于我们本次的游戏实战项目呢，我想分成下面几个点来实现：

1. 协议实现，双端打通；
2. 领域模型实现；
3. 业务逻辑实现；
4. 客户端 Mock 实现；

服务端、客户端实现，是指实现服务端、客户端的框架实现，使得他们可以正常的通信，能够收到互相请求的内容等。

业务逻辑实现，把主要逻辑都实现了，在上面框架的基础上实现。

客户端 Mock 实现，因为本次课程我们主要的关注点还是服务端，所以，需要做一个 Mock 客户端来与服务端进行通信，当然，这个客户端很简单，使用命令行即可。



 #### 系统测试

系统测试，分成很多种，比如单元测试、冒烟测试、接口测试、功能测试、性能测试、白盒测试、黑盒测试、研发自测等，一般来说，研发需要编写单元测试用例、冒烟测试用例等，专门的测试人员要做接口测试、性能测试、冒烟测试等，在国内，大部分企业对测试这块的要求都不是很高，特别是小型互联网企业，可能更大一部分是依赖于专门的测试人员，我认为这是不完全正确的，作为一名合格的研发人员，一定要保证自己手中出去的东西是经过自测可用的。

在本次的实战项目中，我们会通过 Mock 客户端的方式进行自测。



 #### 系统上线

经过完整的系统测试，终于可以上线了，直接扔给运维吧？那你就错了，上线也是每一个后端成员特别是研发经理应该关注的事情，生产环境 JVM 参数如何配置？CPU 多少？堆内存多少？堆外内存多少？预估业务量多少？应急预案是什么？这些都是跟上线息息相关的问题，只有做到了深入理解，才能安心睡觉。在系统上线完成后，产品还要基于生产做验收等。

不过，在本次的实战项目中，我们也不需要上线，所以，也不会涉及过多关于系统上线的问题。



 #### 系统迭代

系统上线了，终于可以歇息了，那你就错了，产品还有源源不断的需求过来，急手急脚地上线，会产生大量的研发债务，这些债务又会转化成研发需求，同时，可能还有生产问题，甚至于，老板要找你看报表，这些都会转化成新一轮的需求，进入下一次迭代。

不过，对于本次的实战项目，我们并不关心产品需求，我们关心的只有研发债务以及老板的报表，所以，我在实战项目之后还安排了实战调优等着你哟 ^^



 ### 后记

本节，我们从软件开发的基本步骤出发，介绍了整个软件开发的生命周期，同时，对于每一个点，也结合了我多年的工作经验，对它们做了一些扩展。

在本次的实战项目中，除了个别步骤不会执行外，我们基本上会按照这个步骤，来实现我们的实战项目。

下一节，我们就从需求分析阶段入手，详细介绍本次实战项目的具体内容。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f39e0b00001383f12051828.png)





<div style="page-break-after:always;"></div>

 ## 28 需求分析，能砍则砍，最小化闭环


![img](https://img3.sycdn.imooc.com/5f0596af00018a2006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才就是长期劳动的结果。——牛顿![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了软件开发的基本步骤，并结合我多年的工作经验做了一些补充和说明。

本节，我们就运用上一节学习到的知识，从需求分析的角度详细介绍我们实战项目做什么。



 ### 实战选题

其实，当初在考虑使用什么选题作为 Netty 的实战项目的时候，我是很纠结的。

使用 Netty 写一个 RPC 框架？

使用 Netty 做一个 Http 服务？

使用 Netty 做一个游戏？

使用 Netty 做一个连接池？

使用 Netty 做一个异步的 Http Client？

使用 Netty 做一个 IM 聊天软件？

这些选题，我统统考虑过，而且有些东西我还真的写过，最终，我决定使用 Netty 做一个游戏，那么，我为什么选择做一个游戏呢？

我想先分析我不选择其它种类的原因：

1. RPC 框架，有很经典的 Dubbo 框架了；
2. Http 服务，有刚出世不久的 Spring WebFlux 或者 Spring Cloud Gateway 了；
3. 连接池，有 Redis 非常好用的 Lettuce 或者 Redisson 了；
4. 异步 Http Client，有 async-http-client 了；
5. IM 聊天软件，某度一搜一大把；

基于以上原因，我决定不选择它们来作为实战项目，但是，我为什么敢选择游戏呢？

因为，我就是做棋牌游戏出身的，我对棋牌游戏这种基于房间制的游戏的架构设计和业务处理非常熟悉，我有信心把这个实战项目讲好讲深，甚至很多细节我也会讲到位，而且，我相信很多同学对游戏编程可能会非常感兴趣，就像当初的我一样，所以，最终，我选择了棋牌游戏作为本次课程的实战项目。

> 这里有个词叫作 “房间制”，它是什么意思呢？
>
> 房间制，通俗一点解释，就是把几个玩家关到一个房间里，他们的游戏范围只限于这个房间，不会涉及到其它房间。常见的房间制游戏有，棋牌游戏，王者荣耀，等等，另外，像一些大型网游，其实也可以看作是房间制，只不过它们这个房间比较特殊，变成了地图，这一个一个的地图就相当于是房间。针对这种房间制的游戏的架构设计，基本的套路都是一样的，至于这个套路是什么，我们后面再详细说明。

说起棋牌游戏，你一定会想到一位资深玩家 —— 发哥，想当年，发哥就已经是王者级别的玩家了，现在的段位，应该是 —— 最强王者，哦不，是神级玩家。

但是，棋牌，棋牌，可不是只有牌类游戏哦，它还包含大量的棋类游戏，比如象棋、军棋、自走棋等等，当然，牌类也不只是扑克，还包括麻将、跑胡子等，基至于，从广义上来说，像捕鱼这种也可以算作是棋牌类的游戏。

而我们要做的实战项目，是一款叫作麻将的棋牌游戏，大家都很熟悉了。

好了，说了这么多，下面我们来详细分析一下麻将这个项目吧。



 ### 需求分析

麻将，在中国的流行可以说是非常广泛的，同时，也是非常具有地方性特色的一种游戏，每个地方的玩法可能都会有一些差异，比如四川血流成河、贵阳捉鸡、广东推倒胡等。

当然了，我们不可能完整地做一个麻将游戏出来，我们的课程是 Netty，所以，主要还是说 Netty 如何在游戏中进行使用，当然了，也不会不做一个游戏出来，我们会做一个简化版的麻将，最起码保证可以正常进行游戏。

按照上一节的理论知识，需求分析阶段应该按照 需求收集 -> 详细分析 -> 可行性分析 三个阶段来完成。



 #### 需求收集

需求收集就非常简单了，对于麻将类的游戏，最好的竞品就是腾讯的欢乐麻将了，另外，还有其他一些小厂开发的地方性特色的麻将，既然，我们要做简化版的麻将，直接拿腾讯欢乐麻将的规则来做减法就可以了。

对于腾讯欢乐麻将，我们可以直接在小程序中打开，点击 更多 -> 帮助 即可看到所有欢乐麻将的规则：
![图片描述](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsQAAA7EAZUrDhsAAAANSURBVBhXYzh8+PB/AAffA0nNPuCLAAAAAElFTkSuQmCC)

我这里就不一一截图了，我简单列举一下麻将的普适性规则：

1. 麻将一般有四个玩家，个别地方可以支持三人或者二人；
2. 麻将一副牌有这么几种牌型：万条筒（序数牌）、东南西北中发白（字牌）、春夏秋冬梅兰竹菊（花牌），共 144 张牌；
3. 二张一样的牌叫对子，三张一样牌的叫刻子，四张一样牌的叫杠，碰出去的叫明刻，手里的叫暗刻，杠别人打出的牌叫明杠，先碰再杠叫补杠，自己摸了四张一样的叫暗杠；
4. 牌局开始会进行洗牌，即打乱牌序；
5. 然后定庄，定庄的规则每个地方不太一样，最常见的掷骰子，按点数算，有的地方掷两次，有的地方掷一次；
6. 接着摸牌，线下是从庄家开始摸，每次摸两墩牌，也就是四张，轮流摸三次后，庄家跳着摸两张，其它玩家各一张，也就是初始摸牌后，庄家有 14 张牌，闲家有 13 张牌，在游戏里，我们称作发牌，发牌的规则不用这么麻烦，直接给庄家发 14 张牌，闲家发 13 张牌即可；
7. 如果发完牌庄家直接胡了，叫天胡；
8. 如果庄家打完第一张牌，闲家胡了，叫地胡；
9. 对于每一次出牌，其他玩家可能有吃、碰、杠、胡、过几种操作，这些操作一般还会有个倒计时，到时间了玩家还没有操作，服务端自动帮玩家操作，多次超时，进入托管状态；
10. 当玩家手里的牌组成了（2+3xN）（3 表示顺子或刻子）的牌型时，则表示可以胡牌了，个别地方支持七对胡；
11. 当玩家手里的牌还差一张就可以胡了的时候，叫作听牌，同时，可以听 1 到多张牌，我见过最吊的，是可以听所有牌（带癞子的玩法），像腾讯欢乐麻将做得比较好，还支持提示听什么牌；
12. 如果胡其他玩家打出的牌，打出这张牌的人叫放炮；
13. 如果胡自己摸的牌，叫自摸；
14. 如果胡别人回头杠的牌，叫抢杠；
15. 如果胡别人开杠摸牌后打的牌，叫杠上炮；
16. 如果胡自己开杠摸的牌，叫杠上开花；
17. 胡牌之后服务器计算番型并发送结算消息给玩家，玩家可以选择离场或者继续；
18. 如果有玩家离场，则等待其他玩家加入，当满足房间人数时，又开始新一轮的游戏；

普适性的规则大概是这样，不过，像血流成河、血战到底等可以无限胡牌或者带癞子的玩法，它们的规则略有出入。

然后，再看看其它竞品，可以发现，除了上面的规则外，它们很多都支持创建房间这样的制度，这样就很方便亲朋好友一起玩了。

到这里，需求收集阶段基本上差不多了，下面就进入需求分析阶段了。



 #### 详细分析

上面介绍的普适性规则，对于我们学 Netty 这门课程来说，还是太多了，所以，结合课程情况，我对这些规则做了一些裁减，裁减后的规则如下：

1. 使用创建房间的方式游戏，在创建房间时可以选择多少人参与游戏，这样，后面调试的时候会比较简单；
2. 为了方便，只保留万条筒三种序数牌，每种序数牌有 1 到 9，各四张，也就是一共 108 张牌；
3. 定庄，直接让创建房间的人为庄家；
4. 开局发牌时庄家 14 张牌，闲家 13 张牌；
5. 可碰、可杠、可胡、可过，不支持吃；
6. 不支持倒计时；
7. 不支持提示听牌；
8. 没有番型，只按最简单的底分计算输赢分数，底分在创建房间的时候传入；
9. 关于胡牌算法，是一种机密，无法透露，这里使用随机数替代；
10. 一局游戏之后直接结束，不支持继续游戏；

裁减之后的规则就比较简单了，用一张图来表示大致流程：
![图片描述](https://img1.sycdn.imooc.com/5f39e0ee0001d67a10280517.png)

当然了，我们这里写的还算比较简单的，真正的需求还会写清楚什么情况下可以碰，什么情况下明杠，什么情况下暗杠，等等，不过，我相信大家都有一定了解， 这里为了节约篇幅，就不再赘述了。



 #### 可行性分析

通过了详细分析，我们拿到了需求，那是不是就代表这个需求就具有可行性呢？显然不是，想像一下，我们平时做的多少需求都是无意义的，所以，还要进行可行性分析。

对于可行性分析，站在个人的角度，本次实战项目能够提升个人对于 Netty 的理解，能够提升个人对于游戏开发的了解，是很有意义的，所以，是可行的。站在老板的角度，这里没有老板，所以，嗯，是可行的。



 ### 后记

本节，我们从需求分析的三个阶段出发，详细介绍了本次实战项目的内容，虽然比较简单，但我相信只要遵循这个套路，在平时的工作中，你也可以对产品的需求提出合理的建议和意见，快速促成项目的落地。

下一节，我将从系统设计的角度来做好前期的架构设计，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f39e0fa0001b43509820741.png)





<div style="page-break-after:always;"></div>

 ## 29 系统设计，前期规划很重要


![img](https://img4.sycdn.imooc.com/5f0596c600012ffc06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)学习这件事不在乎有没有人教你，最重要的是在于你自己有没有觉悟和恒心。 —— 法布尔![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们从需求收集、详细分析、可行性分析三个维度对本次实战项目做了完整的需求分析，最终得出了简化版的麻将需求。

本节，基于软件开发的基本步骤，并结合上一节需求分析的结果，我们将进行系统设计，让我们进入今天的学习吧。



 ### 系统设计

根据软件开发的基本步骤，系统设计，我们将分成技术选型、领域模型设计、接口设计、部署架构设计等四个部分来完成。



 #### 技术选型

技术选型，毫无疑问，我们选择的是 Netty，但是，基于 Netty，我们还需要做一些事情来构建系统，这些事情包含网络协议选型、数据协议设计、编解码设计等。

网络协议选型，也就是说请求是通过什么方式在客户端和服务端进行通信，常用的网络协议选型有 HTTP、HTTP2、TCP、WebSocket、UDP 等，让我们来对比一下：

| 协议      | 层     | 长 / 短连接 | 基于   | 其它                                                         |
| :-------- | :----- | :---------- | :----- | :----------------------------------------------------------- |
| HTTP      | 应用层 | 短连接      | 数据流 | 使用广泛，也可支持长连接，但无法支持服务端主动通信客户端     |
| HTTP2     | 应用层 | 长连接      | 数据流 | 目前使用还不是很广泛                                         |
| WebSocket | 应用层 | 长连接      | 数据流 | HTTP 协议的升级版，可以实现长连接，使用比较广泛              |
| TCP       | 传输层 | 长连接      | 数据流 | 可靠，但数据流无界，需要自己分割，Netty 默认的协议           |
| UDP       | 传输层 | 无连接      | 报文   | 不可靠，需要自己实现可靠性保证，但基于报文，没有粘包半包的问题 |

通过对比，可以发现，HTTP 无法支持服务端主动通信客户端，对于我们是不合适的，HTTP2 虽然支持长连接，但使用还不是很广泛，WebSocket 和 TCP 比较符合我们的要求，UDP 不可靠，还得自己保证可靠性，所以，我们的首要选择在 WebSocket 和 TCP 两者之间，考虑到未来可能会做小程序或者 Web 应用，所以，选择 WebSocket 协议是最佳选择，但是，选择 WebSocket 增加了复杂度和开发成本，第一个版本，我想做的简单点，所以，我们直接使用默认的协议就好了，即 TCP。

> 这里，我想说一下 Socket，Socket 它本身不是一种协议，翻译为套接字，它是应用层和传输层之间的一个抽象层，把 TCP/IP 层的复杂操作抽象成几个简单的接口供应用层调用以实现进程在网络中的通信。从设计模式的角度来看的话，Socket 就是一种门面模式，它把复杂的 TCP/IP 协议族隐藏在 Socket 接口后面。
>
> 另外，WebSocket 与 Socket 没有任何关系，就像 JavaScript 与 Java 的关系一样，纯属借名造势而已。

数据协议设计，主要是解决两个问题：粘包半包问题和协议内容。粘包半包的问题，在前面的章节我们也讨论过，这里肯定选择的是 长度 + 内容 的方式来解决。协议内容的问题就不是那么好确定了，参考业界比较优秀的协议，比如 Dubbo 和 RocketMQ，一般来说，数据协议都会分成消息头和消息体两个部分，消息体存储真正的数据内容，消息头存储着一些扩展信息，比如版本号、请求地址（操作码、命令字）、序列化方式、自定义的扩展字段等。

根据我们的业务场景，即麻将游戏场景，在请求头里面，可以存储版本号、命令字、请求 ID 等三个信息，每个字段占用一个 int 类型，最后，我们的数据协议大概是长这样子：
![图片描述](https://img1.sycdn.imooc.com/5f39e1320001543a10300196.png)

这里，Length 我选择 2 个字节，因为根据评估，我的请求内容不会超过（2^16-1=65535）个字节。

好了，网络协议和数据协议我们都弄好了，下面就是如何编解码了。

编解码设计，根据前面的内容，我们知道，编解码分为一次编解码和二次编解码。一次编解码，是对数据协议的编解码，这个在数据协议设计里面已经处理了，就是解决粘包半包的方式，也就是 长度 + 内容 法。二次编解码，是对 Java 对象的编解码，或者换个通俗的叫法为序列化 / 反序列化方式，对于消息头，格式是固定的，我们直接从 buffer 中读取或写入就好了，对于消息体，常见的序列化方式有 XML、JSON、Java 序列化、Protobuf 等，前面的章节我们也对比过，对于游戏这种对性能要求极高的应用，选择 Protobuf 无疑是最佳选择，但是，第一个版本，我想简单点，所以，我们先选择 JSON 来作为序列化方式，同时，JSON 在易读性方面也很有优势，也便于我们调试代码。

上面，我们从网络协议、数据协议、编解码三个维度对 Netty 这种技术选型做了分析，对于任何网络应用都要经过这些步骤，可以说，是通用化的解决方案，但是，对于具体的业务场景来说，领域模型设计就比较个性化了，下面我们就来看看如何对麻将这种个性化场景做领域模型方面的设计。



 #### 领域模型设计

领域模型设计，在不同的场合，可能也会称作数据库设计，或者数据结构设计，不过，它们多多少少还是有一些区别的，同学们可以自行体会一下。

对于麻将游戏的场景，我先给出下面一段描述：

玩家 A 打开 APP，登录到游戏，选择创建四个人的房间，玩家 B、C、D 同样地打开 APP，登录到游戏，同时，选择加入到玩家 A 创建的房间，此时，房间满足四人条件，游戏自动开始，玩家 A 作为房间创建者，自动成为庄家，开始发牌，玩家 A 获得 14 张牌，玩家 B、C、D 获得 13 张牌，玩家 A 开始出牌，玩家 A 出完牌后，玩家 B、C、D 可能会进行碰、杠、胡等操作，如果没有玩家操作，轮到玩家 B 摸牌、出牌，如此往复，直到摸完所有牌或者有玩家胡牌为止，发送结算消息给所有玩家，牌局结束，玩家离场。

我们先抽出这段描述中所有的名词：玩家、APP、游戏、房间、庄家、牌、消息、牌局，然后去除一些干扰名词。
![图片描述](https://img1.sycdn.imooc.com/5f39e1700001bf3510260204.png)

还剩下玩家、房间、牌、消息这几个名词，它们只是我们寻找的领域对象，让我们来分析一下它们应该具有的属性：



 ##### 玩家

1. 玩家登录游戏需要什么？用户名和密码。
2. 玩家在游戏的时候操作的是什么？牌列表。
3. 碰、杠的牌要不要记录？要记录，补杠的时候需要看碰的牌，以后结算的时候可能会用到杠的牌，而且通常会把碰杠的牌放在玩家面前。
4. 玩家在房间内的位置要不要记录？要记录，不记录的话，每次要获取某个玩家的位置只能遍历房间中的所有玩家。
5. 玩家打出的牌要不要记录？打过线上麻将的同学应该都知道，玩家打出的牌是摆在自己面前的，所以，打出的牌也是要记录一下的。
6. 结算的时候按什么维度？暂且按积分，类似于斗地主那样，赢了加几分，输了扣几分。

所以，玩家至少应该具有 用户名、密码、牌列表、碰的记录、杠的记录、位置、打出的牌、积分等几个属性。
![图片描述](https://img1.sycdn.imooc.com/5f39e1830001402310280401.png)



 ##### 房间

1. 玩家创建房间的时候指定了什么？人数。
2. 房间要不要记录玩家信息？要，玩家列表。
3. 玩家手里的牌从哪来的？房间的桌子上摸的，所以，还需要记录牌的信息，主要是未摸的牌。
4. 房间要不要记录庄家信息？暂时不需要，庄家位置，根据需求分析，现在还用不到庄家。
5. 房间要不要记录出牌玩家的位置？要，如果不记录，客户端随便发出牌消息，服务端无法比对。
6. 房间要不要状态信息？要，没有状态的话，怎么判断房间是不是在等待玩家加入？怎么判断是不是在游戏中？怎么判断是不是当前在等待玩家出牌，还是在等待其他玩家操作（碰杠胡）？
7. 结算的时候用的分数从哪来？在创建房间的时候传进来最好。

所以，房间至少应该具有 人数、玩家列表、未摸的牌、出牌玩家的位置、状态、分数等信息。
![图片描述](https://img1.sycdn.imooc.com/5f39e1920001fead10280407.png)



 ##### 牌

1. 牌有哪些分类？万条筒，不考虑东南西北中发白、春夏秋冬梅兰竹菊的情况下。
2. 每种分类有哪些值？万条筒有 1 到 9 九种数值。

所以，关于牌，其实就这两个属性：类型和数值。
![图片描述](https://img1.sycdn.imooc.com/5f39e1a10001839d09540102.png)

因为类型只有三种，数值只有九种，所以，我们使用一个 byte 就完全可以存储了，甚至还有点浪费，但是没办法，Java 中能操纵的最小单位就是 byte 了。

因此，关于牌，我们并不需要再单独定义一个类型了，直接用 byte 就可以了，不过，为了方便操作，最好定义一个工具类专门用来处理牌相关的信息。



 ##### 消息

1. 消息是指什么？客户端与服务端之间的一次通信就是一次消息的传递过程，消息就是通信。
2. 通信又是什么？一次通信往往伴随着动作，比如，玩家登录，客户端发送登录请求给服务端，服务端处理完成响应客户端，这个过程是两次通信。
3. 动作具有什么特征？动作往往都是动词，所以，只要找上面描述中的动词就八九不离十了。
4. 动词有哪些？打开、登录、创建、加入、开始、成为庄家、发牌、获得、出牌、碰、杠、胡、操作、摸牌、发送、结束、离场。
5. 哪些动词不是客户端与服务端之间通信？打开。
6. 成为庄家是不是？成为庄家，服务端可以不给客户端发送请求，而且，我们这次的需求并没有使用到庄家，所以，暂且认为它不是。
7. 发牌是不是？发牌，发完牌之后，服务端要通知客户端哪个玩家拿了哪些牌或者多少张牌，所以，发牌可以认为是。
8. 获得是不是？同上，发完牌服务端通知客户端玩家获得了哪些牌，所以，获得也可以认为是。
9. 操作是不是？操作这个概念有点抽象，出牌、碰、杠、胡、摸牌都可以说是一种操作，所以，可以认为它是凌驾在这几个消息之上的消息，也就是抽象类的概念。
10. 发送是不是？发送本身不是消息，发送的东西才是消息，所以，发送不是。
11. 结束是不是？结束了，服务端要通知客户端，所以，结束，是。
12. 离场是不是？与结束一样，服务端要通知客户端玩家已离场。

经过上面的分析，还剩下 登录、创建、加入、开始、发牌、获得、出牌、碰、杠、胡、操作、摸牌、结束、离场。

这些消息还能不能再分类呢？

我认为可以分成三类：

1. 客户端请求服务端：登录、创建、加入。
2. 服务端通知客户端：开始、发牌、获得、结束、离场。
3. 包含以上两者，比如出牌先是服务端通知客户端，客户端玩家再出牌：出牌、碰、杠、胡、操作、摸牌。

那么，每一种分类内部还能不能再抽象呢？

我认为是可以的：

1. 开始、发牌、获得，这三者都是在游戏开始的时候服务端主动通知客户端的，而且，是通知所有客户端，所以，这三条消息，我认为可以合并成一条，我们暂且称之为游戏开局通知。
2. 结束、离场，在我们的需求中，一局游戏结束，整个房间的游戏就结束了，所以，暂且也可以把这两个消息合并成一个。
3. 出牌、碰、杠、胡、摸牌，这些消息本身就是不同的操作，所以，我们可以把操作作为父类，把这几个消息作为子类来处理，其实还有个 “过” 的操作，即询问玩家碰不碰的时候，玩家不碰。
4. 另外，每一次操作之后都应该刷新牌局信息，比如，哪张牌打出了，谁摸牌了，等等，这样做的好处是防止某个客户端网络不稳定，依赖于客户端收到出牌消息来刷新牌局可能出现错乱的情况，而这个牌局的刷新其实与游戏开局通知是一样的，都是把房间的完整信息传递给客户端，所以，这两个可以合并为房间刷新通知。
5. 最后，上面的描述最后还有一个结算消息，这也是一个单独的消息。

综上所述，最后的消息有 登录、创建、加入、结束（离场）、操作（出牌、碰、杠、胡、摸牌、过）、房间刷新通知、结算等。
![图片描述](https://img1.sycdn.imooc.com/5f39e1b200013b6e10260510.png)

到这里，领域模型设计到这里基本就完成，下面，我们再来看看接口设计。



 #### 接口设计

接口设计，一般是针对 Web 系统来说的，在 Spring MVC 中，一般是指 Controller 层的设计，这个阶段，可以在领域模型设计完毕之后，立马就开始，接口设计完成之后交给客户端，两边就可以一起开发了。

但是，我们这次的实战项目并不是 Spring MVC，接口设计在哪里呢？

其实，就是每一条消息的详细设计，在上面的领域模型设计中，我们已经归纳出了所有的消息类型，现在只需要把它们加上属性就可以了。真正意义上来说，上面的消息并不能算是领域模型设计，只是我们是第一次分析这个过程，所以，我觉得把它放在领域模型设计这一小节也是可以的，后面，我们熟悉了这个过程，可以直接把消息的设计拿到接口设计这里来。更通俗易懂地来说，在需求的描述中，名词一般就是领域模型，动词一般就是领域模型的行为，行为一般对应着接口。

好了，下面我们就来详细分析每一条消息应该具有的属性，为了方便，我们按照牌局进行的顺序来。



 ##### 登录

登录分成登录请求和登录响应，登录请求需要输入用户名和密码，登录响应返回是否登录成功，同时返回玩家的信息，登录失败还需要有相应的提示，所以，对于登录，应当分化为两条消息：
![图片描述](https://img1.sycdn.imooc.com/5f39e1c00001d80510230291.png)



 ##### 创建房间

根据上面房间的设计，应该在创建房间的时候传入人数和底分，还需要其它属性吗？

好像不需要了，需要响应吗？可以有响应，比如，服务端有检查人数和底分是否满足条件，此时，是需要给客户端一个响应告诉客户端是否创建房间成功的。
![图片描述](https://img1.sycdn.imooc.com/5f39e1d600010aa010250207.png)



 ##### 加入房间

加入房间，比较简单了，输入房间号，如果房间没满就可以加入，如果房间满了就加入失败，所以，加入房间是需要一个响应告诉客户端是否加入成功的。
![图片描述](https://img1.sycdn.imooc.com/5f39e1e400014c4010230206.png)



 ##### 房间刷新通知

房间刷新通知，顾名思义，就是将房间的信息发送给客户端，所以，直接把房间本身作为它的字段就可以了。

不过，有个问题，房间中是包含玩家信息的，每一个玩家是有牌列表的，所以，发送消息的时候要注意一下，针对不同的玩家看到的消息内容本身是不完全一样的，每个玩家都只能看到自己的牌列表，其他玩家的牌列表要隐藏起来。

那么，房间刷新通知在哪些情况下会触发呢？

1. 有个加入房间的时候；
2. 有人操作（出牌、碰、杠、胡、摸牌）的时候；

因此，还需要有个行为类型的字段，客户端拿到不同的行为类型做出不同的动画，比如，出牌就播放玩家出了一张牌的动画，摸牌就播放玩家摸了一张牌的动画。

另外，关于行为类型，除了加入房间，其它的都是牌局操作，所以，我们直接使用操作类型来表示行为类型，当没有操作类型的时候就表示为加入房间。

所以，房间刷新通知一共有两个属性：操作类型和房间。
![图片描述](https://img1.sycdn.imooc.com/5f39e1f9000124f310260105.png)



 ##### 操作消息

操作，在客户端与服务端之间是双向的，服务端首先通知客户端可以进行哪些操作（同时也要通知其他玩家），客户端操作完了，再通知回给服务端，最后，服务端再通知其他玩家，谁谁谁做了什么操作，所以，操作应当分成三种不同类型的消息：操作通知、操作请求、操作结果通知。

另外，针对不同的操作类型，需要传输的数据可能又不太一样，比如出牌通知和碰牌通知，出牌通知其他玩家是知道轮到谁出牌了的，碰牌通知其他玩家是不知道谁可以碰牌的，只有真正碰牌完毕了，其他玩家才知道，所以，这里根据不同的操作类型，又可以分化成不同的消息，比如出牌三种消息，碰牌三种消息，等等，不过，我们并不打算这么做，因为它们太像了，因为个别字段的不同就拆分成更细的消息，有点得不偿失，而且，非常不利于后期的扩展，比如，后面再加一种操作，吃，又要定义三种消息，这样就太费事了，所以，针对操作，我们一共只有三个消息，通过不同的操作类型来区分。

 ###### 操作通知

经过上面的分析，操作类型是必不可少的，但是，有一种状况需要特别关注。

试想，玩家 A 出了一张牌，玩家 B 可能既能碰，也能杠，甚至还可以胡，这种情况下要怎么通知玩家 B 呢？

有两种方案，一种是通知里面维护一个操作列表，不过有点浪费空间，另一种方案是只使用一个 int，不同的位代表不同的操作，我们知道一个 int 有 32 位，所以，可以代表 32 种不同的操作，后期扩展也方便。

除了操作类型还需要什么字段呢？

对于出牌，还需要知道通知谁出牌，所以还需要一个位置的字段。

对于碰、杠、胡，还需要知道哪张牌触发的这些操作，所以还需要一个触发的牌的字段。

综上所述，操作通知一共需要三个字段：操作类型、位置、触发的牌。
![图片描述](https://img1.sycdn.imooc.com/5f39e213000159cf10240254.png)

 ###### 操作请求

操作类型也是必不可少的，还需要其它什么字段呢？

对于出牌，服务端需要知道哪个位置出了哪张牌。

对于碰、杠、胡，服务端也是需要知道操作了哪张牌，不过服务端似乎知道是哪张牌，因为是服务端通知客户端哪张牌触发的操作，所以，服务端应该找个地方记录这张触发的牌，放在哪里比较合适呢？我认为放在房间信息中再合适不过了。

所以，操作请求一共需要两个字段：操作类型和操作的牌。
![图片描述](https://img1.sycdn.imooc.com/5f39e2260001913f10220235.png)

 ###### 操作结果通知

同样地，操作类型也是必不可少的，还需要其它什么字段呢？

其他玩家需要知道哪位玩家做了什么操作，操作的牌是什么，所以，还需要知道操作的位置以及操作的牌。
![图片描述](https://img1.sycdn.imooc.com/5f39e23f00011a8410290243.png)

好了，操作的三个消息就设计完成了，当有玩家胡的时候，游戏就该结束了，此时，应该先发送结束消息，再发送结算消息。



 ##### 结束通知

关于结束通知，也可以有两种设计，一种是与房间刷新通知放在一起，加一种结束的行为类型，同时，发送消息的时候也要注意，所有玩家的手牌都不用隐藏了，每个玩家都可以看到其他玩家的牌。不过，这样设计耦合度感觉有点高，所以，我更倾向于把结束通知单独当成一个消息进行通知。

通过上面的分析，可以知道，结束通知直接把房间的信息发送给客户端就可以了，所以，它只有一个属性：房间信息。
![图片描述](https://img1.sycdn.imooc.com/5f39e24f00016db510260127.png)



 ##### 结算通知

关于结算通知，也有两种设计，一种是服务端只通知客户端谁赢了，客户端自行计算输赢的分数，另一种是服务端全部计算后返回给客户端。像我们的这次实战案例，规则比较简单，让客户端计算输赢也是可以的，不过，如果把规则弄复杂一些，加上各种番型，让客户端计算明显就不合理了，而且，服务端怎么都要计算的，所以，选择服务端全部计算完成再返回给客户端，比较合理。

那么，结算通知需要返回哪些信息呢？

针对本次的实战案例，我们需要简单地计算每位玩家的输赢的分数，而客户端拥有完整的房间信息，所以，我们只需要每个位置的输赢分数，不需要返回每个玩家的信息了，而位置可以通过数组的下标表示，因此，结算通知只需要一个输赢分数的数组，其中下标代表玩家位置。
![图片描述](https://img1.sycdn.imooc.com/5f39e2640001233610310125.png)

OK，到此，所有消息的属性我们都已经确定下来了，也就是完成了接口设计。



 #### 部署架构设计

有了上面的设计，研发同学就可以开工了，为什么在前期还要考虑部署架构的设计呢？

因为不同的部署架构，可能对代码的架构产生巨大的影响。

就拿我们这次的实战案例来说，如果只是单机部署，那部署架构就非常简单，可以说是没有，那么，如果改成多机部署呢？是不是需要一个网关层做流量转发？这个网关该如何设计？有没有现成的开源框架可以使用？
![图片描述](https://img1.sycdn.imooc.com/5f39e2760001494710240304.png)

如果是传统的 Web 应用，我会跟你说，服务做成无状态的就可以了。

但是，我们这次做的是游戏，对于游戏应用，性能的要求非常高，所以，很多数据必须保存在本机的内存中，注意，是本机的内存中，而不是像 Redis 那种分布式缓存的内存中，因此，游戏应用的服务是不可能做成无状态的。

这时候网关就起到至关重要的作用了，对于不在牌局中的消息，玩家的请求随便分发到哪个服务都是可以的，但是，对于牌局中的消息，同一个房间所有玩家的所有消息必须分发到同一台机器的同一个 JVM，这样，这些消息才能共享内存来进行处理。但是，这样还不够快，有没有更快的方法呢？后面实现的时候我再告诉你。

当然了，对于我们本次的实战案例，暂且只考虑单机部署的情况。



 ### 后记

本节，我们从技术选型、领域模型设计、接口设计、部署架构设计等四个方面非常全面地介绍了本次实战项目的系统设计，这些内容也是一个架构师应该具备的技能，也可以说是一个比较通用的系统设计过程，同样，也可以运用的我们的工作中。

有了这么全面的设计，我相信实现起来会变得非常容易，我已经迫不及待了，你呢？



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f39e2840001e84711621768.png)





<div style="page-break-after:always;"></div>

 ## 30 协议实现，双端打通


![img](https://img2.sycdn.imooc.com/5f0596d40001606006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)上天赋予的生命，就是要为人类的繁荣和平和幸福而奉献。——松下幸之助![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们已经从技术选型、领域模型设计、接口设计、部署架构设计等各个方面将系统规划好了。

但是，没有实现的系统是不完美的，毕竟，我们不是 PPT 架构师。

本节，我们就基于系统设计来实现我们的系统，对于本次实战项目的实现，我想通过下面四个部分来讲解：

1. 协议实现，双端打通：根据技术选型的设计，将协议和编解码实现，并打通客户端和服务端，这样在编写代码的过程中随时可以进行一些简单的调试。
2. 领域模型实现：主要是参考领域模型的设计，将这些领域模型都定义好一个个的 Java 对象，同时，我也会把消息的定义也放在这一节，当然了，我们这里使用的也是贫血模型，为什么使用贫血模型呢？彼时，我会详细说明。
3. 业务逻辑实现：主要是服务端如何对这些消息进行处理，如何设计线程模型，加速服务端处理等。
4. Mock 客户端实现：编写一个 Mock 客户端，并自测，四个客户端一桌麻将，妥妥的。

为了减少一节的内容过大，我会将实现分成四个小节，分别对应上面的内容。

好了，下面正式进入今天的学习 —— 协议实现，双端打通。



 ### 协议实现

上一节，我们已经将协议规划好了，协议分为 Header 和 Body，Header 中主要存储版本号、请求 ID、命令字，这里的命令字又可以称为操作码或者序列化类型等，主要是用来反查 Body 的真正类型，对于每一条消息，它们的命令字必须保证唯一性。

因此，我们可以定义协议如下：

```java
@Data
public final class MahjongProtocol {
    /**
     * 协议头
     */
    private MahjongProtocolHeader header;
    /**
     * 协议体
     */
    private MahjongProtocolBody body;
}
@Data
public final class MahjongProtocolHeader {
    /**
     * 版本号
     */
    private int version;
    /**
     * 命令字
     */
    private int cmd;
    /**
     * 请求ID
     */
    private int reqId;
}
interface MahjongProtocolBody {
}
public interface MahjongMessage extends MahjongProtocolBody {
}
```

> Mahjong，麻将的意思。

可以看到，对于协议本身和协议头，我们定义为 final 类型，而对于协议体，我们定义为接口，协议体为什么要定义为接口呢？

其实，这里的协议体，就是我们所说的消息，所有的消息都应该实现该接口，这么做的目的是为了实现统一处理，其实，这是运用了多态的思想。

为了从命名上更直观，我又定义了一个接口 `MahjongMessage` 继承自 `MahjongProtocolBody`，这样所有的消息都实现自 `MahjongMessage`，更清晰。

好了，协议定义完毕，下面我们来一起看看如何对这个协议进行编解码。



 ### 编解码实现

![图片描述](https://img1.sycdn.imooc.com/5f3dd3a70001543a10300196.png)

我们一再强调，编解码分成一次编解码和二次编解码，一次编解码是对粘包半包的处理，将字节流分割成一个一个的片段，二次编解码是将这些片段再转换成 Java 对象。
![图片描述](https://img1.sycdn.imooc.com/5f3dd3c400015dd510260436.png)

对于本次实战项目，最终转换成的 Java 对象就是 MahjongProtocol 对象。

首先，我们来看一次编解码该如何编写，前面我们已经说过了，我们使用的是 长度 + 内容 的方式来进行一次编解码，在 Netty 中，对于这种方式也提供了支持，就是 `LengthFieldPrepender` 和 `LengthFieldBasedFrameDecoder` 类，前者负责编码，后者负责解码，所以，我们只需要继承这两个类就可以轻松地实现一次编解码的工作了，下面我直接给出代码：

```java
public class MahjongFrameEncoder extends LengthFieldPrepender {
    public MahjongFrameEncoder() {
        // 长度字段占用两个字节
        super(2);
    }
}
public class MahjongFrameDecoder extends LengthFieldBasedFrameDecoder {
    public MahjongFrameDecoder() {
        // 2个字节表示最多可传输65535个字节的内容
        super(65535, 0, 2, 0, 2);
    }
}
```

是不是非常简单？没错，就是这么简单。

对于解码器，在经历过一次解码之后，拿到的就是一个一个完整的 MahjongProtocol 对象的字节流了，对于这个字节流，我们再编写相应的解码器将其转换成 MahjongProtocol 对象即可。

对于编码器，整个过程正好是反过来的，先通过二次编码器，将 MahjongProtocol 对象转换成字节流，再通过一次编码器将这个字节流添加上长度字段，然后再发送出去，在发送的时候，它可能会跟其它的字节流合并在一起发送出去，对方拿到这串字节流，根据一次解码器再进行解码就可以了。

那么，二次编解码该如何编写呢？

因为，我们上面定义的协议的 body 是需要先解出 header 中的 cmd，根据 cmd 找到 body 的类型，才能解出 body，所以，在编码的时候也是一样，我们先编码 header，header 中就三个字段，我们手动编码即可，对于 body，我们第一个版本简单点，使用 JSON 序列化成字节流，所以，我们的编码器看起来像下面这样：

```java
public class MahjongProtocolEncoder extends MessageToMessageEncoder<MahjongProtocol> {

    @Override
    protected void encode(ChannelHandlerContext ctx, MahjongProtocol mahjongProtocol, List<Object> out) throws Exception {
        // 调用分配器分配一个ByteBuf
        ByteBuf buffer = ctx.alloc().buffer();
        // 调用的协议的编码方法
        mahjongProtocol.encode(buffer);
        // 添加到out中
        out.add(buffer);
    }
}
public final class MahjongProtocol {
    // 协议的编码方法
    public void encode(ByteBuf buffer) {
        // 调用header的编码方法
        header.encode(buffer);
        // 将body序列化成字节流写入到buffer中
        buffer.writeBytes(JSON.toJSONString(body).getBytes(StandardCharsets.UTF_8));
    }
}
public final class MahjongProtocolHeader {
    // header的编码方法
    public void encode(ByteBuf buffer) {
        // 写入版本号
        buffer.writeInt(version);
        // 写入命令字
        buffer.writeInt(cmd);
        // 写入请求ID
        buffer.writeInt(reqId);
    }
}
```

这里，你可能不禁要问：为什么 header 单独写一个编码方法，而 body 不也写一个编码方法呢？

那是因为 header 类型只有一个，而 body 的类型是有很多个的，如果在 MahjongProtocolBody 接口中定义一个 encode () 方法，那么，所有的消息类型都要实现这个方法，而它们中的内容并没有什么差别。但是，header 就不一样了，如果后面 header 增加新的内容，把编码方法放在 MahjongProtocolHeader 类中，就只需要修改这一个类就够了，如果把 header 的编码方法去掉，放到 MahjongProtocol 类中，也是可以的，只是后面增加新的字段，要同时修改两个类才可以，就不够单纯了。

二次编码器的编写相对来说比较简单一些，可以看到，这里并没有太关心 body 的类型，解码器就不一样了，请看：

```java
public class MahjongProtocolDecoder extends MessageToMessageDecoder<ByteBuf> {
    @Override
    protected void decode(ChannelHandlerContext ctx, ByteBuf msg, List<Object> out) throws Exception {
        // 创建一个协议对象
        MahjongProtocol mahjongProtocol = new MahjongProtocol();
        // 同样委托给协议自己去解码
        mahjongProtocol.decode(msg);
        // 添加到out中
        out.add(mahjongProtocol);
    }
}
public final class MahjongProtocol {
    public void decode(ByteBuf msg) {
        MahjongProtocolHeader header = new MahjongProtocolHeader();
        // 解码header
        header.decode(msg);
        this.header = header;

        // 命令字
        int cmd = header.getCmd();
        // 根据命令字获取body的真实类型
        Class<? extends MahjongProtocolBody> bodyType = getBodyTypeByCmd(cmd);
        this.body = JSON.parseObject(msg.toString(StandardCharsets.UTF_8), bodyType);
    }

    private Class<? extends MahjongProtocolBody> getBodyTypeByCmd(int cmd) {
        // todo 这里该如何写？
        return null;
    }
}
public final class MahjongProtocolHeader {
    public void decode(ByteBuf msg) {
        // 读取一个int赋值给version
        version = msg.readInt();
        // 读取一个int赋值给cmd
        cmd = msg.readInt();
        // 读取一个int赋值给请求ID
        reqId = msg.readInt();
    }
}
```

二次解码的过程相对来说要复杂一些，先解出 header，从 header 中取出 cmd，根据 cmd 找到正确的 body 类型，再使用 JSON 反序列化为 body 对象，这里的难点在于如何根据 cmd 的值找到正确的 body 类型，我提供以下几种思路：

1. 使用 Spring 容器来管理这些消息类型；
2. 使用枚举类型来管理这些消息类型；
3. 使用一个全局 Map 来管理这些消息类型；

使用 Spring 容器的话相对来说要方便一些，不过要编写自定义的 BeanPostProcessor 或者 BeanFactoryPostProcessor 来处理 cmd 和消息类型之间的映射关系，容错率也相对高一些，不过要引入 Spring，不在本课程的讨论范围之内。

使用全局 Map 的话，何时初始化这个 Map，怎么初始化这个 Map，是个头疼的问题。

使用枚举类型的话，每次添加一个新的消息，都要记得在枚举类中添加一条记录，相对来说有点麻烦，不过好在也比较简单，也不用依赖其它组件，所以，我们这里暂且使用枚举这种方式来管理这些消息类型，请看：

```java
@Slf4j
@Getter
public enum MessageManager {
    HELLO_REQUEST(1, HelloRequest.class),
    ;

    private int cmd;
    private Class<? extends MahjongMessage> msgType;

    MessageManager(int cmd, Class<? extends MahjongMessage> msgType) {
        this.cmd = cmd;
        this.msgType = msgType;
    }

    public static Class<? extends MahjongMessage> getMsgTypeByCmd(int cmd) {
        for (MessageManager value : MessageManager.values()) {
            if (value.cmd == cmd) {
                return value.msgType;
            }
        }
        log.error("error cmd: {}", cmd);
        throw new RuntimeException("error cmd:" + cmd);
    }
}
```

在这里，我们定义了一个 HelloRequest 的消息，把它添加到枚举中，并给它分配一个 cmd，这样我们就可以根据 cmd 取出消息的类型了，这种方式的缺点有两个：一是新增的消息要记得在枚举中添加一次，二是 cmd 千万不能重复。

此时，我们再回过头去修改 MahjongProtocol 中的解码方法：

```java
public final class MahjongProtocol {
    public void decode(ByteBuf msg) {
        MahjongProtocolHeader header = new MahjongProtocolHeader();
        // 解码header
        header.decode(msg);
        this.header = header;

        // 命令字
        int cmd = header.getCmd();
        // 根据命令字获取body的真实类型
        Class<? extends MahjongProtocolBody> bodyType = getBodyTypeByCmd(cmd);
        this.body = JSON.parseObject(msg.toString(StandardCharsets.UTF_8), bodyType);
    }

    private Class<? extends MahjongProtocolBody> getBodyTypeByCmd(int cmd) {
        // 从MessageManager中获取
        return MessageManager.getMsgTypeByCmd(cmd);
    }
}
```

这样的话，以后如果更换 cmd 与消息类型的映射方式，只需要修改 `getBodyTypeByCmd()` 这个方法就可以了。

好了，到此，协议实现和编解码实现都搞定了，下面就是把服务端和客户端实现，来检验它们的实现是否可行了。



 ### 服务端实现

服务端实现就比较简单了，前面我们已经着重分析过了，直接把代码拿过来即可。

```java
public class MahjongServer {

    static final int PORT = Integer.parseInt(System.getProperty("port", "8080"));

    public static void main(String[] args) throws Exception {
        // 1. 声明线程池
        EventLoopGroup bossGroup = new NioEventLoopGroup(1);
        EventLoopGroup workerGroup = new NioEventLoopGroup();
        try {
            // 2. 服务端引导器
            ServerBootstrap serverBootstrap = new ServerBootstrap();
            // 3. 设置线程池
            serverBootstrap.group(bossGroup, workerGroup)
                    // 4. 设置ServerSocketChannel的类型
                    .channel(NioServerSocketChannel.class)
                    // 5. 设置参数
                    .option(ChannelOption.SO_BACKLOG, 100)
                    // 6. 设置ServerSocketChannel对应的Handler，只能设置一个
                    .handler(new LoggingHandler(LogLevel.INFO))
                    // 7. 设置SocketChannel对应的Handler
                    .childHandler(new ChannelInitializer<SocketChannel>() {
                        @Override
                        public void initChannel(SocketChannel ch) throws Exception {
                            ChannelPipeline p = ch.pipeline();
                            // 打印日志
                            p.addLast(new LoggingHandler(LogLevel.INFO));
                            // 一次编解码器
                            p.addLast(new MahjongFrameDecoder());
                            p.addLast(new MahjongFrameEncoder());
                            // 二次编解码器
                            p.addLast(new MahjongProtocolDecoder());
                            p.addLast(new MahjongProtocolEncoder());
                        }
                    });

            // 8. 绑定端口
            ChannelFuture f = serverBootstrap.bind(PORT).sync();
            // 9. 等待服务端监听端口关闭，这里会阻塞主线程
            f.channel().closeFuture().sync();
        } finally {
            // 10. 优雅地关闭两个线程池
            bossGroup.shutdownGracefully();
            workerGroup.shutdownGracefully();
        }
    }
}
```



 ### 客户端实现

客户端的实现是我们之前没有讲过的，我这里先给出代码：

```java
@Slf4j
public class MahjongClient {

    static final int PORT = Integer.parseInt(System.getProperty("port", "8080"));

    public static void main(String[] args) throws Exception {
        // 工作线程池
        NioEventLoopGroup workerGroup = new NioEventLoopGroup();
        try {
            Bootstrap bootstrap = new Bootstrap();
            bootstrap.group(workerGroup);
            bootstrap.channel(NioSocketChannel.class);
            bootstrap.handler(new ChannelInitializer<SocketChannel>() {
                @Override
                protected void initChannel(SocketChannel ch) throws Exception {
                    ChannelPipeline pipeline = ch.pipeline();
                    // 打印日志
                    pipeline.addLast(new LoggingHandler(LogLevel.INFO));
                    // 一次编解码器
                    pipeline.addLast(new MahjongFrameDecoder());
                    pipeline.addLast(new MahjongFrameEncoder());
                    // 二次编解码器
                    pipeline.addLast(new MahjongProtocolDecoder());
                    pipeline.addLast(new MahjongProtocolEncoder());
                }
            });

            // 连接到服务端
            ChannelFuture future = bootstrap.connect(new InetSocketAddress(PORT)).sync();

            log.info("connect to server success");

            future.channel().closeFuture().sync();
        } finally {
            workerGroup.shutdownGracefully();
        }
    }
}
```

客户端因为不需要像服务端那样去监听网卡，所以，就不需要 ServerSocketChannel 以及 bossGroup 相关的配置了，相信有服务端编码过程的了解，对于这段代码，你一定可以驾轻就熟的，我们就不再赘述了。



 ### 双端打通

好了，服务端和客户端的代码都写好了，如何把它们连接起来呢？

其实，直接启动两者的 main () 方法，就可以成功连接起来了：

```java
22:38:14 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x1cafd9a5] REGISTERED
22:38:14 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x1cafd9a5] CONNECT: 0.0.0.0/0.0.0.0:8080
22:38:14 [main] MahjongClient: connect to server success
22:38:14 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x1cafd9a5, L:/192.168.175.1:55463 - R:0.0.0.0/0.0.0.0:8080] ACTIVE
```

只不过目前两者还没有任何消息的通信，所以，还看不到任何的效果。

因此，我们还需要定义一对消息，让它们在客户端与服务端之间传递，同时，两端还需要定义各自的 Handler 来处理这一对消息。

这一对消息我们姑且称之为 HelloRequest 和 HelloResponse，HelloRequest 在上面我们已经提起过了，这里给出它的代码：

```java
@Data
public class HelloRequest implements MahjongMessage {
    private String name;
}
```

非常简单，HelloResponse 是对 HelloRequest 的回应，我们姑且给它一个 message 的字段：

```java
@Data
public class HelloResponse implements MahjongMessage {
    private String message;
}
```

另外，记得在 MessageManager 中添加 HelloResponse 与 cmd 的映射关系：

```java
public enum MessageManager {
    HELLO_REQUEST(1, HelloRequest.class),
    HELLO_RESPONSE(2, HelloResponse.class),
    ;
}
```

好了，两个消息我们也定义好了，下面就是定义两个 Handler 分别用来处理 HelloRequest 和 HelloResponse 了，请看服务端的 Handler：

```java
@Slf4j
public class MahjongServerHandler extends SimpleChannelInboundHandler<MahjongProtocol> {

    @Override
    protected void channelRead0(ChannelHandlerContext ctx, MahjongProtocol mahjongProtocol) throws Exception {
        // 协议头
        MahjongProtocolHeader header = mahjongProtocol.getHeader();
        // 检查是不是HelloRequest的cmd
        if (header.getCmd() == MessageManager.HELLO_REQUEST.getCmd()) {
            // 强转
            HelloRequest helloRequest = (HelloRequest) mahjongProtocol.getBody();
            // 打印日志
            log.info("receive msg: {}", helloRequest);
            // 获取消息的内容
            String name = helloRequest.getName();
            // 构建响应
            HelloResponse helloResponse = new HelloResponse();
            helloResponse.setMessage("hello " + name);
            // 响应对应的协议头
            MahjongProtocolHeader outHeader = new MahjongProtocolHeader();
            outHeader.setVersion(header.getVersion());
            outHeader.setReqId(header.getReqId());
            outHeader.setCmd(MessageManager.HELLO_RESPONSE.getCmd());
            // 响应对应的协议
            MahjongProtocol out = new MahjongProtocol();
            out.setHeader(outHeader);
            out.setBody(helloResponse);
            // 写出
            ctx.writeAndFlush(out);
        }
    }
}
```

在服务端的 Handler 中，我们接收到请求之后，构造了一个响应并返回，代码看起来稍微啰嗦了一点，是因为，我们二次编解码针对的是 MahjongProtocol，所以，传递到 MahjongServerHandler 中的也是 MahjongProtocol，如果确定后续的业务逻辑处理不会再使用到 header，那么，也可以在这里统一处理 header，往后面传递的时候只传递消息，这一块我们在业务逻辑实现的小节再详细讲解。

再看客户端的 Handler：

```java
@Slf4j
public class MahjongClientHandler extends SimpleChannelInboundHandler<MahjongProtocol> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, MahjongProtocol mahjongProtocol) throws Exception {
        // 协议头
        MahjongProtocolHeader header = mahjongProtocol.getHeader();
        // 检查是不是HelloResponse的cmd
        if (header.getCmd() == MessageManager.HELLO_RESPONSE.getCmd()) {
            // 强转
            HelloResponse helloResponse = (HelloResponse) mahjongProtocol.getBody();
            // 打印响应
            log.info("receive response: {}", helloResponse);
        }

    }
}
```

客户端接收到消息之后，判断是不是 HelloResponse 的 cmd，然后打印出响应内容。

然后，把这两个 Handler 分别加入到服务端和客户端的 pipeline 中，分别启动服务端和客户端。

效果似乎不是我们预期的那样，仔细检查，发现，没有发送 HelloRequest 的地方呀，那么，在哪里发送 HelloRequest 呢？

无疑，是在客户端，但是，是在客户端的哪里发送比较合适呢？

有两种方式，一种是放到 MahjongClientHandler 的 channelActive () 方法中，一种是在 MahjongClient 的 main () 方法中连接建立之后发送，两种方式的代码分别如下。

放到 MahjongClientHandler 中：

```java
public class MahjongClientHandler extends SimpleChannelInboundHandler<MahjongProtocol> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, MahjongProtocol mahjongProtocol) throws Exception {
        // ...省略
    }

    @Override
    public void channelActive(ChannelHandlerContext ctx) throws Exception {
        HelloRequest helloRequest = new HelloRequest();
        helloRequest.setName("tt");

        MahjongProtocolHeader header = new MahjongProtocolHeader();
        header.setVersion(1);
        header.setReqId(1);
        header.setCmd(1);

        MahjongProtocol mahjongProtocol = new MahjongProtocol();
        mahjongProtocol.setHeader(header);
        mahjongProtocol.setBody(helloRequest);

        ctx.writeAndFlush(mahjongProtocol);
    }
}
```

放在 MahjongClient 中：

```java
public class MahjongClient {

    public static void main(String[] args) throws Exception {
        try{
            // ... 省略
            
            // 连接到服务端
            ChannelFuture future = bootstrap.connect(new InetSocketAddress(PORT)).sync();

            log.info("connect to server success");

            // 连接建立完成之后发送hello消息给服务端
            HelloRequest helloRequest = new HelloRequest();
            helloRequest.setName("tt");

            MahjongProtocolHeader header = new MahjongProtocolHeader();
            header.setVersion(1);
            header.setReqId(1);
            header.setCmd(1);

            MahjongProtocol mahjongProtocol = new MahjongProtocol();
            mahjongProtocol.setHeader(header);
            mahjongProtocol.setBody(helloRequest);

            future.channel().writeAndFlush(mahjongProtocol);

            future.channel().closeFuture().sync();
        } finally {
            workerGroup.shutdownGracefully();
        }
    }
}
```

两者二选其一即可。

此时，分别启动服务端和客户端，观察控制台日志，可以发现，很顺畅。

服务端日志：

```java
//...省略
23:34:00 [nioEventLoopGroup-3-5] MahjongServerHandler: receive msg: HelloRequest(name=tt)
//...省略
```

客户端日志：

```java
//...省略
23:34:00 [nioEventLoopGroup-2-1] MahjongClientHandler: receive response: HelloResponse(message=hello tt)
//...省略
```

至此，双端已经完全打通。



 ### 后记

本节，我们实现了协议及其对应的编解码器，细心的同学会发现，整个过程并没有多少代码，且编解码器在客户端和服务端是通用的，也不用做什么过多的处理，这正是 Netty 的魅力之处，少量的代码就能快速打造一套强力的架构。

下一节，我们将实现系统设计一节中定义的领域模型，彼时，我们会详细讲解为什么我们选择使用贫血模型，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3dd3ee0001039f17131056.png)





<div style="page-break-after:always;"></div>

 ## 31 领域模型实现，我又贫血了


![img](https://img3.sycdn.imooc.com/5f0596df0001a35b06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)从不浪费时间的人，没有工夫抱怨时间不够。——杰弗逊![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起把实战项目的协议给实现了，同时，通过 HelloRequest 和 HelloResponse 把客户端和服务端成功连接起来了。

本节，我们将根据系统设计中领域模型设计的内容，把这些领域模型给实现了。

下面就进入今天的学习吧。



 ### 领域模型实现

根据系统设计一节的内容，我们归纳出来的领域模型有：玩家、房间、牌、各种消息。

> 我这里把消息也看作是领域模型了，更确切地讲，消息属于接口设计的内容，不过为了方便讲解，我是把他们合并在一起了。怎么区分两者呢？看主体本身是不是一个纯粹的名词，比如，玩家就是一个纯粹的名词，所以，它是领域模型，而出牌请求就不是一个纯粹的名词，它包含动词含义，所以，它是接口。不过，总体来说，它们都是一个主体加上一些属性构成，所以，看成是一样的东西也是没问题的。



 #### 玩家

![图片描述](https://img1.sycdn.imooc.com/5f3dd5110001402310280401.png)
所谓实现，就是把设计的内容转换成代码，所以，编码是最简单的工作。当然了，在实现的时候可能也会扩充一些字段，比如，玩家应当具有唯一的 ID，所以，上面这张图转换成代码如下：

```java
@Data
public class Player {
    /**
     * 唯一标识id
     */
    private long id;
    /**
     * 用户名
     */
    private String username;
    /**
     * 密码
     */
    private String password;
    /**
     * 玩家的积分
     */
    private int score;
    
    /**
     * 玩家在房间的位置
     */
    private int pos;
    /**
     * 手牌列表
     */
    private byte[] cards;
    /**
     * 打出的牌
     */
    private byte[] chuCards;
    /**
     * 碰的牌
     */
    private byte[] pengList;
    /**
     * 杠的牌
     */
    private byte[] gangList;

}
```

我这里做了一些调整，将玩家天然的属性移到了上面，将牌局相关的信息移到了下面。

为什么要这么做呢？

因为，牌局相关的信息在每一局都不一样，所以，需要在牌局结束时进行重置，把牌局相关的信息放在一起，到时候写重置方法的时候会比较简单清晰一些。



 #### 房间

![图片描述](https://img1.sycdn.imooc.com/5f3dd4fe0001fead10280407.png)
同样地，房间也会扩充一些属性：

```java
@Data
public class Room {
    /**
     * 房间id
     */
    private long id;
    /**
     * 房间最大的人数
     */
    private int maxPlayerNum;
    /**
     * 底分
     */
    private int baseScore;
    /**
     * 房间内的玩家列表
     */
    private Player[] players;
    /**
     * 未摸的牌
     */
    private byte[] remainCards;
    /**
     * 出牌玩家的位置
     */
    private int chuPos;
    /**
     * 状态
     */
    private int status;
}
```

对于房间的状态，我们也是要定义的，这一块在系统设计的时候给遗漏了，在这里补上。

首先，一个玩家创建了房间之后，房间的状态进入等待其他玩家进入的状态，当玩家满了的情况下，游戏开始了，记录一个游戏开始的状态，发完牌了，轮到庄家出牌，记录一个等待出牌的状态，出牌后如果有其它玩家可以操作，还需要记录一个等待操作的状态，最后，游戏结束了，记录一个结束的状态。

所以，房间的状态一共有：等待玩家、游戏开始、等待出牌、等待操作、游戏结束，简单点，我们把这些常量也定义到房间这个类中：

```java
public class Room {
    /**
     * 等待其他玩家进入房间
     */
    public static final int STATUS_WAITING_PLAYER = 1;
    /**
     * 游戏开始
     */
    public static final int STATUS_GAME_STARTING = 2;
    /**
     * 等待玩家出牌
     */
    public static final int STATUS_WAITING_CHU = 3;
    /**
     * 等待其他玩家操作（碰、杠、胡）
     */
    public static final int STATUS_WAITING_OPERATION = 4;
    /**
     * 游戏结束
     */
    public static final int STATUS_GAME_OVER = 5;
}
```



 #### 牌

![图片描述](https://img1.sycdn.imooc.com/5f3dd4e90001839d09540102.png)
按照系统设计的一节的内容，一张牌用一个 byte 表示就可以的，所以，牌不需要单独的类来表示，但是，需要一个工具类告诉我哪个 byte 表示哪张牌，因此，我们这里也定义一下牌的信息：
![图片描述](https://img1.sycdn.imooc.com/5f3dd4d8000195b810250224.png)
这样设计的话，类型占 4 位，牌值点 4 位，各能代表 16 种不同的数值，是完全足够的，所以，我们的工具类看起来是这样的：

```java
public class CardUtils {
    /**
     * 万的掩码，一万到九万：0x11~0x19
     */
    public static final byte CARD_TYPE_WAN_MASK = 0x10;
    /**
     * 条的掩码，一条到九条：0x21~0x29
     */
    public static final byte CARD_TYPE_TIAO_MASK = 0x20;
    /**
     * 筒的掩码，一筒到九筒：0x31~0x39
     */
    public static final byte CARD_TYPE_TONG_MASK = 0x30;

    /**
     * 类型的掩码
     */
    public static final byte CARD_TYPE_MASK = 0x70;
    /**
     * 值的掩码
     */
    public static final byte CARD_VALUE_MASK = 0x0f;

    /**
     * 获取牌的类型
     * @param card
     * @return
     */
    public static final byte cardType(byte card) {
        return (byte) (CARD_TYPE_MASK & card);
    }

    /**
     * 获取牌的数值
     * @param card
     * @return
     */
    public static final byte cardValue(byte card) {
        return (byte) (CARD_VALUE_MASK & card);
    }

}
```

这里使用 16 进制表示，正好一个数字表示 4 位，同学们好好体会一下。

对于万牌来说，它的值为 0x11~0x19，分别表示一万到九万。



 #### 消息

在系统设计一节中，我们归纳出来的消息一共有：登录、创建房间、加入房间、房间刷新通知、操作通知、操作请求、操作结果通知、结束通知、结算通知。

它们都比较简单，我们快速的定义一下：

```java
@Data
public class LoginRequest implements MahjongMessage {
    private String username;
    private String password;
}
@Data
public class LoginResponse implements MahjongMessage {
    private boolean result;
    private Player player;
    private String message;
}
@Data
public class CreateRoomRequest implements MahjongMessage {
    private int playerNum;
    private int baseScore;
}
@Data
public class CreateRoomResponse implements MahjongMessage {
    private boolean result;
    private String message;
}
@Data
public class EnterRoomRequest implements MahjongMessage {
    private long tableId;
}
@Data
public class EnterRoomResponse implements MahjongMessage {
    private boolean result;
    private String message;
}
@Data
public class RoomRefreshNotification implements MahjongMessage {
    private int operation;
    private Room room;
}
@Data
public class OperationNotification implements MahjongMessage {
    private int operation;
    private int pos;
    private byte fireCard;
}
@Data
public class OperationRequest implements MahjongMessage {
    private int operation;
    private int pos;
    private byte card;
}
@Data
public class OperationResultNotification implements MahjongMessage {
    private int operation;
    private int pos;
    private byte card;
}
@Data
public class GameOverNotificaion implements MahjongMessage {
    private Room room;
}
@Data
public class SettlementNotification implements MahjongMessage {
    private int[] scores;
}
```

另外，要记得把它们都添加到 MessageManager 里面：

```java
public enum MessageManager {
    HELLO_REQUEST(1, HelloRequest.class),
    HELLO_RESPONSE(2, HelloResponse.class),
    LOGIN_REQUEST(3, LoginRequest.class),
    LOGIN_RESPONSE(4, LoginResponse.class),
    CREATE_ROOM_REQUEST(5, CreateRoomRequest.class),
    CREATE_ROOM_RESPONSE(6, CreateRoomResponse.class),
    ENTER_ROOM_REQUEST(7, EnterRoomRequest.class),
    ENTER_ROOM_RESPONSE(8, EnterRoomResponse.class),
    ROOM_REFRESH_NOTIFICATION(9, RoomRefreshNotification.class),
    OPERATION_NOTIFICATION(10, OperationNotification.class),
    OPERATION_REQUEST(11, OperationRequest.class),
    OPERATION_RESULT_NOTIFICATION(12, OperationResultNotification.class),
    GAME_OVER_NOTIFICATION(13, GameOverNotification.class),
    SETTLEMENT_NOTIFICATION(14, SettlementNotification.class),
    ;
}
```

关于操作相关的消息，我们还应该定义有哪些操作类型，所以，我们再新加一个工具类用来定义操作类型：

```java
public class OperationUtils {
    /**
     * 出
     */
    public static final int OPERATION_CHU = 1;
    /**
     * 碰
     */
    public static final int OPERATION_PENG = 2;
    /**
     * 杠
     */
    public static final int OPERATION_GANG = 4;
    /**
     * 胡
     */
    public static final int OPERATION_HU = 8;
    /**
     * 摸
     */
    public static final int OPERATION_GRAB = 16;
    /**
     * 过
     */
    public static final int OPERATION_GUO = 32;
}
```

细心的同学会发现，操作类型的这些数值转换成二进制正好是错开的，这也是为了能在一个 int 字段中表示多个操作类型，比如，玩家 A 出了一张牌，玩家 B 手中有三张，那么，他既可以选择碰，也可以选择杠，此时，我们只需要把 OPERATION_PENG 和 OPERATION_GANG 做一个 “或” 操作就可以了。
![图片描述](https://img1.sycdn.imooc.com/5f3dd4c40001a38110300185.png)

好了，所有的领域模型都实现了，细心的同学可能会发现，所有的领域模型中都没有行为，也就是方法，这也就是传说中的贫血模型，为什么要使用贫血模型呢？

原因主要有以下几点：

1. 我们定义的这些领域模型是要给到客户端的，里面定义了方法，这些方法可能并不适用于客户端，造成冗余；
2. 目前这些领域模型是手动编写的，试想如果后期扩展为 protobuf，它们是通过文件生成的，这些生成的类中是不应该添加自己的方法的；
3. 如果后期要做持久化到数据库，这个持久化的动作放在哪里比较合适，放在领域模型中会很奇怪；
4. 充血模型很难定义业务逻辑的边界，也就是说哪些方法应该放在领域模型中，哪些应该放在 service 中，很难把控，所以，倒不如把这些业务逻辑全部放在 service 中，更加清晰；
5. 开发人员的技术水平参差不齐，使用充血模型会导致上面所说的业务边界的问题更加混乱；

综上所述，虽然使用贫血模型不那么的面向对象（当然，一般程序员可能没有对象），但是，业务逻辑和领域模型的边界都足够清晰，更适合于团队开发，因此，我们这里也同样采用贫血模型来进行开发，这可能也是 Spring MVC 比较流行的主要原因。



 ### 后记

本节，我们根据系统设计中领域模型设计以及接口设计的内容把所有的领域模型给实现了，并在最后，分析了我们使用贫血模型的主要原因。

下一节，我们将给这些贫血的模型加上业务处理的逻辑，当然了，这些逻辑是剥离出去的，同时，会考虑使用什么样的线程池来承载我们的业务处理逻辑，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3dd4b40001983412912501.png)





<div style="page-break-after:always;"></div>

 ## 32 业务逻辑实现，游戏线程池如何设计？


![img](https://img4.sycdn.imooc.com/5f0596ee00011b3f06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)世上无难事,只要肯登攀。——毛泽东![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起将所有的领域模型都实现了，但是，它们都是贫血模型，还缺少了非常重要的行为，本节，我们就一起来把它们的行为实现了，当然了，我们不会直接在这些模型内部实现行为，而是把它们抽离出来，具体的原因在上一节我们已经解释过了，此处，就不再赘述了。

好了，开始今天的学习吧。



 ### 游戏线程池的设计

在前面的章节中，我们一再提到，游戏的业务逻辑复杂，很多数据都是放在内存中进行处理的，但是，仅仅放在内存中还不能完全满足要求。

我举个例子，房间 A 里面的四个玩家打牌，如果使用普通的 Java 线程池处理这个房间的所有信息，就会带来新的问题：

1. 所有消息对于房间信息的修改，需要使用锁，对性能有一定的影响；
2. 使用锁之后，业务实现者要时时考虑锁的使用问题，增加了业务开发的难度；
3. 有序性，我们知道 Java 线程池中任务的流转过程，先看有没有达到核心线程数，再看队列有没有满，最后看有没有达到最大线程数，我举个极端的例子，如果队列满了，此时，发来一条消息，它会去尝试创建一个新的线程（未达最大线程数）来处理当前消息，这导致该房间之前的消息可能还在队列中未处理，而这条消息却先处理了，这明显不符合要求。

基于以上三点原因，使用 Java 线程池肯定是不能满足我们的要求了，那么，使用 Netty 的线程池是否可以呢？

其实也是不行的，我们知道，Netty 线程池中每个 EventExecutor 都会绑定一个队列，不同客户端的消息是发往不同的队列，它依然会带来上面的三个问题。

所以，我们需要重新设计一种线程池：不加锁且消息有序，这要怎么实现呢？

我们前面提到过一个名词：房间制，那么，是不是把同一个房间的消息发到同一个线程进行处理就可以了呢？

答案确实是这样的，但是实现起来并没有那么简单。

首先，使用 Java 自带的线程池肯定是不行的了。

其次，使用 Netty 的线程池，通过前面关于 Netty 线程池的源码剖析，我们知道，在 Netty 中，有两种选择线程的方式，即 PowerOfTwoEventExecutorChooser 和 GenericEventExecutorChooser，然而，它们的内部实现并没有本质上的区别，都是通过轮询的方式调用线程池中的线程来处理任务，所以，乍看之下，也不满足我们的要求。

最后，只能自己来实现了？自己实现的话，也是每个线程维护自己的队列，且把同一个房间的消息都到同一个线程的队列中，这其实跟 Netty 还是有些像的，而且，自己实现的线程池，在稳定性、安全性等方面的考量，也是一个非常重要的问题，所以，我们能不能对 Netty 的线程池进行改造，拿过来即用呢？

通过前面的分析，可以发现，其实 Netty 的线程池本身是满足我们的要求的，关键在于选择线程的方式这里，所以，改造的要点就在这里，我们需要自己实现一种线程选择的方式，比如，按房间号去选择线程。

仔细观察 PowerOfTwoEventExecutorChooser 或者 GenericEventExecutorChooser 的代码：

```java
private static final class PowerOfTwoEventExecutorChooser implements EventExecutorChooser {
    private final AtomicInteger idx = new AtomicInteger();
    private final EventExecutor[] executors;

    PowerOfTwoEventExecutorChooser(EventExecutor[] executors) {
        this.executors = executors;
    }

    @Override
    public EventExecutor next() {
        return executors[idx.getAndIncrement() & executors.length - 1];
    }
}
```

在调用 next () 方法选择线程的时候，似乎不能传递额外的参数了，但是，别忘了，我们还有终极杀器 —— 线程本地变量，在调用 next () 方法之前，可以把房间号存储在 FastThreadLocal 中，这样在 next () 中就能获取到这个房间号，然后，就可以使用房间号来做路由了，比如按房间号取模，完美 ^^

好了，说干就干，让我们来实现之～～



 ### 游戏线程池的实现

参考 DefaultEventExecutorChooserFactory 的代码，我们实现一个自己用的 MahjongEventExecutorChooserFactory，并将其运用到自定义的线程池 MahjongEventExecutorGroup 中：

```java
public class MahjongEventExecutorGroup extends MultithreadEventExecutorGroup {

    private MahjongEventExecutorGroup(int nThreads) {
        // 使用自定义的选择器工厂
        super(nThreads, null, new MahjongEventExecutorChooserFactory(), null);
    }

    @Override
    protected EventExecutor newChild(Executor executor, Object... args) throws Exception {
        return new DefaultEventExecutor(this, executor);
    }
    // 工厂类
    private static class MahjongEventExecutorChooserFactory implements EventExecutorChooserFactory {

        @Override
        public EventExecutorChooser newChooser(EventExecutor[] executors) {
            return new MahjongEventExecutorChooser(executors);
        }
        // 真正使用的选择器
        private static class MahjongEventExecutorChooser implements EventExecutorChooserFactory.EventExecutorChooser {

            private final AtomicInteger idx = new AtomicInteger();
            private final EventExecutor[] executors;

            MahjongEventExecutorChooser(EventExecutor[] executors) {
                this.executors = executors;
            }

            @Override
            public EventExecutor next() {
                // 从上下文中取出当前的房间id
                Long roomId = MahjongContext.currentContext().getCurrentRoomId();
                long id;
                if (roomId != null) {
                    id = roomId;
                } else {
                    // 没获取到房间号的消息轮徇扔到业务线程池中处理
                    // 他们往往跟房间信息没啥关系，比如登录请求
                    id = idx.getAndIncrement();
                }
                // 根据id取模选择线程执行
                return executors[(int) (id & executors.length - 1)];
            }
        }
    }
}
```

与默认的两种选择方式不同的是，在 next () 方法中，我们先尝试从上下文中获取当前的房间号，这里的上下文自然就是线程本地变量了，如果获取到了，就使用这个房间号取模来获取执行的线程，如果没获取到就使用原来的轮询方式进行处理，为什么会有没取到的情况呢？

比如，登录请求，它是没有房间信息的。

好了，现在的问题变成了：在什么时候把房间号放入到上下文中呢？

这就牵涉到要怎么使用这个线程池了，总体来说有两种方式：

1. 在 ChannelPipeline 中与 MahjongServerHandler 进行关联，即 `p.addLast(new MahjongEventExecutorGroup(8), new MahjongServerHandler());`；
2. 在 MahjongServerHandler 中手动调用，即 `mahjongEventExecutorGroup.execute()`；

使用第一种方式无疑是比较友好的，但是，整个过程都是在 ChannelPipeline 中自动完成的，没有地方可以设置房间号到上下文中，所以，只能使用第二种方式了。

第二种方式就要简单得多了，只需要在 `mahjongEventExecutorGroup.execute()` 前一刻把房间号设置到上下文中即可。

为此，我专门在 MahjongEventExecutorGroup 中定义了一个静态方法来处理房间号相关的逻辑，给 MahjongServerHandler 调用：

```java
public class MahjongEventExecutorGroup extends MultithreadEventExecutorGroup {
    // 实例，单例模式
    private static final MahjongEventExecutorGroup INSTANCE = new MahjongEventExecutorGroup(NettyRuntime.availableProcessors());

    // 静态方法，MahjongServerHandler中直接调用该方法
    public static void execute(Channel channel, MahjongProtocol mahjongProtocol) {
        // 协议头
        MahjongProtocolHeader header = mahjongProtocol.getHeader();
        // 协议体
        MahjongMessage message = (MahjongMessage) mahjongProtocol.getBody();
        // 创建房间和加入房间需要做一些处理
        Long roomId;
        if (message instanceof CreateRoomRequest) {
            // 如果是创建房间消息，生成一个roomId，并将当前channel与之绑定
            roomId = IdUtils.generateId();
            // 一个channel一旦建立，始终与一个eventLoop绑定
            // 所以，可以把channel与房间号的绑定放在线程本地缓存中
            MahjongContext.currentContext().setChannelRoomId(channel, roomId);
        } else if (message instanceof EnterRoomRequest) {
            // 如果是加入房间消息，将当前channel与传入的tableId绑定
            EnterRoomRequest enterRoomRequest = (EnterRoomRequest) message;
            roomId = enterRoomRequest.getRoomId();
            MahjongContext.currentContext().setChannelRoomId(channel, roomId);
        } else {
            // 其它消息则从context中获取当前channel对应的房间号
            // 当然，也可能没有，比如登录请求
            roomId = MahjongContext.currentContext().getChannelRoomId(channel);
        }

        // 设置房间id到context中，以便next()方法可以取到
        MahjongContext.currentContext().setCurrentRoomId(roomId);
        // 将消息扔到业务线程池中处理
        INSTANCE.execute(() -> {
            // todo 此处实现在下面
        });

    }
}
```

到此，我们真正实现了根据房间号来选择指定线程的目标，那么，还有一个问题：这个线程池能否保证有序性呢？

答案是肯定的，请看下面这张图：
![图片描述](https://img1.sycdn.imooc.com/5f3dd5c5000134bc07070887.png)

这里有个非常重要的接口 ——OrderedEventExecutor，从名字就可以知道，它就是用来保证有序性的。

另外，根据前面 Netty 线程池源码的剖析，我们也知道，所有的任务提交的时候是第一时间放到队列中的：

```java
private void execute(Runnable task, boolean immediate) {
        boolean inEventLoop = inEventLoop();
        addTask(task);
        if (!inEventLoop) {
            startThread();
            // ...省略其它代码
        }
    }
```

而不是像 Java 那样，把提交的任务与新创建的线程绑定，优先执行这个任务：

```java
Worker(Runnable firstTask) {
    setState(-1); // inhibit interrupts until runWorker
    this.firstTask = firstTask;
    this.thread = getThreadFactory().newThread(this);
}
final void runWorker(Worker w) {
    // 优先执行firstTask
    Runnable task = w.firstTask;
    try {
        while (task != null || (task = getTask()) != null) {
            try {
                beforeExecute(wt, task);
                try {
                    task.run();
                } finally {
                    afterExecute(task, thrown);
                }
            } finally {
            }
        }
    } finally {
        processWorkerExit(w, completedAbruptly);
    }
}
```

所以，使用 Netty 线程池是完全可以保证任务有序执行的，而使用 Java 线程池则不行。

好了，通过这样的线程池实现，在后续的业务处理中，完全不用考虑锁的问题了，因为同一个房间的消息都在同一个线程中有序的执行，完全不需要使用锁，极大地减轻了业务开发的难度，下面我们就来愉快地实现业务逻辑吧。



 ### 业务逻辑实现

为了把代码足够地解耦，我定义了一个 MahjongProcessor 接口，每个消息都可以实现自己的处理器：

```java
public interface MahjongProcessor<T extends MahjongMessage> {
    void process(T message);
}
```

比如，以 HelloRequest 为例：

```java
@Slf4j
public class HelloRequestProcessor implements MahjongProcessor<HelloRequest> {

    @Override
    public void process(HelloRequest message) {
        log.info("receive hello request: {}", message);
        HelloResponse response = new HelloResponse();
        response.setMessage("你好，" + message.getName());
        MessageUtils.sendResponse(response);
    }
}
```

有了前面的铺垫，每个消息处理器里面只需要处理自己的消息即可，非常简单。

同样地，我们需要维护消息与处理器之间的映射，与前面消息与 cmd 的映射一样，我这里同样使用枚举的形式来实现：

```java
public enum MahjongProcessorManager {
    // 映射关系
    HELLO_REQUEST_PROCESSOR(HelloRequest.class, new HelloRequestProcessor()),
    LOGIN_REQUEST_PROCESSOR(LoginRequest.class, new LoginRequestProcessor()),
    CREATE_ROOM_REQUEST_PROCESSOR(CreateRoomRequest.class, new CreateRoomRequestProcessor()),
    ENTER_ROOM_REQUEST_PROCESSOR(EnterRoomRequest.class, new EnterRoomRequestProcessor()),
    OPERATION_REQUEST_REQUEST_PROCESSOR(OperationRequest.class, new OperationRequestProcessor()),
    START_GAME_MESSAGE_PROCESSOR(StartGameMessage.class, new StartGameMessageProcessor()),
    ;

    // 属性
    private Class<? extends MahjongMessage> msgType;
    private MahjongProcessor mahjongProcessor;

    MahjongProcessorManager(Class<? extends MahjongMessage> msgType, MahjongProcessor mahjongProcessor) {
        this.msgType = msgType;
        this.mahjongProcessor = mahjongProcessor;
    }

    // 根据消息选择处理器
    public static MahjongProcessor choose(MahjongMessage message) {
        for (MahjongProcessorManager value : MahjongProcessorManager.values()) {
            if (value.msgType == message.getClass()) {
                return value.mahjongProcessor;
            }
        }
        return null;
    }

}
```

可以看到，对于 MahjongProcessor 我们维护的是一个一个的实例，而不再是 Class 类，因为 MahjongProcessor 是设计成无状态的，整个系统只需要一个实例，即单例。

OK，此时，我们就可以在 MahjongEventExecutorGroup 中补全 execute () 的逻辑了：

```java
public class MahjongEventExecutorGroup extends MultithreadEventExecutorGroup {
    public static void execute(Channel channel, MahjongProtocol mahjongProtocol) {
        // 协议头
        MahjongProtocolHeader header = mahjongProtocol.getHeader();
        // 协议体
        MahjongMessage message = (MahjongMessage) mahjongProtocol.getBody();
        // 创建房间和加入房间需要做一些处理
        Long roomId;
        // ...省略roomId的处理

        // 设置房间id到context中，以便next()方法可以取到
        MahjongContext.currentContext().setCurrentRoomId(roomId);
        // 将消息扔到业务线程池中处理
        INSTANCE.execute(() -> {
            // 已经切换线程，重新设置房间号到context中
            MahjongContext.currentContext().setCurrentRoomId(roomId);
            // 设置channel等其它线程本地变量
            MahjongContext.currentContext().setCurrentChannel(channel);
            MahjongContext.currentContext().setChannelRoomId(channel, roomId);
            MahjongContext.currentContext().setRequestHeader(header);
            MahjongContext.currentContext().setCurrentRoom(MahjongContext.currentContext().getRoomById(roomId));

            Player currentPlayer = DataManager.getChannelPlayer(channel);
            if (currentPlayer != null) {
                MahjongContext.currentContext().setCurrentPlayer(currentPlayer);
                MahjongContext.currentContext().setPlayerChannel(currentPlayer, channel);
            }
            // 寻找处理器
            MahjongProcessor processor = MahjongProcessorManager.choose(message);
            if (processor != null) {
                // 交给处理器处理
                processor.process(message);
            } else {
                throw new RuntimeException("not found processor, msgType=" + message.getClass().getName());
            }
        });

    }
}
```

可以看到，我们这里大量使用了 MahjongContext，它其实就是一个线程本地变量池，怎么实现的呢？我提供两种思路：

1. 把每一个本地变量，比如 `currentChannel`，都声明为一个 ThreadLocal 或者 FastThreadLocal；
2. 把 MahjongContext 声明为一个 ThreadLocal 或者 FastThreadLocal，其它的变量都维护在这个 MahjongContext 中；

两种方式都是可以的，第一种方式实现起来有点繁琐，第二种方式实现起来相对简单一点，我参考 zuul 网关等框架采用了第二种实现方式：

```java
public class MahjongContext {
    // 线程安全，只需要用HashMap就可以了
    private final Map<String, Object> map = new HashMap<>();
    // 把MahjongContext本身放到FastThreadLocal中
    private static final FastThreadLocal<MahjongContext> MAHJONG_CONTEXT = new FastThreadLocal<MahjongContext>() {
        @Override
        protected MahjongContext initialValue() throws Exception {
            return new MahjongContext();
        }
    };

    private MahjongContext() {
    }
    // 当前线程的MahjongContext
    public static MahjongContext currentContext() {
        return MAHJONG_CONTEXT.get();
    }
    // 包装map的put()方法
    private void set(String key, Object value) {
        map.put(key, value);
    }
    // 包装map的get()方法
    private <T> T get(String key) {
        return (T) map.get(key);
    }
    // 包装map的remove()方法
    private void remove(String key) {
        map.remove(key);
    }
    // 设置当前玩家的channel
    public void setCurrentChannel(Channel channel) {
        set("currentChannel", channel);
    }
    // 获取当前玩家的channel
    public Channel getCurrentChannel() {
        return get("currentChannel");
    }
}
```

好了，最后，我再介绍一个稍微复杂一点的消息处理逻辑 —— 出牌。

出牌是通过 OperationRequest 这个消息来承载的，我们先分析一下它的主要逻辑：

1. 服务端收到出牌消息，先检查是不是轮到该玩家出牌了，出的这张牌玩家手里有没有，等等；
2. 从玩家手中移除这张牌，并添加到添加到出牌列表中；
3. 通知所有人谁出了什么牌，并刷新房间的信息；
4. 检查其他玩家是否可以操作；
5. 如果有玩家可以操作，则提醒其操作，并提醒其他玩家等待；
6. 如果没有玩家可以操作，则光标移动到下一个玩家；
7. 下一个玩家摸牌；
8. 检查下一个玩家摸完牌后是否可胡、可杠；
9. 如果其可胡、可杠，则提醒其操作；
10. 如果不可胡、可杠，则提醒其出牌；
11. 不管其他玩家是否可胡、可杠，对于其他玩家一律提示等待该玩家出牌；

OK，这里只列了主要逻辑，还有一些细节的点需要注意的，我就不一一列举了，这里只贴出一小部分的代码实现：

```java
@Slf4j
public class OperationRequestProcessor implements MahjongProcessor<OperationRequest> {
    @Override
    public void process(OperationRequest message) {
        // 获取当前房间信息
        Room room = MahjongContext.currentContext().getCurrentRoom();
        // 当前操作
        int operation = message.getOperation();

        // 检查
        if (room == null) {
            log.error("room not exist");
            return;
        }

        if (room.getStatus() != Room.STATUS_WAITING_CHU && room.getStatus() != Room.STATUS_WAITING_OPERATION) {
            log.error("room status error, roomStatus={}", room.getStatus());
            return;
        }

        if (room.getStatus() == Room.STATUS_WAITING_CHU && operation != OperationUtils.OPERATION_CHU) {
            log.error("operation request error, roomStatus={}, operation={}", room.getStatus(), operation);
            return;
        }

        if (room.getStatus() == Room.STATUS_WAITING_OPERATION && operation == OperationUtils.OPERATION_CHU) {
            log.error("operation request error, roomStatus={}, operation={}", room.getStatus(), operation);
            return;
        }

        if (operation == OperationUtils.OPERATION_CHU) {
            // 如果是出牌操作
            chu(room, message);
        } else {
            // 如果是其他操作，需等待所有可操作之人操作完成之后才能判断谁的操作是有效的
            operate(room, message);
        }
    }

    private void chu(Room room, OperationRequest message) {
        // 当前玩家
        Player player = MahjongContext.currentContext().getCurrentPlayer();
        // 检查是不是当前玩家出牌
        if (room.getChuPos() != player.getPos()) {
            log.error("not current player chu, roomChuPos={}, currentPlayerPos={}", room.getChuPos(), player.getPos());
            return;
        }

        byte chuCard = message.getCard();

        // 从玩家手中移除该牌
        if (!removeCard(player, chuCard)) {
            log.error("player has not that card, playerPos={}, chuCard={}", player.getPos(), chuCard);
            return;
        }

        // 添加到出牌列表中
        addToChuCards(player, chuCard);

        // 通知有人出了一张牌
        OperationResultNotification operationResultNotification = new OperationResultNotification();
        operationResultNotification.setOperation(OperationUtils.OPERATION_CHU);
        operationResultNotification.setPos(player.getPos());
        operationResultNotification.setCard(chuCard);
        MessageUtils.sendNotification(room, operationResultNotification);

        // 刷新房间信息牌
        RoomRefreshNotification refreshNotification = new RoomRefreshNotification();
        refreshNotification.setOperation(OperationUtils.OPERATION_CHU);
        refreshNotification.setRoom(room);
        MessageUtils.sendRoomRefreshNotification(refreshNotification);

        // 检查其他玩家是否可以操作
        if (!checkOtherCanOperation(room, player, chuCard)) {
            // 如果其他玩家不可以操作，移动到下一个玩家摸牌
            moveToNextPlayer(room);
        }
    }
}
```

抛却业务本身逻辑的复杂性，代码写起来是不是非常简单，完全不用关心锁的问题，完美 ^^

OK，到这里，游戏线程池的设计、业务逻辑实现的方法我就介绍完了。



 ### 后记

本节，我们一起学习了 “房间制” 游戏的线程池设计，以及业务逻辑的实现方法，你觉得这种实现方式怎么样？还有没有其它更优的解法呢？欢迎留言，共同讨论。

到此，整个服务端算是全部实现完毕了，可是，没有客户端的服务端是不完美的，所以，下一节，我们将模拟实现一个客户端，并通过这个客户端来真正的打一局，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3dd59100018ed114210776.png)





<div style="page-break-after:always;"></div>

 ## 33 Mock客户端实现，四个人来一局


![img](https://img2.sycdn.imooc.com/5f0596fb0001831006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)上天赋予的生命，就是要为人类的繁荣和平和幸福而奉献。——松下幸之助![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起学习了游戏线程池的设计，并实现了主要的业务逻辑，至此，服务端算是实现完毕了。

然而，没有客户端的服务端是不完美的，因此，本节，我们将一起实现一个模拟客户端，用它来进行调试。

最后，我们也会启动四个客户端真正地打一局。

OK，进入今天的学习吧。



 ### Mock 客户端实现



 #### 实现前

首先，我们分析一下一个 Mock 客户端它应该具备的基本功能：

1. 对于服务端返回的消息，能够友好地显示，何为友好地显示？即不要直接显示消息本身，应该做一些格式化。
2. 对于需要用户操作的内容，不能太复杂，最好能使用 1、2、3、4、5 很简单的数字代替，比如出牌，如果还要输入汉字，就会比较繁琐，交互也不好。

好了，能实现这两个功能基本上差不多了。

接下来，应该以什么样的方式呈现呢？

用命令行显示？

用 java swing 开发一个图形界面？

用客户端语言，比如 lua 或者 javascript，开发一个图形界面？

显然，后面两种方式体验更好，但是，开发成本太高，而且，对于后端程序员，用命令行的方式似乎也不错，因此，我们决定使用命令行的方式。

最后，我们需要调研一下，使用命令行如何进行交互？

在 Java 中，可以使用 `System.in.read()` 读取命令行中的输入，或者使用 Scanner 类对 System.in 进行包装也是可以的，相对来说，使用 Scanner 更简单一些，所以，我们选择使用 Scanner 类来读取用户输入。

好了，实现前我们已经确定了基本功能、呈现方式、交互方式，下面就是真刀真枪地干了。



 #### 实现中

对于客户端收到的消息，无疑是要把它渲染出来，并提供一些选项供用户操作，其实，整个过程跟服务端处理消息的逻辑是比较相像的，所以，我们仿造服务端处理消息的过程，抽象出来一个 MahjongRender 接口，不同的消息实现各自的渲染方法：

```java
public interface MahjongRender<T extends MahjongMessage> {
    void render(T message);
}
```

比如，对于 HelloResponse 这个消息，我们可以这样来实现：

```java
public class HelloResponseRender implements MahjongRender<HelloResponse> {
    @Override
    public void render(HelloResponse message) {
        System.out.println(helloResponse);
    }
}
```

当然，我们还需要维护消息与渲染器之间的关系：

```java
public enum MahjongRenderManager {
    HELLO_RESPONSE_RENDER(HelloResponse.class, new HelloResponseRender()),
    ;
    private Class<? extends MahjongMessage> msgType;
    private MahjongRender mahjongRender;

    MahjongRenderManager(Class<? extends MahjongMessage> msgType, MahjongRender mahjongRender) {
        this.msgType = msgType;
        this.mahjongRender = mahjongRender;
    }

    public static MahjongRender choose(MahjongMessage message) {
        // 通过消息寻找它的渲染器
        for (MahjongRenderManager value : MahjongRenderManager.values()) {
            if (value.msgType == message.getClass()) {
                return value.mahjongRender;
            }
        }
        return null;
    }
}
```

同样地， 对于渲染器，我们使用的也是单例模式。

这样，我们就可以在 MahjongClientHandler 中确定哪个消息使用哪个渲染器来处理了：

```java
@Slf4j
public class MahjongClientHandler extends SimpleChannelInboundHandler<MahjongProtocol> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, MahjongProtocol mahjongProtocol) throws Exception {
        // 协议头
        MahjongProtocolHeader header = mahjongProtocol.getHeader();
        // 协议体
        MahjongMessage message = (MahjongMessage) mahjongProtocol.getBody();
        // 查找渲染器
        MahjongRender mahjongRender = MahjongRenderManager.choose(message);
        if (mahjongRender != null) {
            MahjongContext.currentContext().setCurrentChannel(ctx.channel());
            mahjongRender.render(message);
        } else {
            log.error("not found render, msgType={}", message.getClass().getName());
        }
    }
}
```

为了方便，我又定义了一个类 MockClient，把实际的渲染全部放在了这个类中，比如，对于 HelloResponse，它的渲染器，只做一层简单的转发，实际的工作是在 MockClient 中：

```java
public class HelloResponseRender implements MahjongRender<HelloResponse> {
    @Override
    public void render(HelloResponse message) {
        MockClient.helloResponse(message);
    }
}
public class MockClient {

    public static void helloResponse(HelloResponse helloResponse) {
        System.out.println(helloResponse);
    }
}
```

好了，到这里，Mock 客户端实现的基本步骤大家都比较清楚了，下面就是编写各种各样的渲染器，并把它们转发到 MockClient 中就可以了，比如，对于登录，我是这么来实现的。

首先，在客户端启动之后，给服务端发送一条 HelloRequest 的消息，隔 2 秒之后，提示用户登录：

```java
public class MockClient {

    private static final String MOCK_USER = "\r\n\r\n[mahjong@mock]$ ";

    // 用于读取用户输入
    private static Scanner scanner = new Scanner(System.in);
    // 当前玩家
    private static Player player;
    // 当前房间
    private static Room room;

    public static void start(Channel channel) {
        MahjongContext.currentContext().setCurrentChannel(channel);
        // 发送hello消息
        HelloRequest helloRequest = new HelloRequest();
        helloRequest.setName("彤哥");
        MessageUtils.sendRequest(helloRequest);

        // 停顿2秒
        LockSupport.parkNanos(TimeUnit.SECONDS.toNanos(2));

        // 请登录
        login();
    }

    public static void helloResponse(HelloResponse helloResponse) {
        System.out.println(helloResponse);
    }

    private static void login() {
        oneOperation("\r\n请输入您的用户名和密码，以空格分隔：", line -> {
            if (!line.contains(" ")) {
                return false;
            }
            String[] arr = line.split(" ");
            // 发送登录消息
            LoginRequest request = new LoginRequest();
            request.setUsername(arr[0]);
            request.setPassword(arr[1]);
            MessageUtils.sendRequest(request);
            return true;
        });
    }
    
    private static void oneOperation(String tips, Command command) {
        // 打印提示
        System.out.print(tips + MOCK_USER);
        while (scanner.hasNextLine()) {
            // 读取用户输入
            String line = scanner.nextLine();
            // 处理失败，则提示重新输入
            if (!command.run(line)) {
                System.out.println("\r\n错误的输入，请重新输入：");
            } else {
                // 处理成功，跳出循环
                break;
            }
        }
    }

    public static void loginResponse(LoginResponse message) {
        // 登录成功
        if (message.isResult()) {
            System.out.println("\r\n登录成功，您的信息为：");
            System.out.println(player = message.getPlayer());
            // 登录成功，选择创建房间还是加入房间
            createOrEnterRoom();
        } else {
            // 登录失败
            System.out.println("\r\n登录失败：" + message.getMessage() + "，请您重新登录。");
            login();
        }
    }
}
```

OK，至此，登录的过程就处理完了，登录完成之后，就是提示用户创建房间还是加入房间了，后面都是一样的实现过程，不同之处在于每个消息处理的细节。

经过一番战斗，终于把所有的消息渲染过程都实现了，最后，别忘了维护消息与渲染器的关系：

```java
public enum MahjongRenderManager {
    HELLO_RESPONSE_RENDER(HelloResponse.class, new HelloResponseRender()),
    LOGIN_RESPONSE_RENDER(LoginResponse.class, new LoginResponseRender()),
    CREATE_ROOM_RESPONSE_RENDER(CreateRoomResponse.class, new CreateRoomResponseRender()),
    ENTER_ROOM_RESPONSE_RENDER(EnterRoomResponse.class, new EnterRoomResponseRender()),
    ROOM_REFRESH_NOTIFICATION_RENDER(RoomRefreshNotification.class, new RoomRefreshNotificationRender()),
    OPERATION_NOTIFICATION_RENDER(OperationNotification.class, new OperationNotificationRender()),
    OPERATION_RESULT_NOTIFICATION_RENDER(OperationResultNotification.class, new OperationResultNotificationRender()),
    GAME_OVER_NOTIFICATION_RENDER(GameOverNotification.class, new GameOverNotificationRender()),
    SETTLEMENT_NOTIFICATION_RENDER(SettlementNotification.class, new SettlementNotificationRender()),
    ;
}
```

OK，在所有消息都渲染完毕之后，是时候来打一局了。



 #### 实现后

为了能在 XSHELL 中进行调试（cmd 也是可以的），可以添加 spring-boot 的插件，将程序打包成 jar 包，当然，我们这里只需要打包客户端的代码就可以了，服务端还是在 IDEA 中启动：

```xml
<properties>
    <start-class>com.imooc.netty.mahjong.client.MahjongClient</start-class>
</properties>
<build>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
            <configuration>
                <mainClass>${start-class}</mainClass>
            </configuration>
            <executions>
                <execution>
                    <goals>
                        <goal>repackage</goal>
                    </goals>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>
```

好了，先启动一个客户端来看看效果：

![图片描述](https://img1.sycdn.imooc.com/5f3f2dcb000156c709220601.png)
似乎还不错，再启动三个客户端来加入游戏吧：
![图片描述](https://img1.sycdn.imooc.com/5f3f2dbe0001e6d419040807.png)

其它玩家的牌全部被隐藏成 1 万了，第一个玩家打个 1 万看看：

![图片描述](https://img1.sycdn.imooc.com/5f3f2dd90001a4ad19030810.png)
正好玩家 3 可以碰，碰一个嗮：

![图片描述](https://img1.sycdn.imooc.com/5f3f2e030001360119010808.png)
玩家 1 可以胡了，果断胡之，当然，这里的胡牌算法并没有真正的实现，而是使用的随机算法模拟胡牌算法：
![图片描述](https://img1.sycdn.imooc.com/5f3f2e0e00016a9c19080808.png)

玩家 1 赢了 15 分，其他玩家各输了 5 分，游戏结束。

好了，到这里，Mock 客户端就实现完毕了，通过 Mock 客户端，在命令行打牌，终于可以在上班时间愉快地划水了，关键是还不容易被发现，哈哈～～



 ### 后记

本节，我们一起实现了 Mock 客户端，并通过 Mock 客户端真正地打了一局麻将，到这里， 整个的实战项目也算实现完毕了，但是，体验还不是特别好，比如，打完一局为什么要退出而不是继续游戏，有了前面的学习，我相信这些问题对你来说肯定可以轻松地搞定了。

不过，除了业务逻辑上的毛病，还有一些其他方面的问题，比如安全性、监控、调优等等，这些也是生产环境始终困扰我们的问题，对于这些问题，我们还是要解决的。

好了，下一节我们将进入 “实战进阶” 的篇章，将从优化的角度对本次实战项目再做一次升华，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f2e1d0001bbd812630528.png)




<div style="page-break-after:always;"></div>

 # 第 5 章 实战进阶

 ## 34 如何支持Protobuf


![img](https://img3.sycdn.imooc.com/5f0597060001180306400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)人不可有傲气，但不可无傲骨。——徐悲鸿![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

前面的章节，我们使用 Netty 完整实现了一个麻将游戏的实战项目，不过，它还只能算是一个 Demo 项目，要达到生产级，还需要做一些优化，这些优化包括：性能调优、参数调优、安全性、可扩展性、监控等多个方面。

前面，我们为了省事，使用的是 JSON 方式来序列化消息，不过，JSON 虽然容易阅读，但是性能方面确实要低不少，它的性能损耗主要体现在序列化之后的报文太大的问题。

因此，本节，我们将从性能调优的角度出发，学习如何将 JSON 替换成更高效的序列化方式 ——Protobuf。



 ### Protobuf 简介

Protocol Buffers (简称 Protobuf) ，是 Google 出品的序列化框架，与开发语言无关，和平台无关，具有良好的可扩展性。Protobuf 和所有的序列化框架一样，都可以用于数据存储、通讯协议。

Protobuf 相对于 JSON、XML、Java 序列化等其它序列化方式的优点主要体现在：

1. 序列化速度更快；
2. 序列化之后的体积更小；
3. 能够自动生成代码；
4. 支持多语言合作开发；

其中，前面两点是对性能的提升，后面两点，对于开发效率的提升也是显而易见的，通过 Protobuf 的自动生成代码框架，两端定义好协议，可以快速地进行开发，非常方便。比如，前端使用 lua，后端使用 Java，后端定义好协议，丢给前端，前端自己生成适合 lua 的协议代码，即可进入开发，无需等待后端定义接口文档等繁琐的过程。

另外，Protobuf 分成两个版本：proto2 和 proto3，如无特殊说明，本节所有内容都是基于 proto3 进行讲解的。



 ### Protobuf 的简单使用

Netty 天然就是支持 Protobuf 的，它提供了两组编解码方式的支持：

1. 一次编解码：ProtobufVarint32LengthFieldPrepender/ProtobufVarint32FrameDecoder
2. 二次编解码：ProtobufEncoder/ProtobufDecoder

对于一次编解码，它使用的是一种变异的 “长度 + 内容” 法实现的，在经典的 “长度 + 内容” 法中，长度一旦确定是不能修改的，而 Protoubf 的两个一次编解码器，它们的长度是可变的，会根据内容的大小自动适配，具体怎么实现的呢？有兴趣的同学可以去看看源码。

对于二次编解码，编码过程比较简单，将 Java 对象转换成字节数组即可，解码过程稍微复杂一点，需要传入要解码的类型，根据这个类型去反序列化，这种实现不太友好。

好了，我们以打招呼为例来简单看一下怎么使用吧。

客户端发送 hello 消息，带上当前人的姓名，服务端返回 hello + 姓名，整个过程包含两个协议：HelloRequest 和 HelloResponse。

使用 Protobuf，第一步就是定义前后端通信的协议，以`.proto` 后缀保存：

```protobuf
// 使用的版本
syntax = "proto3";
// 输出到的包名
option java_package = "com.imooc.netty.core.$34.proto";
// 是否拆分成多个文件
option java_multiple_files = true;

// HelloRequest
message HelloRequest {
    string name = 1;
}

// HelloResponse 
message HelloResponse {
    bool result = 1;
    string message = 2;
}
```

定义完协议，第二步，是根据协议生成代码，此时，需要使用到官方提供的工具，或者在 Maven 中引入相关的插件来生成，我这里使用 Maven 插件的形式生成。当然，为了能够支持 Protobuf 协议还需要引入相关的依赖：

```xml
<dependencies>
    <dependency>
        <groupId>com.google.protobuf</groupId>
        <artifactId>protobuf-java</artifactId>
        <version>3.11.4</version>
    </dependency>
</dependencies>
<build>
    <extensions>
        <extension>
            <groupId>kr.motd.maven</groupId>
            <artifactId>os-maven-plugin</artifactId>
            <version>1.4.1.Final</version>
        </extension>
    </extensions>
    <plugins>
        <plugin>
            <groupId>org.xolstice.maven.plugins</groupId>
            <artifactId>protobuf-maven-plugin</artifactId>
            <version>0.5.1</version>
            <configuration>
                <protocArtifact>
                    com.google.protobuf:protoc:3.1.0:exe:${os.detected.classifier}
                </protocArtifact>
            </configuration>
        </plugin>
    </plugins>
</build>
```

使用 Maven 插件需要把上述定义的文件放到 `src/main/proto` 目录下面，在 IDEA 中双击 probobuf compile，即可生成 Java 文件：

![图片描述](https://img1.sycdn.imooc.com/5f3f2e530001d86705610727.png)
生成好的文件在 target 目录下面：
![图片描述](https://img1.sycdn.imooc.com/5f3f2e620001a23505440347.png)

将这些文件 “移动” 到 `src/main/java` 下对应的目录就可以使用了。

我们先来看看如何实现服务端：

```java
public class ProtobufServer {

    public static void main(String[] args) throws Exception {
        // ...省略其他代码
        serverBootstrap.childHandler(new ChannelInitializer<SocketChannel>() {
            @Override
            public void initChannel(SocketChannel ch) throws Exception {
                ChannelPipeline p = ch.pipeline();
                // 一次编解码
                p.addLast(new ProtobufVarint32FrameDecoder());
                p.addLast(new ProtobufVarint32LengthFieldPrepender());
                // 二次编解码，解码器必须传入具体的类型
                p.addLast(new ProtobufDecoder(HelloRequest.getDefaultInstance()));
                p.addLast(new ProtobufEncoder());
                // 服务端处理器
                p.addLast(new DefaultEventLoopGroup(), new ProtobufServerHandler());
            }
        });

    }
}
public class ProtobufServerHandler extends SimpleChannelInboundHandler<HelloRequest> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, HelloRequest msg) throws Exception {
        // 响应
        HelloResponse helloResponse = HelloResponse.newBuilder()
                .setResult(true)
                .setMessage("hello " + msg.getName())
                .build();
        
        ctx.writeAndFlush(helloResponse);
    }
}
```

请注意，ProtobufDecoder 需要传入一个 HelloRequest 的实例。

我们再来看看如何实现客户端：

```java
public class ProtobufClient {

    public static void main(String[] args) throws Exception {
        // ...省略其他代码
        bootstrap.handler(new ChannelInitializer<SocketChannel>() {
            @Override
            protected void initChannel(SocketChannel ch) throws Exception {
                ChannelPipeline p = ch.pipeline();
                // 一次编解码
                p.addLast(new ProtobufVarint32FrameDecoder());
                p.addLast(new ProtobufVarint32LengthFieldPrepender());
                // 二次编解码，解码器必须传入具体的类型
                p.addLast(new ProtobufDecoder(HelloResponse.getDefaultInstance()));
                p.addLast(new ProtobufEncoder());
                // 客户端处理器
                p.addLast(new ProtobufClientHandler());
            }
        });
    }
}
public class ProtobufClientHandler extends SimpleChannelInboundHandler<HelloResponse> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, HelloResponse msg) throws Exception {
        if (msg.getResult()) {
            System.out.println(msg.getMessage());
        }
    }
}
```

注意，ProtobufDecoder 需要传入一个 HelloResponse 的实例。

整个实现过程非常简单，我就不演示结果了。

但是，这里有一个坑就是 ProtobufDecoder 解码器，它必须传入一个参数，指定你要解码成哪个类型，这使得服务端和客户端只能对一种消息类型进行编解码，在我们的麻将实战项目中，使用的是 MahjongProtocol，看似满足条件，实则不满足，还记得 MahjongProtocol 的 body 吗？它是 MahjongProtocolBody 接口类型，如果在 ProtobufDecoder 中使用，它将不知道 body 具体解码成哪个类型，所以，ProtobufDecoder 编码器似乎不太适用于我们的场景，针对这种场景，我们应该怎么处理呢？

我这里提供两种思路：

1. 编写自己的 ProtobufDecoder，从 header 中取出 cmd，再根据 cmd 取出 body 的类型，再使用 protobuf 解码；
2. 把 MahjongProtocol 定义为大消息，里面包含所有的消息类型，而不是现在的 body 形式，MahjongProcessor 中参数修改为 MahjongProtocol，根据 header 中的 cmd 选择对应的 MahjongProcessor，在具体的 MahjongProcessor 中再调用 getXxx () 方法获取真正的消息内容，比如 LoginRequestProcessor 中调用 getLoginRequest ()；

其中，第一种方式对现有代码改动量较少且解析方式保持一致，第二种方式对现有代码改动量较大，故此处我们采用第一种方式对项目进行改造，使其支持 Protobuf。



 ### 项目改造

通过上面的简单案例，我们会发现，生成的消息都实现了 MessageLite 接口，而且，我们已经确定了保持现有协议基本不变，即还是分成 header 和 body 两个部分，所以，需要将 body 的类型换成 MessageLite：

```java
public final class MahjongProtocol {
    /**
     * 协议头
     */
    private MahjongProtocolHeader header;
    /**
     * 协议体
     */
    private MessageLite body;
}
```

那么，下面我们将如何进行改造呢？

我认为通过下面的步骤来改造要轻松一些：

1. 把 pom.xml 中引用的 JSON 依赖去除，并添加 Protobuf 的依赖和插件；
2. 编写 Protobuf 协议文件，把之前定义的消息全部使用 Protobuf 语法全部写一遍；
3. 删除 MahjongProtocolBody 和 MahjongMessage 这两个接口；
4. 修改所有 MahjongMessage 为 MessageLite；
5. 修改服务启动编解码器；
6. 修改其他报错的地方；

OK，让我们按照这个步骤来走一遍。



 ##### 去除 JSON 依赖，添加 Protobuf 依赖和插件

这一步比较简单，相关的依赖和插件在上面案例讲过了，这里就不再赘述了。



 ##### 编写 Protobuf 协议文件

我们以下面四条协议为例简单讲一下编写 proto 文件应该注意的点：

```protobuf
// 使用的版本
syntax = "proto3";
// 输出到的包名
option java_package = "com.imooc.netty.mahjong.common.proto";
// 是否拆分成多个文件
option java_multiple_files = true;

message LoginRequest {
    string username = 1;
    string password = 2;
}

message LoginResponse {
    bool result = 1;
    PlayerMsg player = 2;
    string message = 3;
}

message OperationRequest {
    int32 operation = 1;
    int32 pos = 2;
    int32 card = 3;
}
message PlayerMsg {
    int64 id = 1;
    string username = 2;
    string password = 3;
    int32 score = 4;
    int32 pos = 5;
    bytes cards = 6;
    bytes chuCards = 7;
    bytes pengList = 8;
    bytes gangList = 9;
}
```

1. 在第一行要定义协议的语法（版本信息），默认为 proto2，使用 proto3 需要显式地指定；
2. 协议文件无法引用外部类，所以需要把房间信息和玩家信息也定义成相应的协议，不过，多个 proto 文件之间是可以相互引用的；
3. 协议文件无法支持 `byte` 类型，不足 4 个字节的数值类型统一使用 int32，还有 uint32、sint32、fixed32、sfixed32 也可以使用，略微有些差别，虽然不支持字节类型，但是在编码的时候会根据实际占用的字节数进行压缩，所以，不怕；
4. 字节数组可以使用 `bytes` 类型，对应到 Java 的 `ByteString` 类，可以支持遍历、按索引取值等操作，不支持修改；
5. 协议文件不支持数组，如果表示多个，可以在前面加上 `repeated`，生成的类中使用的是 `List<T>` 表示的；
6. 生成的类不支持修改，一般只作查询使用，如果要修改会很麻烦，需要重新 build，所以，我们依然保留原来的 Room 和 Player 领域对象，只有发送消息的时候才将他们转换成 RoomMsg 和 PlayerMsg。

OK，编写完协议文件，双击 maven 插件，即可生成相应的类，把这些类移动到 `com.imooc.netty.mahjong.common.proto` 包下面，注意是移动，不是复制，复制后 target 目录下面还有一份源文件，启动项目的时候会报重复的类错误。



 ##### 删除 MahjongProtocolBody 和 MahjongMessage 接口

选中这两个接口，按下 Delete 即可，不要犹豫。



 ##### 修改所有 MahjongMessage 为 MessageLite

这个主要是在各个接口中：MessageManager、MahjongProcessorManager、MahjongRenderManager 等，还有 MahjongEventExecutorGroup 中，修改起来还算比较容易。



 ##### 修改服务启动编解码器

根据前面的描述，对于一次编解码，我们完全可以换成 ProtobufVarint32LengthFieldPrepender 和 ProtobufVarint32FrameDecoder，所以，直接把原来的一次编解码删除。

对于二次编解码，总体逻辑跟原来是一致的，其实编解码类本身并不需要修改，主要逻辑都在 MahjongProtocol 类中，可以参考 ProtobufEncoder 和 ProtobufDecoder 的写法，修改为如下：

```java
public final class MahjongProtocol {
    /**
     * 协议头
     */
    private MahjongProtocolHeader header;
    /**
     * 协议体
     */
    private MessageLite body;

    public void decode(ByteBuf msg) throws InvalidProtocolBufferException {
        MahjongProtocolHeader header = new MahjongProtocolHeader();
        // 解码header
        header.decode(msg);
        this.header = header;

        // 命令字
        int cmd = header.getCmd();
        // 根据命令字获取body的真实类型
        MessageLite msgType = getBodyTypeByCmd(cmd);

        // 解码body
        final byte[] array;
        final int offset;
        final int length = msg.readableBytes();
        if (msg.hasArray()) {
            array = msg.array();
            offset = msg.arrayOffset() + msg.readerIndex();
        } else {
            array = ByteBufUtil.getBytes(msg, msg.readerIndex(), length, false);
            offset = 0;
        }

        this.body = msgType.getParserForType().parseFrom(array, offset, length);
    }

    private MessageLite getBodyTypeByCmd(int cmd) {
        return MessageManager.getMsgTypeByCmd(cmd);
    }

    public void encode(ByteBuf buffer) {
        header.encode(buffer);
        buffer.writeBytes(body.toByteArray());
    }
}
```

可以看到，编码非常简单，解码的过程相对复杂一些，我们根据 cmd 从 MessageManager 中拿到实际的消息类型，再通过一系列操作解析出 body。

当然，不要忘记修改 MahjongClient 和 MahjongServer 中的 Pipeline：

```java
// 一次编解码器
p.addLast(new ProtobufVarint32FrameDecoder());
p.addLast(new ProtobufVarint32LengthFieldPrepender());
// 二次编解码器
p.addLast(new MahjongProtocolDecoder());
p.addLast(new MahjongProtocolEncoder());
// 处理器
p.addLast(new MahjongServerHandler());
```



 ##### 修改其他报错的地方

这个步骤特别繁琐，主要都是消息构造方式的改变带来的锅，以前构造消息是这样的：

```java
LoginResponse response = new LoginResponse();
response.setResult(false);
response.setMessage("username error");
MessageUtils.sendResponse(response);
```

现在构造消息变成了这样：

```java
LoginResponse response = LoginResponse
        .newBuilder()
        .setResult(false)
        .setMessage("username error")
        .build();
MessageUtils.sendResponse(response);
```

要把所有发送消息的地方都修改一遍，是个体力活。

这个步骤修改完成后，基本上就差不多了，还有一些报错的地方再针对性的修改即可。

OK，当我们全部修改完成后，启动四个客户端来打一局试试：
![图片描述](https://img1.sycdn.imooc.com/5f3f2e7d000183ae19050804.png)

注意观察出牌结果、格式化、牌局刷新等情况是否都跟之前保持一致，可以发现，除了直接打印的消息换行有点奇怪，其他的都是没问题的。关于直接打印消息的换行问题，在 Protobuf 中是使用 `\n` 表示换行，在 XSHELL 中使用 `\r\n` 表示换行，所以，这个问题可以忽略。

OK，到此，Protobuf 改造完毕。



 ### 后记

本节，我们一起将 JSON 序列化更改为了 Protobuf 的形式，可以看到，如果前期没有规划好，到后期再去动架构层面的东西是非常痛苦的。

如果老板说，我们现在要做微信小游戏了，此时应该怎么办？

下一节，我们将从可扩展性的角度来分析，如何让服务端支持 WebSocket 协议，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f2e88000161e115911241.png)





<div style="page-break-after:always;"></div>

 ## 35 如何支持WebSocket


![img](https://img2.sycdn.imooc.com/5f0597120001b3d106400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才就是这样，终身努力，便成天才。——门捷列夫![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们从性能的角度一起学习了如何支持 Protobuf，并对整个实战项目进行了改造，工作量还是有点大的。

本节，我们将从扩展性的角度一起学习如何支持 WebSocket 协议，什么是 WebSocket 协议？为什么要使用 WebSocket 协议呢？扩展性体现在哪里呢？对于项目又该如何改造呢？

让我们带着这些问题进入今天的学习吧。



 ### WebSocket 协议是什么？

WebSocket，是 HTML5 开始提供的一种在单个 TCP 连接上进行全双工通信的协议，它的建立连接的过程是基于 Http 协议的，需要客户端发送一个 Http 请求，并携带升级为 WebSocket 协议的头，服务端收到这个请求会尝试把这个 Http 请求升级为 WebSocket 请求，并返回给客户端类似的报文。客户端与服务端之间只有这一条请求是 Http 的，之后的通信都是基于 WebSocket 协议的了。

客户端发送的报文：

```java
GET http://127.0.0.1:8080/websocket HTTP/1.1
Host: 127.0.0.1:8080
Upgrade: websocket
Connection: Upgrade
Pragma: no-cache
Cache-Control: no-cache
User-Agent: Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/78.0.3904.108 Safari/537.36
Origin: http://127.0.0.1:8080
Sec-WebSocket-Version: 13
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Sec-WebSocket-Key: VPGPDF5FOFK2wkrmTxNIgg==
Sec-WebSocket-Extensions: permessage-deflate; client_max_window_bits
```

服务端返回的报文：

```java
HTTP/1.1 101 Switching Protocols
upgrade: websocket
connection: upgrade
sec-websocket-accept: Knk4EsfLZFClttKFPqd98QXUagU=
sec-websocket-extensions: permessage-deflate
```

相比较于传统的 Http 协议，WebSocket 协议具有以下优势：

1. 是一种长连接，建立一次连接可以复用；
2. 全双工，服务端可以主动向客户端推送消息；
3. header 很小，不像 Http 请求一次需要传输大量的 header 头信息；
4. 可以支持二进制传输，不像 Http 协议是基于文本的；
5. 实时性更好，服务端可以主动推送，因此，客户端不需要轮询；

问题来了，WebSocket 虽然好，那么，我们是否一定要使用它呢？

不一定，看具体的业务场景，比如，做一个后端 RPC 框架，它完全不会跟 Web 打交道，那就可以不用考虑。如果你的应用是需要跟前端（安卓、IOS、Web、小程序）有交互的，那我建议你前期就把 WebSocket 协议考虑在内，毕竟谁也无法预测哪天是不是就要把安卓改成小程序呢，比如，同花顺（炒股软件），它的数据实时更新都是服务端主动推送给客户端的，前期它只有 APP 端，后面有了小程序端，如果前期不支持 WebSocket 协议，后期升级风险就很大。

对于，我们的麻将实战项目也是一样，谁也无法预测老板哪天是不是就要做小程序端的麻将了，所以，我们前期就支持 WebSocket 协议会比较妥当。



 ### Netty 如何使用 WebSocket 协议？

Netty 天然就是支持 WebSocket 协议的，WebSocket 的相关处理位于 `netty-codec-http` 工程下面的 `io.netty.handler.codec.http.websocketx` 包中，那么，怎么在 Netty 中使用 WebSocket 协议呢？

Netty 都替你想好了，在 `netty-example` 工程有现成的案例，不过，那个案例还是有点小复杂，我简化了一下，以下是服务端的代码：

```java
public class WebSocketServer {

    private static final String WEBSOCKET_PATH = "/websocket";
    private static final int PORT = 8080;

    public static void main(String[] args) throws InterruptedException {
        EventLoopGroup bossGroup = new NioEventLoopGroup(1);
        EventLoopGroup workerGroup = new NioEventLoopGroup();
        try {
            ServerBootstrap b = new ServerBootstrap();
            b.group(bossGroup, workerGroup)
                    .channel(NioServerSocketChannel.class)
                    .handler(new LoggingHandler(LogLevel.INFO))
                    .childHandler(new ChannelInitializer<SocketChannel>() {
                        @Override
                        protected void initChannel(SocketChannel ch) throws Exception {
                            ChannelPipeline pipeline = ch.pipeline();
                            // 添加Http协议编解码器、处理器
                            pipeline.addLast(new HttpServerCodec());
                            pipeline.addLast(new HttpObjectAggregator(65536));
                            // 添加WebSocket处理器
                            pipeline.addLast(new WebSocketServerCompressionHandler());
                            pipeline.addLast(new WebSocketServerProtocolHandler(WEBSOCKET_PATH, null, true));
                            pipeline.addLast(new WebSocketFrameHandler());
                        }
                    });

            Channel ch = b.bind(PORT).sync().channel();
            ch.closeFuture().sync();
        } finally {
            bossGroup.shutdownGracefully();
            workerGroup.shutdownGracefully();
        }
    }
}

class WebSocketFrameHandler extends SimpleChannelInboundHandler<WebSocketFrame> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, WebSocketFrame frame) throws Exception {
        if (frame instanceof TextWebSocketFrame) {
            String request = ((TextWebSocketFrame) frame).text();
            // 回写给客户端，转换成大写
            ctx.channel().writeAndFlush(new TextWebSocketFrame(request.toUpperCase(Locale.US)));
        } else {
            String message = "unsupported frame type: " + frame.getClass().getName();
            throw new UnsupportedOperationException(message);
        }
    }
}
```

是不是超级简单，只需要添加 5 个 Handler 就可以了，让我们来测试一下。

打开百度，搜索 “websocket 在线测试”，会出来很多结果，随便打开一个，输入地址 “ws://localhost:8080/websocket”，连接到服务器，在下面的框框中输入任意内容，发送后服务端都会返回一个转换成大写的响应返回，说明服务端是 OK 的。
![图片描述](https://img1.sycdn.imooc.com/5f3f2ef50001403009460405.png)

使用就是如此简单，那么，对于我们的实战项目该如何改造呢？



 ### 项目如何改造？

了解项目改造之前，我们有必要先了解一下 WebSocket 协议的报文结构：
![图片描述](https://img1.sycdn.imooc.com/5f3f2f35000155da10260387.jpg)

可以看到，使用 WebSocket 传输的时候它本身是会指定传输内容的大小的，所以，对于一次编解码，我们直接交给 WebSocket 就可以了，通过上面的案例也可以发现，通过 WebSocket 接收到的内容最终会被转化为 TextWebSocketFrame，我们直接从 TextWebSocketFrame 里面拿解码之后的内容就可以了。

不过，我们的情况似乎不太一样，TextWebSocketFrame 只是用来传输文本，如果是用之前的 JSON 序列化的话，使用 TextWebSocketFrame 问题不大，但是，我们已经改成 Protobuf 了，它是一种二进制的序列化方式，所以，WebSocket 能不能支持二进制传输呢？

答案是肯定的，找到 TextWebSocketFrame 的父类， 在 IDEA 中按 CTRL+ALT+B 查看其所有子类：
![图片描述](https://img1.sycdn.imooc.com/5f3f2f460001389709130225.png)

可以看到，第一个就是二进制的帧协议，使用它就完事了。

好了，我们先从服务端开始，以服务端接收请求为例，它收到请求之后会解析出 BinaryWebSocketFrame，它里面存储的内容就是 MahjongProtocol 编码之后的二进制数据，所以，在这之后，还需要对 MahjongProtocol 的二进制解码，也就是二次解码，这个可以复用之前的 MahjongProtocolDecoder，后面的过程就都一样的。
![图片描述](https://img1.sycdn.imooc.com/5f3f2f5a00012dc510260471.png)

所以，我们应该把从 BinaryWebSocketFrame 中提取出 MahjongProtocol 二进制的过程定义为一个解码器，而不是像上面简单案例中一样定义为 Handler，我们姑且叫这个解码器为 BinaryWebSocketFrameDecoder：

```java
public class BinaryWebSocketFrameDecoder extends MessageToMessageDecoder<BinaryWebSocketFrame> {

    @Override
    protected void decode(ChannelHandlerContext ctx, BinaryWebSocketFrame frame, List<Object> out) throws Exception {
        out.add(frame.content());
    }
}
```

它的实现很简单，就是从 BinaryWebSocketFrame 拿出二进制数据往后传递。

如果把 MahjongProtocolDecoder 和 BinaryWebSocketFrameDecoder 合并成一个可不可以呢？

也是可以的，只是不建议，这样分层比较清晰，每个 Decoder 都有自己的职责，组合起来也比较方便，对原有代码也没有入侵。

编码的过程正好是反过来的，让我们定义一个 BinaryWebSocketFrameEncoder，它的职责是把 MahjongProtocol 的二进制数据转换成 BinaryWebSocketFrame，发送出去：

```java
public class BinaryWebSocketFrameEncoder extends MessageToMessageEncoder<ByteBuf> {
    @Override
    protected void encode(ChannelHandlerContext ctx, ByteBuf msg, List<Object> out) throws Exception {
        BinaryWebSocketFrame binaryWebSocketFrame = new BinaryWebSocketFrame(msg);
        out.add(binaryWebSocketFrame);
    }
}
```

好了， 这样服务端基本上就 OK 了，再把 WebSocket 的那几个常规处理器加入到 Pipeline 中就可以了：

```java
ChannelPipeline p = ch.pipeline();
// 打印日志
p.addLast(new LoggingHandler(LogLevel.INFO));

// 添加Http协议编解码器、处理器
p.addLast(new HttpServerCodec());
p.addLast(new HttpObjectAggregator(65536));
// 添加WebSocket处理器
p.addLast(new WebSocketServerCompressionHandler());
p.addLast(new WebSocketServerProtocolHandler(WEBSOCKET_PATH, null, true));
// websocket编解码器
p.addLast(new BinaryWebSocketFrameDecoder());
p.addLast(new BinaryWebSocketFrameEncoder());

// 二次编解码器
p.addLast(new MahjongProtocolDecoder());
p.addLast(new MahjongProtocolEncoder());
// 处理器
p.addLast(new MahjongServerHandler());
```

最后，记得把原来的一次编解码器删除掉，其实，留着问题也不大，只是多此一举，BinaryWebSocketFrame 中存储的将不再是 MahjongProtocol 的二进制数据，而是经过 长度 + 内容法处理之后的二进制数据，因为 WebSocket 已经帮我们处理好了粘包半包的问题，所以，不需要再多此一举了。

服务端改造好了，我们再来看客户端该如何改造呢？

客户端在启动的时候是要发起一次额外的握手请求的，待这次握手完毕之后的处理过程，跟服务端就是完全一样的了，其实，对应的服务端也是有处理握手的过程的，查看源码会发现是在 WebSocketServerProtocolHandler 处理器处理的，但是，客户端主动发起握手并没有现成的处理器可以使用，所以，需要我们自己写一个。

参考官方的使用案例，我写了一个：

```java
public class HandshakerClientHandler extends SimpleChannelInboundHandler<Object> {

    // 用于发起握手请求
    private final WebSocketClientHandshaker handshaker;
    // 监听握手请求是否完成
    private ChannelPromise handshakeFuture;

    public HandshakerClientHandler(WebSocketClientHandshaker handshaker) {
        this.handshaker = handshaker;
    }

    public ChannelFuture handshakeFuture() {
        return handshakeFuture;
    }

    @Override
    public void handlerAdded(ChannelHandlerContext ctx) {
        handshakeFuture = ctx.newPromise();
    }

    @Override
    public void channelActive(ChannelHandlerContext ctx) throws Exception {
        // 连接完成后立马发起握手请求
        handshaker.handshake(ctx.channel());
    }

    @Override
    protected void channelRead0(ChannelHandlerContext ctx, Object msg) throws Exception {
        Channel ch = ctx.channel();
        // 第一个请求必然是握手请求
        if (!handshaker.isHandshakeComplete()) {
            try {
                handshaker.finishHandshake(ch, (FullHttpResponse) msg);
                System.out.println("WebSocket Client connected!");
                handshakeFuture.setSuccess();
            } catch (WebSocketHandshakeException e) {
                System.out.println("WebSocket Client failed to connect");
                handshakeFuture.setFailure(e);
            }
            return;
        } else {
            // 如果已经握手完成了，交给后面的处理器进行处理
            ctx.fireChannelRead(msg);
        }
    }

    @Override
    public void exceptionCaught(ChannelHandlerContext ctx, Throwable cause) {
        cause.printStackTrace();
        if (!handshakeFuture.isDone()) {
            handshakeFuture.setFailure(cause);
        }
        ctx.close();
    }
}
```

比一般的 Handler 稍微复杂一点，首先在连接创建完成之后立马发起握手请求，对于接收到的数据，先判断是不是握手的响应，只有响应成功了，才能视为 WebSocket 连接建立成功了，之后，就跟 Http 没啥关系了。

除了多这么一步操作，其它的跟服务端一模一样，所以，一样是修改客户端的 Pipeline：

```java
public class MahjongClient {

    static final String URL = System.getProperty("url", "ws://127.0.0.1:8080/websocket");

    public static void main(String[] args) throws Exception {
        // 工作线程池
        NioEventLoopGroup workerGroup = new NioEventLoopGroup();
        try {
            URI uri = new URI(URL);
            final HandshakerClientHandler handler =
                    new HandshakerClientHandler(
                            WebSocketClientHandshakerFactory.newHandshaker(
                                    uri, WebSocketVersion.V13, null, true, new DefaultHttpHeaders()));

            Bootstrap bootstrap = new Bootstrap();
            bootstrap.group(workerGroup);
            bootstrap.channel(NioSocketChannel.class);
            bootstrap.handler(new ChannelInitializer<SocketChannel>() {
                @Override
                protected void initChannel(SocketChannel ch) throws Exception {
                    ChannelPipeline p = ch.pipeline();

                    // 打印日志
                    p.addLast(new LoggingHandler(LogLevel.INFO));

                    p.addLast(new HttpClientCodec());
                    p.addLast(new HttpObjectAggregator(8192));
                    p.addLast(WebSocketClientCompressionHandler.INSTANCE);
                    p.addLast(handler);

                    // websocket编解码器
                    p.addLast(new BinaryWebSocketFrameDecoder());
                    p.addLast(new BinaryWebSocketFrameEncoder());

                    // 二次编解码器
                    p.addLast(new MahjongProtocolDecoder());
                    p.addLast(new MahjongProtocolEncoder());
                    // 处理器
                    p.addLast(new MahjongClientHandler());
                }
            });

            // 连接到服务端
            ChannelFuture future = bootstrap.connect(new InetSocketAddress(uri.getPort())).sync();
            // 等待WebSocket握手完成
            handler.handshakeFuture().sync();

            log.info("connect to server success");

            MockClient.start(future.channel());

            future.channel().closeFuture().sync();
        } finally {
            workerGroup.shutdownGracefully();
        }
    }
}
```

这里要注意的是，需要等待握手完成之后，才能进行后续的操作，也就是 Mock 客户端开始工作。

好了，到这里，基本客户端和服务端都改造完毕了，让我们调试起来看看效果。

先启动服务端，一切正常，再启动客户端，你会发现客户端请求发送失败，而且没有任何报错信息，经过断点跟踪，会发现抛出了一个 IllegalReferenceCountException 的异常，这个异常被设置到了 Promise 中，这个 Promise 又是什么呢？它其实是写数据时返回的一个对象，名叫 ChannelFuture，所以，我们只需要给它添加一个监听器，发送数据失败的时候打印下异常就可以了：

```java
private static void send(Channel channel, MahjongProtocol mahjongProtocol) {
        if (channel != null && channel.isActive() && channel.isWritable()) {
            ChannelFuture channelFuture = channel.writeAndFlush(mahjongProtocol);
            channelFuture.addListener(future -> {
                if (!future.isSuccess()) {
                    log.error("send message error", future.cause());
                }
            });
        } else {
            log.error("channel unavailable, channelId={}, msgType={}", channel.id(), ((MessageLite) mahjongProtocol.getBody()).getClass());
        }
    }
```

这个确实有点小复杂，没有前面的源码剖析的基础，这一块也很难定位并完善。

抛出这个异常的原因是 BinaryWebSocketFrame 直接使用了 MahjongProtocol 对应的 ByteBuf，而每一次编解码或者 Handler 处理之后，msg 的引用计数都会减一，导致 ByteBuf 的引用计数减完了，以 BinaryWebSocketFrameEncoder 为例：

```java
public class BinaryWebSocketFrameEncoder extends MessageToMessageEncoder<ByteBuf> {
    @Override
    protected void encode(ChannelHandlerContext ctx, ByteBuf msg, List<Object> out) throws Exception {
        // 直接使用的msg，这个msg就是MahjongProtocol转换后的二进制数据
        BinaryWebSocketFrame binaryWebSocketFrame = new BinaryWebSocketFrame(msg);
        out.add(binaryWebSocketFrame);
    }
}
public abstract class MessageToMessageEncoder<I> extends ChannelOutboundHandlerAdapter {
    @Override
    public void write(ChannelHandlerContext ctx, Object msg, ChannelPromise promise) throws Exception {
        //...省略其他代码
        try {
            // 调用上面的encode()
            encode(ctx, cast, out);
        } finally {
            // 调用完减了一次引用计数
            ReferenceCountUtil.release(cast);
        }
    }
```

默认地，一个 ByteBuf 创建完成之后它只能被使用一次，如果需要重复使用这个 ByteBuf，需要调用 `ReferenceCountUtil.retain(msg);` 方法给它加次数，所以，要解决这个问题也很简单，在 BinaryWebSocketFrameEncoder 中显式地调用一下这个方法：

```java
public class BinaryWebSocketFrameEncoder extends MessageToMessageEncoder<ByteBuf> {
    @Override
    protected void encode(ChannelHandlerContext ctx, ByteBuf msg, List<Object> out) throws Exception {
        // 显式地增加引用计数
        ReferenceCountUtil.retain(msg);
        // 直接使用的msg，这个msg就是MahjongProtocol转换后的二进制数据
        BinaryWebSocketFrame binaryWebSocketFrame = new BinaryWebSocketFrame(msg);
        out.add(binaryWebSocketFrame);
    }
}
```

同样地，BinaryWebSocketFrameDecoder 以及 HandshakerClientHandler 也有同样的问题，分别调用一下这个方法即可：

```java
public class BinaryWebSocketFrameDecoder extends MessageToMessageDecoder<BinaryWebSocketFrame> {

    @Override
    protected void decode(ChannelHandlerContext ctx, BinaryWebSocketFrame frame, List<Object> out) throws Exception {
        ReferenceCountUtil.retain(frame.content());
        out.add(frame.content());
    }
}
public class HandshakerClientHandler extends SimpleChannelInboundHandler<Object> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, Object msg) throws Exception {
        Channel ch = ctx.channel();
        // 第一个请求必然是握手请求
        if (!handshaker.isHandshakeComplete()) {
            //...省略其他代码
        } else {
            // 如果已经握手完成了，交给后面的处理器进行处理
            ReferenceCountUtil.retain(msg);
            ctx.fireChannelRead(msg);
        }
    }
}
```

修改完毕之后，重启服务端、客户端，发现一切都正常了，我这里就不演示了。



 ### 后记

本节，我们一起学习了如何在 Netty 中使用 WebSocket 协议，并将我们的项目改造成了支持 WebSocket，期间还发现了一个小问题。

细心的同学可能会想，这样显式地调用 `ReferenceCountUtil.retain(msg);` 真的好么？会不会有内存泄漏的风险？

这个问题我们后面再详细讨论，下一节，我将从安全性的角度出发，给实战项目添加上安全的外衣，减少被攻击被窃取数据的风险，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f2f920001fa8a16002170.png)







<div style="page-break-after:always;"></div>

 ## 36 如何增加安全性


![img](https://img2.sycdn.imooc.com/5f05971e0001d17b06400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)人的差异在于业余时间。——爱因斯坦![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起从扩展性的角度将实战项目的通信协议修改为了 WebSocket，有了 WebSocket，服务端可能很轻松地适配各端各语言，但是，如果我们的应用是暴露在外网的，还缺乏安全性。

因此，本节，我将从安全性的角度来给实战项目添加上安全的外衣，增加连接和数据的安全性。

好了，让我们开始今天的学习吧。



 ### 何为安全性？

安全，是一个非常广泛地词，从广义上来讲，对于我们的应用，分为内部安全和外部安全。

内部安全，即系统本身是不是安全，有没有 OOM 的风险，数据是否加密存储，等等。

外部安全，即外部系统访问该系统是不是安全，连接是否可靠，是否是非法连接，传输数据是否安全，等等。

本节，我们讨论的主题主要是外部安全，对于外部安全，我把它分成三个部分：连接可靠性、连接合法性、数据安全性，我们一起来学习 Netty 是怎么解决这些问题的。



 ### 连接可靠性

身为互联网人，你肯定听过一个词 ——keepalive，在不同的场合，它可能还会被称为心跳监测、空闲检测等，它的主要目的是为了告诉服务端，我还活着，不要关闭我的连接。

常用的处理方法是客户端定时的给服务端发送一个心跳包，服务端隔一定时间没收到这个客户端的心跳包，则认为它死了，可以把它关闭了。

但是，这样有个缺陷，如果客户端本身一直在和服务端交互，这种定时发送的方式就有点浪费带宽和流量，所以，比较好的方法是，客户端检测一定时间没跟服务端交互了才发送一个心跳包，服务端隔一定时间没收到客户端的请求了才认为它可以关闭了。

那么，在 Netty 中，我们该如何实现呢？

其实，Netty 天然就支持空闲检测，不过还缺少心跳的部分，正好上一节介绍的 WebSocket 是支持心跳协议的，两者结合起来就达到了 “空闲检测 + 心跳” 的目的。

> 在 WebSocket 中，是通过 Ping/Pong 这一对消息来表示心跳的，它们分别是 PingWebSocketFrame 和 PongWebSocketFrame。

好了，让我们先看服务端的实现：

```java
@Slf4j
public class ServerIdleCheckHandler extends IdleStateHandler {
    // 重写构造方法
    public ServerIdleCheckHandler() {
        // 10秒钟没收到读事件就认为是空闲了
        super(10, 0, 0);
    }

    @Override
    protected void channelIdle(ChannelHandlerContext ctx, IdleStateEvent evt) throws Exception {
        if (evt == IdleStateEvent.FIRST_READER_IDLE_STATE_EVENT) {
            log.error("idle check close the client");
            // 检测到读空闲则关闭连接
            ctx.close();
            return;
        }
        super.channelIdle(ctx, evt);
    }
}
```

是不是非常简单？！只需要继承 IdleStateHandler 即可，重写构造方法指定空闲时间，并在 channelIdle () 方法中处理空闲事件。

然后，别忘了将其添加到 Pipeline 中，可以把它放在前面：

```java
ChannelPipeline p = ch.pipeline();
// 打印日志
p.addLast(new LoggingHandler(LogLevel.INFO));

// 空闲检测 ********
p.addLast(new ServerIdleCheckHandler());

// 添加Http协议编解码器、处理器
p.addLast(new HttpServerCodec());
p.addLast(new HttpObjectAggregator(65536));
// 添加WebSocket处理器
p.addLast(new WebSocketServerCompressionHandler());
p.addLast(new WebSocketServerProtocolHandler(WEBSOCKET_PATH, null, true));
// websocket编解码器
p.addLast(new BinaryWebSocketFrameDecoder());
p.addLast(new BinaryWebSocketFrameEncoder());

// 二次编解码器
p.addLast(new MahjongProtocolDecoder());
p.addLast(new MahjongProtocolEncoder());
// 处理器
p.addLast(new MahjongServerHandler());
```

好了，再来客户端的实现：

```java
public class ClientIdleCheckHandler extends IdleStateHandler {
    public ClientIdleCheckHandler() {
        super(0, 5, 0);
    }
}
```

客户端除了要实现空闲检测外，还需要发送 Ping 请求，而 Ping 请求是 WebSocket 的东西，它需要经过 WebSocket 的进一步编解码，所以还需要写一个处理空闲的 Handler，要放在 WebSocket 处理器的后面：

```java
@Slf4j
public class PingPongHandler extends SimpleChannelInboundHandler<PongWebSocketFrame> {
    @Override
    protected void channelRead0(ChannelHandlerContext ctx, PongWebSocketFrame msg) throws Exception {
        // 返回pong响应
        log.info("client received pong response");
    }

    @Override
    public void userEventTriggered(ChannelHandlerContext ctx, Object evt) throws Exception {
        // 检测到是写空闲事件
        if (evt == IdleStateEvent.FIRST_WRITER_IDLE_STATE_EVENT) {
            log.info("idle check, send ping request");

            // 发送ping请求
            ByteBuf buffer = ctx.alloc().buffer();
            buffer.writeBytes(new byte[] {6, 6, 6});
            PingWebSocketFrame frame = new PingWebSocketFrame(buffer);
            ctx.writeAndFlush(frame);
        }
        super.userEventTriggered(ctx, evt);
    }
}
```

在这个处理器中，检测到空闲了就发一个 Ping 请求给服务端，并处理 Pong 响应。

然后，把这两个 Handler 分别添加到 Pipeline 中：

```java
ChannelPipeline p = ch.pipeline();

// 打印日志
p.addLast(new LoggingHandler(LogLevel.INFO));

// 空闲检测 ********
p.addLast(new ClientIdleCheckHandler());

p.addLast(new HttpClientCodec());
p.addLast(new HttpObjectAggregator(8192));
p.addLast(WebSocketClientCompressionHandler.INSTANCE);
p.addLast(handler);

// 心跳 ********
p.addLast(new PingPongHandler());

// websocket编解码器
p.addLast(new BinaryWebSocketFrameDecoder());
p.addLast(new BinaryWebSocketFrameEncoder());

// 二次编解码器
p.addLast(new MahjongProtocolDecoder());
p.addLast(new MahjongProtocolEncoder());
// 处理器
p.addLast(new MahjongClientHandler());
```

细心的同学可能会发现，怎么没看到服务端处理 Ping 请求呢？

其实，Ping 请求的处理是在 WebSocketServerProtocolHandler 中，它接收到是 Ping 请求，直接返回了一个 Pong 响应：

```java
protected void decode(ChannelHandlerContext ctx, WebSocketFrame frame, List<Object> out) throws Exception {
    if (frame instanceof PingWebSocketFrame) {
        frame.content().retain();
        ctx.channel().writeAndFlush(new PongWebSocketFrame(frame.content()));
        readIfNeeded(ctx);
        return;
    }
    if (frame instanceof PongWebSocketFrame && dropPongFrames) {
        readIfNeeded(ctx);
        return;
    }

    out.add(frame.retain());
}
```

> 细心的同学会看到，它这里也使用了 retain () 方法，跟我们上一节用的 `ReferenceCountUtil.retain(msg);` 是一样的。

到这里，空闲检测 + 心跳 就完成了，分别启动服务端和客户端，查看日志：

```java
19:28:09 [nioEventLoopGroup-2-1] PingPongHandler: idle check, send ping request
19:28:09 [nioEventLoopGroup-2-1] PingPongHandler: client received pong response
```

一切正常，不过，试着在牌局中停顿一会，会发现，连接被无情地断开了，这是因为客户端有一个等待用户输入的操作，这个操作是阻塞的，导致客户端的心跳没有发送出去，要解决这个问题其实也很简单，在客户端添加一个业务线程池，专门处理业务逻辑：

```java
// 添加业务线程池
p.addLast(new DefaultEventLoopGroup(), new MahjongClientHandler());
```

再次运行程序，一切都正常了，我就不演示了。

好了，到这里，空闲检测 + 心跳就介绍完毕了，你 Get 到了吗？



 ### 连接合法性

其实，上面介绍的空闲检测 + 心跳的方式，在一定程度上，也包含了连接合法性的要求，你可能已经发现了，PingWebSocketFrame 是可以设置一个参数的，这个参数相当于是密钥，我们可以利用这个参数提高一定的安全性，如果是非法的客户端，它可能都不一定知道要心跳，即使知道要心跳，也不一定知道密钥是多少。

那么，我们这里说的连接合法性是什么呢？

一般是指黑白名单。

所谓黑名单，是被服务端禁止访问的用户，反之，白名单表示只有在白名单中的用户才可以访问服务端。

最简单的黑白名单实现方式，就是通过 IP 地址进行判断。

Netty 支持黑白名单吗？

天然支持。

在 Netty 中，定义了两种 IP 策略，一种是 UniqueIpFilter，一种是 RuleBasedIpFilter，前者表示一个 IP 地址只能建立一条连接，后者表示基于 IP 的过滤器，你可以设置一些规则，常用的规则是根据子网判断。

我以 RuleBasedIpFilter 为例添加一个黑名单过滤器：

```java
ChannelPipeline p = ch.pipeline();
// 打印日志
p.addLast(new LoggingHandler(LogLevel.INFO));

// 黑名单过滤器 ******
IpFilterRule ipFilterRule = new IpSubnetFilterRule("192.168.175.1", 8, IpFilterRuleType.REJECT);
p.addLast(new RuleBasedIpFilter(ipFilterRule));

// 空闲检测
p.addLast(new ServerIdleCheckHandler());

// ...省略其他
```

这里的 IpSubnetFilterRule 使用的是 CIDR 表示法，即经常看到的 `130.39.37.100/24` 表示法，有兴趣的同学可以去了解下，当然，你也可以实现 IpFilterRule 接口定义自己的规则。

此时，重启服务端，启动客户端会被无情的断开连接：

```java
21:02:45 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x11a6fb5a, L:/192.168.175.1:54759 - R:0.0.0.0/0.0.0.0:8080] CLOSE
21:02:45 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x11a6fb5a, L:/192.168.175.1:54759 ! R:0.0.0.0/0.0.0.0:8080] USER_EVENT: io.netty.channel.socket.ChannelInputShutdownReadComplete@41034074
21:02:45 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x11a6fb5a, L:/192.168.175.1:54759 ! R:0.0.0.0/0.0.0.0:8080] INACTIVE
21:02:45 [nioEventLoopGroup-2-1] AbstractInternalLogger: [id: 0x11a6fb5a, L:/192.168.175.1:54759 ! R:0.0.0.0/0.0.0.0:8080] UNREGISTERED
```

好了，黑白名单我们就介绍到这里，是不是超级简单，想不想了解源码怎么实现的？自己看去～～



 ### 数据安全性

到目前为止，前后端传输的数据还是明文的，怎么做到加密传输呢？

> 虽然已经使用 Protobuf 序列化成字节数组了，但是仍然视为明文，别人只要拿到这个数据和结构体很容易就分析出来的。

这就不得不提鼎鼎大名的 SSL/TLS 了，有兴趣的同学可以去了解下它加密传输的过程，非常有意思。

那么，Netty 支持 SSL 吗？

天然支持，一个 Handler 的事，没有什么是 Handler 不能解决的问题。

好，我们来看 Netty 如何支持 SSL，先看服务端：

```java
public class MahjongServer {

    private static final String WEBSOCKET_PATH = "/websocket";
    static final int PORT = Integer.parseInt(System.getProperty("port", "8443"));

    public static void main(String[] args) throws Exception {
        // ssl，使用自己生成的证书
        SelfSignedCertificate ssc = new SelfSignedCertificate();
        SslContext sslCtx = SslContextBuilder.forServer(ssc.certificate(), ssc.privateKey())
                .build();
        // 查看证书生成的位置
        System.out.println(ssc.certificate().getPath());

        // ...省略其他代码
        
        serverBootstrap.childHandler(new ChannelInitializer<SocketChannel>() {
            @Override
            public void initChannel(SocketChannel ch) throws Exception {
                // ...省略其他代码

                // 空闲检测
                p.addLast(new ServerIdleCheckHandler());

                // ssl，创建一个handler
                p.addLast(sslCtx.newHandler(ch.alloc()));
            }
    }
}
```

使用自己生成的证书，并通过 SslContext 生成一个 Handler 添加到 Pipeline 中即可，就是这么简单。

我们再来看看客户端的实现：

```java
public class MahjongClient {

    // 记得修改协议为wss
    static final String URL = System.getProperty("url", "wss://127.0.0.1:8443/websocket");

    public static void main(String[] args) throws Exception {
        // 创建sslContext
        SslContext sslCtx = SslContextBuilder.forClient().build();

        // 工作线程池
        NioEventLoopGroup workerGroup = new NioEventLoopGroup();
        try {
            Bootstrap bootstrap = new Bootstrap();
            bootstrap.group(workerGroup);
            bootstrap.channel(NioSocketChannel.class);
            bootstrap.handler(new ChannelInitializer<SocketChannel>() {
                @Override
                protected void initChannel(SocketChannel ch) throws Exception {
                    // ...省略其他代码
                    
                    // 空闲检测
                    p.addLast(new ClientIdleCheckHandler());

                    // ssl，创建handler
                    p.addLast(sslCtx.newHandler(ch.alloc()));
                }
            }
    }
}
```

客户端的实现基本上类似，是不是很简单？让我们运行起来看看，报错了，提示找不到证书，这是怎么回事呢？

那是因为我们的证书是自己生成的，不是从权威机构花钱买的，所以，不受信任，此时，需要把导入证书，客户端才能正常访问服务器，导入命令如下：

```java
// 导入证书
keytool.exe -import -alias netty-core -keystore "D:\Program Files\Java\jdk1.8.0_202\jre\lib\security\cacerts" -file "C:\Users\alan\AppData\Local\Temp\keyutil_example.com_8575751454001666416.crt" -storepass changeit

// 移除证书
keytool.exe -delete -alias netty-core -keystore "D:\Program Files\Java\jdk1.8.0_202\jre\lib\security\cacerts" -storepass changeit
```

注意，保存的位置是你的 IDEA 使用的 JRE 的位置下面的 `lib\security\cacerts`，我的 IDEA 一般配置的是 JDK 的目录，那就用 JDK 目录下面的 JRE 下面对应的路径，别弄错了。证书的位置在服务端启动的时候会打印出来路径。

OK，再次重启客户端，一切正常了，我就不演示了。

到此，我们也通过 SSL 的方式实现了数据安全了。



 ### 后记

本节，我们从空闲检测（心跳）、黑白名单、SSL 三个方面分别对我们的实战项目做了安全增强，在 Netty 中，使用这些技术都变得非常简单，没有什么是一个 Handler 不能搞定的事，如果真的有，那就用两个，可见，Netty 的扩展性真的是无话可说。

到这里，Netty 还可以再调优吗？

下一节，我们将从参数的角度来对实战项目进行调优，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f31cd0001419614410953.png)





<div style="page-break-after:always;"></div>

 ## 37 如何调优参数


![img](https://img3.sycdn.imooc.com/5f0597310001051206400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)我们有力的道德就是通过奋斗取得物质上的成功；这种道德既适用于国家，也适用于个人。——罗素![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起从安全性的角度对实战项目进行了改造，可以说，现在这个项目已经基本具有上线的标准了。

不过，还能够再压榨压榨，使它更健壮，那么，还有哪些手段呢？

本节，我们将从一些小的方面对实战项目进行调优，这些小的方面包括：

- 注解支持
- Native 支持
- 系统参数
- Netty 参数

其中，前两项跟参数关系不大，不过内容太零散，就放在这节一起了，请知悉。

好了，让我们进入今天的学习吧。



 ### 注解支持

说起 Netty 的注解，就不得不提 `@Sharable` 了，在 Netty 中，`@Sharable` 添加在 Handler 上，表示的是这个 Handler 没有线程安全的问题，可以被多个 Channel 共享，简单点讲，就是这个 Handler 我们可以创建为单例。

那么，该如何使用 `@Sharable` 注解呢？

其实，非常简单，加在 Handler 上面即可，这样，在往 Pipeline 中添加 Handler 的时候就可以提取出去添加为单例了，以 MahjongServerHandler 为例：

```java
@ChannelHandler.Sharable
public class MahjongServerHandler extends SimpleChannelInboundHandler<MahjongProtocol> {
    // ...省略代码
}
public class MahjongServer {
    public static void main(String[] args) throws Exception {
        try {
            // 在外部创建一个实例
            MahjongServerHandler mahjongServerHandler = new MahjongServerHandler();

            ServerBootstrap serverBootstrap = new ServerBootstrap();
            
            serverBootstrap.childHandler(new ChannelInitializer<SocketChannel>() {
                @Override
                public void initChannel(SocketChannel ch) throws Exception {
                    ChannelPipeline p = ch.pipeline();
                    // 添加到pipeline中
                    // 如果是在这里new，是每来一个Channel都会创建一个实例的
                    p.addLast(mahjongServerHandler);
                }
            });
        }
    }
}
```

我们编写的大部分 Handler 都应该是 Sharable 的，不应该在 Handler 中添加状态信息，这有点类似于 Spring 中的 Service，无状态才能作为单例来使用。

除了 @Sharable 注解，还有个 @Skip 注解，它是注解在方法上的，表示这个方法在 Pipeline 中执行的时候是跳过的，一般是放在适配类（父类）中使用，不过，一旦子类重写了这个方法，这个注解就失效了，比如 ChannelInboundHandlerAdapter 它的所有方法都加了这个注解：

```java
public class ChannelInboundHandlerAdapter extends ChannelHandlerAdapter implements ChannelInboundHandler {
    @Skip
    @Override
    public void channelRegistered(ChannelHandlerContext ctx) throws Exception {
        ctx.fireChannelRegistered();
    }
    @Skip
    @Override
    public void channelUnregistered(ChannelHandlerContext ctx) throws Exception {
        ctx.fireChannelUnregistered();
    }
    @Skip
    @Override
    public void channelActive(ChannelHandlerContext ctx) throws Exception {
        ctx.fireChannelActive();
    }
    @Skip
    @Override
    public void channelInactive(ChannelHandlerContext ctx) throws Exception {
        ctx.fireChannelInactive();
    }
    @Skip
    @Override
    public void channelRead(ChannelHandlerContext ctx, Object msg) throws Exception {
        ctx.fireChannelRead(msg);
    }
    @Skip
    @Override
    public void channelReadComplete(ChannelHandlerContext ctx) throws Exception {
        ctx.fireChannelReadComplete();
    }
    @Skip
    @Override
    public void userEventTriggered(ChannelHandlerContext ctx, Object evt) throws Exception {
        ctx.fireUserEventTriggered(evt);
    }
    @Skip
    @Override
    public void channelWritabilityChanged(ChannelHandlerContext ctx) throws Exception {
        ctx.fireChannelWritabilityChanged();
    }
    @Skip
    @Override
    @SuppressWarnings("deprecation")
    public void exceptionCaught(ChannelHandlerContext ctx, Throwable cause)
            throws Exception {
        ctx.fireExceptionCaught(cause);
    }
}
```



 ### Native 支持

所谓 Native 支持，是指在不同平台开启对应平台的特性。

比如，Linux 系统有更优的多路复用模型 Epoll，那么，我们在部署到生产环境的时候完全可以修改为使用 Epoll。

> select 和 epoll 有什么区别呢？
>
> 简单点讲，select 是轮询的方式，epoll 是回调的方式。比如，有 1000 个连接，select 是一个一个去询问有没有准备好的 IO，epoll 是当有准备好的 IO 会主动通知它，所以，select 的时间复杂度是 O (n)，epoll 的时间复杂度是 O (1)，epoll 在连接多的情况下更高效。

好了，让我们看看 Netty 如何开启 Epoll 吧。

其实也非常简单，在 `netty-transport-native-epoll` 工程下面提供了一个 `Epoll` 类，它里面有一个 `isAvailable()` 方法判断是否支持 Epoll，所以，我们只需要简单的修改启动类就可以了：

```java
public class MahjongServer {
    
    public static void main(String[] args) throws Exception {
        // 1. 声明线程池******
        EventLoopGroup bossGroup = Epoll.isAvailable()? new EpollEventLoopGroup(1) : new NioEventLoopGroup(1);
        EventLoopGroup workerGroup = Epoll.isAvailable()? new EpollEventLoopGroup() : new NioEventLoopGroup();
        try {
            // 2. 服务端引导器
            ServerBootstrap serverBootstrap = new ServerBootstrap();
            // 3. 设置线程池
            serverBootstrap.group(bossGroup, workerGroup)
                    // 4. 设置ServerSocketChannel的类型*****
                    .channel(Epoll.isAvailable()? EpollServerSocketChannel.class : NioServerSocketChannel.class);
            
            // ...省略其他代码
        } finally {
            
        }
    }
}
```

把创建 bossGroup、workerGroup 以及设置 channel 的地方修改为 Epoll 的相关实现即可，其他地方都不用修改，就能享受到 Linux 系统带来的性能提升，可以说是非常值得的。



 ### 系统参数

Netty 对系统参数的支持主要集中在 `ChannelOption` 及其子类中：

```java
public static final ChannelOption<Boolean> SO_BROADCAST = valueOf("SO_BROADCAST");
public static final ChannelOption<Boolean> SO_KEEPALIVE = valueOf("SO_KEEPALIVE");
public static final ChannelOption<Integer> SO_SNDBUF = valueOf("SO_SNDBUF");
public static final ChannelOption<Integer> SO_RCVBUF = valueOf("SO_RCVBUF");
public static final ChannelOption<Boolean> SO_REUSEADDR = valueOf("SO_REUSEADDR");
public static final ChannelOption<Integer> SO_LINGER = valueOf("SO_LINGER");
public static final ChannelOption<Integer> SO_BACKLOG = valueOf("SO_BACKLOG");
public static final ChannelOption<Integer> SO_TIMEOUT = valueOf("SO_TIMEOUT");

public static final ChannelOption<Boolean> TCP_NODELAY = valueOf("TCP_NODELAY");
```

这些参数包括了 UDP、TCP 等各种各样的参数，这些参数都是标准参数，我这里挑几个比较重要的参数讲解一下。



 ##### SO_KEEPALIVE

TCP 的心跳机制，默认关闭，我们已经有了应用层的心跳检测机制，也不需要开启此参数。

为什么不直接使用 TCP 的心跳机制呢？

原因主要有以下三点：

- TCP 的 keepalive 只能检测连接是否存在，不能检测连接是否可用。比如一方负载过高导致无法响应请求但是连接还在，此时无法判断连接是否可用。
- 超时时间过长，默认超时时间为 120 分钟，太长了。
- 如果一方无故断了，另一方会尝试重传，重传消息的优先级是大于 keepalive 的，导致连接迟迟无法断开。

所以，还是使用应用层的心跳，自己控制比较好一些。



 ##### SO_BACKLOG

用于配置最大的等待连接数，Linux 系统默认值是 128，Windows 系统默认值为 200。

这个参数的主要作用是防止一次性过来太多客户端连接，服务器处理不过来的场景，比较典型的例子是服务端重启，所有客户端都要重新建立连接，为了防止惊群效应，可以把这个参数调大一些，比如 1024 等。



 ##### TCP_NODELAY

TCP/IP 协议中针对 TCP 默认开启了 Nagle 算法。Nagle 算法通过减少需要传输的数据包，来优化网络。在内核实现中，数据包的发送和接受会先做缓存，分别对应于写缓存和读缓存。

启动 TCP_NODELAY，就意味着禁用了 Nagle 算法，允许小包的发送。

这个参数默认为 false，可以理解为延迟写，如果有非常小的报文需要发送，则需要开启该参数。

好了，关于系统参数，我就介绍这么多，还有很多其它的参数，有兴趣的同学可以自行查阅。



 ### Netty 参数

相比于 Netty 对系统参数的支持，Netty 本身的参数显然要凌乱的多，基本上是哪里使用哪里定义，使用 IDEA 的同学可以使用全局搜索（CTRL+SHIRT+F），输入 `"io.netty.`（前面加个引号）：

![图片描述](https://img1.sycdn.imooc.com/5f3f31f80001e83b17850409.png)
这部分参数可以配置在程序启动参数上，比如：-Dio.netty.allocator.type=unpooled。

另外，还有一部分参数在 ChannelOption 中：

```java
public static final ChannelOption<ByteBufAllocator> ALLOCATOR = valueOf("ALLOCATOR");
public static final ChannelOption<RecvByteBufAllocator> RCVBUF_ALLOCATOR = valueOf("RCVBUF_ALLOCATOR");
public static final ChannelOption<MessageSizeEstimator> MESSAGE_SIZE_ESTIMATOR = valueOf("MESSAGE_SIZE_ESTIMATOR");
public static final ChannelOption<Integer> CONNECT_TIMEOUT_MILLIS = valueOf("CONNECT_TIMEOUT_MILLIS");
public static final ChannelOption<Integer> WRITE_SPIN_COUNT = valueOf("WRITE_SPIN_COUNT");
public static final ChannelOption<WriteBufferWaterMark> WRITE_BUFFER_WATER_MARK = valueOf("WRITE_BUFFER_WATER_MARK");
public static final ChannelOption<Boolean> ALLOW_HALF_CLOSURE = valueOf("ALLOW_HALF_CLOSURE");
public static final ChannelOption<Boolean> AUTO_READ = valueOf("AUTO_READ");
public static final ChannelOption<Boolean> AUTO_CLOSE = valueOf("AUTO_CLOSE");
public static final ChannelOption<Boolean> SINGLE_EVENTEXECUTOR_PER_GROUP = valueOf("SINGLE_EVENTEXECUTOR_PER_GROUP");
```

对于这些参数，大部分情况下，我们都是不需要修改的，不过，我们还是应该做到大致了解，心中有数，这里我简单介绍几个：



 ##### io.netty.allocator.type

指定是否使用池化的分配器，默认值是 pooled，如果要使用非池化，则添加这个参数并赋值为 unpooled 即可。



 ##### io.netty.maxDirectMemory

设置 Netty 可使用的最大的直接内存空间，小于 0 表示它使用 JDK 的定义的直接内存大小，默认为 2 倍的堆内存大小，大于 0 表示 Netty 可使用的最大直接内存大小，它跟 JDK 可使用的没有任何关系，等于 0 表示它也使用 JDK 的直接内存大小，同时还会使用 JDK 的清理方式，即 Cleaner。



 ##### io.netty.noPreferDirect

不偏向于使用直接内存，默认为 false，即使用直接内存，注意这个参数的名称是 “不偏向于”，即使开启了该参数也不代表就不使用直接内存了。



 ##### io.netty.noUnsafe

不使用 Unsafe，默认为 false，即使用 Unsafe，这里的不使用 Unsafe 只代表 Netty 不使用 Unsafe，若开启该参数，则 Netty 自己不会使用 Unsafe 去操作底层数组或者直接内存，但是它调用的 JDK 的类还是有可能会使用到 Unsafe 的，比如 Java 原生的直接内存 Buffer。



 ##### CONNECT_TIMEOUT_MILLIS

客户端连接超时时间，默认为 30 秒，30 秒有点长了，可以设置短一点，比如 10 秒。

好了，我们就简单介绍这么几个参数，其实，大多数参数都是不需要修改的，了解这些参数，也能更全面地了解 Netty，在看源码的时候看到这些参数也会会心一笑。



 ### 后记

本节，我们一起从注解支持、Native 支持、系统参数、Netty 参数等四个维度更深地挖掘了一下 Netty，通过进一步改造，也能更进一步提升 Netty 应用的性能。

到这里，我们的实战项目基本上算是达到了上线的标准，不过，你敢现在就把项目部署到生产环境吗？

我想，还可以做些什么事，毕竟现在应用对于我们还是个黑盒子，使用了多少内存？连接数有多少？对于这些问题，我们一无所知。

所以，我们还需要给应用加上监控，有了监控我们心里才底，因此，下一节，我将介绍如何对 Netty 应用进行监控，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f32030001d37209510843.png)





<div style="page-break-after:always;"></div>

 ## 38 如何增加监控


![img](https://img3.sycdn.imooc.com/5f05973d0001bb2706400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才就是百分之二的灵感，百分之九十八的汗水。——爱迪生![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

通过前面章节的不断调优，我们的实战项目不管是扩展性、安全性，还是性能方面，都有了质的提升。

不过，要说现在可以上线了，总感觉还缺点什么，现在应用对我们还像一个黑盒子一样，也不知道内存使用情况、连接数情况等，也不知道有没有达到系统瓶颈。

所以，我们还需要给应用添加上监控，做到对服务运行的各种指标心里有数，才能更可控。

好了，让我们一起进入今天的学习吧。



 ### 什么是监控？

所谓监控，是指收集系统的一系列数据（指标），并以某种形式展示出来，从而达到监测系统运行状况的目的。

有了监控，我们可以提前发现系统运行的问题，比如内存持续增高，并针对性地进行修改，以防止生产出现事故。

即使生产出现事故，我们也可以利用监控数据协助排查问题，达到快速定位快速解决生产问题的目的。

那么，以上一节为例，我们如何监控 Netty 对内存的使用情况呢？



 ### 如何监控内存？

在 Java 应用程序中，内存分为堆内存和直接内存，堆内存使用 jmap、jconsole 等工具都可以很方便地查看，但是，直接内存目前也没有特别好的方法去查看，然而，Netty 使用的又是直接内存，所以，我们需要把直接内存监控起来，时刻注意 Netty 使用直接内存的情况。

那么，该如何监控 Netty 对直接内存的使用情况呢？

其实，在之前的源码分析中，我们都多多少少见过 `metric` 相关的字眼，它们就是用来做监控的，比如，在创建非池化的直接内存的 ByteBuf 时，实际创建的是它的增强类，里面就有一些监控的东西：

```java
private static final class InstrumentedUnpooledUnsafeDirectByteBuf extends UnpooledUnsafeDirectByteBuf {
    InstrumentedUnpooledUnsafeDirectByteBuf(
        UnpooledByteBufAllocator alloc, int initialCapacity, int maxCapacity) {
        super(alloc, initialCapacity, maxCapacity);
    }

    @Override
    protected ByteBuffer allocateDirect(int initialCapacity) {
        ByteBuffer buffer = super.allocateDirect(initialCapacity);
        // 增加直接内存的使用
        ((UnpooledByteBufAllocator) alloc()).incrementDirect(buffer.capacity());
        return buffer;
    }

    @Override
    protected void freeDirect(ByteBuffer buffer) {
        int capacity = buffer.capacity();
        super.freeDirect(buffer);
        // 减少直接内存的使用
        ((UnpooledByteBufAllocator) alloc()).decrementDirect(capacity);
    }
}
public final class UnpooledByteBufAllocator extends AbstractByteBufAllocator implements ByteBufAllocatorMetricProvider {
    private final UnpooledByteBufAllocatorMetric metric = new UnpooledByteBufAllocatorMetric();
    
    void incrementDirect(int amount) {
        // 监控直接内存的使用
        metric.directCounter.add(amount);
    }
}
private static final class UnpooledByteBufAllocatorMetric implements ByteBufAllocatorMetric {
    // 统计直接内存
    final LongCounter directCounter = PlatformDependent.newLongCounter();
    // 统计堆内存
    final LongCounter heapCounter = PlatformDependent.newLongCounter();
}
```

可以看到，连堆内存的使用情况也有监控到，不过，默认地，Netty 使用的是池化的直接内存的 ByteBuf，这里只能做到非池化的监控，所以，这里的直接内存的使用情况对我们的帮助并不大。

那么，还有没有其它地方有类似的监控指标呢？

答案还是在源码里，不管是池化的还是非池化的，最终都会调用到 PlatformDependent 的 `allocateDirectNoCleaner()` 方法分配内存，关于 `NoCleaner` 我们之前分析过了，它是 Netty 可以实现自己控制内存的关键，这里就不再赘述了：

```java
public static ByteBuffer allocateDirectNoCleaner(int capacity) {
    assert USE_DIRECT_BUFFER_NO_CLEANER;

    incrementMemoryCounter(capacity);
    try {
        return PlatformDependent0.allocateDirectNoCleaner(capacity);
    } catch (Throwable e) {
        decrementMemoryCounter(capacity);
        throwException(e);
        return null;
    }
}
```

这里有个 `incrementMemoryCounter(capacity)` 方法，跟踪进去：

```java
private static void incrementMemoryCounter(int capacity) {
    if (DIRECT_MEMORY_COUNTER != null) {
        long newUsedMemory = DIRECT_MEMORY_COUNTER.addAndGet(capacity);
        if (newUsedMemory > DIRECT_MEMORY_LIMIT) {
            DIRECT_MEMORY_COUNTER.addAndGet(-capacity);
            throw new OutOfDirectMemoryError("failed to allocate " + capacity
                                             + " byte(s) of direct memory (used: " + (newUsedMemory - capacity)
                                             + ", max: " + DIRECT_MEMORY_LIMIT + ')');
        }
    }
}
```

看见没，分配了多少内存，DIRECT_MEMORY_COUNTER 的值就增加多少，这不就是妥妥地监控吗？

所以，我们只需要拿到这个值，就可以监控直接内存的使用情况了，该如何拿到这值呢？

查看该值，发现它是一个私有变量，不过好在，Netty 提供了一个公共静态方法可以获取到它的值，除了它的值，我们还可以获取最大可使用的直接内存的值：

```java
public final class PlatformDependent {
    private static final AtomicLong DIRECT_MEMORY_COUNTER;
    // 已使用的直接内存
    public static long usedDirectMemory() {
        return DIRECT_MEMORY_COUNTER != null ? DIRECT_MEMORY_COUNTER.get() : -1;
    }
    // 最大可使用的直接内存
    public static long maxDirectMemory() {
        return DIRECT_MEMORY_LIMIT;
    }
}    
```

好了，现在知道我们要监控的数据在哪了，下面就是该如何实现监控了？

其实，实现监控并没有想像得那么难，简单一点，我们只需要定时的打印上面这两个值即可，稍微复杂一点，公司如果有监控平台，也可以把这两个值发送过去，使用图表更直观地监控起来。

我们这里就简单点，定时地打印到控制台。

在业界，也有一些框架可以帮我们实现监控，比如 dropwizard，本节，我们就使用它来将监控指标打印到控制台。

首先，是在 pom.xml 中添加依赖：

```xml
<dependency>
    <groupId>io.dropwizard.metrics</groupId>
    <artifactId>metrics-core</artifactId>
    <version>4.1.9</version>
</dependency>
```

然后编写一个监控的工具类：

```java
public class MetricsUtils {

    public static void start() {
        // 注册
        MetricRegistry metricRegistry = new MetricRegistry();
        metricRegistry.register("usedDirectMemory"
                , (Gauge<Long>) () -> PlatformDependent.usedDirectMemory());
        metricRegistry.register("maxDirectMemory"
                , (Gauge<Long>) () -> PlatformDependent.maxDirectMemory());
        // 打印到控制台
        ConsoleReporter consoleReporter = ConsoleReporter.forRegistry(metricRegistry).build();
        consoleReporter.start(5, TimeUnit.SECONDS);
    }
}
```

在服务端的 main () 方法中调用这个静态的 start () 方法就可以了，让我们来看看效果：

```java
20-6-27 16:37:17 ===============================================================

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 0
```

因为我现在只是启动了程序，还没有客户端连接进来，所以，usedDirectMemory 还是 0，连一个客户端进来试试：

```java
20-6-27 16:38:32 ===============================================================

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 16777223
```

usedDirectMemory 有值了，是 16M，因为默认情况下 Netty 使用的是池化的直接内存的 ByteBuf，创建第一个 ByteBuf 时需要向直接内存申请一个 PoolChunk 的大小，也就是 16M，跟内存池的知识联系起来了。

使用 Netty 的时候直接内存是一个非常重要的指标，除了这个指标，还有哪些指标应该监控起来呢？



 ### 还要监控哪些指标？

我认为一些常用的指标都可以监控起来，有些是排查问题的时候需要，有的是预警需要的，还有些可能是老板比较关心的，总结起来大概有：

1. 线程池的使用情况，监控线程数
2. 待处理任务的情况，监控每个线程的待处理任务数
3. 发送缓冲区的情况，监控服务器是否健康，是否有消息积累
4. 连接数的情况，统计日活、峰值，灰度发布的时候需要
5. 内存使用情况

等等，你还能想到哪些指标应该监控起来呢？



 ### 后记

本节，我们一起给实战项目加上了监控，有了监控，我们才能做到心里有数，能够帮助我们提前规避掉问题，甚至出现问题了，我们也可以做到不慌，协助我们快速定位问题、快速解决问题。

到这里，整个实战项目的调优就讲解完毕了，使用了这些调优手段，终于可以安心的部署到生产环境了。

但是，到了生产就一定不会出现问题吗？真的出现问题怎么办？

下一节，我将介绍一下如何快速排查生产问题，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f322d0001431a11781096.png)







<div style="page-break-after:always;"></div>

 ## 39 如何快速排查生产问题


![img](https://img1.sycdn.imooc.com/5f0597480001a91406400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)耐心是一切聪明才智的基础。——柏拉图![img](https://www.imooc.com/static/img/column/bg-r.png)





 ### 前言

你好，我是彤哥。

上一节，我们一起从监控的角度对实战项目做了增强，有了监控，不仅可以预防生产问题，还可以协助解决生产问题。

本节，我们就来谈谈如何快速排查生产问题。

好了， 进入今天的学习吧。



 ### 如何快速排查生产问题？

大家都遇到过哪些生产问题呢？

磁盘满了？

CPU 飙高？

内存溢出？

内存溢出又分好几种：堆内存溢出、元空间溢出、线程栈溢出、直接内存溢出。

在 Netty 中，最常见的当属直接内存溢出了，而内存溢出，往往又是内存泄漏导致的，所以，我们一般是排查内存泄漏。

那么，对于直接内存泄漏，我们该如何快速排查呢？

这里，我总结了几个步骤以供参考：

1. 查看监控，直接内存使用情况是否稳定；
2. 查看日志，是否有直接内存相关的报错；
3. 本地调试，关闭池化内存、添加内存泄漏检测、模拟大量请求、步步为营、耐心寻找泄漏点；

OK，我们以实战项目为例来描述一下各种步骤。



 ### 实战项目内存泄漏排查过程



 #### 伪造内存泄漏

要想复现内存泄漏，我们需要伪造一个内存泄漏的项目，我们还是以实战项目为例，添加一行代码即可：

```java
public class BinaryWebSocketFrameEncoder extends MessageToMessageEncoder<ByteBuf> {
    @Override
    protected void encode(ChannelHandlerContext ctx, ByteBuf msg, List<Object> out) throws Exception {
        // 给msg多加一次引用
        ReferenceCountUtil.retain(msg);
        ReferenceCountUtil.retain(msg);
        BinaryWebSocketFrame binaryWebSocketFrame = new BinaryWebSocketFrame(msg);
        out.add(binaryWebSocketFrame);
    }
}
```

在前面的章节中，我们也分析过，retain () 这个方法是给 ByteBuf 加引用次数的，同时，对应的 release () 方法是给 ByteBuf 减引用次数的，每调用一次 Handler（Encoder/Decoder 本质也是 Handler），这个 ByteBuf 的引用次数都会自动减 1，这个自动减 1 的操作是在父类中自动完成的，当然，也不是所有的父类都会帮你完成这个动作，比如，ChannelInboundHandlerAdapter 就不会帮你把引用次数自动减 1。

所以，我们这里多次使用的时候需要显式地给 msg 加一次引用次数，但是，一不小心，我手抖了一下，多加了一次引用次数就发到生产上了，会出现什么样的情况呢？

首先，程序是肯定可以正常运行的。

其次，内存溢出是一个非常缓慢的过程，可能十天半个月才会出现一次。

最后，导致的结果就是难以排查，无奈之下，只能重启，甚至，有的公司会写个定时任务，每天晚上系统没人用的时候偷偷地自动重启一次。

针对这种情况，我们来看看怎么排查。



 #### 查看监控

查看监控，会发现，直接内存的使用情况，呈现一条缓慢上升的曲线，类似于这样：
![图片描述](https://img1.sycdn.imooc.com/5f3f32490001c16310260292.png)

这个时间的长度可能是几个小时、一天、几天、十几天，都有可能，取决于系统的流量，随着时间的推移，最终达到了监控告警值，半夜被喊起来排查问题。



 #### 查看日志

遇到这种问题先不要慌，先去日志中查看是否有直接内存相关的报错，如果运气好是有相关日志的，拿出来分析一波，最坏的情况是完全没有，在完全没有日志可以参考的情况下，只能启用本地调试大法了。



 #### 本地调试

本地调试不是说拿到代码胡乱调试一通，也要讲究一些策略。

**第一步，关闭池化内存，为什么要关闭池化内存？**

因为，使用池化内存的时候，创建第一个 ByteBuf 的时候会分配 16M 的内存块，等这 16M 的内存块不够使用的时候才会创建下一个 16M 的内存块，而且，这 16M 使用完了之后并不会立即释放，而是交给 Netty 的内存来进行管理，方便后续复用，有内存池的干扰，很难看出内存泄漏导致的直接内存缓慢增长的过程。

下面是没有关闭池化内存的情况：

```java
-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 16777223
    
-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 16777223
    
-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 16777223
```

长期维持在 16M，也看不出有没有内存泄漏。

下面是关闭池化内存的情况：

```java
-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 0

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 1799

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 4359
```

可以看到，关闭了池化内存之后，是有一个缓慢增长的过程的。

那么，要怎么关闭池化内存呢？

这就要使用到前面章节讲过的一个参数了：`-Dio.netty.allocator.type=unpooled`，将这个参数的值设置为 unpooled 即可。

**第二步，添加内存泄漏检测，如何添加内存泄漏检测？**

这就要使用一个我们没讲过的参数了：`-Dio.netty.leakDetection.level=PARANOID`，这个参数有四个值：

- DISABLED，表示不检测内存泄漏；
- SIMPLE，表示会追踪小部分对象的内存使用情况，同时会消耗少量的资源；
- ADVANCED，表示会追踪大部分对象的内存使用情况，同时会消息大量的资源；
- PARANOID，表示会追踪所有对象的内存使用情况。

其中，默认值是 SIMPLE，四个值的强度为依次增加。

上面在查看日志的时候说的运气好，就是指这里使用 SIMPLE 的情况下有可能会有相关的日志。

在本地调试，直接开启最高级别 ——PARANOID。

**第三步，模拟大量请求，为什么要模拟大量请求呢？**

因为，上面的内存泄漏检测，只有在 gc 的时候才会打印相关的日志，平时，这些信息会保存在 Set 中，有兴趣的同学可以看看 `ResourceLeakDetector` 这个类，怎么才能快速 gc 呢？模拟大量的请求不失为一种好方法。

那么，怎么模拟大量的请求呢？

其实，也很简单，只需要在 MockClient 中加一个循环即可：

```java
public class MockClient {
    public static void start(Channel channel) {
        // 发送hello消息
        for (int i = 0; i < 1000; i++) {
            HelloRequest helloRequest = HelloRequest.newBuilder()
                    .setName("彤哥")
                    .build();
            MessageUtils.sendRequest(helloRequest);
            try {
                TimeUnit.MILLISECONDS.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

OK，此时，分别启动服务端和客户端，观察服务端的日志，正常来说，就会出现错误信息了，我这里摘取一条：

```java
07:40:04 [nioEventLoopGroup-3-2] ResourceLeakDetector: LEAK: ByteBuf.release() was not called before it's garbage-collected. See https://netty.io/wiki/reference-counted-objects.html for more information.
Recent access records: 
#1:
	io.netty.buffer.DefaultByteBufHolder.release(DefaultByteBufHolder.java:115)
	io.netty.util.ReferenceCountUtil.release(ReferenceCountUtil.java:88)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:91)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite(AbstractChannelHandlerContext.java:707)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:790)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:700)
	io.netty.channel.ChannelOutboundHandlerAdapter.write(ChannelOutboundHandlerAdapter.java:113)
	io.netty.handler.codec.http.websocketx.WebSocketCloseFrameHandler.write(WebSocketCloseFrameHandler.java:73)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite(AbstractChannelHandlerContext.java:707)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:790)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:700)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:112)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite(AbstractChannelHandlerContext.java:707)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:790)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:700)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:112)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
#2:
	io.netty.util.ReferenceCountUtil.release(ReferenceCountUtil.java:88)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:91)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite(AbstractChannelHandlerContext.java:707)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:790)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:700)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:112)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
#3:
	io.netty.buffer.AdvancedLeakAwareByteBuf.retain(AdvancedLeakAwareByteBuf.java:36)
	io.netty.util.ReferenceCountUtil.retain(ReferenceCountUtil.java:40)
	com.imooc.netty.mahjong.common.codec.BinaryWebSocketFrameEncoder.encode(BinaryWebSocketFrameEncoder.java:17)
	com.imooc.netty.mahjong.common.codec.BinaryWebSocketFrameEncoder.encode(BinaryWebSocketFrameEncoder.java:12)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite(AbstractChannelHandlerContext.java:707)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:790)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:700)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:112)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
#4:
	io.netty.buffer.AdvancedLeakAwareByteBuf.retain(AdvancedLeakAwareByteBuf.java:36)
	io.netty.util.ReferenceCountUtil.retain(ReferenceCountUtil.java:40)
	com.imooc.netty.mahjong.common.codec.BinaryWebSocketFrameEncoder.encode(BinaryWebSocketFrameEncoder.java:16)
	com.imooc.netty.mahjong.common.codec.BinaryWebSocketFrameEncoder.encode(BinaryWebSocketFrameEncoder.java:12)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite(AbstractChannelHandlerContext.java:707)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:790)
	io.netty.channel.AbstractChannelHandlerContext.write(AbstractChannelHandlerContext.java:700)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:112)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
#5:
	io.netty.buffer.AdvancedLeakAwareByteBuf.writeInt(AdvancedLeakAwareByteBuf.java:562)
	com.imooc.netty.mahjong.common.protocol.MahjongProtocolHeader.encode(MahjongProtocolHeader.java:30)
	com.imooc.netty.mahjong.common.protocol.MahjongProtocol.encode(MahjongProtocol.java:52)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:17)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:11)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
#6:
	io.netty.buffer.AdvancedLeakAwareByteBuf.writeInt(AdvancedLeakAwareByteBuf.java:562)
	com.imooc.netty.mahjong.common.protocol.MahjongProtocolHeader.encode(MahjongProtocolHeader.java:29)
	com.imooc.netty.mahjong.common.protocol.MahjongProtocol.encode(MahjongProtocol.java:52)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:17)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:11)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
#7:
	io.netty.buffer.AdvancedLeakAwareByteBuf.writeInt(AdvancedLeakAwareByteBuf.java:562)
	com.imooc.netty.mahjong.common.protocol.MahjongProtocolHeader.encode(MahjongProtocolHeader.java:28)
	com.imooc.netty.mahjong.common.protocol.MahjongProtocol.encode(MahjongProtocol.java:52)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:17)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:11)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
Created at:
	io.netty.buffer.UnpooledByteBufAllocator.newDirectBuffer(UnpooledByteBufAllocator.java:96)
	io.netty.buffer.AbstractByteBufAllocator.directBuffer(AbstractByteBufAllocator.java:187)
	io.netty.buffer.AbstractByteBufAllocator.directBuffer(AbstractByteBufAllocator.java:173)
	io.netty.buffer.AbstractByteBufAllocator.buffer(AbstractByteBufAllocator.java:107)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:16)
	com.imooc.netty.mahjong.common.codec.MahjongProtocolEncoder.encode(MahjongProtocolEncoder.java:11)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
	io.netty.channel.AbstractChannelHandlerContext.invokeWrite0(AbstractChannelHandlerContext.java:715)
	io.netty.channel.AbstractChannelHandlerContext.invokeWriteAndFlush(AbstractChannelHandlerContext.java:762)
	io.netty.channel.AbstractChannelHandlerContext$WriteTask.run(AbstractChannelHandlerContext.java:1089)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute$$$capture(AbstractEventExecutor.java:164)
	io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java)
	io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:472)
	io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:497)
	io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:989)
	io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
	io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
	java.lang.Thread.run(Thread.java:748)
: 8 leak records were discarded because the leak record count is targeted to 4. Use system property io.netty.leakDetection.targetRecords to increase the limit.
```

这是一条日志就有这么长，它记录了发生内存泄漏的那个 ByteBuf 所经过的路径，像这样的日志还有很多条躺在 Console 中，等待你去分析 ^^

**第四步，步步为营，耐心寻找泄漏点**。

这一步没有什么取巧的办法，只能慢慢分析上面的日志，或者，使用调试大法跟踪 ByteBuf 走过的路径，再慢慢缩小范围一步一步排查。

在上面日志的最后，已经明确告诉了你这个 ByteBuf 是在哪里创建的了，所以，使用调试大法的时候直接把断点打在那里一步一步往后面跟就可以了。

调试大法，前面我们已经用过太多次了，这里就不细说了，主要还是看日志，找到上面日志的 “#”3 处：

```java
#3:
	io.netty.buffer.AdvancedLeakAwareByteBuf.retain(AdvancedLeakAwareByteBuf.java:36)
	io.netty.util.ReferenceCountUtil.retain(ReferenceCountUtil.java:40)
	com.imooc.netty.mahjong.common.codec.BinaryWebSocketFrameEncoder.encode(BinaryWebSocketFrameEncoder.java:17)
	com.imooc.netty.mahjong.common.codec.BinaryWebSocketFrameEncoder.encode(BinaryWebSocketFrameEncoder.java:12)
	io.netty.handler.codec.MessageToMessageEncoder.write(MessageToMessageEncoder.java:89)
```

这里有个类叫作 “BinaryWebSocketFrameEncoder”，比较可疑，在 IDEA 中点击类名即可跳到对应的类：

```java
public class BinaryWebSocketFrameEncoder extends MessageToMessageEncoder<ByteBuf> {
    @Override
    protected void encode(ChannelHandlerContext ctx, ByteBuf msg, List<Object> out) throws Exception {
        ReferenceCountUtil.retain(msg);
        ReferenceCountUtil.retain(msg);
        BinaryWebSocketFrame binaryWebSocketFrame = new BinaryWebSocketFrame(msg);
        out.add(binaryWebSocketFrame);
    }
}
```

好吧，原来是这里多加了一次引用计数，导致这个 msg 回收不掉，最终导致内存泄漏。

把 retain () 去掉一行，重启服务端和客户端，观察服务端日志：

```java
-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 7

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 78

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 14

-- Gauges ----------------------------------------------------------------------
maxDirectMemory
             value = 1883242496
usedDirectMemory
             value = 7
```

一切都正常了，直接内存即使偶而有升高，也会很快降下来。

好了，整个排查过程就介绍完了，那么，我们在平时的开发中有没有什么好的方法可以规避这种问题呢？



 #### 预防

要想预防这种直接内存泄漏的问题，方法还是有的，最简单有效的方法就是在测试环境设置这两个参数：

- -Dio.netty.allocator.type=unpooled
- -Dio.netty.leakDetection.level=PARANOID

在测试同学压测的时候，观察一下监控的情况，如果监控出现了直接内存缓慢增长的情况，那说明就有内存泄漏了，提前排查问题提前规避，当然，排查的过程还是一样要分析日志，或者耐心调试，这是少不了的步骤。

最后，在生产环境，记得把这两个参数去掉，或者恢复到默认值。



 ### 后记

本节，我们一起研究了如何快速排查生产问题中的直接内存泄漏问题，通过模拟实战项目的直接内存泄漏，可以给我们快速积累经验，即使生产环境真的出现了，我们也可以淡然面对，快速找出真凶。

在本节的附录部分，我准备了一个小案例，看看你能不能找出其中内存泄漏的真正原因。

到此，整个专栏就趋近于尾声了，下一节，我将对整个课程做一个总结与回顾，敬请期待。



 ### 思维导图

![图片描述](https://img1.sycdn.imooc.com/5f3f32a40001ceb614170807.png)



 ### 附录 —— 直接内存泄漏的小案例

点击链接直达：https://github.com/alan-tang-tt/springcloud-gateway-oom


<div style="page-break-after:always;"></div>

 # 第 6 章 课程总结

 ## 40 课程总结与回顾


![img](https://img1.sycdn.imooc.com/5f0597550001bce006400359.jpg)

![img](https://www.imooc.com/static/img/column/bg-l.png)天才就是这样，终身努力，便成天才。——门捷列夫![img](https://www.imooc.com/static/img/column/bg-r.png)



你好，我是彤哥。

不知不觉，整个专栏到这里就结束了，感谢大家对课程的认可和支持！



 #### 为什么我要写这篇专栏呢？

其实，在写这篇专栏之初，我也是有调研过市面上关于 Netty 的专栏的，我发现它们都不够全面，要么就是泛泛而谈，很多知识点没有深入到原理源码级别，要么就是不够实战，用聊天 IM 作为案例的最多，甚至还有一些错误，比如对象池和内存池傻傻分不清，所以，我决定写这篇专栏，我想深入到源码级别，把 Netty 彻底剖析清楚，展现给你。



 #### 为什么我有自信可以写好这篇专栏呢？

我的公众号叫做 “彤哥读源码”，你也可以看到，我对源码的研究很深入，特别是 JDK 的源码，很多细节的东西我都有研究，像 CAS、CPU 缓存行、伪共享、弱引用、Unsafe 这些非常底层的东西，在我的公众号都有讲过。而且，我以前还做过游戏，对 Netty 的源码也看过不少，说白了，底层的东西看来看去就这些，掌握了这些底层的东西，看源码才能更加事半功倍。所以，我有信心写好这篇专栏，我想把这些底层的东西分享给你。



 #### 为什么我要选择游戏作为实战项目呢？

我的想法是，我肯定不能跟市面上的大部分专栏一样，浅尝辄止，我要写就要把整个软件的开发周期写出来，并通过不断的迭代不断地优化，达到上线标准。而且，游戏是大部分同学没有接触过的东西，使用游戏作为实战项目也是为了增加同学的兴趣、加强吸引力。



 #### 我的小感悟

说句心里话，我都不知道自己是怎么坚持下来的。为了写这个专栏，我过年没有回家，节假日基本无休，再加上疫情的原因，公司的人员一直得不到补充，虽然是远程办公，但是事情只多不少，而且，公司的事情比较杂，每天晚上脑袋都是嗡嗡的。

为了让自己更专注，我也改变自己的作息时间，设置了早上 5 点和 5 点半的两个闹钟，晚上早点睡觉，用早起倒逼早睡，这样，我每天早上可以写到 9 点左右，大概 3 到 4 小时的样子，而且，这段时间不会有人来干扰，非常安静，非常好。好了，吐槽到此结束：-）

就希望这个专栏对大家学习 netty 有一定的帮助，这样有什么我们的努力和时间都是值得的，都会有自己的收获。

最后，我想说，这里只是个起点，路还很长。青山不改，绿水长流，我们江湖再见。