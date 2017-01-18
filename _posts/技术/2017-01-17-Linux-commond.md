---
layout: post
title: Linux常用命令
category: 技术
tags: Linux
keywords: 
description: 
---

### 安装，查找，卸载软件   
```
sudo apt-get install   #安装软件
sudo apt-get remove    #卸载软件
sudo apt-cache search  #查找软件
sudo apt-get upgrade   #更新已安装软件
```

### vim commond
```
:%s/^M//gc               #去掉所有的^M-->ctrl+v ctrl+m
:%s/a/b/                 #将当前行中的第一个a转化为b
:%s/a/b/g                #将当前行所有的a转化为b
:n,$s/a/b/               #将从n到文末的所有行中的第一个a转化为b
:n,$s/a/b/g              #将从n到文末的所有行中的a转化为b
:%s/a/b/                 #将所有行的第一个a替换为b
:%s/a/b/g                #将所有行的a替换为b
ngg                      #跳转到指定行 
:set fileencoding=utf-8  #编码格式转换  
```

### sed commond
```
sed -n '1,$p'        input.txt #打印指定的行       
sed -n '/lyb/p'      input.txt #匹配正则表达式
sed -n '1,2d'        input.txt #删除指定行          
sed -n '1,3a Hello'  input.txt #1行到3行后添加 Hello  
sed -n '1,3c Ha'     input.txt #代替
sed -n 's/old/new/g' input.txt #正则代替
```

### 惯用的关机命令：
```
shutdown -h now                                #立刻关机
shutdown -h 20:25                              #晚上8点25分关机
shutdown -h +10                                #过十分钟后关机
shutdown -r now                                #立刻重启
shutdown -r +30 ‘The system will be reboot’    #再过30分钟关机，并显示后面的消息给所有在线用户
shutdown -k now ‘The system will be reboot’    #仅发出警告，系统并不会真正关机
```

### 压缩和解压缩相关命令
```
#解压
tar -xzf  all.tar.gz         
tar -xjf  all.tar.bz2
tar -xvJf all.tar.xz
rar x input.rar
#解包
tar -xvf so.tar
#打包
tar -cvf  so.tar dir_name
#压缩
tar -jcvf so.tar.bz2 dir_name #打包后以bzip2压缩
tar -zcvf so.tar.gz  dir_name #打包后以gzip压缩
```

### 和编译相关的命令
```
gcc -L/usr/local/ffmpeg/lib -lavcodec                                       #指定编译时动态库的位置
gcc -w                                                                      #去掉所有警告
sudo ld.so.config                                                           #更新运行时的动态库
sudo ln -s /usr/local/ffmpeg/lib/pkgconfig/lib* /usr/lib/pkgconfig/
export PKG_CONFIG_PATH=/usr/local/ffmpeg/lib/pkgconfig:$PKG_CONFIG_PATH
pkg-config libavcodec --libs                                                #显示链接动态库的参数
pkg-config libavcodec --cflags                                              #显示编译时的头文件位置
pkg-config --modversion libavcodec                                          #显示数据库的版本信息
```

### 和系统管理相关的命令
```
dd                 #制作大文件
df -hT             #查看挂载在当前设备上的文件系统的使用情况
du -sh / home      #显示某一目录下所有文件的大小
fdisk -l           #显示所有未挂载的设备
free -h            #显示内存的使用情况
jobs -l            #显示所有的后台工作
fg %jobnumber      #将指定后台工作移到前台
kiil -9 pid        #强制删除某一进程
ln                 #设置硬链接和软连接
mkfs               #格式化
mount              #挂载设备
ps                 #显示当前用户的进程
ps aux             #显示所有用户的进程
route -n           #显示路由表
ss -tua            #显示系统已启用的服务
systemctl enable http.service  #设置服务的启动，重启，停止，以及是否开机启动
service mysql restart          #服务重启
uname -r           #查看内核版本，稳定版本的偶数版，如2.6.x，开发中版本，如2.5.x
```

### 和视音频  相关的命令
```
ffmpeg -codecs                                         #查看支持的编码格式
mediainfo input.mp4                                    #查看视音频的封装格式和编码格式
android list targets                                   #显示Available Android targets
mksdcard 128M sdcard.img                               #创建镜像文件
android create avd -n Sim2 -t 1 -c "the path to SD"    #创建avd
```

### 其他常用命令
```
bc                 #计算器
cal 10 2014        #显示日历
date               #显示日期与实践
pandoc -f markdown -t html -o demo.html demo.md   #将markdown转化为html
cat /etc/passwd | awk -F ':' '{print $1}'         #对行进行切割
```




