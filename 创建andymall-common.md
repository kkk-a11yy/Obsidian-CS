	每一个微服务公共的类、依赖、工具类等放在这里
- 在andymall 总项目下 new module创建 maven类的
	- ![](Pasted%20image%2020230820133653.png)
	- pom.xml添加description
		- pom文件路径：andymall-common/pom.xml
		- `<description>每一个微服务公共的类、依赖、工具类等放在这里</description>`
	- `product`模块添加`common`模块的依赖
		``` java
		<dependency>
			<groupId>com.andymall</groupId>
			<artifactId>andymall-common</artifactId>
			<version>0.0.1-SNAPSHOT</version>
		</dependency>
		```
	- `common` 模块添加其他模块需要的依赖
		- `andymallproduct/dao` 层的 `BaseMapper` 、`@Mapper` 爆红
			- mybatis-plus.  
				-  [安装 | MyBatis-Plus](https://baomidou.com/pages/bab2db/#release)
				``` java 
				//老师用的是3.2.0，我的maven是3.6.1
				<dependency>
				    <groupId>com.baomidou</groupId>
				    <artifactId>mybatis-plus-boot-starter</artifactId>
				    <version>最新版本</version>
				</dependency>
				```
		- `entity` 层的 `@Date` 爆红
			- lombok 
				- 简化 `java bean` 开发 ， 有这个插件，编译期间会自动给有
				```java
				<dependency>  
					<groupId>org.projectlombok</groupId>  
					<artifactId>lombok</artifactId>  
					<version>1.18.4</version>  
				</dependency>  
				```
				