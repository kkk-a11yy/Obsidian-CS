# 下载centos9 mysql8.0

- 由于是m1pro的芯片， 要选择支持arm架构的mysql版本
```r
docker pull mysq:8.0

root@bogon ~]# docker images
REPOSITORY   TAG       IMAGE ID       CREATED                  SIZE
mysql        8.0       6a0560a40914   Less than a second ago   599MB
```

# docker 容器文件挂载与端口映射
``` r

	//注意8的版本mysql位子已经改变了-v /mydata/mysql/conf:/etc/mysql \  这个改为 -v /mydata/mysql/conf:/etc/mysql/conf.d \

sudo docker run -p 3306:3306 --name mysql \      
-v /mydata/mysql/log:/var/log/mysql \
-v /mydata/mysql/data:/var/lib/mysql \
-v /mydata/mysql/conf:/etc/mysql/conf.d \
-e MYSQL_ROOT_PASSWORD=root \
-d mysql:8.0

		 -p : 是Linux中的MySQL容器里面装的MySQL的端口号3306和Linux的端口号映射,访问linux的3306就可以访问容器mysql的3306
		 -name: 给当前容器起名叫mysql
		 -v:  目录挂载：每个命令的冒号前面是linux的，后面是mysql的，这几步是做一个端口映射和log、lib、etc这几个文件的挂载挂载，挂载后去linux的对应文件夹下修改，对应的mysql下的文件也就改了
		 -d: 初始化root用户密码
		 注意：防火墙关闭：`systemctl stop firewalld `、挂在目录可以先不加、加的话要看三个目录是否存在，且里面不能有东西
		 启动不了的，购买的云服务器，去安全组开放一下端口，试试 `run mysql  --priviledged=true`
		 高版本mysql要额外设置，连接不上的搜索：mysql 运行外网主机访问


//查看容器是否启动
[root@bogon ~]# docker ps
CONTAINER ID   IMAGE       COMMAND                   CREATED         STATUS         PORTS                                                  NAMES
c57e3d9cf27e   mysql:8.0   "docker-entrypoint.s…"   6 minutes ago   Up 6 minutes   0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 33060/tcp   mysql


-------

//问题：可能是因为 iptables 配置或 Docker 的网络问题。
	docker: Error response from daemon: driver failed programming external connectivity on endpoint mysql (e4e74e1cafdb1d2364b193d318b95305d965a64392068d4ec93e82e137a73189):  (iptables failed
	//解决：
sudo systemctl restart iptables
sudo systemctl restart docker

docker stop <container name/id>
docker rm <>

------
如果文件挂载有报错 在上面的启动脚本中 加 --privileged==true

------

//进入到容器内部，mysql是一个小小的linux														 [root@bogon ~]# docker exec -it mysql /bin/bash
bash-4.4# ls /
bin   dev			  entrypoint.sh  home  lib64  mnt  proc  run   srv  tmp  var
boot  docker-entrypoint-initdb.d  etc		 lib   media  opt  root  sbin  sys  usr

//查看挂载目录
[root@bogon ~]# cd /mydata/
[root@bogon mydata]# ls
mysql
```

# 修改cetnos9下mysql容器的my.cnf文件

``` r
//登陆
ksia@bogon ~ %  ssh root@192.168.0.103

root@192.168.0.103's password: 
Activate the web console with: systemctl enable --now cockpit.socket

Last login: Fri Aug  4 11:00:03 2023 from 192.168.0.101

//查看要修改的文件夹
[root@bogon ~]# cd /mydata/mysql/conf
[root@bogon conf]# ls
my.cnf

//修改my.cnf文件内容
[root@bogon conf]# cat my.cnf 
[client]
default-character-set=utf8
[mysql]
default-character-set=utf8
[mysqld]
init_connect='SET collation_connection = utf8_unicode_ci'
init_connect='SET NAMES utf8'
character-set-server=utf8
collation-server=utf8_unicode_ci
skip-character-set-client-handshake
skip-name-resolve

//修改完重启容器
[root@bogon /]# docker restart mysql
mysql
```

# 在容器mysql内部查看挂载目录下文件的修改内容

``` r
//进入到mysql的交互模式
[root@bogon ~]# docker exec -it mysql /bin/bash

	//查看文件my.cnf,路径为：/etc/mysql/conf.d/my.cnf
bash-4.4# pwd
/etc/mysql/conf.d
bash-4.4# cat my.cnf 
[client]
default-character-set=utf8
[mysql]
default-character-set=utf8
[mysqld]
init_connect='SET collation_connection = utf8_unicode_ci'
init_connect='SET NAMES utf8'
character-set-server=utf8
collation-server=utf8_unicode_ci
skip-character-set-client-handshake
skip-name-resolve
```
# mac mysql
下载：
- [MySQL :: Begin Your Download](https://dev.mysql.com/downloads/file/?id=520742)
安装mysql：
- [MySQL for Mac（M1）安装指南](https://www.zhihu.com/tardis/zm/art/360858309?source_id=1003)
- [mac for m1(arm)：安装mysql的三种方式（本机安装、虚拟机安装、docker安装） - 掘金](https://juejin.cn/post/7103508875634016270)
- [Navicat Premium for Mac 破解版下载 Mac上最强大的数据库客户端 - 麦氪搜(iMacSO.com)](https://www.imacso.com/navicat-premium.html)

	root:
		password:123456root
	登陆：
```text
mysql -u root -p
```