# 401.2

# Module 7:Defense-in-Depth

纵深防御，全方面的防御措施。单层次的安全措施已经无法保证，整个运转系统的安全

## Risk

- 安全是减少损失的一项活动
- 也没有绝对的安全
- 风险是一种 威胁能够变成漏洞造成损失的概率

## CIA Triad

安全性的关键

- 机密性Confidentiality
- 完整性Integrity
- 可用性Availability

## What is a Threat?

- Possible danger 
- Protect against the ones that are most likely or most worrisome based on:
  - Intellectual property
  - Business goals
  - Validated data
  - Past history
- Primary threats:
  - Malware
  - Insider
  - Natural disasters
  - Terrorism
  - Pandemic



## Approaches to DiD

- Deploy measures to reduce, eliminate, or transfer risk
- Four basic approaches:
  - Uniform protection
  - Protected enclaves
  - information centric
  - Threat vector analysis

## Viruses and Malicious Code

### Malicious Software

恶意软件是一个通用术语，指的是恶意编写并在未经用户许可的情况下执行其操作的软件。

### Viruses

病毒是一种恶意软件样本，具有复制和具有寄生特性的能力。

### COM/Script Program Infectors

宏病毒或者脚本感染

## Worms

- 自动扫描更多系统以进行攻击 
- 降低系统防御，安装rootkit或root shell，和/或通知攻击者系统已被入侵

- 允许对一组系统进行快速传播或针对性攻击

### The Morris Worm 1988

1988年莫里斯蠕虫，很著名的蠕虫攻击事件

### Linux Worms

Ramen蠕虫

在Ramen进入系统后，它：

用一个名为“Hackers looooooooooooove noodles”的网页替换系统中的所有网页，并显示拉面包的图像将密码文件邮件发送到两个电子邮件帐户，可能是攻击者所拥有的替代ps和网使用隐藏Ramen安装存在的版本并运行Stacheldraht分布式拒绝服务代理程序关闭它用于中断的漏洞



### SQL Slammer Worm

SQL Slammer蠕虫针对UDP端口1434来利用Microsoft SQL Server和Microsoft Desktop Engine（MSDE）中的缓冲区溢出漏洞。 蠕虫具有激进的传播机制，并导致本地网络的DoS。



### Sasser/Netsky Worms

Sasser被称为网络望远镜，在三天内感染了超过500,000台机器。 当悉尼的火车没有按时运行时，超过30万乘客被困; 他们的系统不仅失败了，因为他们没有安装补丁，但他们的备份系统也失败了。

### Conficker蠕虫

- 通过各种方法感染了数百万个系统
  - 可以通过3种方式传播：
     - MS Server服务中的漏洞（补丁发布5个月）
     - 通过网络共享强制密码（管理员）
     - 使用恶意自动运行脚本感染可移动设备



## Malware Capabilities

- Destruction of Data
- Leaking Confidential Information
-  Providing Backdoor Access
- Countless Other Opportunities



## Propagation Techniques

- Removable media
- E-Mail attachments
- Web browsing
- Network vulnerabilities
- Instant messaging applications
-  Peer-to-peer networks



## Malware Defense Techniques

- Activity monitoring programs
- Malware scanners
-  File and resource integrity checking
-  Stripping e-mail attachments
-  Remember defense-in-depth
-  Patch all systems



### Malware Analysis

- 强化系统或者修复系统
- 使用新技术重构系统



