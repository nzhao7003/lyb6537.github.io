---
layout: post
title: FFmpeg在ubuntu下的安装
category: 技术
tags: FFmpeg
keywords: 
description: 
---

### SDL ubuntu 安装 ---  如果不生成ffplay，可以不安装
1. 从 [SDL官网](http://www.libsdl.org/) 下载SDL源码
2. ./configure && make && sudo make install

### ffmpeg linux 安装过程
```
$ git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg
$ ./configure --enable-shared --prefix=/usr/local/ffmpeg #指定生成动态库和指定安装目录 
$ make && sudo make install
```

### 安装完成后，在/usr/local/ffmpeg下生成了三个文件夹
```
1. sudo sh -c  "echo /usr/local/ffmpeg/lib > ffmpeg.conf" ## sh -c 使得一行命令都具有sudo权限
2. sudo ldconfig     重新读取动态库 **这里指的是程序运行时的动态库**
3. sudo cp -r /usr/local/ffmpeg/lib* /usr/include/
4. sudo ln -s /usr/local/ffmpeg/bin/ff* /usr/bin/
5. bin 可执行文件 
 1. ffplay  播放
 2. ffmpeg  转码
 3. ffprobe 查看文件格式
```

### 参考网站
1. [configure分析](http://blog.csdn.net/leixiaohua1020/article/details/44587465)
