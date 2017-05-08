# TCP/IP
> Made by **uyiqgyy**  
> 8th May, 2017

## 1. What is TCP/IP
1. **TCP**:Transmission Control Protocol;**IP**:Internet Protocol
2. TCP/IP 不是一个协议，而是一个协议族的统称，里面包括了 IP 协议、ICMP 协议、TCP 协议、以及 http、ftp、pop3 协议等。网络中的计算机都采用这套协议族进行互联。
3. **OSI**:Open Systems Interconnection
![compare OSI with TCP/IP](https://dn-anything-about-doc.qbox.me/TCP_IP/TCP-1-01.png)
4. 可见 TCP/IP 被分为 4 层，每层承担的任务不一样，各层的协议的工作方式也不一样，每层封装上层数据的方式也不一样：

 1. 应用层：应用程序通过这一层访问网络，常见 FTP、HTTP、DNS 和 TELNET 协议；

 2. 传输层：TCP 协议和 UDP 协议；

 3. 网络层：IP 协议，ARP、RARP 协议，ICMP 协议等；

 4. 网络接口层：是 TCP/IP 协议的基层，负责数据帧的发送和接收。
![](https://dn-anything-about-doc.qbox.me/document-uid18510labid448timestamp1482199421440.png/wm)  

## 2. Pre-learning  
### 1. IP地址
MAC（Media Access Control）地址，或称为物理地址、硬件地址，用来定义互联网中设备的位置。

在 TCP/IP 层次模型中，网络层管理 IP 地址，链路层则负责 MAC 地址。因此每个网络位置会有一个专属于它的 IP 地址，而每个主机会有一个专属于它 MAC 地址。  

```
ifconfig -a
```
### 2. 域名
用 12 位数字组成的 IP 地址很难记忆，在实际应用时，用户一般不需要记住 IP 地址，互联网给每个 IP 地址起了一个别名，习惯上称作域名。  

域名与计算机的 IP 地址相对应，并把这种对应关系存储在域名服务系统 DNS(Domain Name System)中，这样用户只需记住域名就可以与指定的计算机进行通信了。  

常见的域名包括 com、net 和 org 三种顶级域名后缀，除此之外每个国家还有自己国家专属的域名后缀（比如我国的域名后缀为 cn）。目前经常使用的域名诸如百度（www.baidu.com）、Linux 组织（www.lwn.net）等等。
### 3. MAC地址
MAC（Media Access Control）地址，或称为物理地址、硬件地址，用来定义互联网中设备的位置。

在 TCP/IP 层次模型中，网络层管理 IP 地址，链路层则负责 MAC 地址。因此每个网络位置会有一个专属于它的 IP 地址，而每个主机会有一个专属于它 MAC 地址。
### 4. 端口号
MAC（Media Access Control）地址，或称为物理地址、硬件地址，用来定义互联网中设备的位置。

在 TCP/IP 层次模型中，网络层管理 IP 地址，链路层则负责 MAC 地址。因此每个网络位置会有一个专属于它的 IP 地址，而每个主机会有一个专属于它 MAC 地址。
### 5. 分装和分用
**封装**：当应用程序发送数据的时候，数据在协议层次当中从顶向下通过每一层，每一层都会对数据增加一些首部或尾部信息，这样的信息称之为协议数据单元（Protocol Data Unit，缩写为PDU），在分层协议系统里，在指定的协议层上传送的数据单元，包含了该层的协议控制信息和用户信息。如下图所示：

* 物理层（一层）PDU指数据位（Bit）
* 数据链路层（二层）PDU指数据帧（Frame）
* 网络层（三层）PDU指数据包（Packet）
* 传输层（四层）PDU指数据段（Segment）
* 第五层以上为数据（data）
![分层](https://dn-anything-about-doc.qbox.me/TCP_IP/TCP-1-05.png/logoblackfont)  
**分用**：当主机收到一个数据帧时，数据就从协议层底向上升，通过每一层时，检查并去掉对应层次的报文首部或尾部，与封装过程正好相反。  

### 6. RFC
RFC（Request for Comment）文档是所有以太网协议的正式标准，并在其官网上面公布，由 IETF 标准协会制定。大量的 RFC 并不是正式的标准，出版的目的只是为了提供信息。RFC 的篇幅不一，从几页到几百页不等。每一种协议都用一个数字来标识，如 RFC 3720 是 iSCSI 协议的标准，数字越大说是 RFC 的内容越新或者是对应的协议（标准）出现的比较晚。

所有的 RFC 文档都可以从网络上找到，其官网为IETF。在网站上面可以通过分类以及搜索快速找到目标协议的 RFC 文档。目前在 IETF 网站上面的 RFC 文档有数千个，但是我们不需要全部掌握，在工作或学习中如果遇到可以找到对应的解释，理论与实际结合会有更好地效果，单纯阅读 RFC 的效果一般。