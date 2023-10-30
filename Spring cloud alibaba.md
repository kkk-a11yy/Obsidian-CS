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
- 我的docker: **zhusaidong/nacos-server-m1**
>[!info]
>mac终端启动nacos，到bin目录下启动终端，然后输入sh startup.sh -m standalone
>启动闪退的，jdk版本换成1.8的版本，环境变量也配一下
>./startup.cmd -m standalone
>用nacos2.0的同学 需要注意9848这个端口, 阿里云和docker都要做好处理
>前面改版本导致test错误的要去掉原来的import 并且注解是@RunWith(SpringRunner.class)
>用junit4的，在测试方法的类型和方法名前加上 public 即可
>@enableDiscoveryClient后面版本nacos自动配置那里默认开启了
>这注解新版本是默认开启了,可以不用写了

## 拉取m1版本的nacos并启动(我在虚拟机docker安装)

```java
	docker pull zhusaidong/nacos-server-m1:2.0.3
## 映射端口并启动
	docker run -d -p 8848:8848 --env MODE=standalone  --name nacos  zhusaidong/nacos-server-m1:2.0.3
## 本地nacos地址：localhost:8848/nacos
**nacos初始账号密码都为nacos**
```

## 访问 127.0.0.1:8848
