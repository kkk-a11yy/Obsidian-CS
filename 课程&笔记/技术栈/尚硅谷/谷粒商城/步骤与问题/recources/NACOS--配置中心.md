
- [spring-cloud-alibaba/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme-zh.md at 2022.x · alibaba/spring-cloud-alibaba](https://github.com/alibaba/spring-cloud-alibaba/blob/2022.x/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme-zh.md)
- [Nacos Spring Cloud 快速开始](https://nacos.io/zh-cn/docs/quick-start-spring-cloud.html)
## 引入`nacos-config`依赖
`common`模块，
```java
<!--   服务注册/发现     -->
        <dependency>
            <groupId>com.alibaba.cloud</groupId>
            <artifactId>spring-cloud-starter-alibaba-nacos-discovery</artifactId>
        </dependency>
<!--        配置中心：服务配置管理-->
        <dependency>
            <groupId>com.alibaba.cloud</groupId>
            <artifactId>spring-cloud-starter-alibaba-nacos-config</artifactId>
        </dependency>
```

## 创建bootstrap.properties
	会优先于application.properties加载，新版别忘了加 spring-cloud-starter-bootstrap
```java
spring.application.name=andymall-coupon
//配置中心地址
spring.cloud.nacos.config.server-addr=127.0.0.1:8848
```

启动后有一行：
	``Located property source: [BootstrapPropertySource {name='bootstrapProperties-andymall-coupon.properties,DEFAULT_GROUP'}, BootstrapPropertySource {name='bootstrapProperties-andymall-coupon,DEFAULT_GROUP'}]
	意思：定位数据源从nacos当中的`andymall-coupon.properties`这个文件
		于是在nacos当中配置这个文件
## 配置 Nacos Config 地址并引入服务配置
```java
//微服务模块 application.yml添加
  config:
    import:
      - nacos:nacos-config-example.properties?refresh=true
```

![Pasted image 20231101160650|400](BEFORE/附件/Pasted%20image%2020231101160650.png)

>![note]
>spring-boot2.4以后的版本需要在common pom里导入spring-cloud-starter-bootstrap依赖
>注意以下几点：1.添加bootstrap依赖.2配置完重启nacos