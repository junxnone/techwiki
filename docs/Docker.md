---
Title | Docker
-- | --
Create Date | `2018-09-06T16:18:38Z`
Update Date | `2021-11-17T08:16:46Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/39)

---
## Reference

- [install-docker-ce - ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce)
- [Install docker-compose](https://docs.docker.com/compose/install/#install-compose)
- [Configure Docker to use a proxy server](https://docs.docker.com/network/proxy/)
- [The Docker daemon proxy](https://docs.docker.com/config/daemon/systemd/#runtime-directory-and-storage-driver)
- [Docker 镜像分析工具 diving](https://www.oschina.net/p/diving)
- [docker改国内官方镜像](https://www.cnblogs.com/coolwinds/p/7465475.html)
- [Dokcer使用总结（Dockerfile、Compose、Swarm）](https://www.cnblogs.com/wyt007/p/11154156.html)

## Brief
- [Install docker](#install-docker)
- [Docker Usecase/Setup proxy/mirror](#usecase)
- [Docker Network](/Docker_Network)
- [Docker GUI](/Docker_GUI)
- [Docker compose](/Docker_compose)
- [Docker Dockerfile](/Docker_Dockerfile)
- [Docker Volume](/Docker_Volume)
- [Docker Tools](/Docker_Tools)
- **Issues**
  - [Docker move data to new storage location](/Docker_move_data_to_new_storage_location)


## Install Docker
### Ubuntu 下安装docker

```
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce
```
-  将当前用户添加到 docker 组

```
sudo usermod -aG docker $USER
```

### 安装指定版本的docker

```
curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get -y update
sudo apt-cache madison docker-ce
sudo apt-get install -y docker-ce=$(apt-cache madison docker-ce | grep 17.12.1 | head -1 | awk '{print $3}')
```



## UseCase

Usecase |  cmd
-- | --
Verify Install | `docker run hello-world`
Save docker image | `docker save -o my_ubuntu_v3.tar runoob/ubuntu:v3`
Import docker image | `docker import  my_ubuntu_v3.tar runoob/ubuntu:v4`
Load docker image | `sudo docker load -i hmi.tar`
Run in bash | `docker exec -it docker_name bash`
删除 `none` 镜像 | docker rmi -f  \`docker images \| grep 'none' \| awk '{print $3}'\`

> 如果打包包含了多个 `image` 则可以通过 `your_image.tar/repositories` 查看 `镜像名称` 和 `commit id`

## Proxy setup

- Setup container proxy
- Setup daemon proxy

### Setup container Proxy

```
vi ~/.docker/config.json
```
```
{
 "proxies":
 {
   "default":
   {
     "httpProxy": "http://127.0.0.1:8123",
     "httpsProxy": "http://127.0.0.1:8123",
     "noProxy": "*.test.example.com,.example2.com"
   }
 }
}
```

### Setup daemon proxy

```
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo vi /etc/systemd/system/docker.service.d/http-proxy.conf
sudo vi /etc/systemd/system/docker.service.d/https-proxy.conf
```
/etc/systemd/system/docker.service.d/http-proxy.conf
```
[Service]
Environment="HTTP_PROXY=http://127.0.0.1:8123"
```
/etc/systemd/system/docker.service.d/https-proxy.conf
```
[Service]
Environment="HTTPS_PROXY=http://127.0.0.1:8123"
```

- Proxy & Mirror 配置完后都要重新加载配置文件和重启 docker 生效
  - `sudo systemctl daemon-reload`
  - `sudo systemctl restart docker`


## Mirrors Setup

```
sudo vi /etc/docker/daemon.json
```
```
{
 "registry-mirrors": ["https://registry.docker-cn.com"]
}
```
- **Yocto**
  - Yocto 环境下 docker build 不能获取 `apt update`： 需要配置 `DNS`
- **mirrors**
  - USTC Mirror : `https://docker.mirrors.ustc.edu.cn`
- 如果碰到如下问题可以更换 mirror 试试

```
toomanyrequests: You have reached your pull rate limit. You may increase the limit by authenticating and upgrading: https://www.docker.com/increase-rate-limit
```

## docker容器的自启动

**--restart 参数**

- no  不自动重启容器. (默认值)
- on-failure  容器发生error而退出(容器退出状态不为0)重启容器,可以指定重启的最大次数，如：on-failure:10
- unless-stopped  在容器已经stop掉或Docker stoped/restarted的时候才重启容器
- always  在容器已经stop掉或Docker stoped/restarted的时候才重启容器，手动stop的不算

> e.g. 
> `docker run --restart always -d -v ~/workm/opengrok_src:/opengrok/src -p 8080:8080 opengrok/docker:latest`
> 如果容器已经被创建，我们想要修改容器的重启策略
> e.g.
> docker update --restart always xxxx


