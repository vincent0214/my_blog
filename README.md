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

### 安装主题
```bash
npm install --save hexo-theme-fluid
```
然后在博客目录下创建`_config.fluid.yml`，将主题的 [_config.yml](https://github.com/fluid-dev/hexo-theme-fluid/blob/master/_config.yml) 内容复制进去。
> 参考: https://github.com/fluid-dev/hexo-theme-fluid


## 使用说明

### 开启本地服务器
调试页面时, 不用生成页面. 直接开启本地服务器即可 
如果修改了配置文件, 重新开启本地服务器即可

```bash
hexo s
```

> 原文 https://hexo.io/zh-cn/docs/generating


### 生成页面

```bash
hexo g
```

> 原文 https://hexo.io/zh-cn/docs/server

### 发布到github (一键部署)
**执行部署之前, 需要`生成页面`**

修改配置文件`_config.yml`

```yml
deploy:
  type: git
  repo: <repository url> #https://bitbucket.org/JohnSmith/johnsmith.bitbucket.io
  branch: [branch]
```
执行命令
```bash
hexo d
```

## github设置

![image-20210629125902869](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629125902869.png)

![image-20210629130032633.png](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130032633.png)

`blog.wingogo.tk`是提前准备好的域名

## 配置域名

dns设置`CNAME`记录值为github page的url

![image-20210629130228507](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130228507.png)

在`source`文件夹添加`文件`CNAME

![image-20210629130549711](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130549711.png)

设置`url`为域名

![image-20210629130647291](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210629130647291.png)

>[官方原文](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain)
> 
> To set up a www or custom subdomain, such as www.example.com or blog.example.com, you must add your domain in the repository settings, which will create a CNAME file in your site’s repository. After that, configure a CNAME record with your DNS provider.