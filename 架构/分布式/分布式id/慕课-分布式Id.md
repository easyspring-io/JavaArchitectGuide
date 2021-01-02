# 分布式ID

美团开源的分布式 id

![image-20201229181553933](http://qiniu.cdn.easyspring.net/20201229181553.png)

## 为什么需要分布式id

### 传统方案

#### 时间戳

#### UUID

## 分布式ID的特点

![image-20201229181923285](http://qiniu.cdn.easyspring.net/20201229181923.png)

#### 全局唯一

一个应用在

#### 高并发

#### 高可用

## 实现方案

![image-20201229182018240](http://qiniu.cdn.easyspring.net/20201229182018.png)

受 Redis 数据持久化机制的影响



![image-20201229182448547](http://qiniu.cdn.easyspring.net/20201229182448.png)

### 雪花算法

![image-20201229182747745](http://qiniu.cdn.easyspring.net/20201229182747.png)

* 时间戳（41位）：69年

* 工作进程（10位：5+5）： 1024 台机器
* 序列号位（12位）：4096 为

![image-20201229182629978](http://qiniu.cdn.easyspring.net/20201229182630.png)



## 开源组件