# 开启nacos注册发现
- `AndymallWareApplication`
	- `@Transactional   @MapperScan("com.andymall.ware.dao")  @EnableDiscoveryClient`
- `ware: application.yml`
	- `cloud:  nacos:  discovery:  server-addr: 127.0.0.1:8848  
	- `application:  name: andymall-ware`
- ware 服务重新启动，查看 nacos 是否服务上线