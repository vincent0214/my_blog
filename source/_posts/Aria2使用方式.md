---
title: Aria2使用方式
tags: [下载工具]
category: 软件
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210709224201.png 
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210709222312.png
date: 2021-07-09 22:26:00
---



## 简介

> Aria2 是一个多平台轻量级，支持 HTTP、FTP、BitTorrent 等多协议、多来源的命令行下载工具。Aria2 可以从多个来源、多个协议下载资源，最大的程度上利用了你的带宽。Aria2 有着非常小的资源占用，在关闭磁盘缓存的情况下，物理内存占用通常为 4M（正常 HTTP/FTP 下载的情况下），BitTorrent 下载每秒2.8M/S的情况下，CPU 占有率约为 6%。Aria2 支持 JSON-RPC 和 XML-RPC 接口远程调用。

## 下载

服务端`aria2`: https://github.com/aria2/aria2/releases/tag/release-1.35.0

![image-20210710113706713](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121320.png)

客户端`Aria2Ng`: https://github.com/mayswind/AriaNg/releases/tag/1.2.2

![image-20210710113758236](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121323.png)

## 安装

### 解压安装包

**安装包文件夹存放位置就是本文所说的`aria2`安装目录**

![image-20210710114058804](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121340.png)

### 添加环境变量
在环境变量`Path`中添加`aria2`安装目录



![image-20210710114307321](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121233.png)

![image-20210710114230218](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121236.png)

![image-20210710114445538](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121239.png)

![image-20210709214803477](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210709222314.png)

### 创建配置文件

在`aria2`安装目录创建`aria2.conf`配置文件. 

```properties
## 全局设置 ## ============================================================
# 日志
#log-level=warn
#log=/PATH/.aria2/aria2.log

# 后台运行
daemon=true

# 下载位置, 默认: 当前启动位置
dir=d:/downloads

# 从会话文件中读取下载任务
input-file=./session/aria2.session

# 在Aria2退出时保存`错误/未完成`的下载任务到会话文件
save-session=./session/aria2.session

# 定时保存会话, 0为退出时才保存, 需1.16.1以上版本, 默认:0
save-session-interval=30

# 断点续传
continue=true

# 启用磁盘缓存, 0为禁用缓存, 需1.16以上版本, 默认:16M
#disk-cache=32M

# 文件预分配方式, 能有效降低磁盘碎片, 默认:prealloc
# 预分配所需时间: none < falloc ? trunc < prealloc
# falloc和trunc则需要文件系统和内核支持
# NTFS建议使用falloc, EXT3/4建议trunc, MAC 下需要注释此项
file-allocation=none

# 客户端伪装
user-agent=netdisk;5.2.6;PC;PC-Windows;6.2.9200;WindowsBaiduYunGuanJia
referer=http://pan.baidu.com/disk/home

# 禁用IPv6, 默认:false
disable-ipv6=true

# 其他
always-resume=true
check-integrity=true

## 下载位置 ## ============================================================
# 最大同时下载任务数, 运行时可修改, 默认:5
max-concurrent-downloads=5

# 同一服务器连接数, 添加时可指定, 默认:1
max-connection-per-server=5

# 最小文件分片大小, 添加时可指定, 取值范围1M -1024M, 默认:20M
# 假定size=10M, 文件为20MiB 则使用两个来源下载; 文件为15MiB 则使用一个来源下载
min-split-size=10M

# 单个任务最大线程数, 添加时可指定, 默认:5
split=8

# 整体下载速度限制, 运行时可修改, 默认:0
#max-overall-download-limit=0

# 单个任务下载速度限制, 默认:0
#max-download-limit=0

# 整体上传速度限制, 运行时可修改, 默认:0
#max-overall-upload-limit=0

# 单个任务上传速度限制, 默认:0
#max-upload-limit=0

## RPC设置 ## ============================================================
# 启用RPC, 默认:false
enable-rpc=true

# 允许所有来源, 默认:false
rpc-allow-origin-all=true

# 允许非外部访问, 默认:false
rpc-listen-all=true

# 事件轮询方式, 取值:[epoll, kqueue, port, poll, select], 不同系统默认值不同
#event-poll=select

# RPC监听端口, 端口被占用时可以修改, 默认:6800
rpc-listen-port=6800

# 设置的RPC授权令牌, v1.18.4新增功能, 取代 --rpc-user 和 --rpc-passwd 选项
#rpc-secret=<TOKEN>

# 是否启用 RPC 服务的 SSL/TLS 加密,
# 启用加密后 RPC 服务需要使用 https 或者 wss 协议连接
#rpc-secure=true

# 在 RPC 服务中启用 SSL/TLS 加密时的证书文件,
# 使用 PEM 格式时，您必须通过 --rpc-private-key 指定私钥
#rpc-certificate=/path/to/certificate.pem

# 在 RPC 服务中启用 SSL/TLS 加密时的私钥文件
#rpc-private-key=/path/to/certificate.key

## BT/PT下载相关 ## ============================================================
# 当下载的是一个种子(以.torrent结尾)时, 自动开始BT任务, 默认:true
#follow-torrent=true

# BT监听端口, 当端口被屏蔽时使用, 默认:6881-6999
listen-port=51413

# 单个种子最大连接数, 默认:55
#bt-max-peers=55

# 打开DHT功能, PT需要禁用, 默认:true
enable-dht=false

# 打开IPv6 DHT功能, PT需要禁用
#enable-dht6=false

# DHT网络监听端口, 默认:6881-6999
#dht-listen-port=6881-6999

dht-file-path=./dht/dht.dat
dht-file-path6=./dht/dht6.dat

# 本地节点查找, PT需要禁用, 默认:false
#bt-enable-lpd=false

# 种子交换, PT需要禁用, 默认:true
enable-peer-exchange=false

# 每个种子限速, 对少种的PT很有用, 默认:50K
#bt-request-peer-speed-limit=50K

# 设置 peer id 前缀
peer-id-prefix=-TR2770-

# 当种子的分享率达到这个数时, 自动停止做种, 0为一直做种, 默认:1.0
seed-ratio=0

# 强制保存会话, 即使任务已经完成, 默认:false
# 较新的版本开启后会在任务完成后依然保留.aria2文件
#force-save=false

# BT校验相关, 默认:true
#bt-hash-check-seed=true

# 继续之前的BT任务时, 无需再次校验, 默认:false
bt-seed-unverified=true

# 保存磁力链接元数据为种子文件(.torrent文件), 默认:false
bt-save-metadata=true

bt-max-open-files=16
```

### 创建session文件

在`aria2`安装目录**创建文件夹**`session`

然后在文件夹`session`, **创建空白文件**`aria2.session`

> `aria2.session`是一个记录了下载任务记录的文件

### 解压缩客户端安装包

![image-20210710115511400](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210710121253.png)

`index.html`就是客户端`AriaNg`的执行文件.

## RPC使用方式

### 开启服务端`aria2`

> **原理**: 通过读取指定的配置文件,把`aria2`的`rpc`模式(服务器模式)开启.客户端用ip和端口连接到`aria2`.
>
> 默认情况下`aria2`是一个命令行下载工具.

#### 方式一

在`aria2`安装目录, 创建`runAria2.vbs`

```vbscript
CreateObject("WScript.Shell").Run "aria2c.exe --conf-path=aria2.conf",0
```

双击`runAria2.vbs`文件运行`aria2`.

#### 方式二

在`aria2`安装目录, 创建`run.sh`

```bash
aria2c.exe --conf-path=aria2.conf  
```

然后在bash命令行输入`sh run.sh`运行`aria2`.



### 开启客户端`AriaNg`

打开`AriaNg`的安装目录的`index.html`,即可进入`AriaNg` 界面

客户端`AriaNg`会自动连接服务端. 如果出现连接不成功, 说明客户端`AriaNg`没有找到服务端

![image-20210709213842832](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210709222312.png)



## 命令行使用方式

在命令行输入命令, 来下载文件.  这种方式**可以不用`AriaNg`客户端**

Download from WEB:

```bash
$ aria2c http://example.org/mylinux.iso
```

Download from 2 sources:

```bash
$ aria2c http://a/f.iso ftp://b/f.iso
```

Download using 2 connections per host:

```bash
$ aria2c -x2 http://a/f.iso
```

BitTorrent:

```bash
$ aria2c http://example.org/mylinux.torrent
```

BitTorrent Magnet URI:

```bash
$ aria2c 'magnet:?xt=urn:btih:248D0A1CD08284299DE78D5C1ED359BB46717D8C'
```

Metalink:

```bash
$ aria2c http://example.org/mylinux.metalink
```

Download URIs found in text file:

```bash
$ aria2c -i uris.txt
```

## 参考

- [Aria2配置详解](https://www.jianshu.com/p/6adf79d29add)
- [aria2官方网站](https://aria2.github.io/)
- [Aria2基础上手指南](https://zhuanlan.zhihu.com/p/30666881)

