---
layout: post
title: 结构体对齐规则
category: 技术
tags: Coding
keywords: 
description: 
---

### 设置对齐规则
```
#pragma pack(1)
```

```
struct Node
{
   char a;
   int b;
   double c;
};
```

![1](https://github.com/lyb6537/lyb6537.github.io/blob/master/public/img/data-struct/1.jpg);


```
struct Node
{
   char a;
   double b;
   int c;
};
```

![2](https://github.com/lyb6537/lyb6537.github.io/blob/master/public/img/data-struct/2.jpg);


```
struct Node
{
   double a;
   char b;
   int c;
};
```

![3](https://github.com/lyb6537/lyb6537.github.io/blob/master/public/img/data-struct/3.jpg);

```
struct Node
{
   double a;
   char b;
   int c;
   char d;
};
```

![4](https://github.com/lyb6537/lyb6537.github.io/blob/master/public/img/data-struct/4.jpg);

```
struct Node
{
    double a;
    char b;
    int c;
    char d;
    int e; 
};
```

![5](https://github.com/lyb6537/lyb6537.github.io/blob/master/public/img/data-struct/5.jpg);

```
struct Node
{
    int e;
    double a;
    char b;
    int c;
    char d;
};
```

![6](https://github.com/lyb6537/lyb6537.github.io/blob/master/public/img/data-struct/6.jpg);


## 参考资源
1. [结构体对齐](http://blog.csdn.net/liukun321/article/details/6974282)
