由于是m1pro的芯片， 要选择支持arm架构的mysql版本
```r
docker pull mysq:8.0

root@bogon ~]# docker images
REPOSITORY   TAG       IMAGE ID       CREATED                  SIZE
mysql        8.0       6a0560a40914   Less than a second ago   599MB

注意8的版本mysql位子已经改变了-v /mydata/mysql/conf:/etc/mysql \  这个改为 -v /mydata/mysql/conf:/etc/mysql/conf.d \
```