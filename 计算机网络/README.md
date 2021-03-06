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

## 6. HTTP 2.0 和 HTTP1.1 的区别

ME:  
---  
http2.0比http1.1增加了三个功能:  
+ 增加了多路复用功能；  
+ 头部数据压缩；  
+ 服务器推送。  

ANSWER:  
---  
[http2.0和http1.1的区别](https://blog.csdn.net/tugangkai/article/details/88729171)  

## 7. tcp和udp区别  

ME:  
---  
+ TCP是面向流传输的，UDP是面向报文传输的；    
+ TCP可靠(序号+ack+重传)，UDP不可靠；  
+ TCP会建立连接，一对一传输，UDP不需要建立连接，可以多对多传输；  
+ TCP有拥塞控制，UDP没有；  
+ TCP首部报文长20字节，UDP首部报文长8字节；  
+ TCP传输速度慢于UDP； 
+ TCP有序，UDP无序；     
+ TCP适合的场景对准确性要求较高，如邮件传输等；  
+ UDP适合的场景对速度要求较高，如视频通话，直播等。  

ANSWER:  
---  
[TCP和UDP的区别](https://www.cnblogs.com/williamjie/p/9390164.html)  

## 8. http和https区别  

ME:  
---  
+ HTTP使用80端口，HTTPS使用443端口；  
+ HTTP明文传输，HTTPS加密传输（对称加密+非对称加密）HTTP+SSL/TLS  
+ HTTPS使用前需要向CA申请证书，相当耗钱。  

ANSWER:  
---  
[http和https区别](https://www.leiue.com/http-vs-https)  

## 9. session和cookies的区别  

ME:  
---  
+ cookies是客户端保存消息的一种方式，session是服务器保存消息的一种方式。  
+ cookie不安全，可以进行cookie欺骗，session比较安全  
+ session保存在服务器上，大量的session会造成服务器性能方面的问题。  

ANSWER:  
---  
[Cookie和Session的区别](https://www.jianshu.com/p/2f7031a69f43)  

## 10. POST/GET请求  

ME:  
---  
+ GET请求参数在url中，？隔开格式为url？k=v&k=v；POST请求在请求体中。  
+ GET参数有长度限制，POST无长度限制。  
+ GET只能是ASCII编码，POST可以是任意编码。  
+ GET不安全，POST安全。  

ANSWER:  
---  
[get/post请求区别](https://www.cnblogs.com/wgyi140724-/p/10577053.html)  

## 11. HTTP保持长连接  

ME:  
---  
HTTP首部中可以设置Connection:keep-alive,设置过期时间Keep-Alive: timeout=60。  

ANSWER:  
---  
[HTTP保持长连接](https://www.cnblogs.com/kabi/p/7693500.html)  

## 12. HTTP请求包含的部分  

ME:  
---  
http请求包含请求行，请求头，空行，请求数据

ANSWER:  
---  
[HTTP请求包含的部分](https://www.cnblogs.com/sweeeper/p/11243756.html)  

