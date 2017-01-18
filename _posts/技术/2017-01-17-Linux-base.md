---
layout: post
title: Linux基础知识
category: 技术
tags: Linux
keywords: 
description: 
---

## Linux基础知识
```
/etc/fstab 开机挂载
umask 文件默认权限
chattr lsattr 文件隐藏属性
SUID 文件执行者在执行文件时具有文件所有者的权限 例如 /usr/bin/passwd
SGID 目录 用户新建文件所属的用户组与此目录的用户组相同
SBIT 目录 只有root和文件的所有者可以删除 例如/tmp
pwd -P                   # -P：代表显示正确的完整路径，而不是连接路径
chmod 4755 filename
chmod u=rwxs,go=x test; ls -l test      # 配置权限为-rws--x--x的模样
chmod g+s,o+t test; 
ls -l test          # 配置权限为-rws--s--t，即加入SGID,SBIT权限
```

## ctags commond
1. sudo apt-get install ctags
2. ctags -R 递归创建tags文件
3. vim -t tag tag为要查找的变量或函数名


### size a.out 显示一个应用程序所占的各个空间
```
BSS Block Started by Symbol      #存放未初始化的全局变量
data segment                     #存放已初始化的全局变量
code segment                     #代码段
heap                             #动态分配的数据
stack                            #局部变量
```
