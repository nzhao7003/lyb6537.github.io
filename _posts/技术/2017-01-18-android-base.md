---
layout: post
title: ubuntu下android开发平台的搭建
category: 技术
tags: Android
keywords: 
description: 
---

## NDK 的安装
1. 从 http://www.androiddevtools.cn/ 下载NDK
2. 解压NDK
3. sudo vim /etc/bash.bashrc 在末尾添加 
 1. export NDK=/home/..../ndk
 2. export PATH=$PATH:$NDK
4. . /etc/bash.bashrc 之后便可以使用ndk-build等命令
 
## JAVA的安装
1. 从 https://www.java.com/en/download/manual.jsp#lin 下载JDK
2. 解压JDK
3. sudo vim /etc/bash.bashrc 在末尾添加
 1. export JAVA_HOME=/home/..../jdk-1.8.0
 2. export JRE_HOME=${JAVA_HOME}/jre
 3. export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib:${JAVA_HOME}/lib/tools.jar
 4. export PATH=${JAVA_HOME}/bin:$PATH
4. . /etc/bash.bashrc 之后使用 java -version && javac -version 验证安装
 
## ADT bundle 的安装 
1. 从 http://www.androiddevtools.cn/ 下载ADT bundle
2. 在eclipse里 Window->Android SDK Manager里更新sdk 配置见 http://www.androiddevtools.cn/ 重启eclipse生效

## ADT 基础概念
1. ADT bundle: 用于开发android项目的eclipse
 1. sdk(soft Development Kit): 软件开发包
  1. system_images: 系统仿真器
  2. plaform-tools: 和android虚拟机vad相关的命令
  3. tools/android update sdk 命令打开sdk manager
2. ndk 将*.c 和 *.so 文件编译成 *.so 文件， 供java调用

## Android资源网站
1. [androiddevtools](http://www.androiddevtools.cn/)
2. [东软镜像](http://mirrors.neusoft.edu.cn/android/repository/)
3. [ndk 9d linux 32](http://www.360doc.com/content/15/0822/16/597197_494072869.shtml)

