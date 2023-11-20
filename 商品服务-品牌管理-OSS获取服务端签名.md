- 创建新的微服务
	- `andymall-third-part` dependency: SpringWeb , OpenFeign , andymall-common
	- `<spring-cloud.version>Hoxton.SR3`
	- `<spring-boot-starter-parent> <version>2.2.5.RELEASE`
	- `depemdencymanagement> spring-cloud-alibaba-dependencies><version>2.2.1.RELEASE`
	- `<aliyun-oss-spring-boot-starter</artifactId>  <version>1.0.0`
- nacos 注册 `third-party` 命名空间，创建 `oss.yml`,写入oss 配置数据（key,secret,endpoint）
	- `third-party: bootstarp.properties`:命名空间id
- `AndymallThirdPartyApplicationTests`
	- `testUpload01()` 测试成功
- [如何进行服务端签名直传_对象存储 OSS-阿里云帮助中心](https://help.aliyun.com/zh/oss/use-cases/obtain-signature-information-from-the-server-and-upload-data-to-oss?spm=a2c4g.11186623.0.0.618e2bdbs0o2WZ)


------
## 问题

#datasource_url错误
	- `exclude: renrenfast ; mybatus-plus-boot-starter`

#使用OSS接口而不是OSSClient

 #空指针
	 低版本SpringBoot加@RunWith(SpringRunner.class)