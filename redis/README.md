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

