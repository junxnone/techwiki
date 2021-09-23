---
Title | OpenProject
-- | --
Create Date | `2021-09-23T03:33:30Z`
Update Date | `2021-09-23T03:33:30Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/165)

---
# Inference
- [Github](https://github.com/opf/openproject)
- [Install with Docker](https://www.openproject.org/docker/)
- [Docker image](https://hub.docker.com/r/openproject/community/)

# Brief
- project management software

## Install with Docker

**Pull image**
```
docker pull openproject/community
```
**Run Container**
```
docker run -itd -p 8090:80 -e SECRET_KEY_BASE=secret openproject/community
```
> access the websit: xxx.xxx.xxx.xxx:8090

## UseCase

![image](https://user-images.githubusercontent.com/2216970/61180525-3f38f980-a64a-11e9-8b0d-9d7ea7f12f2b.png)

