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


------
# 这里是黑马课程的openfeign配置
![Pasted image 20231102162149|500](BEFORE/附件/Pasted%20image%2020231102162149.png)

![Pasted image 20231102162232](BEFORE/附件/Pasted%20image%2020231102162232.png)

## 引入连接池

![Pasted image 20231102164247](BEFORE/附件/Pasted%20image%2020231102164247.png)

## 最佳实践
![Pasted image 20231102165407](BEFORE/附件/Pasted%20image%2020231102165407.png)

下一个[Nacos--配置中心](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Nacos--配置中心.md)