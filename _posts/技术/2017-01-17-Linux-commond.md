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
sudo apt-get install   安装软件
sudo apt-get remove    卸载软件
sudo apt-cache search  查找软件
sudo apt-get upgrade   更新已安装软件
```


```
uname -r       查看内核版本，稳定版本的偶数版，如2.6.x，开发中版本，如2.5.x
dd             制作大文件
df -hT         查看挂载在当前设备上的文件系统的使用情况
du -sh / home  显示某一目录下所有文件的大小
echo $LANG     显示目前支持的语言
fdisk -l       显示所有未挂载的设备
ffmpeg -codecs 查看支持的编码格式
free -h        显示内存的使用情况

```

LANG=en_US   #将语言改为英文系
date         #显示日期与实践
cal 10 2014  #显示日历
bc           #计算器
quit         #退出
```

### 正确的关机方法
```
who         #查看目前有谁在线
netstat -a  #查看网络的联机状态
ps -aux     #查看后台执行的程序
```

### 惯用的关机命令：
```
shutdown -h now     #立刻关机
shutdown -h 20:25   #晚上8点25分关机
shutdown -h +10     #过十分钟后关机
shutdown -r now     #立刻重启
shutdown -r +30 ‘The system will be reboot’    #再过30分钟关机，并显示后面的消息给所有在线用户
shutdown -k now ‘The system will be reboot’    #仅发出警告，系统并不会真正关机
```

### tar commond
```
tar -xzf  all.tar.gz         
tar -xjf  all.tar.bz2
tar -xvJf all.tar.xz
rar x input.rar
tar -xvf so.tar
tar -cvf  so.tar dir_name
tar -jcvf so.tar.bz2 dir_name 打包后以bzip2压缩
tar -zcvf so.tar.gz  dir_name 打包后以gzip压缩
```
