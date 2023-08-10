由于本人用vpn，配置阿里云镜像这步跳过
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