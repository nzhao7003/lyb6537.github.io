---
layout: post
title: 运行SDL下android的例子
category: 技术
tags: SDL
keywords: 
description: 
---

## 如何运行[SDL官网](https://wiki.libsdl.org/)的android项目 
### NDK JDK ADT bundle 安装见[环境配置](https://lyb6537.github.io/2017/01/18/android-develop.html)

1. 切换到SDL根目录
2. mkdir android-project/jni/SDL
3. cp -r src/ include/ Android.mk android-project/jni/SDL
4. cp main.c android-project/jni/src/main.c 文件见参考资源
5. 将android-project/jni/src/Android.mk中的YourSourceHere.c 改为 main.c
6. cd android-project && ndk-build 生成两个动态库，前提ndk装好，ndk-build配置到当前的path中, 
7. 更改project.properties和default.properties 和当前的vad版本相对应，vad版本大于15时支持use host GPU
8. 将该项目导入到eclipse中
9. 在项目的assets目录下加入文件 image.bmp 文件见参考资源 
10. 运行该项目，即可成功

## 参考资源
1. [资源文件](https://github.com/lyb6537/develop-resource/tree/master/SDL/Android)
