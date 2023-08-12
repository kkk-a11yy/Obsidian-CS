# 下载
老师的是5.0.5，我下载最新的
``` r
docker pull redis
```

# 创建实例并启动
``` r

mkdir -p /mydata/redis/conf
touch /mydata/redis/conf/redis.conf

docker run -p 6379:6381 --name redis \
-v /mydata/redis/data:/data \
-v /mydata/redis/conf/redis.conf:/etc/redis/redis.conf \
-d redis redis-server /etc/redis/redis.conf

```

# 检查
```r
[root@bogon conf]# docker ps
CONTAINER ID   IMAGE       COMMAND                   CREATED              STATUS              PORTS                                                  NAMES
550bd3f5a009   redis       "docker-entrypoint.s…"   About a minute ago   Up About a minute   0.0.0.0:6379->6379/tcp, :::6379->6379/tcp              redis
c57e3d9cf27e   mysql:8.0   "docker-entrypoint.s…"   26 hours ago         Up 52 minutes       0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 33060/tcp   mysql
```

# 连接redis客户端

``` r
 docker exec -it redis redis-cli
```

# redis持久化
由于之后的redis版本默认进行了持久化操作，不用设置
```r
vi /mydata/redis/conf/redis.conf 
// 添加引号内内容 :"appendonly yes"
docker restart redis
```

# redis 可视化工具
- [qishibo/AnotherRedisDesktopManager: 🚀🚀🚀A faster, better and more stable Redis desktop manager [GUI client], compatible with Linux, Windows, Mac.](https://github.com/qishibo/AnotherRedisDesktopManager)
- 测试连接：
	- ![](Pasted%20image%2020230812160807.png)
	- 