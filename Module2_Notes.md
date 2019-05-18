# Module 2: IP Concepts I  

## 网络协议

为了在不同的网络主体之间进行网络通信而指定的标准的规范，为了方便管理，协议划分一系列的协议栈，从而层级之间传递数据，提供服务

### OSI协议栈（七层）【ISO组织制定】

- 物理层(Physical Layer) - 物理介质上的传输，电压脉冲等等
- 数据链路层（Data Link Layer）- 可以理解为数据包与电信号的一个转换
- 网络层（Network Layer）- 不同网络、网段上的传输
- 传输层（Transport Layer）- 端到端的网络传输
- 会话层（Session Layer）- 系统之间连接的建立，协商设置维护连接
- 表示层（Presentation Layer）- 确保传输两端数据格式的可用性
- 应用层（Application Layer）- 与系统上的不同应用程序交互

### TCP/IP协议栈（四层）

- 网络层
- internet层（IP）
- 传输层（TCP）
- 应用层

### 协议栈是如何工作的

​	下层为上层提供服务，两个网络实体通信时，可视为对应层级之间的传输，上层无需知道下层具体的处理细节。但在实际工作时，数据包经由每一层的打包处理，最终由最底层物理层在物理介质上传输，等到接收方的时候，再依次解包。

### IP - The Internet Protocol	

​	IP协议是互联网所有通信协议的基础， lP包括容错（生存时间，校验和），流量优先级（服务类型）的基本度量，并支持将大数据包分段为多个较小的数据包（lD字段，片段偏移）。

​	起初IP定义了互联网上的一个唯一主机，但在如今由于内网NAT技术，现在更多的是多个主机共用一个出口IP

## IP包

### IP包头格式（20字节）

![](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-18-085423.png)

关键字段：

- 版本号version：4bit
- 协议Protocol：8bit
- 生存时间TTL：8bit
- 分段Fragmentation - 16bit
  - 13bit 段偏移
  - 3bit 标识位
- 源地址 ： 32bit
- 目的地址： 32bit

有一个IP分片攻击，单独的包不包含危险，组合之后存在风险

便于理解的图片：

![](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-18-090043.png)

## 网络地址

### 地址的两个部分

- 地址可以分为网络部分和主机部分
- 网络地址唯一、主机地址可以不同
- 两个节点，在不同的网段，可以有相同的主机地址

### IPV4地址和子网

- IP地址唯一，4bytes — 32 bit
- A类子网 1-127 /8
- B类子网  128-191  /16
- C类子网  192-223  /24

### 子网掩码和CIDR

- 子网掩码划分了网络号和主机号
- CIDR（Classless Inter-Domain Routing），任意划分子网大小，避免浪费

### 网络地址和广播地址

- 172.20.15.0/24 这个子网的广播地址为 172.20.15.255，主机号全部都为1

### 私有网络地址

- 规定一些网段进行保留，用作私有地址，不再公网路由
- 10.0.0.0 ·> 10.255.255.255
- 172.16.0.0 ·> 172.31.255.255
- 192.168.0.0 -> 192.168.255.255
- 回环地址 127.0.0.0/8

### MAC地址和IP地址

- MAC address (Layer 2)  48bit （12 hexadecimal digits）硬件地址，厂商分配给网卡唯一
- IP address is configurable (Layer 3)  32bit

### ARP协议-地址解析协议

- 路由寻址时 把IP转换为MAC地址,IP地址映射到数据链路层上
- RARP   MAC-> IP 反向映射

### 域名系统DNS

1. 静态主机表

   存在自己的电脑里，遇到一个域名首先查询本地的hosts文件

2. 把IP地址转换为主机名

   1. 使用静态主机表
   2. 使用DNS

3. DNS层级结构

   顶级域名、一级域名、二级域名、。。。。

4. DNS查询的类型

   - 正向查询
   - 反向查询

   - 递归查询

### DNS的安全问题

攻击方式：

- Cache poisoning 
- Denial of service
- Footprinting -information leakage 
- Registration spoofing

## IPV6

- 128位长度，可容纳地址数几乎无穷
- 有更好的安全性和数据传输质量，作为ipv4的替代品，却没能替代ipv4
- ![image-20190518215420080](https://susengle-1256376498.cos.ap-beijing.myqcloud.com/2019-05-18-135423.png)
- 连续的0000 可以用 :: 表示