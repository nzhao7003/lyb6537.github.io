## 这是关于多线程的常用变量和函数的使用
* `include<pthread.h>`
* gcc -o thread main.c -pthread


### pthread
* pthread_t id;----------------------------------线程ID
* pthread_create(&id, NULL, thread, st);---------线程的创建
* pthread_join(id, NULL);------------------------线程等待
* pthread_exit(st);------------------------------线程退出


### pthread_mutex
* pthread_mutex_t mutex;-------------------------互斥锁ID
* pthread_mutex_init(&mutex, NULL);--------------互斥锁初始化
* pthread_mutex_lock(&mutex);--------------------互斥锁加锁
* pthread_mutex_unlock(&mutex);------------------互斥锁解锁
* pthread_mutex_destroy(&mutex);-----------------互斥锁资源释放


### pthread_cond
* pthread_cond_t cond;---------------------------条件变量ID
* pthread_cond_init(&cond, NULL);----------------条件变量初始化
* pthread_cond_wait(&cond, &mutex);--------------条件变量阻塞
* pthread_cond_signal(&cond);--------------------条件变量解除阻塞
* pthread_cond_broadcast(&cond);-----------------条件变量解除所有线程上的阻塞
* pthread_cond_destroy(&cond);-------------------条件变量释放资源



