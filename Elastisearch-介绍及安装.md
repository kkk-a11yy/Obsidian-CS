# 下载
```java
# 存储和检索数据
docker pull elasticsearch:8.11.3

# 可视化检索数据
docker pull kibana:8.11.3
```

# 配置挂载数据文件夹
```java
# 创建配置文件目录
mkdir -p /mydata/elasticsearch/config

# 创建数据目录
mkdir -p /mydata/elasticsearch/data

# 将/mydata/elasticsearch/文件夹中文件都可读可写
chmod -R 777 /mydata/elasticsearch/

# 配置任意机器可以访问 elasticsearch，这里注意冒号后面有空格！
echo "http.host: 0.0.0.0" >/mydata/elasticsearch/config/elasticsearch.yml

检查，查看文件内容是否修改
root@localhost config]# cat elasticsearch.yml 
http.host: 0.0.0.0
```

# 启动Elasticsearch
	命令后面的 \是换行符，注意前面有空格
```java
docker run --name elasticsearch -p 9200:9200 -p 9300:9300 --privileged=true \
-e  "discovery.type=single-node" \
-e ES_JAVA_OPTS="-Xms64m -Xmx512m" \
-v /mydata/elasticsearch/config/elasticsearch.yml:/usr/share/elasticsearch/config/elasticsearch.yml \
-v /mydata/elasticsearch/data:/usr/share/elasticsearch/data \
-v  /mydata/elasticsearch/plugins:/usr/share/elasticsearch/plugins \
-d elasticsearch:8.11.3

挂载出错要添加到白名单chcon -Rt svirt_sandbox_file_t（需要挂载的文件目录）或者chmod -R 777 /mydata/elasticsearch/ 保证权限
记得改成自己的ip地址
echo "" 那个 host:冒号和0.0之间有空格不能漏
还是不行 换成7.10.1版本
授予也了也不行，前面说的加--privileged==true才是正解
云服务器记得在安全组放行9200端口
虚拟机和本地都无法访问的话，设置一下虚拟机的网卡。
日志正常，端口也开放了，但浏览器访问失败时，可以重新启动虚拟机和elasticsearch
```

- `-p 9200:9200 -p 9300:9300`：向外暴露两个端口，9200用于HTTP REST API请求，9300 ES 在分布式集群状态下 ES 之间的通信端口；
- `-e  "discovery.type=single-node"`：es 以单节点运行
- `-e ES_JAVA_OPTS="-Xms64m -Xmx512m"`：设置启动占用内存，不设置可能会占用当前系统所有内存
- -v：挂载容器中的配置文件、数据文件、插件数据到本机的文件夹；
- `-d elasticsearch:8.11.3`：指定要启动的镜像

访问 IP:9200 看到返回的 json 数据说明启动成功。

- [神坑：ElasticSearch8集群启动报错“Device or resource busy”（Docker方式）_/usr/share/elasticsearch/config/elasticsearch.yml:-CSDN博客](https://blog.csdn.net/tiancao222/article/details/131469295)

最终解决：我的elasticsearch.yml:
```java
[root@localhost ~]# cat /mydata/elasticsearch/config/elasticsearch.yml

http.host:  0.0.0.0

  # 开启x-pack插件,用于添加账号密码、安全控制等配置

xpack.security.enabled: false #最关键的一句

xpack.security.transport.ssl.enabled: false

xpack.security.enrollment.enabled: true
```

访问：http://192.168.101.104:9200
# 设置 Elasticsearch 随Docker启动
```java
# 当前 Docker 开机自启，所以 ES 现在也是开机自启
docker update elasticsearch --restart=always
```


# 启动可视化Kibana
```java
docker run --name kibana \
-e ELASTICSEARCH_HOSTS=http://192.168.101.104:9200 \
-p 5601:5601 \
-d kibana:8.11.3

//我的docker inspect elasticsearch 的ip为172.17.0.4，但这里使用的是虚拟机ip，可以访问成功
docker run --name kibana \
-e ELASTICSEARCH_HOSTS=http://172.17.0.4:9200 \
-p 5601:5601 \
-d kibana:8.11.3

注意 这个ip不是虚拟机地址 要查docker inspect XXXXXXX |grep IPAddress  XXXX代表的是elastic的容器id

可以用docker inspect elasticsearch查看NetworkSettings:IPAddress获取ip

docker-compose up -d  嗖嗖。。。
```

访问：http://192.168.101.104:5601

- 使用apiPost测试命令
- 使用kibana 测试
	- http://192.168.101.104:5601/app/dev_tools#/console
```java
POST /books/_bulk
{"delete":{"_index":"website","_id":"123"}}
{"create":{"_index":"website","_id":"123"}}
{"title":"my first blog post"}
{"index":{"_index":"website"}}
{"title":"my second blog post"}
{"update":{"_index":"website","_id":"123"}}
{"doc":{"title":"my updated blog post"}}
```
- 测试数据
	- https://github.com/elastic/elasticsearch/blob/v6.8.18/docs/src/test/resources/accounts.json
	- [Query DSL | Elasticsearch Guide [8.9] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/8.9/query-dsl.html)

# 安装分词器

- [Releases · medcl/elasticsearch-analysis-ik](https://github.com/medcl/elasticsearch-analysis-ik/releases)
- 下载8.11.3版本
```java

put /Users/ksia/Downloads/elasticsearch-analysis-ik-8/*  /mydata/elasticsearch/plugins/ik8.11.3/
```

```java
[root@localhost plugins]# mkdir ik8.11.3

/mydata/elasticsearch/plugins

[root@localhost plugins]# cd ik8.11.3/

[root@localhost plugins]# docker restart elasticsearch 

elasticsearch


[root@localhost plugins]# docker exec -it 20c /bin/bash

elasticsearch@20cecd37a51e:~$ ls

LICENSE.txt  NOTICE.txt  README.asciidoc  **bin**  **config**  data  **jdk**  **lib**  **logs**  **modules**  plugins

elasticsearch@20cecd37a51e:~$ cd bin/

elasticsearch@20cecd37a51e:~/bin$ ls

         **elasticsearch-plugin**  
elasticsearch@20cecd37a51e:~/bin$ elasticsearch-plugin list

ik8.11.3

elasticsearch@20cecd37a51e:~/bin$ exit

[root@localhost plugins]# docker restart elasticsearch 


```
然后重新进入：http://192.168.101.104:5601/app/dev_tools#/console

#检查虚拟机内存
```java
[root@localhost ~]# free -m
[root@localhost ~]# docker stats
```

下一个：