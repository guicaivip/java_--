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

## 4. wait sleep区别  

ME:  
---  
+ wait是object的方法，sleep是thead类的方法；  
+ wait会释放锁资源，sleep不会释放锁资源；  
+ sleep必须传入参数，wait可以传入参数，也可以不传参数；  
+ wait必须在同步块或同步方法中使用，sleep可以在任何地方使用；  
+ wait可以不捕获异常，sleep必须捕获异常。  

ANSWER:  
---  
[sleep和wait的区别](https://www.jianshu.com/p/c83a119ef54a)  

## 5. 乐观锁和悲观锁  

ME:  
---  
+ 乐观锁是指线程在操作数据时认为其他线程不会对这个数据进行修改，只有在修改数据时会检查数据的版本号是否发生过改变，适合于多读的场景，CAS就是使用的乐观锁技术。  
+ 悲观锁是指线程在操作数据时认为其他线程会对数据进行修改，因此只要拿到数据就会对数据上锁，防止其他线程修改数据，适合于多写的场景，synchronized就是悲观锁。  

ANSWER:  
---  
[乐观锁和悲观锁](https://blog.csdn.net/qq_34337272/article/details/81072874)  