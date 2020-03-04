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

## 3. 类加载机制  

ME:  
---  
类加载机制分为三个大的步骤，五个小步骤:  
+ 加载：将类的二进制文件加载到内存中  
+ 连接  
    + 验证：验证文件是否符合jvm规范，是否安全  
    + 准备：为类的类变量分配内存，设置默认初始值    
    + 解析：将常量池中的符号引用替换为直接引用  
+ 初始化： 类变量初始化  

ANSWER:  
---  
[类加载机制](https://www.cnblogs.com/jsersudo/p/10179082.html)  

## 4. 双亲委派机制  

ME:  
---  
java类的加载器有4类：  
+ bootstrp loader  
+ extClassLoader  
+ AppClassLoader  
+ 自定义类加载器  
java在加载类时会先把请求委派给父类加载器，如果加载不成功，则交给子类处理。  

ANSWER:  
---  
[什么是双亲委派机制？](https://www.cnblogs.com/SuperManer/p/11935948.html)  

## 5. 什么是内存泄漏？哪些情况造成内存泄漏？  

ME:  
---  
内存泄露是指一些无用的对象无法被GC回收。  
+ 静态集合类。    
+ 监听器。  
+ 连接未释放。  

ANSWER:  
---  
[java中是否存在内存泄漏？什么情况下才是内存泄漏？](https://blog.csdn.net/qq_44941119/article/details/97008877)  

## 6. JVM内存结构  

ME:  
---  
1.7以前:  
+ 堆  
+ 方法区  
+ 虚拟机栈  
+ 本地方法栈  
+ 程序计数器  

1.8之后将方法区变成了元数据区， 元数据区使用的是本地内存，而不是堆内存。  

ANSWER:  
---  
[JVM内存结构](https://blog.csdn.net/rongtaoup/article/details/89142396)  