# 分布式组件--注册
- 选择 SpringCloudAlibaba
	- 根据 boot&cloud 选择alibaba：2.2.1 .RELEASE
	  - [alibaba/spring-cloud-alibaba: Spring Cloud Alibaba provides a one-stop solution for application development for the distributed solutions of Alibaba middleware.](https://github.com/alibaba/spring-cloud-alibaba)
	    - [spring-cloud-alibaba/spring-cloud-alibaba-docs/src/main/asciidoc-zh/nacos-discovery.adoc at 2022.x · alibaba/spring-cloud-alibaba](https://github.com/alibaba/spring-cloud-alibaba/blob/2022.x/spring-cloud-alibaba-docs/src/main/asciidoc-zh/nacos-discovery.adoc)
	![Pasted image 20231030130229](BEFORE/附件/Pasted%20image%2020231030130229.png)
## 在 common 模块 引入 SpringCloudAlibaba2.2.1 以及nacos
  ```java
  <dependencyManagement>
<dependencies>
	<dependency>
		<groupId>com.alibaba.cloud</groupId>
		<artifactId>spring-cloud-alibaba-dependencies</artifactId>
		<version>2.2.1.RELEASE</version>
		<type>pom</type>
		<scope>import</scope>
	</dependency>
</dependencies>
</dependencyManagement>

<dependency>
<groupId>com.alibaba.cloud</groupId>
<artifactId>spring-cloud-starter-alibaba-nacos-discovery</artifactId>
</dependency>
```


## 下载 nacos server(可以用docker安装,Mac m1 )

^bcff8b

- 我的docker: **zhusaidong/nacos-server-m1**
>[!info]
>mac终端启动nacos，到bin目录下启动终端，然后输入sh startup.sh -m standalone
>启动闪退的，jdk版本换成1.8的版本，环境变量也配一下
>用nacos2.0的同学 需要注意9848这个端口, 阿里云和docker都要做好处理
>前面改版本导致test错误的要去掉原来的import 并且注解是@RunWith(SpringRunner.class)
>用junit4的，在测试方法的类型和方法名前加上 public 即可

### 拉取m1版本的nacos并启动

^1d36ee

- [解决M1 无法使用nacos高版本(2.0.3)问题 · Issue #8674 · alibaba/nacos](https://github.com/alibaba/nacos/issues/8674)
- [nacos/nacos-server Tags | Docker Hub](https://hub.docker.com/r/nacos/nacos-server/tags?page=1)

```java
## pull 的时候关魔法
	docker pull zhusaidong/nacos-server-m1:2.0.3
## 映射端口并启动
	docker run -d -p 8848:8848 --env MODE=standalone  --name nacos  zhusaidong/nacos-server-m1:2.0.3
	#leaderhead 项目
docker run --env MODE=standalone --name nacos --restart=always  -d -p 8848:8848 zhusaidong/nacos-server-m1:2.0.3

## 本地nacos地址：localhost:8848/nacos
**nacos初始账号密码都为nacos**
```

## 微服务application.yml
```java
  cloud:
    nacos:
      discovery:
        server-addr: 127.0.0.1:8848
  application:
    name: andymall-coupon
```

### 开启注册发现功能

```java
//添加这个注释，这注解新版本是默认开启了,可以不用写了
@EnableDiscoveryClient  
public class AndymallCouponApplication {  
  
public static void main(String[] args) {  
SpringApplication.run(AndymallCouponApplication.class, args);  
}  
  
}
```
- rerun 微服务，nacos查看注册的服务

下一个[Feign--远程调用](Feign--远程调用.md)