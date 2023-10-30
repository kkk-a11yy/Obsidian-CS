# 分布式组件--注册
- 选择 SpringCloudAlibaba
	- 根据 boot&cloud 选择alibaba：2.2.1 .RELEASE
	  - [alibaba/spring-cloud-alibaba: Spring Cloud Alibaba provides a one-stop solution for application development for the distributed solutions of Alibaba middleware.](https://github.com/alibaba/spring-cloud-alibaba)
	    - [spring-cloud-alibaba/spring-cloud-alibaba-docs/src/main/asciidoc-zh/nacos-discovery.adoc at 2022.x · alibaba/spring-cloud-alibaba](https://github.com/alibaba/spring-cloud-alibaba/blob/2022.x/spring-cloud-alibaba-docs/src/main/asciidoc-zh/nacos-discovery.adoc)
	![Pasted image 20231030130229](BEFORE/附件/Pasted%20image%2020231030130229.png)
	- 在 common 模块 引入 SpringCloudAlibaba2.2.1 以及nacos：
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
	- 下载 nacos server(可以用docker安装)