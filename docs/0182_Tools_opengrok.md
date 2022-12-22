---
Title | Tools opengrok
-- | --
Created @ | `2019-04-20T16:08:54Z`
Last Modify @| `2022-12-22T07:21:19Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/182)

---
## Reference
- https://oracle.github.io/opengrok/
- [opengrok Docker](https://hub.docker.com/r/opengrok/docker/)

## Brief
- 浏览代码用的Web工具 
- 可以实现较快的跳转搜索

## Setup With Docker

- **Pull opengrok docker image**
```
docker pull opengrok/docker
```

- **Run container**
```
docker run -d -v <path/to/your/src>:/opengrok/src -p 8080:8080 opengrok/docker:latest
```

> e.g. 
`docker run -d -v ~/workm/opengrok_src:/opengrok/src -p 8080:8080 opengrok/docker:latest`

- **Manually trigger an reindex**

```
docker exec <container> /scripts/index.sh
```
