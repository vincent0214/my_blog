---
title: 红米7刷LineageOS 
tags: [红米手机,刷ROM]
category: 手机
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702180935.png
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702180935.png
date: 2021-07-02 18:00:00
---


## 安装adb和fastboot

[下载地址](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)

设置环境变量

![image-20210702180557233](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181052.png)

确保你的电脑已经配置好`adb` 和`fastboot` 的环境变量.

>原文: https://wiki.lineageos.org/adb_fastboot_guide.html

![Image2](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181056.png)

## 解锁手机

###  下载解锁工具

> http://www.miui.com/unlock/index.html

![Image3](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181058.png)

### 开启开发者选项

`「设置」`-> `「全部参数」`-> 连续点击`「MIUI 版本」`（直至开启开发者选项即可）

### 设备绑定小米账号
`「设置」`->`「更多设置」` ->`「开发者选项」` ->`「设备解锁状态」`（登录小米账号）

### 开启USB调试

`「设置」`->`「更多设置」`->`「开发者选项」`->`「USB调试」`（开启即可）。

### 使手机进入  fastboot 模式 

**方法1**, 电脑打开 `cmd（命令提示符）`，执行下列命令

```bash
adb reboot bootloader
```

**方法2,** 手机关机, 然后同时长按`音量减` 和  `电源`进入模式 

### 在电脑里，运行小米官方解锁工具

解压完后，文件夹里找到 **miflash_unlock.exe**，双击运行即可。登录账号依照提示完成解锁即可。

![Image4](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181102.png)

##  刷ROM

> 官网原文: https://wiki.lineageos.org/devices/onclite/install

### 1. 下载这两个东西 

> 下载地址 [https://download.lineageos.org/onclite](https://download.lineageos.org/onclite)

![Image5](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181112.png)

### 2. 手机开启USB调试

`「设置」`-> `「全部参数」`-> 连续点击`「MIUI 版本」`（直至开启开发者选项即可）

`「设置」`->`「更多设置」`->`「开发者选项」`->`「USB调试」`（开启即可）。

### 3. USB数据线连接手机和电脑

### 4. 电脑执行命令

```bash
adb reboot bootloader
```

一旦手机处于快速启动模式，请通过键入以下内容`验证您的PC是否找到它`

```bash
fastboot devices
```

### 5. 闪存恢复到您的设备

![Image6](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181116.png)

```
fastboot flash recovery  xxxxx.img    
```

### 6. 断开数据线, 手机同时按**音量+**和**电源建** (有点难进入,要尝试多次) 

成功的话, 如图所示

![Image7](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181119.png)

### 7 清除数据

![Image9](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181122.png)

![Image8](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181124.png)

### 8. 插入数据线, 刷ROM

![Image10](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181127.png)

选择`Apply from ADB`

![Image11](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181129.png)

![Image12](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181131.png)

电脑执行以下命令

```bash
adb sideload lineage-18.1-20210613-nightly-onclite-signed.zip   
```

### 9 完成

![Image13](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181134.png)

![Image14](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181137.png)

![Image15](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181139.png)

![Image16](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210702181141.png)
