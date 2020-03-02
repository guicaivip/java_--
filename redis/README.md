# redis面试题
## 1. redis的过期策略  

ME:  
---  
+ 定时删除策略
+ 懒汉式删除
+ 定期删除

redis采用定期删除 + 懒汉式删除  

ANSWER:  
---  
[Redis过期策略](https://blog.csdn.net/qq_41864967/article/details/88424532)  

## 2. redis淘汰策略  

ME:  
---  
+ AllKeys-Random  
+ Volatile-Random  
+ AllKeys-Lru  
+ Volatile-Lru  
+ volatile-ttl  
+ noeviction  

ANSWER:  
---  
[淘汰策略](https://blog.csdn.net/ligupeng7929/article/details/79603060)  

## 3. redis持久化

ME:  
---  
redis持久化有两种方式，rdb和aof。  
+ rdb是默认的持久化方案，在指定的时间间隔内，执行写的操作，将内存中的数据写入磁盘中。  
+ aof是redis每执行一次查询以外的操作时，都会将指令以追加的方式写入日志中。  

ANSWER:  
---  
[Redis持久化](https://blog.csdn.net/tiantang_1986/article/details/90695952)  