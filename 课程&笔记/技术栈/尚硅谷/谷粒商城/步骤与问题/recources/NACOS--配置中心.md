
- [spring-cloud-alibaba/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme-zh.md at 2022.x · alibaba/spring-cloud-alibaba](https://github.com/alibaba/spring-cloud-alibaba/blob/2022.x/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme-zh.md)
- [Nacos Spring Cloud 快速开始](https://nacos.io/zh-cn/docs/quick-start-spring-cloud.html)
## common引入依赖
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

## 微服务配置 Nacos Config 地址并引入服务配置
```java
//微服务模块 application.yml添加
  config:
    import:
      - nacos:nacos-config-example.properties?refresh=true
```

![Pasted image 20231101160650|400](BEFORE/附件/Pasted%20image%2020231101160650.png)

>![note]
>spring-boot2.4以后的版本需要在common pom里导入spring-cloud-starter-bootstrap依赖