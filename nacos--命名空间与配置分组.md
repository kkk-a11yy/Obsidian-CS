	利用命名空间做环境隔离
	每一个微服务之间相互隔离，创建自己的命名空间，vi jw zl zi ji

## 创建命名空间
![](BEFORE/附件/Pasted%20image%2020231110165317.png)

## 在不同命名空间新建配置

![](BEFORE/附件/Pasted%20image%2020231110165526.png)

## bootstrap.properties 添加
```java
//添加不同命名空间的配置管理信息（在nacos查看，这里是prop的）
spring.cloud.nacos.config.namespace=3113f714-3e39-4146-9dea-1254b09f7497

```

- 重启微服务
- 访问 http://127.0.0.1:13000/coupon/coupon/test
- 获得不同命名空间的配置信息