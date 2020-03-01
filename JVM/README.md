# JVM面试题
## 1. jvm垃圾回收算法  

ME:  
---  
JVM判断垃圾机制：  
+ 引用计数法(简单，但是会出现循环引用的情况)
+ 可达性算法

JVM中常用的垃圾回收算法:  
+ 标记清除法  
+ 复制法  
+ 标记整理法  
+ 分代算法  

ANSWER:  
---  
[JVM的垃圾回收机制 总结](https://www.cnblogs.com/aspirant/p/8662690.html)  

## 2. CMS垃圾回收器回收过程  

ME:  
---  
CMS垃圾回收器采用的是标记清理法，清理过程分为4个步骤：
+ 初步标记(仅标记GC roots直接达到的对象)
+ 并发标记  
+ 最终标记  
+ 并发清理  

ANSWER:  
---  
[CMS垃圾收集器](https://www.jianshu.com/p/86e358afdf17)  