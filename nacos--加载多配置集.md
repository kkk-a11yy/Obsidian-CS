## 分离配置

![](BEFORE/附件/Pasted%20image%2020231110174457.png)

## bootstrap.properties修改

```java
spring.application.name=andymall-coupon

spring.cloud.nacos.config.server-addr=127.0.0.1:8848
spring.cloud.nacos.config.namespace=20bb1b87-a7f3-49e5-82ac-b1cf0500a872
//如果这里不指定读取配置中心的哪个分组的配置，配置中心没有，就加载本项目中的application.properties文件中的配置，
spring.cloud.nacos.config.group=dev

spring.cloud.nacos.config.extension-configs[0].data-id=datasource.yml
spring.cloud.nacos.config.extension-configs[0].group=dev
spring.cloud.nacos.config.extension-configs[0].refresh=true

spring.cloud.nacos.config.extension-configs[1].data-id=mybatis.yml
spring.cloud.nacos.config.extension-configs[1].group=dev
spring.cloud.nacos.config.extension-configs[1].refresh=true

spring.cloud.nacos.config.extension-configs[2].data-id=other.yml
spring.cloud.nacos.config.extension-configs[2].group=dev
spring.cloud.nacos.config.extension-configs[2].refresh=true

```

- 访问：
- http://127.0.0.1:13000/coupon/coupon/list
- http://127.0.0.1:13000/coupon/coupon/test

>[!note] 
>此时的配置文件是临时的，重启nacos数据会消失，要数据持久化，可以nacos配置成自己的数据库

下一个：[SpringCloudGateway--配置网关](SpringCloudGateway--配置网关.md)