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
提前准备
```bash
sudo apt update
sudo apt install -y curl wget vim git
```
安装zsh
```bash
sudo apt install -y zsh 
```
##  配置zsh为默认终端
查看zsh路径
```bash
cat /etc/shells  # 查看是否存在zsh,并查看zsh路径
```

把当前的`shell`切换为zsh
```bash
chsh -s /bin/zsh # 从上面的命令查到zsh的路径是`/bin/zsh`
```
然后source一下
```bash
source ~/.zshrc
````

`chsh -s`原理是修改`/etc/passwd`文件中和我们所登录的用户名相对应的那一行。
```bash
[roc@roclinux]~% cat /etc/passwd|grep ^roc
roc:x:1001:1001::/home/roc:/bin/zsh
```

## 安装oh-my-zsh
```bash
sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"
```

## 安装命令提示插件zsh-autosuggestion
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions  ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
```
编辑`~/.zshrc`
```bash
vim  ~/.zshrc
```
加入插件`zsh-autosuggestions`
![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830220807.png)

重启`Terminal`，按 ➡ 键可生效
![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210830220920.png)

# 安装命令高亮插件zsh-syntax-highlighting
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git  ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlightings
```
编辑`~/.zshrc`
```
plugins=(其他插件 zsh-syntax-highlighting)`
```
然后source一下
```bash
source ~/.zshrc
```

![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20210905093013.png)