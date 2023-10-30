# 分布式组件--注册
- 选择 SpringCloudAlibaba
	- 根据 boot&cloud 选择alibaba：2.2.1 .RELEASE
	  - [alibaba/spring-cloud-alibaba: Spring Cloud Alibaba provides a one-stop solution for application development for the distributed solutions of Alibaba middleware.](https://github.com/alibaba/spring-cloud-alibaba)
	![Pasted image 20231030130229](BEFORE/附件/Pasted%20image%2020231030130229.png)
	- 在 common 模块 粘贴：
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
```