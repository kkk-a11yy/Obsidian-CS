- [centos-stream-9 centos9 配置国内yum源 阿里云源_centos9的yum源-CSDN博客](https://blog.csdn.net/lqzixi/article/details/132237899)

```java

[root@localhost ~]# mv /etc/yum.repos.d/centos.repo /etc/yum.repos.d/centos.repo.backup

[root@localhost ~]# yum clean all

	28 个文件已删除

[root@localhost ~]# cd /etc/yum.repos.d/

[root@localhost yum.repos.d]# ls

	centos-addons.repo  centos.repo.backup  docker-ce.repo

[root@localhost yum.repos.d]# mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup

	mv: 无法获取'/etc/yum.repos.d/CentOS-Base.repo' 的文件状态(stat): 没有那个文件或目录

[root@localhost yum.repos.d]# ls

	centos-addons.repo  centos.repo.backup  docker-ce.repo

[root@localhost yum.repos.d]# vim CentOS-Base.repo

[root@localhost yum.repos.d]# yum makecache

[root@localhost yum.repos.d]# yum update

```