#高并发

- itmdf
- shard  repl  prim    -master:转移，恢复
- 写：coord node p-r all   
  - buffer os cache1 搜到 准实时, fsync seg file  ，translog5  commit (flush)
  - .del
  - delete  refresh seg file  merge  删 新 commit point 
- 读： doc id , coo node  , hash  round  coo 
- 搜：coo ,shard p-r,query,fetch document
- 倒排索引：关键词 文档

<br/>

filesys catch :seg file   ; 字段  es +hbase ;预热 ； 冷热分索引 分机器 ； document 简单 ； 

分页性能优化： 不深，scroll api (快照)/after

5 6.64 320 2000 500 6 15 100 5 20 8 
