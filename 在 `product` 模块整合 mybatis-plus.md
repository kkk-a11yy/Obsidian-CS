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
		1. 导入数据库的驱动
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
	1. 配置 mybatis-plus 