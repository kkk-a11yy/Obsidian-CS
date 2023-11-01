
- [spring-cloud-alibaba/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme-zh.md at 2022.x · alibaba/spring-cloud-alibaba](https://github.com/alibaba/spring-cloud-alibaba/blob/2022.x/spring-cloud-alibaba-examples/nacos-example/nacos-config-example/readme-zh.md)
- 
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

>![note]
>could版本用的如果跟老师不一样  高版本一定要映入bootstarp依赖