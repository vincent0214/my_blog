---
title: Git文件怎么撤销修改 
tags: [Git]
category: Git笔记
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231230931.jpg
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231230931.jpg
date: 2021-12-31 22:30:00
---

> 原文: [https://www.cnblogs.com/my466879168/p/12960700.html](https://www.cnblogs.com/my466879168/p/12960700.html)
> 

### 1. 本地仓库修改过，但是还没有使用add提交的文件撤销修改

```bash
# 放弃单个文件的修改
git checkout -- <文件名>
git restore <文件名>

# 放弃多个文件的修改
git checkout .
git restore .
```

### 2. 文件已经add过了从工作区到暂存区了,怎么在回退到工作区中

```bash
git reset HEAD -- . 回退所有的
git reset HEAD -- <文件名>
git restore --staged <文件名>
git restore --staged . # 回退所有的文件
git restore--staged *.js # 所有暂存区的js文件回退
```

### 3. 文件已经commit过后怎么回退

```bash
git restore -s HEAD~1 . # 回退到上一个commit版本这次的代码全消失
git restore -s 91410eb9 . # 指定明确的commit id 然后回退
git reset --soft HEAD^ # 撤销本次的commit 回退到暂存区
```

### 4. commit之后发现注释写错了修改注释

```bash
git commit --amend  # 此时会进入vim编辑器 修改后保存即可
```