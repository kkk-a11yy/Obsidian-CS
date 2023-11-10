- [Spring Cloud Gateway](https://docs.spring.io/spring-cloud-gateway/docs/3.0.8/reference/html/)
## 创建gateway模块
	
![](BEFORE/附件/Pasted%20image%2020231110185740.png)

- 添加gateway依赖
- maven 添加 gateway模块
- andymall添加gateway模块
- 添加andymall-common依赖
- 修改pom.xml:
	- spring-boot：2.2.5.REALEASE
	- java.version：1.8
	- spring-cloud.version：Hoxton.SR3
- AndymallGatewayApplication 开启注册发现：@EnableDiscoveryClient
- application.properties:
	- 添加配置注册中心地址：nacos.config.server-addr=127.0.0.1:8848
	- 添加服务名称：application.name=andymall-gateway
	- 添加端口：server.port=88
- bootstrap.properties:
	- 添加项目名字：application.name=andymall-gateway
	- 添加nacos.config.server-addr=127.0.0.1:8848
	- 添加 gateway命名空间的id
- application.yml:
```java
spring:
  cloud:
    gateway:
      routes:
        - id: test_route
          uri: https://www.baidu.com
          predicates:
            - Query=url,baidu

        - id: qq_route
          uri: https://www.qq.com
          predicates:
            - Query=url,qq
```
- nacos添加gateway命名空间
- 启动项目

#datasource_url错误
1. 因为引入common的mybatis依赖，就有了数据源的操作，但是这里还没有用到数据源，所以可以屏蔽mybatis的依赖
	1. 在项目的application添加：`@SpringBootApplication(exclude = DataSourceAutoConfiguration.class)`
	2. 排除了还是报错的话，不导入common包直接导入config和discover就好
	3. DataSourceAutoConfiguration和DruidDataSourceAutoConfigure都要排除
	4. 如果common中引入了web启动器，注意在引入common的时候排除掉web-starter
	5. 正解：排除mysql驱动依赖，排除mybatis依赖，可以在子模块pom依赖下加scope test就能排除了
	6. 启动报错的是网关版本!!!!!!!!!!!!!!!
	7. 访问不到的，看看pom.xml中是不是引入了tomcat服务器，排除就好了

#无法找到名称查询的RoutePredicateFactory

#bean_of_type_org_springframework_http_codec_ServerCodecConfigurer_that_could_not_be_found
- [java - bean of type 'org.springframework.http.codec.ServerCodecConfigurer' that could not be found - Stack Overflow](https://stackoverflow.com/questions/52447223/bean-of-type-org-springframework-http-codec-servercodecconfigurer-that-could-n)
	- 排除掉start-web的依赖