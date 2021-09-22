---
Title | Docker Volume
-- | --
Create Date | `2021-09-22T03:32:20Z`
Update Date | `2021-09-22T03:32:20Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/85)

---
# Reference
- [docker volume](https://docs.docker.com/engine/reference/commandline/volume/)
- [Docker系列05—Docker 存储卷详解](https://www.cnblogs.com/along21/p/10237219.html)
- [你必须知道的Docker数据卷(Volume)](https://www.cnblogs.com/edisonchou/p/docker_volumes_introduction.html)
- [将宿主机数据挂载到容器中的三种方式](https://edu.51cto.com/center/course/lesson/index?id=347193)

# Brief
docker 管理 data 的两种方式
- mount
- volume


Target | Commands
-- | --
查看所有 volume | `docker volume ls`
查看指定 volume 详细信息 | `docker volume inspect your_volume`
创建 volume | `docker volume create your_volume`
删除 volume | `docker volume rm your_volume`
清理 没有被 任意 container 使用的 volume | `docker volume prune`
