---
layout: post
title: vlc-android下的编译
category: 技术
tags: vlc
keywords: 
description: 
---

## vlc-android 安装
1. protobuf install 最新的vlc源码要求protobuf 3.0
  1. [下载protobuf](https://github.com/google/protobuf) 
  2. ./autogen.sh
  3. ./configure
  4. make && make check 
  5. sudo make install
  6. sudo ldconfig         更新动态库
2. git clone https://code.videolan.org/videolan/vlc-android.git 下载vlc—android源码
  1. 参考[官网](https://wiki.videolan.org/AndroidCompile/) 安装依赖库 
  2. 参考[androiddevtools](http://www.androiddevtools.cn/) 下载NDK SDK JDK 并建立相应的变量，并将其命令加入到PATH中，重新读取配置信息
   ```
    export ANDROID_NDK=/home/djstava/Workshop/tool/SDK/ndk-bundle
    export ANDROID_SDK=/home/djstava/Workshop/tool/SDK
    export JAVA_HOME=/home/song/jdk/jdk1.6.0_45
    export ANDROID_ABI=armeabi-v7a
    export PATH=$PATH:$ANDROID_SDK/tools:$ANDROID_SDK/platform-tools:$JAVA_HOME/bin:$JAVA_HOME/jre/bin
   ```
  3. sh compile.sh 
  
## 参考资源
1. [vlc-android源码](https://code.videolan.org/videolan/vlc-android)
2. [vlc-android编译](https://wiki.videolan.org/AndroidCompile/)
3. [vlc-ubuntu](https://wiki.videolan.org/UnixCompile/)
