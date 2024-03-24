---
dg-publish: true
dg-home: true
---

# AndyMall 架构图
![](https://i.imgur.com/PDv6F32.png)

# 参考资料
- [学习计划（资料）](https://www.yuque.com/zhangshuaiyin/andy-mall/wrbzgy)
- [Linux开发环境配置（Docker）](https://www.yuque.com/zhangshuaiyin/andy-mall/lb4zw1)
- [raymond-zhao.](https://raymond-zhao.top/campus-interview/#/Home)
# 环境搭建

- 机器：m1 pro 2021  , macOS:13.4.1 
- 包管理： [Homebrew](Configuration/homebrew/Homebrew.md) , sdkman 
- CI/CD：
	- Git：
		- [SSH连接问题](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/SSH连接问题.md)
		- [AndyMall--SSH](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/AndyMall--SSH.md)
- Shell 工具：
	- [ZOC8-下载与连接虚拟机](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/ZOC8-下载与连接虚拟机.md)
	- [Mac terminal](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Mac%20terminal.md)
虚拟机：
- Parallels 19.1
	- [Parallels Desktop 19.1.0 54729 破解教程（pd19永久授权）](https://luoxx.top/archives/pd-18-active)
	- CenOS 9.  
		- [Centos9环境搭建](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Centos9环境搭建.md)
			- [Docker安装 --Mac m1pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Docker安装%20--Mac%20m1pro.md)
			- [MySql8.0--centos stream9](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/MySql8.0--centos%20stream9.md)
			- [Redis--centos stream9](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Redis--centos%20stream9.md)
 Mac主机：
 - [Another Redis desktop manager](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Another%20Redis%20desktop%20manager.md)
 - [MySql-Mac m1pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/MySql-Mac%20m1pro.md)
 - [JDK1.8-Mac m1 pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/JDK1.8-Mac%20m1%20pro.md)
 - [Maven-Mac m1pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Maven-Mac%20m1pro.md)
 - [VSCode-Mac m1pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/VSCode-Mac%20m1pro.md)
 - [IDEA-Mac m1 pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/IDEA-Mac%20m1%20pro.md)
 - [Navicat premium](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Navicat%20premium.md)

- Vue 环境搭建：
	- Node JS
		- Npm
			- Vue 脚手架
			- webpack
	- Chrome 安装 vue-devtools 插件
	- VS Code 安装 Vue 2 Snippets 插件

## 组织结构


```
andymall
├── andymall-common -- 工具类及通用代码
├── renren-generator -- 人人开源项目的代码生成器
├── andymall-auth-server -- 认证中心（社交登录、OAuth2.0）
├── andymall-cart -- 购物车服务
├── andymall-coupon -- 优惠卷服务
├── andymall-gateway -- 统一配置网关
├── andymall-order -- 订单服务
├── andymall-product -- 商品服务
├── andymall-search -- 检索服务
├── andymall-seckill -- 秒杀服务
├── andymall-third-party -- 第三方服务（对象存储、短信）
├── andymall-ware -- 仓储服务
└── andymall-member -- 会员服务
```

## 技术选型

### 后端技术



|技术|说明|官网|
|:-:|:-:|:-:|
|SpringBoot|容器+MVC框架|[https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)|
|SpringCloud|微服务架构|[https://spring.io/projects/spring-cloud](https://spring.io/projects/spring-cloud)|
|SpringCloudAlibaba|一系列组件|[https://spring.io/projects/spring-cloud-alibaba](https://spring.io/projects/spring-cloud-alibaba)|
|MyBatis-Plus|ORM框架|[https://mp.baomidou.com](https://mp.baomidou.com/)|
|renren-generator|人人开源项目的代码生成器|[https://gitee.com/renrenio/renren-generator](https://gitee.com/renrenio/renren-generator)|
|Elasticsearch|搜索引擎|[https://github.com/elastic/elasticsearch](https://github.com/elastic/elasticsearch)|
|RabbitMQ|消息队列|[https://www.rabbitmq.com](https://www.rabbitmq.com/)|
|Springsession|分布式缓存|[https://projects.spring.io/spring-session](https://projects.spring.io/spring-session)|
|Redisson|分布式锁|[https://github.com/redisson/redisson](https://github.com/redisson/redisson)|
|Docker|应用容器引擎|[https://www.docker.com](https://www.docker.com/)|
|OSS|对象云存储|[https://github.com/aliyun/aliyun-oss-java-sdk](https://github.com/aliyun/aliyun-oss-java-sdk)|

### 前端技术

|技术|说明|官网|
|:-:|:-:|:-:|
|Vue|前端框架|[https://vuejs.org](https://vuejs.org/)|
|Element|前端UI框架|[https://element.eleme.io](https://element.eleme.io/)|
|thymeleaf|模板引擎|[https://www.thymeleaf.org](https://www.thymeleaf.org/)|
|node.js|服务端的js|[https://nodejs.org/en](https://nodejs.org/en)|


### 业务架构图

[![](https://camo.githubusercontent.com/eace78b97127938606c43fc68b02707d153d71b2c84d042dcdfbf23e8d9fae01/68747470733a2f2f692e6c6f6c692e6e65742f323032312f30322f31382f79426a6c717673436770566b454e632e706e67)](https://camo.githubusercontent.com/eace78b97127938606c43fc68b02707d153d71b2c84d042dcdfbf23e8d9fae01/68747470733a2f2f692e6c6f6c692e6e65742f323032312f30322f31382f79426a6c717673436770566b454e632e706e67)
### 开发环境


|      工具       |  版本号  |                                                                            下载                                                                            |
| :-----------: | :---: | :------------------------------------------------------------------------------------------------------------------------------------------------------: |
|      JDK      |  1.8  | [https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) |
|     Mysql     |  8.0  |                                                     [https://www.mysql.com](https://www.mysql.com/)                                                      |
|     Redis     | Redis |                                                  [https://redis.io/download](https://redis.io/download)                                                  |
| Elasticsearch | 7.6.2 |                                           [https://www.elastic.co/downloads](https://www.elastic.co/downloads)                                           |
|    Kibana     | 7.6.2 |                                           [https://www.elastic.co/cn/kibana](https://www.elastic.co/cn/kibana)                                           |
|   RabbitMQ    | 3.8.5 |                                      [http://www.rabbitmq.com/download.html](http://www.rabbitmq.com/download.html)                                      |
|     Nginx     | 1.1.6 |                                          [http://nginx.org/en/download.html](http://nginx.org/en/download.html)                                          |

注意：以上的除了jdk都是采用docker方式进行安装，详细安装步骤可参考百度!!!

### 搭建步骤


- 修改本机的host文件，映射域名端口至Nginx地址

```
192.168.101.104	andymall.com
192.168.101.104	search.andymall.com
192.168.101.104  item.andymall.com
192.168.101.104  auth.andymall.com
192.168.101.104  cart.andymall.com
192.168.101.104  order.andymall.com
192.168.101.104  member.andymall.com
192.168.101.104  seckill.andymall.com
以上ip换成自己Linux的ip地址
```

- 修改Linux中Nginx的配置文件

```shell
1、在nginx.conf中添加负载均衡的配置   
upstream andymall{
	# 网关的地址
	server 192.168.101.1:88;
}    
2、在andymall.conf中添加如下配置
server {
	# 监听以下域名地址的80端口
    listen       80;
    server_name  andymall.com  *.andymall.com.mynatapp.cc;

    #charset koi8-r;
    #access_log  /var/log/nginx/log/host.access.log  main;

    #配置静态资源分离
    location /static/ {
        root   /usr/share/nginx/html;
    }

    #支付异步回调的一个配置
    location /payed/ {
        proxy_set_header Host order.andymall.com;        #不让请求头丢失
        proxy_pass http://andymall;
    }

    location / {
        #root   /usr/share/nginx/html;
        #index  index.html index.htm;
        proxy_set_header Host $host;        #不让请求头丢失
        proxy_pass http://andymall;
    }
```

或者直接用项目nginx模块替换本机nginx配置目录文件

- 克隆前端项目 `renren-fast-vue` 以 `npm run dev` 方式去运行
- 克隆整个后端项目 `andymall` ，并导入 IDEA 中完成编译

----
# 创建项目
之前创建过，参考这里：
- [搭建过程 --Windows（先导）](课程&笔记/技术栈/尚硅谷/谷粒商城/搭建过程%20--Windows（先导）.md#^5daf8b)
- [搭建过程 -- M1 pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/搭建过程%20--%20M1%20pro.md)





