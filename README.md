## 准备工作

### 安装Node.js 

建议安装node 12或以上版本

> https://nodejs.org/en/

![image-20210629123856338](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629123856338.png)

### 安装hexo

```bash
npm install -g hexo-cli
```
### 安装依赖

```bash
npm i
```


## 命令说明

### 清理生成的页面

```bahs
hexo clean
```

### 开启本地服务器

`调试页面`时, **不用**生成页面. 直接`启动`本地服务器即可 
如果修改了`配置文件`, **重新**开启本地服务器即可

```bash
hexo s
```

> 原文 https://hexo.io/zh-cn/docs/generating


### 生成页面

```bash
hexo g
```

> 参考: https://hexo.io/zh-cn/docs/server

### 发布到github (一键部署)
**执行部署之前, 先需要`生成页面`**

修改配置文件`_config.yml`
```yml
deploy:
  type: git
  repo: <repository url> #https://bitbucket.org/JohnSmith/johnsmith.bitbucket.io
  branch: [branch]
```
执行命令
```bash
hexo g && hexo d
```
## 主题设置
### 修改首页banner图片

> 建议用`1920*1080`分辨率的图片. 图片大小最好**不要超过1MB**

在`source/img`文件夹中加入`banner图片`

![image-20210702160049822](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210702160049822.png)

到`_config.fluid.yml`配置中修改banner图片路径
![image-20210702154505648](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210702154505648.png)

### 修改网站ICON图标

- 在icon网站下载`彩色图标`png文件
  例如: https://www.iconfont.cn/

- 把icon文件放入/source/img文件夹.
  ![image-20210702155020528](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210702155020528.png)

- 在`_config.fluid`文件, 修改icon文件路径
  ![image-20210702154952583](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210702154952583.png)

  


## 写作说明
### 文章添加封面图片
在文章的最上面设置以下信息
```
---
title: <文章标题> 
index_img: <文章封面图片地址>
banner_img: <文章Banner图片地址> 
date: <文章创建时间>
---

...文章内容...
```


## github设置

![image-20210629125902869](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629125902869.png)

![image-20210629130032633.png](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130032633.png)

`blog.wingogo.tk`是准备好的`域名`

## 配置域名

DNS设置`CNAME`记录值为github page的url

![image-20210629130228507](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130228507.png)

在`source`文件夹添加`文件`**CNAME**

![image-20210629130549711](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130549711.png)

> [官方原文](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain)
>
> To set up a www or custom subdomain, such as www.example.com or blog.example.com, you must add your domain in the repository settings, which will create a CNAME file in your site’s repository. After that, configure a CNAME record with your DNS provider.

设置`url`为`域名`

![image-20210629130647291](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130647291.png)

## 参考:

- hexo官网: https://hexo.io/

- fluid主题: https://github.com/fluid-dev/hexo-theme-fluid