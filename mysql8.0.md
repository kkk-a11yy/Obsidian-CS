# centos9 mysql8.0
- 下载：
由于是m1pro的芯片， 要选择支持arm架构的mysql版本
```r
docker pull mysq:8.0

root@bogon ~]# docker images
REPOSITORY   TAG       IMAGE ID       CREATED                  SIZE
mysql        8.0       6a0560a40914   Less than a second ago   599MB

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
	docker: Error response from daemon: driver failed programming external connectivity on endpoint mysql (e4e74e1cafdb1d2364b193d318b95305d965a64392068d4ec93e82e137a73189):  (iptables failed: iptables --wait -t nat -A DOCKER -p tcp -d 0/0 --dport 3306 -j DNAT --to-destination 172.17.0.2:3306 ! -i docker0: iptables: No chain/target/match by that name.

	//解决：
sudo systemctl restart iptables
sudo systemctl restart docker

docker stop <container name/id>
docker rm <>

//进入到容器内部，mysql是一个小小的linux														 [root@bogon ~]# docker exec -it mysql /bin/bash
bash-4.4# ls /
bin   dev			  entrypoint.sh  home  lib64  mnt  proc  run   srv  tmp  var
boot  docker-entrypoint-initdb.d  etc		 lib   media  opt  root  sbin  sys  usr

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