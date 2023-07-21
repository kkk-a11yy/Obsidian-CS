#HA

- 延迟 容错保护 故障隔离(bulkhead swimline circuit breaker) 快速失败ff 快速恢复 降级fb 监控 报警 运维

大型网站：变更：mq  redis  ngixn  本地  渲染

- 接口服务故障导致服务资源耗尽

线程池隔离*：command    observableCommand   

- ngixn 失效  
- tomcat 线程 hystrix线程  
- timeout 
- 粒度：command key group  一个线程池 thread pool  , core size10,queueSizeRejection

信号量：

- 内部  量少 访问频繁

hy执行：

- 创建 调用:  comm getfallback 降级; observable: resumewithfallback 对象+降级   ，  req cache 断路器 资源池 run 出错/timeout      fallback

超时：

- tomillsec  1000 ,  toenabled
