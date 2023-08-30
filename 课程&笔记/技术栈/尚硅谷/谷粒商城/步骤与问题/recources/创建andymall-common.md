	每一个微服务公共的类、依赖、工具类等放在这里
# 在andymall 总项目下 new module创建 maven类
- ![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230820133653.png)
- pom.xml添加description
	- pom文件路径：andymall-common/pom.xml
	- `<description>每一个微服务公共的类、依赖、工具类等放在这里</description>`
## `product`模块添加`common`模块的依赖
``` java
<dependency>
	<groupId>com.andymall</groupId>
	<artifactId>andymall-common</artifactId>
	<version>0.0.1-SNAPSHOT</version>
</dependency>
```
## `common` 模块添加其他模块需要的依赖
- 记得要点击右边 `maven` 的 `+` , 把 `common` 这个模块加进去
## `andymallproduct/dao` 层的 `BaseMapper` 、`@Mapper` 爆红
- mybatis-plus.  
	-  [安装 | MyBatis-Plus](https://baomidou.com/pages/bab2db/#release)
	``` java 
	//老师用的是3.2.0，我的maven是3.6.1
	<dependency>
		<groupId>com.baomidou</groupId>
		<artifactId>mybatis-plus-boot-starter</artifactId>
		<version>3.3.1</version>
	</dependency>
	```
## `entity` 层的 `@Date` 爆红
- lombok 
	- 简化 `java bean` 开发 ， 有这个插件，编译期间会自动给有`@Date` 注解的实体类添加 get set方法
	```java
	<dependency>  
		<groupId>org.projectlombok</groupId>  
		<artifactId>lombok</artifactId>  
		<version>1.18.4</version>  
	</dependency>  
	```
## 其他工具类爆红
- 路径：`renren-fast/src/main/java/io/renren/common/utils` 
- 去这下面复制粘贴到对应模块
- 例如：
	- `com/andymall/andymallproduct/service/impl/AttrGroupServiceImpl.java` 下的  `query` ` 和 pageutils 爆红
		- ![](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/imgs/Pasted%20image%2020230820164934.png)
			- 那么就在 `common` 模块 创建这个包 ，并把这两个类复制过来： `com.andymall.product.common.utils`
## `controller` 的注解 爆红
- 例如：`com/andymall/product/controller/AttrController.java`
	- `@RequiresPermissions`
		- 之后会用 `spring secutity`   的，这个可以先删或者先不管
## utils 类的 `R` 爆红 
	从 `renren-generator`  复制来的 utils 类的 `R`  
- 路径：`com/andymall/product/common/utils/R.java`
- 爆红：
	- `org.apache.http.HttpStatus` 
		- apache 设计的使用java代码发送http请求的工具类
		- 导入4.4.12版本地址：
			- [Maven Repository: org.apache.httpcomponents » httpcore » 4.4.12](https://mvnrepository.com/artifact/org.apache.httpcomponents/httpcore/4.4.12)
			- 复制 maven 下的 dependency，粘贴到 `common` 模块的 `pom.xml` 当中,然后maven 刷新，太慢就配置镜像
				- [Maven-Mac m1pro](课程&笔记/技术栈/尚硅谷/谷粒商城/步骤与问题/recources/Maven-Mac%20m1pro.md#^fb86c8)
			```java
			<!-- https://mvnrepository.com/artifact/org.apache.httpcomponents/httpcore -->
			<dependency>
				<groupId>org.apache.httpcomponents</groupId>
				<artifactId>httpcore</artifactId>
				<version>4.4.12</version>
			</dependency>
			```
## utils 类的 `Query`爆红
	从 `renren-generator`  复制来的 utils 类的 `Query`
- 路径：`com/andymall/product/common/utils/Query.java`
- 爆红：
	- `io.renren.common.xss.SQLFilter` 
		- 把 `renren-fast/src/main/java/io/renren/common/xss` 这个文件夹复制到 `andymall-common/src/main/java/com/andymall/product/common` 这个文件夹下
		- 然后在 `Query` 当中改变 `SQLFilter` 的引用：import class
		- `Constant` 在 `renren-fast` 的 `Constant.java`  ,也粘贴到 `common`模块的 `util` 目录下
	- `org.apache.commons.lang.StringUtils`  
		- 把 `renren-fast/pom.xml` 的 `common-lang`  依赖包粘贴到 `andymall-common/pom.xml`
		```java
		<dependency>  
			<groupId>commons-lang</groupId>  
			<artifactId>commons-lang</artifactId>  
			<version>2.6</version>  //版本与<properties>下面的2.6这个版本一致
		</dependency>
		
		<properties>  
			<commons.lang.version>2.6</commons.lang.version>
		```

## RequiresPermissions 爆红
	`andymall-product/src/main/java/com/andymall/product/controller` 下的类中的 `org.apache.shiro.authz.annotation.RequiresPermissions` 爆红
- 先全部都删掉，因为要转成 `spring security` 的权限控制
- 然后设置 `renren-generator` 先不生成这个
	- 路径：`renren-generator/src/main/resources/template/Controller.java.vm`
		- 把对应的 `@RequiresPermissions` 注释掉
		- 把上面的 `import org.apache.shiro.authz.annotation.RequiresPermissions;` 删掉
	- 然后重启这个逆向工程 `renren-generator`的`RenrenApplication.java`
		访问80端口，重新生成文件，我们只需要 `controller` 里面的，所以对 `product` 模块下的controller进行替换
最后总结 :
- `common` 模块
	- `pom.xml` 
		![](pom.xml)
	- 目录结构：
		- ![](Pasted%20image%2020230830145304.png)
		- 