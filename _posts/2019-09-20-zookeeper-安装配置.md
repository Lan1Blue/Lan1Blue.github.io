---
layout: article
title: zookeeper-安装配置
tags: [中间件]
---

### 1、下载

下载路径 [https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.4.14/zookeeper-3.4.14.tar.gz](https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.4.14/zookeeper-3.4.14.tar.gz) 下载需要的版本即可

```shell
wget https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.4.14/zookeeper-3.4.14.tar.gz
```



### 2、解压到目录

```shell
tar -zxvf  zookeeper-3.4.14.tar.gz 
```

### 3、配置zoo.cfg

复制 zoo_sample.cfg 为zoo.cfg 

```shell
cp zoo_sample.cfg zoo.cfg 
```

```shell
# The number of milliseconds of each tick
tickTime=2000
# The number of ticks that the initial 
# synchronization phase can take
initLimit=10
# The number of ticks that can pass between 
# sending a request and getting an acknowledgement
syncLimit=5
# the directory where the snapshot is stored.
# do not use /tmp for storage, /tmp here is just 
# example sakes.
#dataDir=/tmp/zookeeper
dataDir= /数据目录
# the port at which the clients will connect
clientPort=2181
# the maximum number of client connections.
# increase this if you need to handle more clients
maxClientCnxns=300
#
# Be sure to read the maintenance section of the 
# administrator guide before turning on autopurge.
#
# http://zookeeper.apache.org/doc/current/zookeeperAdmin.html#sc_maintenance
#
# The number of snapshots to retain in dataDir
#autopurge.snapRetainCount=3
# Purge task interval in hours
# Set to "0" to disable auto purge feature
#autopurge.purgeInterval=1

```

### 4、启动，停止，重启等

进入到bin目录下执行启动脚本 zkServer.sh 

```sh
# 启动
zkServer.sh start
# 停止
zkServer.sh stop
# 查看状态
zkServer.sh status
# 重启
zkServer.sh restart
```

启动客户端

```sh
zkCli.sh -server 127.0.0.1:2181
```

