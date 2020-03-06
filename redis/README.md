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

## 4. 缓存雪崩和缓存穿透  

ME:  
---  
+ 缓存雪崩是指redis中大量的缓存同时过了有限期，同时失效，这时所有的查询都会直接进入数据库查询，导致数据库短时间之后响应大量的请求。  
+ 缓存穿透是指故意查询数据库中没有的数据，自然不会保存在缓存中，因此查询会直接向数据库申请。  

ANSWER:  
---  
[缓存穿透、缓存击穿、缓存雪崩区别和解决方案](https://blog.csdn.net/kongtiao5/article/details/82771694)  

## 5. redis为什么快？  

ME:  
---  
+ redis是内存数据库，查询数据时不进入磁盘查询，减少了IO次数；  
+ redis是单线程数据库  
+ redis数据结构简单  

ANSWER:  
---  
[redis为什么快](https://segmentfault.com/a/1190000017375843)  

