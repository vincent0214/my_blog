---
title: Git合并多次提交 
tags: [Git]
category: Git笔记
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231174052.webp
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231174052.webp
date: 2021-12-31 17:30:00
---

### 以交互方式rebase操作最近4次提交

```bash
git rebase  -i  HEAD~4  
```
- -i 交互方式
- HEAD~4 最近4次提交

![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231172119.png)

### 把需要合并提交用”s”标记, 合并到上一次提交(上面的提交)

![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231172116.png)

### 编辑新提交(合并后的提交)的message, 输入":wq"确定并保存,完成合并commit

![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231172118.png)

### 取消本次合并
把画面中的所有文字注释或者清空(输入`gg`后输入`dG`), 再按`:wq`保存
然后`git rebase --abort`