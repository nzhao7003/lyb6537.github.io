---
layout: post
title: 视音频基础知识
category: 技术
tags: FFmpeg
keywords: 
description: 
---


# 视频播放的过程
1. 解协议
2. 解封装 封装以后生成TS流
3. 解码视音频 编码之后生成ES流
4. 视音频同步


# 视音频基本概念
1. ES(Elementary Stream): 基本码流
2. PES（Packet Elementary Stream）： 打包的基本码流。将ES切割成长度不同的数据包并加上包头形成PES。
3. TS（Transport Stream）： ES封装生成TS
4. 码率： 清晰度 kbps
5. 帧率： 流畅度 fps
6. 分辨率： 画面大小
7. 采样率： 44.1K
8. 720p 1080p 指的是垂直分辨率
9. 4K  8K   指的是水平分辨率
10. Y表示亮度，UV表示色度
11. YUV411 水平方向上，每四个像素点存储四个Y，一个U，一个V， 压缩比为 1/2
12. YUV422 水平方向上，每两个像素点存储两个Y，一个U，一个V， 压缩比为 2/3
13. YUV420 水平方向上，每两个像素点存储一个U或V；垂直方向上， U和V隔行存储，即 第n行存储U，第n+1行存储V 压缩比为 1/2
