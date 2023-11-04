
![Pasted image 20231104134331](BEFORE/附件/Pasted%20image%2020231104134331.png)

-------
- 用户注册加密：
	- md5+盐
		- ![Pasted image 20231104134628](BEFORE/附件/Pasted%20image%2020231104134628.png)
- 用户登录解密：
	- ![Pasted image 20231104134818](BEFORE/附件/Pasted%20image%2020231104134818.png)
## 配置 bootstrap.yml
```java
路径：heima-leadnews-service/heima-leadnews-user/src/main/resources/bootstrap.yml

server:
  port: 51801
spring:
  application:
    name: leadnews-user
  cloud:
    nacos:
      discovery:
        server-addr: 192.168.101.130:8848
      config:
        server-addr: 192.168.101.130:8848
        file-extension: yml
    
```

## 配置logback.xml
```java
路径：heima-leadnews-service/heima-leadnews-user/src/main/resources/logback.xml
```

## 配置 nacos

下一个 ：[app登陆--微服务搭建](app登陆--微服务搭建.md)
