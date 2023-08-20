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
	- 