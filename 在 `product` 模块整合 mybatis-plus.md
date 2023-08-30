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
2. 配置
	1. 配置数据源
		1. 参考资料
			- [Maven Repository: com.mysql » mysql-connector-j » 8.0.33](https://mvnrepository.com/artifact/com.mysql/mysql-connector-j/8.0.33)
		2. 导入数据库的驱动
			   要对应现在数据库的版本，我的是：8.0.34
		```java
				<!-- https://mvnrepository.com/artifact/com.mysql/mysql-connector-j -->
		<dependency>
		    <groupId>com.mysql</groupId>
		    <artifactId>mysql-connector-j</artifactId>
		    <version>8.0.33</version>
		</dependency>
		```
	1. 配置 mybatis-plus 