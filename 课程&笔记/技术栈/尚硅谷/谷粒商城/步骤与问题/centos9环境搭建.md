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
- ip: 
	- centos9: 
		- `ip addr` 
		- enp0s5: 
			- inet 10.211.55.7    host-only.  
			- inet 10.37.129.3. shard
			- 设置静态网络：192.168.0.24
	- mac m1 pro : 
		- `ifconfig`  或者  option+wifi图标
		- en0  :  192.168.0.101
# m1 pro SSH连接虚拟机服务器：（terminal）

- 前提：要有你需要连接的服务器的ip，端口号，服务器上的账户和密码 
	- 1、首先打开终端，然后输入sudo su – 回车进入根目录 
	- 2、然后输入：ssh -p 端口号 服务器用户名@ip （例如ssh -p 22 userkunyu@119.29.37.63
# 设置静态IP

- `CentOS Stream 9` 的网卡配置文件移动在 `/etc/NetworkManager/system-connections/` 目录下
- 重启：
``` r
nmcli c reload
nmcli c up enp0s5		
```

``` bash

```