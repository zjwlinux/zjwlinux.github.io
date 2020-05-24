---
title: UDP
date: 2020-05-22 17:10:07
categories:
-   网络
tags:
-   UDP
---

简介
<!--more-->

## 概要
UDP(User Datagram Protocol) 指用户数据包协议。特点是传输比 TCP 速度快，但是出错的可能性大，主要用于对数据准确性要求不高的视频、音频的传输。

## 结构
UDP 数据包由首部和数据组成  
首部有 8 个字节，分成 4 个字段
* 源端口号
* 目标端口号
* 长度
* 校验和

长度定义了数据包的总长度，包括首部和数据

校验和用来检验接收的数据包是否出错，校验和的计算使用了整个数据包的数据，包括首部和数据。

### 数据包大小
UDP 数据包的**数据部分**长度范围是 0~65507 字节。但是实际应用中，**数据部分**的长度通常不会这么大，这是受到底层传输协议的限制。  
1. 在链路层，由以太网的特性限制，一个数据帧的长度范围是 (46 + 18) 字节到 (1500 + 18) 字节，其中 18 指数据帧的头和尾的长度，因此数据部分最多只有 1500 字节，即 MTU(Maximum Transmission Unit) 为1500 字节。  
2. 在网络层，IP 数据包的头部需要 20 个字节，因此 MTU = 1500 - 20 = 1480 字节
3. 在传输层，UDP 数据包的头部需要 8 个字节，因此 MTU = 1480 - 8 = 1472 字节

因此，在应用层，UDP 数据包的数据部分最大长度为 1472 字节，如果超出 1472 字节，在网络层就需要分片传输，即分成多个 IP 包传输。在接收方的网络层需要对多个 IP 分片进行重组，因为 UDP 是不可靠传输协议，因此如果分片丢失，则整个 UDP 数据包都会被丢弃。  
但是 1472 字节只是在局域网内的最大值，互联网上各个路由器配置的不同，标准的 MTU 为 576，从而开发时 UDP 的数据部分的最大值最好控制在 548(576 - 20 - 8 = 548)字节以内。