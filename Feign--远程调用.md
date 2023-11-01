微服务之间相互调用:http
![Pasted image 20231101150611|500](BEFORE/附件/Pasted%20image%2020231101150611.png)


## dependency
```java
//创建微服务时已导入
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-openfeign</artifactId>
        </dependency>
```

![Pasted image 20231101151935](BEFORE/附件/Pasted%20image%2020231101151935.png)

- 重启服务
- 给member发请求：`http://127.0.0.1:14000/member/member/coupons`
	是发到MemberController

下一个[NACOS--配置中心](NACOS--配置中心.md)