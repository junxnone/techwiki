---
Title | Docker move data to new storage location
-- | --
Create Date | `2021-09-22T03:36:48Z`
Update Date | `2021-09-22T03:36:48Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/87)

---
# Reference
- [迁移 Docker 容器储存位置](https://zhuanlan.zhihu.com/p/73576522)

# Brief
- 因硬盘容量问题或者其他问题，想要更改 `docker image` 存储位置

## Steps

- 1 Stop docker service
```
sudo systemctl stop docker
```

- 2 rsync your `/var/lib/docker` to `your new path`
```
rsync -avz /var/lib/docker /your_path/docker
```
- 3 Set docker config `data-root` - `/your_path/docker`
```
vi /etc/docker/daemon.json
```
```
{
+    "data-root": "/your_path/docker",
}
```
> 如果本身有其他配置，记得加 `,`
- 4 Start docker service
```
sudo systemctl daemon-reload
sudo systemctl start docker
```
- 5 restart your container
> 默认会重启自启动的 `container`
```
docker info | grep 'Docker Root'
```
` Docker Root Dir: /your_path/docker`
