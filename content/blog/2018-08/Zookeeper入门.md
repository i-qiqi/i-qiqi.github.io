---
date: "2019-05-07T10:23:48+08:00"
publishdate: "2018-08-04"
lastmod: "2018-08-07"
draft: false
title: "Zookeeper入门"
tags: ["zookeeper"]
series: ["分布式协调"]
categories: ["毕设"]
img: "images/blog/2018-08/test4.jpg"
toc: true
---
## Zookeeper安装
###  1. Standalone mode
- [get-started](https://zookeeper.apache.org/doc/r3.4.9/zookeeperStarted.html)

### 2. Doker mode
- 下载镜像
	```bash
	//latest
	docker pull zookeeper
	```
- 启动ZK镜像
	```bash
	docker run --name my_zookeeper -d zookeeper:latest
	# 查看运行情况
	docker logs -f my_zookeeper
	```
- 使用ZK命令行客户端连接ZK
	```
	# 当我们执行了这个命令后, 就可以像正常使用 ZK 命令行客户端一样操作 ZK 服务了
	docker run -it --rm --link my_zookeeper:zookeeper zookeeper zkCli.sh -server zookeeper
	# 命令含义
	1> 启动一个 zookeeper 镜像, 并运行这个镜像内的 zkCli.sh 命令, 命令参数是 "-server zookeeper"
	2> 将我们先前启动的名为 my_zookeeper 的容器连接(link) 到我们新建的这个容器上, 并将其主机名命名为 zookeeper
	```
	- **<font color="red">Docker 的 link 机制???</font>**

## Zookeeper使用
## Reference
[1] [使用 Docker 一步搞定 ZooKeeper 集群的搭建](https://www.cnblogs.com/kingkoo/p/8732448.html)

## 版本控制

| Version | Action            | Time       |
| ------- | ----------------- | ---------- |
| 1.0     | Init 静态页面路线 | 2018-08-05 |
