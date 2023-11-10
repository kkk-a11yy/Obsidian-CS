- [Spring Cloud Gateway](https://spring.io/projects/spring-cloud-gateway)

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
- nacos添加gateway命名空间
- 启动项目

#datasource_url错误
	1. 因为引入common的mybatis依赖，就有了数据源的操作，但是这里还没有用到数据源，所以可以屏蔽mybatis的依赖
		1. 在项目的application添加：`@SpringBootApplication(exclude = DataSourceAutoConfiguration.class)`
		2. 排除了还是报错的话，不导入common包直接导入config和discover就好
		3. DataSourceAutoConfiguration和DruidDataSourceAutoConfigure都要排除
		5. 如果common中引入了web启动器，注意在引入common的时候排除掉web-starter
