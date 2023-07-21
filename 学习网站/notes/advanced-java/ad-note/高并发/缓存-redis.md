#高并发

高性能高并发

不一致

雪崩   穿透   击穿

redis:  

- 集群 cluster   单核    socket IO 分派 处理（应答 请求 回复）
- readable writbale   k-v  ok
- 纯内存 C IO 避免
- str hash l(消息队列，分页) s（去重，共同好友） ss  bit hll str
- LRU:定期 惰性  过期key 随机   ；淘汰：报错、键空间/过期的（最少、随机、早）
- HA：主从+哨兵
  - redis rep:异步、1多，nn，非阻塞   ; master持久化 :rdb aof
  - s-psync ,full resy,rdb-s-本地磁盘-内存，m-缓存-s,断开重连（m-backlog,ms-rep offset  resy） 
  - 无磁盘：m-rdb-s
  - m-过期/LRU key .del -s
  - 复制流程：s-mhost-ip,socket ping reqpass masauth m-全量，异步复制-s
  - 全量：m-bgsave rdb  -s 60 ,m-内存-s,s-清加，s-AOF
  - 增量：m-断网 backlog-s,m-s psync offset backlog
  - heartbeat m10 s1
- rdb:冷备，amazon s3 odps,fork 子进程 磁盘io，5，大暂停
- aof:后台进程1 append  rewrite最小日志merge,flushall ,大 性能
- cluster： 分片-m,10000 bus  gossip
  - 节点通信：集中：时效好 压力  ； gossip:ping-延时 1/10  pong meet fail 
  - hash缓存重建， 一致性hash：缓存迁移+虚拟节点：负载  ，  hashslot：迁移 key tag 节点
  - HA：判断宕机：pfail fail ,断开时间选举：半数    ，
- 数据一致性
  - 严格：读写串行 1队列   吞吐低
  - 先读缓存，先写数据库
  - - 1：先删缓存：不一致
    - 2：删缓存2
  - 复杂：唯一 路由（nginx） 内存队列  串行  
  - - 不重复
    - 读请求阻塞 走数据库
- 并发竞争：分布式锁（zook）  CAS:时间戳
- 生产部署：5主5从，QPS:5    25  3281   50  主从切换  10 10 1  200 20 0.5 3500