![](BEFORE/附件/Pasted%20image%2020231104154259.png)
- [model--创建实体类对应数据库](课程&笔记/技术栈/黑马/黑马头条/resource/model--创建实体类对应数据库.md)
- 创建 ApUserLoginController

镜像中的redis没有密码  所以nacos配置得把密码去掉
报redis连接错误是因为直接用了nacos里自带的配置文件，建议删除重新自己一个一个添加，默认的里边配置的有redis，需要启动redis才行，但现在还没有用到redis，没有启动redis导致报错