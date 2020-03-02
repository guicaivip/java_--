# 分布式面试题  
## 1. 分布式锁的实现方式  

ME:  
---  
+ 利用redis实现分布式锁
    + setnx key value / expire key 过期时间  
    + set key value nx px 时间  
+ 利用mysql数据库实现分布式锁  

ANSWER:  
---  
[分布式锁三种实现方式](https://www.jianshu.com/p/1b139f037b15)  