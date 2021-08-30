---
title: 安装Zookeeper 
tags: [中间件]
category: JAVA开发
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830225713.png
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830225713.png
date: 2021-08-30 21:00:00
---



## 下载
[下载地址](http://zookeeper.apache.org/releases.html)

选择二进制包

![image-20210830224358632](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830230525.png)

wget 下载地址

```bash
wget https://www.apache.org/dyn/closer.lua/zookeeper/zookeeper-3.5.9/apache-zookeeper-3.5.9-bin.tar.gz 
```

## 安装

### 0. 准备安装
```bash
sudo yum install -y wget  vim # centos
sudo apt install -y wget curl vim # ubuntu
```

### 1. 移动压缩包到/opt文件夹
```
mv apache-zookeeper-3.5.9-bin.tar.gz  /opt/
```
### 2. 解压缩安装包

```
tar -zxvf apache-zookeeper-3.5.9-bin.tar.gz 
mv apache-zookeeper-3.5.9-bin zookeeper  # 把文件夹改名
```

## 配置
把`config`文件夹的`zoo_sample.cfg `文件改名为`zoo.cfg `

```bash
mv /opt/zookeeper/config/zoo_sample.cfg /opt/zookeeper/config/zoo.cfg 
```

创建`data`目录

```bash
mkdir /opt/zookeeper/data
```

修改配置文件`config/zoo.cfg`
```bash
ticketTime=2000
clientPort=2181
dataDir=/opt/zookeeper/data
dataLogDir=/opt/zookeeper/logs
```

## 启动服务器端
```bash
/opt/zookeeper/bin/zkServer.sh start
```

## 运行命令行客户端
```bash
 /opt/zookeeper/bin/zkCli.sh 
```

zkCli执行成功后, 查看zNode输入` ls / `