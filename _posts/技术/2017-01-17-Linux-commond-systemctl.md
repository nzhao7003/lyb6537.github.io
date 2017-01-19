---
layout: post
title: Linux-commond-systemctl
category: 技术
tags: Linux
keywords: 
description: 
---


```
$ systemctl enable       httpd.service          #设置开机自启
$ systemctl disable      httpd.service          #禁止开机启动     
$ systemctl status       httpd.service          #服务详细信息
$ systemctl list-units   --type=service         #显示所有已启动的服务
$ systemctl start        httpd.service          #启动服务
$ systemctl stop         httpd.service          #停止服务
$ systemctl restart      httpd.service          #重启服务
```
 
## 参考资料
1. [linux_commond](http://man.linuxde.net/)
