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

## 5. ConcurrentHashMap，1.8中怎么实现线程安全  

ME:  
---  
node + volatile + CAS + synchronized  

ANSWER:  
---  
[ConcurrentHashMap 1.8中怎么实现线程安全](https://www.cnblogs.com/junjiang3/p/8686290.html)  

## 6. set原理  

ME:  
---  
set底层实现是用hashmap实现的，key值保存要存储的值，value值为随便一个值，因此set只能保存一个值，不能保存重复的数值。  

ANSWER:  
---  
[Java Set类](https://www.jianshu.com/p/3950f64821a6)  

## 7. Hashmap中的get和put  

ME:  
---  
+ put  
hashmap会先将key值计算哈希之后，与桶的长度取余，在编号为余数的桶中去放入数据，如果里面没有数据，直接放入key-value；如果存在数据，判断key是否相等，相等则更新，不相等则采用头插法或者尾插法的方式往链表中插入数据。  
+ get  
hashamp使用get方法时，会先对key值计算哈希取余之后，和对应桶中的数据进行比较，key相等，返回value，负责遍历链表，找到相同的key，返回value,没有返回null。  

ANSWER:  
---  
[Java中HashMap的put与get方法原理](https://www.cnblogs.com/kangkaii/p/8473793.html)  

## 8. set list区别  

ME:  
---  
+ set中的元素无序且不重复，而list中的数据可以重复且有序；  

ANSWER:  
---  
[Java中的list和set有什么区别](https://www.cnblogs.com/q2546/p/11394723.html)  

## 9. 数组怎么实现对象排序  

ME:  
---  
java的数组实现对象排序，可以实现comparable类，重写compareTo(Object o)方法,或者实现comparator类，重写compare(Object o1, Object o2)方法，然后使用Arrays.sort()方法排序。  

ANSWER:  
---  
[如何在Java中对对象数组进行排序？](http://www.imooc.com/wenda/detail/581283)  

