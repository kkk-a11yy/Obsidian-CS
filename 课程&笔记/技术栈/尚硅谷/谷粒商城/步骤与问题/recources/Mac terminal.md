
``` r
//连接不成功原因可能是没关闭防火墙
ksia@bogon ~ % ssh root@192.168.0.103
root@192.168.0.103's password: 
[root@bogon ~]# 
```


----

# 防火墙命令

``` r
sudo systemctl stop firewalld
sudo systemctl disable firewalld
sudo systemctl status firewalld
sudo systemctl enable firewalld
sudo systemctl start firewalld

```