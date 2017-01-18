---
layout: post
title: FFmpeg常见问题
category: 技术
tags: FFmpeg
keywords: 
description: 
---

## AVPacket AVFrame
每一次 av_read_frame 后，必须手动释放packet的数据缓存，而不必要手动处理frame的数据缓存，系统自动处理

