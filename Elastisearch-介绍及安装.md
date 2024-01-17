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

# 配置任意机器可以访问 elasticsearch
echo "http.host: 0.0.0.0" >/mydata/elasticsearch/config/elasticsearch.yml

检查，查看文件内容是否修改
root@localhost config]# cat elasticsearch.yml 
http.host: 0.0.0.0
```

# 启动Elasticsearch
	命令后面的 \是换行符，注意前面有空格
```java
docker run --name elasticsearch -p 9200:9200 -p 9300:9300 \
-e  "discovery.type=single-node" \
-e ES_JAVA_OPTS="-Xms64m -Xmx512m" \
-v /mydata/elasticsearch/config/elasticsearch.yml:/usr/share/elasticsearch/config/elasticsearch.yml \
-v /mydata/elasticsearch/data:/usr/share/elasticsearch/data \
-v  /mydata/elasticsearch/plugins:/usr/share/elasticsearch/plugins \
-d elasticsearch:8.11.3

挂载出错要添加到白名单chcon -Rt svirt_sandbox_file_t（需要挂载的文件目录）或者chmod -R 777 /mydata/elasticsearch/ 保证权限
记得改成自己的ip地址
echo "" 那个 host:冒号和0.0之间有空格不能漏
```

- `-p 9200:9200 -p 9300:9300`：向外暴露两个端口，9200用于HTTP REST API请求，9300 ES 在分布式集群状态下 ES 之间的通信端口；
- `-e  "discovery.type=single-node"`：es 以单节点运行
- `-e ES_JAVA_OPTS="-Xms64m -Xmx512m"`：设置启动占用内存，不设置可能会占用当前系统所有内存
- -v：挂载容器中的配置文件、数据文件、插件数据到本机的文件夹；
- `-d elasticsearch:8.11.3`：指定要启动的镜像

访问 IP:9200 看到返回的 json 数据说明启动成功。