#  Parallels desktop 安装 CentOS9
- M1的芯片选择ARM64版本
-  [下载 CentOS Linux 7-2009-ARM64](https://www.centos.org/download/)诶很奇怪下了7安装不了，就下了 Stream9
- 下载工具：Flox
- SSH工具：- [EmTec Innovative Software - About to Download ZOC8 (macOS)](https://www.emtec.com/cgi-local/download.php?what=ZOC8%20(macOS)&link=zoc/zoc8064.dmg&ext=html)
- 
# 虚拟机信息：
- 用户名：root , centos9
- password：123456
	- **Parallels Desktop 在安装 centos 的时候是默认不激活root这个超级用户的，需要手动激活**
- 名称：CentOS Linux
- 安装路径：/Volumes/VM/Parallels
- 查看安装的虚拟机版本：`cat /etc/redhat-release`
- 进入root用户：`su root ` 本机密码：123456
- ip: 
	- centos9: 
		- `ip addr` 
		- 查看可配置的ip网段：
			![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230808205031.png)
		- enp0s5: 
			- inet 10.211.55.7    host-only.  
			- inet 10.37.129.3. shard
	- mac m1 pro : 
		- `ifconfig`  或者  option+wifi图标
		- en0  :  192.168.0.101
# m1 pro SSH连接虚拟机服务器：（terminal）

- 前提：要有你需要连接的服务器的ip，端口号，服务器上的账户和密码 
	- 1、首先打开终端，然后输入sudo su – 回车进入根目录 
	- 2、然后输入：ssh -p 端口号 服务器用户名@ip （例如ssh -p 22 userkunyu@119.29.37.63
# 设置静态IP
- 参考文章：
	- [我应该对虚拟机使用哪种网络模式（桥接、共享还是 Host-Only）？](https://kb.parallels.com/cn/4948)
	-  [Parallels Desktop 16共享网络、桥接网络和Host-Only网络设置方法-软件-众番科技资讯网](https://www.szxnet.com/articles/501.html)	
- 设置虚拟机网络为桥接模式的默认适配器模式
	- ![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230809165010.png)
	- ip地址变为：`192.168.101.104`
	- 互相ping,可以ping通
- but后续虚拟机还是会换ip , 故还是设置静态ip
	- [设置静态ip--m1pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/设置静态ip--m1pro.md)
