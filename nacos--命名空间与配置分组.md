	利用命名空间做环境隔离
	每一个微服务之间相互隔离，创建自己的命名空间，只加载自己命名空间的所有配置

## 创建命名空间
![](BEFORE/附件/Pasted%20image%2020231110170626.png)

## 在不同命名空间新建配置

![](BEFORE/附件/Pasted%20image%2020231110173738.png)

## bootstrap.properties 添加
```java
//添加不同命名空间的配置管理信息（在nacos查看，这里是coupon的）
spring.cloud.nacos.config.namespace=20bb1b87-a7f3-49e5-82ac-b1cf0500a872
//读取dev组下的配置
spring.cloud.nacos.config.group=dev
```

- 重启微服务
- 访问 http://127.0.0.1:13000/coupon/coupon/test
- 获得不同命名空间的配置信息

下一个：