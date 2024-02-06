# 开启nacos注册发现
- `AndymallWareApplication`
	- `@Transactional   @MapperScan("com.andymall.ware.dao")  @EnableDiscoveryClient`
- `ware: application.yml`
	- `cloud:  nacos:  discovery:  server-addr: 127.0.0.1:8848  
	- `application:  name: andymall-ware`
- ware 服务重新启动，查看 nacos 是否服务上线

# 配置网管路由规则
- `gateway: application.yml: andymall-ware`
- 重启

查看前端：仓库维护

# 模糊检索功能
- `/ware/wareinfo/list`

#调整日志级别
- `gateway: application.yml: logging:   level:   com.andymall: debug`

下一个：[仓储服务-API-仓库管理-查询库存&创建采购需求 1](仓储服务-API-仓库管理-查询库存&创建采购需求%201.md)