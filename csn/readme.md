# 第十八章、线程
进程为了创建一条新的执行流复制了父进程整个内存空间，包括堆栈，堆和其他内存。
但是除了堆栈，其余内存空间是不需要复制的。

进程：在操作系统构成单独执行流的单位。
线程：在进程构成单独执行流的单位。

通过 sleep 来控制进程流是极其困难的，不过幸好我们有 pthread_join 函数。

pthread_join线程安全函数结尾通常是 `_r` 。

互斥量：mutex
信号量：semaphore

线程的销毁：
``` c++
pthread_join(); // 会阻塞调用线程的函数
pthread_detach();   // 不会阻塞
```
# 多线程 TCP 聊天服务器