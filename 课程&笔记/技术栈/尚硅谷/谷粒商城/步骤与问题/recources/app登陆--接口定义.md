- jwt token : 
	- 不存token，登录之后的功能没token无法访问
	- token里放jwt令牌，用来校验和传输用户id
	- token具有时效性的 过段时间 过期了 会提示你重新登录的哦
- 报redis连接错误是因为直接用了nacos里自带的配置文件，建议删除重新自己一个一个添加，默认的里边配置的有redis，需要启动redis才行，但现在还没有用到redis，没有启动redis导致报错
- token是用于识别用户身份，而user信息是用来展示，登陆之后要怎么获取当前用户信息？通过jwt啊
- 报错redis的如果自己下载了redis可以先本地启动一下，再在nacos配置文件中更改端口号为localhost，有密码就写密码，没有就删掉老师给的那个密码，就可以
- 如果启动报错redis的问题，那是因为老师提供的配置里写了redis的配置，我们代码这边还没跟上，后续会写的，这里只需要在服务列表看有没有我们启动的服务就代表是不是成功了