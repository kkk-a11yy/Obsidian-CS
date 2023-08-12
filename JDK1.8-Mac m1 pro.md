#  java版本控制工具
- sdkman
	- [SDKMAN: Install Multiple JDK Versions and Much More! | Scalastic 👨🏻‍💻](https://scalastic.io/en/installer-java-sdkman/)
- [我应该使用哪个版本的 JDK？ | Maxgao](https://www.ga0x.com/docs/Java/base/whichjdk)
```java
ksia@bogon ~ % sdk version

SDKMAN!
script: 5.18.2
native: 0.3.0

--------
ksia@bogon ~ % sdk list java
ksia@bogon ~ % sdk install java 8.0.382-amzn

--------
ksia@bogon ~ % sdk current java 

Using java version 8.0.382-amzn

---------
ksia@bogon ~ % sdk default java 8.0.382-amzn 
set java 8.0.382-amzn as default version

---------
ksia@bogon ~ % java -version 
openjdk version "1.8.0_382"
OpenJDK Runtime Environment Corretto-8.382.05.1 (build 1.8.0_382-b05)
OpenJDK 64-Bit Server VM Corretto-8.382.05.1 (build 25.382-b05, mixed mode)
ksia@bogon ~ % 
```

[配置jdk1.8编译项目](maven-mac%20m1pro.md#配置jdk1.8编译项目)