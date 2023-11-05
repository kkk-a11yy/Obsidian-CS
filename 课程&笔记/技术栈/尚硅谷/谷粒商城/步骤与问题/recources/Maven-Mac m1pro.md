# sdk安装maven 3.6.1

```r
ksia@bogon ~ % sdk list maven
ksia@bogon ~ % sdk install maven 3.6.1

ksia@bogon ~ % sdk default maven 3.6.1

```

# 配置maven 的conf/setting.xml

本机路径为：/Users/ksia/.sdkman/candidates/maven/3.6.1/conf/settings.xml
## 配置阿里云镜像

^fb86c8

	
``` r
<mirrors>
	<mirror>
		<id>nexus-aliyun</id>
		<mirrorOf>central</mirrorOf>
		<name>Nexus aliyun</name>
		<url>http://maven.aliyun.com/nexus/content/groups/public</url>
	</mirror>
</mirrors>

```

 - 另一个镜像
```r
        <mirror>
            <id>alimaven</id>
            <name>aliyun maven</name>
            <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
            <mirrorOf>central</mirrorOf>
        </mirror>
 
        <mirror>
            <id>uk</id>
            <mirrorOf>central</mirrorOf>
            <name>Human Readable Name for this Mirror.</name>
            <url>http://uk.maven.org/maven2/</url>
        </mirror>
 
        <mirror>
            <id>CN</id>
            <name>OSChina Central</name>
            <url>http://maven.oschina.net/content/groups/public/</url>
            <mirrorOf>central</mirrorOf>
        </mirror>
 
        <mirror>
            <id>nexus</id>
            <name>internal nexus repository</name>
            <!-- <url>http://192.168.1.100:8081/nexus/content/groups/public/</url>-->
            <url>http://repo.maven.apache.org/maven2</url>
            <mirrorOf>central</mirrorOf>
        </mirror>

```
## 配置jdk1.8编译项目
```r
<profiles>
	<profile>
		<id>jdk-1.8</id>
		<activation>
			<activeByDefault>true</activeByDefault>
			<jdk>1.8</jdk>
		</activation>
		<properties>
			<maven.compiler.source>1.8</maven.compiler.source>
			<maven.compiler.target>1.8</maven.compiler.target>
			<maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
		</properties>
	</profile>
</profiles>
```

# 项目settings

![](BEFORE/附件/Pasted%20image%2020231104124125.png)

file encoding: utf-8
![Pasted image 20231104124421](BEFORE/附件/Pasted%20image%2020231104124421.png)

#maven项目编译太慢
参考：- [解决idea加载maven速度慢问题_idea中加载maven原型列表很慢怎么解决-CSDN博客](https://blog.csdn.net/weixin_44894962/article/details/107871578)
路径：`/Applications/Delevopment/IntelliJ IDEA.app/Contents/plugins/maven/lib/maven3/conf/settings.xml`
修改添加：
```java
<mirror>  
    <id>nexus-aliyun</id>  
    <mirrorOf>central</mirrorOf>    
    <name>Nexus aliyun</name>  
    <url>http://maven.aliyun.com/nexus/content/groups/public</url>
</mirror>

```
