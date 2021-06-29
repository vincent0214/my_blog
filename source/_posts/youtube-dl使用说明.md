---
title: 使用Youtube-dl下载视频
tags: [下载工具]
category: 软件
index_img: /img/article/2021/1.jpg
date: 2021-06-29 10:00:00
---


## 准备工作

### 安装`python3` 

   >  下载地址: https://www.python.org/downloads/
   >  安装教程: https://zhuanlan.zhihu.com/p/344887837

###  安装`pip`

安装python时, 勾选`pip`选项即可
![](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/11.png)


### 安装`ffmpeg`

   > https://github.com/BtbN/FFmpeg-Builds/releases

   ![image-20210627185448896](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627185448896.png)

   解压缩安装包, 然后把`ffmpeg解压缩目录\bin`添加到`环境变量`

   ![image-20210627185651420](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627185651420.png)

   ![image-20210627185738563](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627185738563.png)

   ![image-20210627185817039](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627185817039.png)

   如图所示, 添加环境变量`ffmpeg解压缩目录\bin`

   ![image-20210627185841049](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627185841049.png)

### 安装`youtube-dl`

> 参考网站 https://github.com/ytdl-org/youtube-dl

命令安装:

```bash
pip install --upgrade youtube-dl
```

或者[下载ext文件](https://yt-dl.org/latest/youtube-dl.exe)
 > 官方原话:
 > Windows users can [download  an .exe file](https://yt-dl.org/latest/youtube-dl.exe) and place it in any location on their [PATH](https://en.wikipedia.org/wiki/PATH_(variable)) except for `%SYSTEMROOT%\System32` (e.g. **do not** put in `C:\Windows\System32`).

## 使用说明

### 1. 下载视频列表

```bash
youtube-dl \
--playlist-reverse \
-o "E:\保存位置\%(playlist_index)s-%(title)s-%(upload_date)s.%(ext)s" \
-f 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/mp4' \
https://www.youtube.com/c/RandomHands/videos
```
`-o "E:\保存位置\%(playlist_index)s-%(title)s-%(upload_date)s.%(ext)s"` 视频输出路径和视频文件名称,
`-f 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/mp4'`设置视频格式为mp4,
`--playlist-reverse`反转下载列表, 因为默认是按最新时间为开头排序,所以要加这个参数
最后的参数是`视频列表地址`

### 2.下载字幕

`youtube-dl --write-sub [url]`这样会下载一个vtt格式的英文字幕和mkv格式的1080p视频下来
`youtube-dl --write-sub --skip-download [url]`下载单独的vtt字幕文件,而不会下载视频
`youtube-dl --write-sub --all-subs [url]`下载所有语言的字幕(如果有的话)
`youtube-dl --write-auto-sub [url]`下载自动生成的字幕(YouTube only)

### 3.按日期下载视频列表

Youtube-dl 允许我们按照上传日期来筛选和下载视频或播放列表，例如：

- 要下载 2019 年 8 月 1 日上传的视频，可以使用：`youtube-dl --date 20190801 [URL]`；

- 下载在特定日期或之前上传的视频：`youtube-dl --datebefore 20190801 [URL]`；

- 下载在特定日期或之后上传的视频：`youtube-dl --dateafter 20190101 [URL]`；

- 仅下载过去 6 个月内上传的视频：`youtube-dl --dateafter now-6months [URL]`；

- 下载特定时间段内（例如 2018 年 1 月 1 日至 2019 年 1 月 1 日）上传的视频：`youtube-dl --dateafter 20180101 --datebefore 20190101 [URL]`。

### 4. 查看视频的所有类型，只看不下载

命令：`youtube-dl -F [url]`或者`youtube-dl --list-formats [url]`。
这是一个列清单参数，执行后并不会下载视频，但能知道这个目标视频都有哪些格式存在，以便有选择的下载。

  ![img](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/v2-fbd29bcc7dc8c7e2b9ea393714b5f038_720w.jpg)

如上图所示，Youtube-dl 列出了给定视频的所有可用格式，从左到右分别为：format code（视频格式代码）、extension（扩展名）、resolution（分辨率）和 note（注释）。当您想要以特定质量或格式下载视频时，先查看一下有哪些可用，会非常便利。


### 5. 下载视频列表文件名称, 输出到txt文件
```bash
youtube-dl \
--playlist-reverse \
--write-description \
--get-filename  \
-o '%(playlist_index)s-%(title)s-%(upload_date)s.mp4'  \
https://www.youtube.com/c/RandomHands/videos \
> video_names.txt
```

### 6. 更多使用方法

> 
>  https://zhuanlan.zhihu.com/p/105141332
>  https://github.com/ytdl-org/youtube-dl

## 其他问题

### 1. xx.sh文件如何使用?


- 安装[git for windows](https://gitforwindows.org/)

- 在`xx.sh`的所在目录, 点击鼠标右键, 选择`git bash here` 
 ![image-20210627193025438](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627193025438.png)

- 在`git bash`输入`sh download_videos.sh`,  按回车执行
  ![image-20210627191925305](https://markdown-1301532546.cos.ap-guangzhou.myqcloud.com/markdown/image-20210627191925305.png)

  
