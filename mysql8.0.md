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

	 -p : 是Linux中的MySQL容器里面装的MySQL的端口号3306和Linux的端口号映射
	 -name: 给当前容器起名叫mysql
	 -v:  目录挂载：每个命令的冒号前面是linux的，后面是mysql的，这几步是做一个端口映射和log、lib、etc这几个文件的挂载挂载，挂载后去linux的对应文件夹下修改，对应的mysql下的文件也就改了
	 -d: 初始化root用户密码
	 注意：防火墙关闭：`systemctl stop firewalld `、挂在目录可以先不加、加的话要看三个目录是否存在，且里面不能有东西
	 启动不了的，购买的云服务器，去安全组开放一下端口，试试 `run mysql  --priviledged=true`
	 高版本mysql要额外设置，连接不上的搜索：mysql 运行外网主机访问
```