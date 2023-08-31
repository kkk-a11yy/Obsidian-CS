	为了用	mybatis-plus 操作数据库
1. 在 `common` 模块导入依赖
	```java
		<!-- mybatis-plus-->  
	<dependency>  
		<groupId>com.baomidou</groupId>  
		<artifactId>mybatis-plus-boot-starter</artifactId>  
		<version>3.3.1</version>  
	</dependency>
```
2. 配置 `common` 模块的 pom.xml
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
			2. 解决 `httpservletrequest` 爆红
				1. 爆红路径：`com/andymall/product/common/xss/XssFilter.java`
				2. 在 pom 导入
				```java
				<dependency>  
					<groupId>javax.servlet</groupId>  
					<artifactId>servlet-api</artifactId>  
					<version>2.5</version>  
					<scope>provided</scope>
				</dependency>
				```
				3. 这两个类可以先删掉
					![](Pasted%20image%2020230830171424.png)
			3. SQLFilter 的RRException爆红
				1. 在 `renren-generator/src/main/java/io/renren/utils/RRException.java`,复制过去
		3. 创建 application.yml文件,在这里配置数据源信息
			1. 路径：`andymall-product/src/main/resources/application.yml`
	2. 配置 mybatis-plus 
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
最终：![](application.yml)
- 测试：
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
	- ![](AndymallProductApplicationTests.java)
	- run test 的时候：
		- `java.lang.IllegalStateException: Failed to load ApplicationContext` 错误
			- `Caused by: java.lang.IllegalArgumentException: Cannot instantiate interface org.springframework.context.ApplicationListener : org.springframework.cloud.bootstrap.BootstrapApplicationListener`
			- 意思是：
			  ```java
			  你的代码似乎在运行时尝试实例化 `BootstrapApplicationListener` 这个类，但这个类是由一个较新版本的 Java 编译的，而你的运行时只支持较旧的 Java 版本。这可能是因为你的开发环境中的 Java 版本与项目所需的版本不匹配。
			```
