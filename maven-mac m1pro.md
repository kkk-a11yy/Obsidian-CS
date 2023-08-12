# sdk安装maven 3.6.1

```r
ksia@bogon ~ % sdk list maven
ksia@bogon ~ % sdk install maven 3.6.1

ksia@bogon ~ % sdk default maven 3.6.1

```

# 配置maven 的conf/setting.xml

本机路径为：/Users/ksia/.sdkman/candidates/maven/3.6.1/conf/settings.xml
## 配置阿里云镜像
	- 本人已翻墙，此处先不加
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

下一步：[[