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

## 4. 