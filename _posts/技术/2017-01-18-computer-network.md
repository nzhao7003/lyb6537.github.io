---
layout: post
title: 计算机网络基础知识
category: 技术
tags: network
keywords: 
description: 
---

## 从输入URL到界面加载完成
1. DNS 域名=>IP
2. TCP三次握手
3. 网页的请求与显示
4. TCP四次挥手

##  计算机网络基础知识
* 网关： 连接不同的网段
* 数据包跨越不同的网络时，源MAC和目的MAC会改变
* 网络字节序为大端存储
* Network   IP: 主机号全为0
* Broadcast IP: 主机号全为1
* 私有IP 
 * 10.0.0.0～10.255.255.255
 * 172.16.0.0～172.31.255.255
 * 192.168.0.0～192.168.255.255

### TCP 三次握手
1. client向server发送SYN，                client=>SYN_SENT
2. server接受client的SYN，并返回ACK和SYN   server=>SYN_RCVD
3. client接受ACK和SYN，并返回ACK           client=>ESTAB
4. server接受ACK                         server=>ESTAB

### TCP 四次释放 A端既可以是客户端，也可以是服务器端
1. A端向B端发送FIN            A=>FIN_WAIT_1       A端发送结束
2. B端接受A端的FIN,并返回ACK   B=>close_wait       B端接受结束
3. A端接受B端的ACK            A=>FIN_WAIT_2    
4. B端向A端发送FIN            B=>LAST_ACK         B端发送结束
5. A端接受B端的FIN，返回ACK    A=>TIME_WAIT 2MSL  =>closed  A端接受结束
6. B端接受ACK                B=>closed 

TIME_WAIT 的意义：

1. TCP全双工的结束
2. 互联网内重复分节的消逝

### 计算机网络的结构
1. 应用层   ： DHCP DNS FTP HTTP 16位端口号
2. 传输层   ： TCP/UDP
3. 网络层   ： 32位IP
4. 网络接口层： 48位MAC

### 计算机网络常用协议
1. DNS 域名=>ip
2. ARP IP=>MAC
3. NAT 网络地址转换

### 计算机网络常用端口
* 20 FTP-data
* 21 FTP
* 22 SSH
* 23 Telnet
* 53 DNS
* 80 www
* 443 HTTPS
