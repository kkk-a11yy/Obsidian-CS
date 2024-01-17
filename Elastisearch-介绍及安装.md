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
```