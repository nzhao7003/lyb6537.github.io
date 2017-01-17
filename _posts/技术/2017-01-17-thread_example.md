---
layout: post
title: thread_example
category: 技术
tags: Linux
keywords: 
description: 
---

#### 函数流程
主函数创建st_len个线程，每个线程将字符串st的指定索引所对应的字符打印COUNT次，通过条件变量和互斥锁使得打印出的顺序和指定的顺序相同。

#### 例如

##### 初始化
* COUNT=10
* FIRST_INDEX=1
* st = "ABC123";

##### 输出
BC123ABC123ABC123ABC123ABC123ABC123ABC123ABC123ABC123ABC123A

#### linux下程序的编译与运行
* $ make clean && make
* $ ./thread

#### [完整项目]( https://github.com/lyb6537/Thread ) 


####  代码详情
```
#include <stdio.h>
#include <pthread.h>
#include <string.h>
#include <stdlib.h>

#define COUNT 10                               //打印的次数
#define FIRST_INDEX 1                          //起始索引      

static char*           st       = "ABC123";    //打印的字符串
static int             st_len   = 0;           //字符串的长度以及线程的个数
static int 	       st_index = FIRST_INDEX; //字符串的索引

static pthread_mutex_t mutex;                  //互斥锁
static pthread_cond_t  cond;                   //条件变量

static void* thread(void*);                    //线程函数

int main(int argc, char** argv) {
	pthread_t* id;
	int i;

	st_len = strlen(st);
	id = (pthread_t*)malloc(sizeof(pthread_t)*st_len);
	if (id==NULL) {
		puts( "pthread malloc error" );
		return -1;
	}

	pthread_cond_init( &cond,  NULL);  //条件变量初始化
	pthread_mutex_init(&mutex, NULL);  //互斥锁初始化

	for (i = 0; i < st_len; ++i) {
		pthread_create(id+i, NULL, thread, st+i);  //线程创建
	}

	for (i = 0; i < st_len; ++i) {
		pthread_join(id[i], NULL);  //线程等待
	}

	puts("");	

	pthread_mutex_destroy(&mutex); //互斥锁销毁
	pthread_cond_destroy( &cond );  //条件变量销毁
	free(id);

	return 0;
}

//线程函数---打印指定的字符COUNT次
static void* thread(void* arg) {
	int k = (char*)arg - st;                 //该线程打印索引k，所对应的字符
	int i;

	for (i = 0; i < COUNT; ++i) {
		pthread_mutex_lock(&mutex); //互斥锁加锁
		while (st_index != k) {
			pthread_cond_wait(&cond, &mutex); //条件变量等待
		}
		st_index = ( st_index + 1 ) % st_len;     
		putchar(st[k]);
		pthread_cond_broadcast(&cond); //条件变量广播
		pthread_mutex_unlock(&mutex);  //互斥锁解锁
	}

	return NULL;
}
```
