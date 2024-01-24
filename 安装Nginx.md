```java
root@192.168.101.104's password: 

Connected to 192.168.101.104.

sftp> put /Users/ksia/Downloads/analysis-icu-8/* /mydata/elasticsearch/plugins/analysis-icu-8/

```

```java
[root@localhost ~]# mkdir -p /mydata/nginx/conf


[root@localhost ~]# cd /mydata/

[root@localhost mydata]# ls

elasticsearch  **mysql**  **nginx**  **redis**

[root@localhost mydata]# docker container cp nginx:/etc/nginx /mydata/nginx/conf

[root@localhost mydata]# mv /mydata/nginx/conf/nginx/* /mydata/nginx/conf/

[root@localhost mydata]# rm -rf /mydata/nginx/conf/nginx

[root@localhost mydata]# cd nginx/

[root@localhost nginx]# ls

**conf**

[root@localhost nginx]# docker stop nginx

nginx

[root@localhost nginx]# docker rm nginx

nginx

[root@localhost nginx]# pwd

/mydata/nginx

```

```java
[root@localhost nginx]# docker pull nginx:stable

[root@localhost nginx]# docker run -p 80:80 --name nginx \

-v /mydata/nginx/html:/usr/share/nginx/html \

-v /mydata/nginx/logs:/var/log/nginx \

-v /mydata/nginx/conf/:/etc/nginx \

-d nginx:stable

907033ae5222891e4a38b6baf4a8406fa1d57ae94a6075cf54596b341780730e

[root@localhost nginx]# docker update nginx --restart=always

nginx

[root@localhost nginx]# pwd

/mydata/nginx

[root@localhost nginx]# ls

**conf**  **html**  **logs**

[root@localhost nginx]# cd html/

[root@localhost html]# ls

[root@localhost html]# vi index.html

[root@localhost html]# pwd

/mydata/nginx/html

[root@localhost html]# mkdir es

[root@localhost html]# ls

**es**  index.html

[root@localhost html]# cd es/

[root@localhost es]# vi fenci.txt

```


```java
<?xml version="1.0" encoding="UTF-8"?>

**<!**DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd"**>**

**<properties>**

        **<comment>**IK Analyzer 扩展配置**</comment>**

        <!--用户可以在这里配置自己的扩展字典 -->

        **<entry** key="ext_dict"**></entry>**

         <!--用户可以在这里配置自己的扩展停止词字典-->

        **<entry** key="ext_stopwords"**></entry>**

        <!--用户可以在这里配置远程扩展字典 -->

        **<entry** key="remote_ext_dict"**>**http://192.168.101.104/es/fenci.txt**</entry>**

        <!--用户可以在这里配置远程扩展停止词字典-->

        <!-- <entry key="remote_ext_stopwords">words_location</entry> -->

**</properties>**

~                                                                                                      

~                                                                                                      

~                                                                                                      

~                                                                                                      

~                                                                                                      

~                                                                                                      

~                                                                                                      

~                                                                                                      

~
```