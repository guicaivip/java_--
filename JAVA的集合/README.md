# 集合面试题  
## 1. ArrayList和LinkedList的区别？增加元素的时间复杂度？  

ME:  
---  
+ arrayList底层实现是数组，linkedList底层实现是链表。  
+ arrayList适合元素的随机访问，即根据下标查找元素，是O(1)的操作，但是增加元素或者删除元素十分耗时，是O(n)的操作。  
+ linkedList适合增加/删除元素，O(1)的操作，然而访问元素时需要从头指针一步步查询，O(n)的操作。  

ANSWER:  
---  
[ArrayList && LinkedList](https://www.cnblogs.com/zjss/p/5232048.html)  

## 2. HashMap的底层实现  

ME:  
---  
jdk1.7及以前：数组+链表，采用头插法的方式添加链表元素。  
jdk1.8之后：数组+链表+红黑树(链表长度>=8)，采用尾插法的方式添加元素。  注意：红黑树在链表长度<7之后会退化成链表。  

ANSWER:  
---  
[HashMap底层实现和原理](https://blog.csdn.net/qq_41345773/article/details/92066554)  

## 3. HashMap如何解决哈希冲突

ME:  
---  
hashmap采用链地址法解决哈希冲突，即发生冲突时，如果value值与桶中的值相同，则更新；否则采用头插或者尾插的方式插入key-value键值对。  

ANSWER:  
---  
[hashmap实现及哈希冲突](https://www.cnblogs.com/marcocao/p/9884243.html)  

## 4. 什么时候重写hashcode()和equals()  

ME:  
---  
当往hashmap中插入的元素不是基本数据类型的数据，即自定义对象时，需要重写hashcode()和equals()方法，对对象的hashcode重新计算，重写比较算法。  

ANSWER:  
---  
[为什么要重写hashCode()和equals()方法](https://www.cnblogs.com/xinghaonan/p/11933378.html)  

