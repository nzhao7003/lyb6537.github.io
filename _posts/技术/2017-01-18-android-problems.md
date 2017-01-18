---
layout: post
title: Android常见问题
category: 技术
tags: Android
keywords: 
description: 
---

## VAD apk的安装与卸载
1. adb inatall XXX.apk 安装
2. 删除data/app下的apk文件，重启vad， 卸载 
 
## 两个Activity如何通信
### 发送数据
```
Intent it = new Intent(Activity.Main.this, Activity2.class);
Bundle bundle=new Bundle();
bundle.putString("name", "This is from MainActivity!");
it.putExtras(bundle)；
startActivity(it);
```

### 就收数据
```
Bundle bundle=getIntent().getExtras();
String name=bundle.getString("name");
```

### 返回结果
```
Intent intent=getIntent();
Bundle bundle2=new Bundle();
bundle2.putString("name", "This is from ShowMsg!");
intent.putExtras(bundle2);
setResult(RESULT_OK, intent);
```

## 注意sdcard目录的读写权限

在AndroidManifest.xml中添加
`<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />`

## 如何用C语言在android中打log
```
#include <android/log.h>
#define APPNAME "SDL_Lesson"  
#define LOGV(...) __android_log_print(ANDROID_LOG_VERBOSE, APPNAME, __VA_ARGS__)
#define LOGD(...) __android_log_print(ANDROID_LOG_DEBUG , APPNAME, __VA_ARGS__)
#define LOGI(...) __android_log_print(ANDROID_LOG_INFO , APPNAME, __VA_ARGS__)
#define LOGW(...) __android_log_print(ANDROID_LOG_WARN , APPNAME, __VA_ARGS__)
#define LOGE(...) __android_log_print(ANDROID_LOG_ERROR , APPNAME, __VA_ARGS__)
```

