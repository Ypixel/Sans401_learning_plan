# Module3 IP Concepts II

- UDP、TCP、ICMP、IP协议在OSI模型中对应的层级位置，和相互关系。

![image-20190519231805354](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-19-151832.png)

## User Datagram protocol(UDP)

### 基本特点

- 无连接通信
- 只管发包，并不关心对方是否收到。通过牺牲一定的数据可靠性，来获得更高的网络吞吐量。
- 开销更少
- 如果可接受少量数据包丢失，传输效果更好

### 使用场景

- 实时流媒体传输，丢失一两个包并不影响整体，更加注重实时性。
- 少量数据的发送。如反复的DNS查询
- 组播的是实现，由一个数据源同时发送到多个接收方
- Network Time Protocol (NTP)网络时间协议NTP，用于时间同步
- BOOTP / DHCP协议 
- 网络文件系统Network File System（NFS）unix系列文件共享
- 简单网络管理协议Simple Network Management Protocol （SNMP）用作管理工具，用于查询基于网络和服务器的设备，以进行监控或故障排除。
- 简单文件传输协议Trivial File Transfer Protocol（TFTP）用作将文件从一个设备传输到另一个设备而无需身份验证的方法。 TFTP最常见的用途是更新基于网络的设备上的代码。

### UDP 头部（8 字节 开销少）

- 源端口 2bytes 16 bit  0-65535
- 目标端口 2bytes 16 bit  0-65535
- 数据报长度 2bytes
- 校验和 2bytes

## Transmission Control Protocol (TCP)

### 基本特点

1. 目前最常用的传输协议
2. 面向连接
3. 确保可靠的数据包传输
4. 开销用于最大限度的提高性能

### 使用场景

1. 提供流量控制来处理网路阻塞
2. 每个数据包可以携带大量数据
3. 传输可靠性比速度重要
4. 有更好的安全机制
5. 常用TCP端口 FTP20/21、 Telnet 23 、SMTP25、DNS53、finger79 、HTTP80、POP110、HTTPS443

### FTP (File Transfer Protocol)文件传输协议

- FTP使用了TCP，但并不等于安全
- 匿名FTP存在风险
- FTP是一个明文传输工具，本身传输就存在风险

### 建立TCP连接（三次握手）

![image-20190520102636478](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-20-022642.png)

### TCP头部（20字节）

![image-20190520103051111](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-20-023058.png)

- 源端口、目的端口各两字节
- 序号Sequence Number 4字节
- 确认号Acknowledgement Number 4字节
- 偏移量（头部长度）4bit
- Reserved保留字段 6bit
- 标志位 6bits 分别为Urgent (URG)、Acknowledgement (ACK)、Push (PSH)、Reset, (RST)、Synchronize (SYN)、Finish (FIN).
- 窗口字段  2字节
- 校验和 2字节
- 紧急指针 2bytes

### TCP 代码位/标志位

- CWR (Congestion Window Reduced) 减少拥塞窗口，与显式拥塞通知（ECN）关联
- ECE (ECN Echo)
- URG（Urgent）紧急位，表示紧急数据
- ACK (Acknowledgement) 确认位，确认标志用于确认数据的接收
- PSH (Push) 设置PSH标志以指示它不应该被缓冲，而是应该立即传递给远程应用程序进行处理
- RST (Reset)重置，设置了重置标志的数据包后，主机应立即终止包含该数据包的连接
- SYN (Synchronize) 同步，同步标志表示连接请求
- FIN (Finish)，FIN标志与SYN相反.lt表示连接正在以有序的方式关闭。它与RST形成对比，因为FIN是一种更加优雅的关闭连接的方式。

### 关闭TCP连接（四次握手）

![image-20190520115847187](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-20-035908.png)

### TCP和UDP的比较

1. TCP
   - 保证数据包的交付
   - 面向连接
   - 但是有更多的开销（慢）
   - 会话优化、纠错功能
2. UDP
   - 不保证数据包的交付
   - 无连接
   - 更少的开销（快）
   - 针对查询响应进行了优化

## Internet Control Message Protocol(ICMP) - Error reporting and troubleshooting

- 它带有关于网络状态和发生的错误情况的关键和基本信息。它不是用作数据传输的协议;而是专为错误报告和基于网络的故障排除技术而设计的。许多其他协议依赖于lCMP来执行功能并传达错误条件。

- ICMP头部 只有三个字段，虽然包在IP包中发送，但是实际上是和IP协议对等的

  ![image-20190520130812006](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-20-050826.png)

- ICMP Type ，8bit，用一个整数来表示，发送的ICMP包类型

- ICMP Code，8bit，子类型详细说明，包含更多的信息。

- ICMP Checksum 校验和，

### 常用ICMP类型和code详解

- Type0 - Echo Reply，远程服务器可达
- Type3 - Destination Unreachable ，目标不可达
  - Code 0: Network Unreachable 
  - Code 1: Host Unreachable 
  - Code 3: Port Unreachable 
  - Code 9: Destination Network Administratively Prohibited
- Type5 - Redirect重定向
- Type8 - Echo Request 回应请求
- Type11- Time exceeded

### Ping命令（发送ICMP数据包，一般是Type0/Type8）

- 确定目的主机是否可达
- 确定两个位置之间的延迟
- 确定丢包率
- 猜测远程主机连接跳数
- 为了安全考虑，有时候会禁用ICMP

### Tranceroute命令




