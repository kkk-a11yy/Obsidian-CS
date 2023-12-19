## 参考资料
- [CentOS Stream 9设置静态IP_centos-stream-9 7的qubie_zhongxj183的博客-CSDN博客](https://blog.csdn.net/zhongxj183/article/details/122811236)

## 查看虚拟机当前ip

```java
[root@bogon ~]# ifconfig
enp0s5: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.0.105  netmask 255.255.255.0  broadcast 192.168.0.255
        inet6 fe80::21c:42ff:fe40:e86d  prefixlen 64  scopeid 0x20<link>
        ether 00:1c:42:40:e8:6d  txqueuelen 1000  (Ethernet)
        RX packets 814548  bytes 1002356277 (955.9 MiB)

```

## 查看虚拟机当前路由

```java
[root@bogon ~]# route -n
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
0.0.0.0         192.168.0.1     0.0.0.0         UG    100    0        0 enp0s5
172.17.0.0      0.0.0.0         255.255.0.0     U     0      0        0 docker0
192.168.0.0     0.0.0.0         255.255.255.0   U     100    0        0 enp0s5
```

## 关闭防火墙

[查看防火墙状态](https://so.csdn.net/so/search?q=%E6%9F%A5%E7%9C%8B%E9%98%B2%E7%81%AB%E5%A2%99%E7%8A%B6%E6%80%81&spm=1001.2101.3001.7020)：`systemctl status firewalld`  
关闭当前防火墙：`systemctl stop firewalld.service`  
永久关闭（重启后生效）： `systemctl disable firewalld.service`

## 修改

	m1pro 的enp0s5的文件路径：`/etc/NetworkManager/system-connections/enp0s5.nmconnection`
	
```java
[root@bogon ~]# cd /etc/NetworkManager/system-connections/
[root@bogon system-connections]# ls
enp0s5.nmconnection
[root@bogon system-connections]# vi enp0s5.nmconnection 

[connection]
id=enp0s5
uuid=91bed26a-1729-3de5-a92e-072133c18cc9
type=ethernet
autoconnect-priority=-999
interface-name=enp0s5
timestamp=1690295354

[ethernet]

[ipv4]
method=auto

[ipv6]
addr-gen-mode=eui64
method=auto

[proxy]
~                                                                               
~                                                                               
~                                                                               
~                                                                               
~                                                                               
"enp0s5.nmconnection" 18L, 229B                               18,1         全部
```


- 打开网络设置，修改为以下值：
	- ipaddr: mac主机是 `192.168.0.101` , 这里的前8位保持一致
	- 子网掩码：`255.255.255.255`
	- 网关：GATEWAY：通常前三组数和ip地址是一样的，最后一个是1，不然没法访问外网
	- DNS: `114.114.114.114,8.8.8.8`
		![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230830134836.png)
- 然后重启网络和网卡,查看ip,ping主机看是否能连通：
```java
sudo nmcli c reload
sudo nmcli c up enp0s5

```
- ![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230829231000.png)