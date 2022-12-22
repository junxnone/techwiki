---
Title | Ubuntu Download aria2
-- | --
Created @ | `2020-06-06T15:32:47Z`
Last Modify @| `2022-12-22T07:42:37Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/36)

---
# Reference
- [aria2-ariang-docker](https://github.com/wahyd4/aria2-ariang-docker)
- [aria2-ariang-x-docker-compose](https://github.com/wahyd4/aria2-ariang-x-docker-compose)
- [trackerslist](https://github.com/ngosang/trackerslist)
- [磁力链接转种子工具](http://magnet2torrent.com/)



## Install & Setup with Docker

- Setup Docker Env

```
docker run -d --name ariang \
     --restart=always\
     -p 80:80 \
     -p 443:443 \
     -e PUID=1000 \
     -e PGID=1000 \
     -e ENABLE_AUTH=true \
     -e RPC_SECRET=Hello \
     -e ARIA2_USER=admin \
     -e ARIA2_PWD=admin \
     -e ARIA2_SSL=false \
     -e ARIA2_EXTERNAL_PORT=443 \
     -v /home/xxx/aria_data:/data \
     wahyd4/aria2-ui
```

# 使用

- aria2 - http://yourip/ui
- 文件管理 - http://yourip
- 默认密码 admin/admin
