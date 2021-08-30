---
title: 安装终端zsh和oh-my-zsh 
tags: [Linux终端]
category: Linux教程
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830223037.png
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830223037.png
date: 2021-08-30 20:00:00
---

## zsh是什么

zsh是一个Linux下强大的shell, 由于大多数Linux产品安装以及默认使用bash shell, 但是丝毫不影响极客们对zsh的热衷, 几乎每一款Linux产品都包含有zsh，通常可以用apt-get、urpmi或yum等包管理器进行安装.

## 安装zsh
```bash
sudo apt update
sudo apt install -y zsh
```
##  配置zsh为默认终端
```bash
chsh -s /usr/bin/zsh
```
如果执行失败,用命令`which zsh`查询zsh的位置.然后执行`chsh -s zsh的位置`
之后`重启`或者`重新登录`

`chsh -s`其实修改的就是`/etc/passwd`文件中和我们所登录的用户名相对应的那一行。

```bash
[roc@roclinux]~% cat /etc/passwd|grep ^roc
roc:x:1001:1001::/home/roc:/bin/zsh
```


## 安装oh-my-zsh
```bash
sudo apt install -y curl wget vim git
sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"
```

## 安装oh-my-zsh插件zsh-autosuggestion

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions  ~/.oh-my-zsh/custom/plugins/
```
编辑` .zshrc`
```
vim  ~/.zshrc
```
加入插件`zsh-autosuggestions`
![alt tag](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830220807.png)

重启`Terminal`，按 ➡ 键可生效
![alt tag](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830220920.png)
