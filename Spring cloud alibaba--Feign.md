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
## @EnableFeignClient

## @FeignClient
下一个[NACOS--](NACOS--.md)