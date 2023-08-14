# centos stream9 docker安装
- [Install Docker Engine on CentOS | Docker Documentation](https://docs.docker.com/engine/install/centos/)
- 命令：
``` r
//set up the repo
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

//last version 
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

//start
sudo systemctl start docker

//设置为开机自启
systemctl enable docker
```

# 配置阿里云镜像
- [容器镜像服务](https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors)
- 代码：
``` r
sudo mkdir -p /etc/docker sudo tee /etc/docker/daemon.json <<-'EOF' { "registry-mirrors": ["https://u0euiox4.mirror.aliyuncs.com"] } EOF sudo systemctl daemon-reload sudo systemctl restart docker  
```
- 由于本人用vpn，配置阿里云镜像这步跳过