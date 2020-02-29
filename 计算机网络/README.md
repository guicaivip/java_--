# 计算机网络面试题
## 1. TCP的4层模型  
数据链路层 -> 网络层 -> 传输层 -> 应用层
![TCP的4层模型](https://img-blog.csdn.net/20180930155137505?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZG5fa291/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)  

## 2. TCP的三次握手  

ME:
---  
客户端会先给服务器发送一个SYN信号，服务器在收到之后会回传一个SYN+ACK的信号，最后客户端回复ACK信号，双方正式建立连接。  

ANSWER:  
---  
第一次握手：建立连接时,客户端发送syn包(syn=j)到服务器,并进入SYN_SEND状态,等待服务器确认； SYN：同步序列编号(Synchronize Sequence Numbers)  
第二次握手：服务器收到syn包,必须确认客户的SYN（ack=j+1）,同时自己也发送一个SYN包（syn=k）,即SYN+ACK包,此时服务器进入SYN_RECV状态；   
第三次握手：客户端收到服务器的SYN＋ACK包,向服务器发送确认包ACK(ack=k+1),此包发送完毕,客户端和服务器进入ESTABLISHED状态,完成三次握手.

![TCP的三次握手](http://blog.chinaunix.net/attachment/201304/8/22312037_1365405910EROI.png)  

## 3. 输入域名发生了什么  

ME:  
---
+ 浏览器解析网址，获得URL  
+ DNS查找URL对应的IP地址  
    + 检查浏览器缓存  
    + 检查本地缓存
    + 检查路由器缓存
    + 检查ISP缓存
+ 利用获得的IP地址和默认端口建立TCP连接
+ 浏览器发送请求
+ 服务器处理请求，发送响应信息
+ 浏览器解析HTML代码，并请求资源
+ 浏览器渲染得到网页

ANSWER:  
---  
[输入一个网址后发生了什么](https://blog.csdn.net/kongmin_123/article/details/82555936)  

## 4. TCP的四次挥手  

ME:
---  
第一次挥手：客户端向服务器发送FIN信号，并进入FIN-WAIT1状态  
第二次挥手: 服务器向客户端发送FIN+ACK信号，并进入CLOSE-WAIT状态，客户端接收后进入FIN-WAIT2状态  
第三次挥手：服务器再次发送FIN+ACK信号，并进入LASKT-ACK状态  
第四次挥手：客户端发送ACK信号后，进入TIME-WAIT状态，等待2MSL后，关闭连接   

ANSWER:  
---  
[TCP四次挥手过程](https://blog.csdn.net/O9A0MA/article/details/90731748)  
![四次挥手](https://img-blog.csdnimg.cn/20190602181243782.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L085QTBNQQ==,size_16,color_FFFFFF,t_70)  

## 5. TCP的拥塞控制  

ME:  
---  
+ 慢开始：发送端在发送数据时，会先从一个报文段开始发送，之后指数增长，直到达到慢开始门限。  
+ 拥塞避免：达到慢开始门限之后，发送端会一个一个报文段的增加，如果发生拥塞情况，会将慢开始门限设定为当前报文段的一半。  
+ 快重传：当发送端连续收到3个重复确认时，发送端会直接重发报文，而不是等待报文超时。  
+ 快恢复：当发送端收到3个重复确认后，把慢开始门限减半，直接进行拥塞避免算法。  

ANSWER：  
---  
[TCP拥塞控制](https://www.cnblogs.com/wuquaaa/p/11953352.html)  

