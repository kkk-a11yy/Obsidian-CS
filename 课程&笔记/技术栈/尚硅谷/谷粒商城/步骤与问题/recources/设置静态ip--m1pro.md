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