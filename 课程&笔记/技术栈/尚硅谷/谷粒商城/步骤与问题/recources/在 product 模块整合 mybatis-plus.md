> 为了用	mybatis-plus 操作数据库

## 在 `common` 模块导入依赖
```java
		老师的是3.2.0
	<!-- mybatis-plus-->  
	<dependency>  
		<groupId>com.baomidou</groupId>  
		<artifactId>mybatis-plus-boot-starter</artifactId>  
		<version>3.2.0</version>  
	</dependency>
```

## 配置 `common` 模块的 pom.xml
1. 配置数据源
	1. 参考资料
		- [Maven Repository: com.mysql » mysql-connector-j » 8.1.0](https://mvnrepository.com/artifact/com.mysql/mysql-connector-j/8.1.0)
		- [MySQL :: MySQL Connector/J 8.1 Developer Guide :: 2 Compatibility with MySQL and Java Versions](https://dev.mysql.com/doc/connector-j/8.1/en/connector-j-versions.html)
	2. 导入数据库的驱动
		  1.  要对应现在数据库的版本，我的是：8.0.34 , mysql官方支持的connector版本是8.1
				```java
			<!-- https://mvnrepository.com/artifact/com.mysql/mysql-connector-j -->
				<dependency>
					<groupId>com.mysql</groupId>
					<artifactId>mysql-connector-j</artifactId>
					<version>8.1.0</version>
				</dependency>
				```
		1. 解决 `httpservletrequest` 爆红
			1. 爆红路径：`com/andymall/product/common/xss/XssFilter.java`
			2. 在 pom 导入
				```java
				<dependency>  
					<groupId>javax.servlet</groupId>  
					<artifactId>servlet-api</artifactId>  
					<version>2.5</version> 
					//目标环境已提供--tomcat自带的，打包的时候就不用带这个servlet-api了
					<scope>provided</scope>
				</dependency>
				```
			1. 这两个类可以先删掉
				![](Pasted%20image%2020230830171424.png)
		3. SQLFilter 的RRException爆红
			1. 在 `renren-generator/src/main/java/io/renren/utils/RRException.java`,复制过去
	3. 创建 application.yml文件,在这里配置数据源信息
		1. 路径：`andymall-product/src/main/resources/application.yml`
## 配置 mybatis-plus 

1. 在 `AndymallProductApplication` 类名上面加 `@MapperScan` 注解
	1. `@MapperScan("com/andymall/product/dao")` 告诉注解Mapper接口在哪
	2. 告诉mybatis-plus 映射文件在哪
		1. 把renren-generator 生成的 `resources/mapper/product` 文件夹拷贝到 product 模块下的 `resource/mapper` 文件夹下
		2. 在application.yml文件,在这里配置数据源信息
			1. 路径：`andymall-product/src/main/resources/application.yml`
			2. 添加 `mapper-locations`,后面添加内容：`command` 键摁住点`mapper-location` 进去查看，是这段：
				1. `/classpath*:/mapper/**/*.xml`
					1. `/classpath*` 的意思是，不只扫描我自己的类路径，包括我引用的其他依赖的java包的类路径
				2. 添加到yml文件里
			3. 设置数据库主键自增
				1. 路径：application.yml文件里
				2. 内容：添加 db-config

最终：![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/files/application.yml)

## 测试：
- 路径：`andymall-product/src/test/java/com/andymall/product/AndymallProductApplicationTests.java`
- @Test 爆红
	- dependency 导入 junit5.8.1
		- 参考资料：
			- [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/#overview)
			- [Maven Repository: org.junit.jupiter » junit-jupiter-api » 5.8.1](https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api/5.8.1)
				```java
				<!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api -->  
				<dependency>  
					<groupId>org.junit.jupiter</groupId>  
					<artifactId>junit-jupiter-api</artifactId>  
					<version>5.8.1</version>  
					<scope>test</scope>  
				</dependency>
				```
- `constant` 类的 `AliyunGroup;  QcloudGroup;  QiniuGroup;` 爆红
	- 在 `renren-fast` 模块下，复制过来
- ![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/files/AndymallProductApplicationTests.java)
- run test 的时候（测试失败的  注意springboot 和 cloud 版本匹配问题）：
	- `java.lang.IllegalStateException: Failed to load ApplicationContext` 错误
		```java
		Caused by: java.lang.UnsupportedClassVersionError: org/springframework/cloud/bootstrap/BootstrapApplicationListener has been compiled by a more recent version of the Java Runtime (class file version 61.0), this version of the Java Runtime only recognizes class file versions up to 52.0
		
		note:
		- the major version numbers map to Java versions:
			- 52 = Java 8
			- 61 = Java 17---springboot 2.6往上
		
		```
		- 意思是：
		  ```java
		我的java version: 8  
		应该对应的spring boot ：2.4.x
		改成了：2.3.2.RELEASE
			```
		- java version 对应
			- [How to Fix java.lang.UnsupportedClassVersionError | Baeldung](https://www.baeldung.com/java-lang-unsupportedclassversion)
			- [你该不会不知道SpringBoot版本与springCloud的版本关系吧 - mdnice 墨滴](https://mdnice.com/writing/c08e9d1917b0439f92babc0734955ed4)
- renren-fast. pom.xml
	- 本来的：![](BEFORE/附件/pom.xml)
	- 老师的：![](BEFORE/附件/pom%201.xml)
> [!note]
> 这里测试一定要注意springboot和cloud版本问题，老师用的是2.1.8.RELEASE, 对应的cloud是Greenwich.SR3
> 遇到了RenrenApplication启动问题，common模块clean package一下

```java
Caused by: org.springframework.beans.factory.BeanCreationException
	bean无法创建 是springboot版本问题
	
```

最后springboot. and springcloud 版本：
	AndyMall--product-pom.xml
```java
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.2.5.RELEASE</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.andymall</groupId>
	<artifactId>andymall-product</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>andymall-product</name>
	<description>andymall-product</description>
	<properties>
		<java.version>1.8</java.version>
		<spring-cloud.version>Hoxton.SR3</spring-cloud.version>
	</properties>
```

`AndymallProductApplicationTests` 测试成功

然后用`renren-generator` 给 其他 服务生成数据库 [[]]