## 准备工作

### 安装Node.js 12以上版本

> https://nodejs.org/en/

![image-20210629123856338](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629123856338.png)

### 安装hexo

```bash
npm install -g hexo-cli
```

### 安裝hexo发布插件

```bash
npm install hexo-deployer-git --save
```



## 使用说明

### 生成页面

```bash
hexo g
```

> 原文 https://hexo.io/zh-cn/docs/server

### 本地服务器

```bash
hexo s
```

> 原文 https://hexo.io/zh-cn/docs/generating

### 发布到github (一键部署)

```bash
hexo d
```

修改配置文件`_config.yml`

```yml
deploy:
  type: git
  repo: <repository url> #https://bitbucket.org/JohnSmith/johnsmith.bitbucket.io
  branch: [branch]
```

## github设置

![image-20210629125902869](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629125902869.png)

![image-20210629130032633.png](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130032633.png)

`blog.wingogo.tk`是我的域名

## 配置域名

dns设置`CNAME`记录值为github page的url

![image-20210629130228507](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130228507.png)

`source`文件夹添加`文件`cname

![image-20210629130549711](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130549711.png)

设置`url`为域名

![image-20210629130647291](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130647291.png)
