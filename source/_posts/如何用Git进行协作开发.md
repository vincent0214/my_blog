---
title: 如何用Git进行协作开发
tags: [Git]
category: Git笔记
index_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20220218121132.jpg
banner_img: https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20220218121132.jpg
date: 2021-12-31 17:35:00
---

|  原文出处: https://www.zhihu.com/question/25816758/answer/386246507

## 理想效果

![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/20211231183642.jpg)
想要这种效果? 那就**多用**`rebase`

## 如何实现?


### 0. 每次拉取远程服务器的代码,都用`git pull --rebase`
- 切换到`master分支`, 然后用`git pull --rebase`拉取远程分支的代码
- 切换到`功能/开发`分支. 用`git rebase master`合并`master分支`的代码到当前分支

### 1. 新增/修改代码
### 2. `git diff` 检查代码变更

### 3. `git add`把修改加到index里

### 4. 提交代码
```bash
git commit -m 'xxxxx'
```
> commit到本地仓库，不同的公司有不同的commit模板。Follow公司标准，推荐commit message写详细，不要一句话modify xxx service。大家看git log知道你改了xxx service，但是具体改了什么，是改了接口，还是删了什么函数，麻烦说清楚。好的commit message应该交代清楚本次代码变更的背景，以及具体改了什么。以及，贴上你解决了什么需求，什么bug的连接（如果你们有需求管理平台和缺陷跟踪平台，类似Jira？

### 5. Code Review
> Code Review请Follow你们公司的标准。原则上Code Review的diff 不能太庞大，

### 6. 重构一下commit
`git pull --rebase` # 获取线上代码, 解决conflict，merge之后的代码要重新发起CR
`git log` # check the commit history
`git rebase -i HEAD~N` # 重构提交 (这个rebase操作可以把多个commit合并)



