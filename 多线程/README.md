# 多线程面试题  
## 1. 线程池的参数如何作用  

ME:  
---  
1. 核心线程数  
2. 最大线程数  
3. 空闲时间  
4. 空闲时间单位  
5. 阻塞队列  
6. 线程工厂  
7. 异常处理策略  

ANSWER:  
---  
[JAVA线程池有哪些配置参数，各自的作用是什么？](https://www.cnblogs.com/yefeng654321/articles/11253842.html)  

## 2. 自旋锁  

ME:  
---  
自旋锁是指线程在获取锁的时候，如果锁被其他线程获取，则一直循环等待，直到获取成功。一般使用CAS判断锁的状态。这种方式可以是线程一直处于active状态，不会被阻塞从而陷入内核态，减少了线程从内核态到用户态的切换。  

ANSWER:  
---  
[自旋锁到底是什么](https://www.jianshu.com/p/9d3660ad4358?utm_source=oschina-app)  

## 3. Java的Synchronized锁的是什么东西？  

ME:  
---  
方法锁锁的是调用这个方法的对象；  
代码块锁的是指定的对象；  
类锁锁的是类对象。  

ANSWER:  
---  
[Java synchronized到底锁住的是什么？](https://www.cnblogs.com/LearnAndGet/p/9365752.html)  