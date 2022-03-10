---
title: Git文件怎么撤销修改 
tags: [Git]
category: Git笔记
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231230931.jpg
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231230931.jpg
date: 2022-03-10 10:39:00
---

## 回退到上个版本

```bash
git reset --hard HEAD^ 
```

## 回退到指定版本
格式: `git reset --hard 版本号 `

```bash
git reset --hard 9495f0c
```

