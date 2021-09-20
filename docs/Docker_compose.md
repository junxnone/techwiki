---
Title | Docker compose
-- | --
Create Date | `2018-09-06T16:19:34Z`
Update Date | `2021-09-20T10:48:05Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/42)

---
# Reference
- [install-compose](https://docs.docker.com/compose/install/#install-compose)
- [Docker Compose Document](https://docs.docker.com/compose/)
- [Compose file version 3 reference](https://docs.docker.com/compose/compose-file/#compose-and-docker-compatibility-matrix)
- [compose Github repo](https://github.com/docker/compose/)
- [Compose file  reference](https://docs.docker.com/compose/compose-file/)

# Brief

- [Install](#Install)
- [UseCase](#usecase)
- [Examples](#examples)

Compose 是一个用户定义和运行多个容器的 Docker 应用程序。在 Compose 中你可以使用 YAML 文件来配置你的应用服务。然后，只需要一个简单的命令，就可以创建并启动你配置的所有服务。

1. 在 Dockfile 中定义你的应用环境，使其可以在任何地方复制。
2. 在 docker-compose.yml 中定义组成应用程序的服务，以便它们可以在隔离的环境中一起运行。
3. 最后，运行dcoker-compose up，Compose 将启动并运行整个应用程序。




# Install 
## 二进制安装
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```
## pip 安装
```
pip install docker-compose
```
# Config File - docker-compose.yml
在 services 标签下的第二级标签是服务名称, 用户自定义。

- build - can be specified either as a string containing a path to the build context:
- context - Either a path to a directory containing a Dockerfile, or a url to a git repository.
- dockerfile - Compose uses an alternate file to build with. A build path must also be specified.
- image - 则是指定服务的镜像名称或镜像 ID。如果镜像在本地不存在，Compose 将会尝试拉取这个镜像。
- args - 添加构建参数，这些参数是仅在构建过程中可访问的环境变量
- command - 可以覆盖容器启动后默认执行的命令。
- ports - 使用HOST:CONTAINER格式或者只是指定容器的端口，宿主机会随机映射端口。
- depends_on - 启动依赖
- container_name -  Compose 的容器名称格式是：<项目名称><服务名称><序号>
- volumes - 挂载一个目录或者一个已存在的数据卷容器，可以直接使用 [HOST:CONTAINER] 这样的格式


# UseCase

Usecase | cmd
-- | --
Start | `docker-compose up -d`
Stop | `docker-compose down`

- **docker-compose 共享目录**

```
 volumes:
      - $PWD/:/test/
```
> 把当前目录共享到container中/test 下，需要重现`docker-compose up` 才能工作。


# Examples
## Web

```
composetest
├── app.py
├── docker-compose.yml
├── Dockerfile
└── requirements.txt
```

```
$ mkdir composetest
$ cd composetest
vi app.py
```
**app.py**
```
import time

import redis
from flask import Flask


app = Flask(__name__)
cache = redis.Redis(host='redis', port=6379)


def get_hit_count():
    retries = 5
    while True:
        try:
            return cache.incr('hits')
        except redis.exceptions.ConnectionError as exc:
            if retries == 0:
                raise exc
            retries -= 1
            time.sleep(0.5)


@app.route('/')
def hello():
    count = get_hit_count()
    return 'Hello World! I have been seen {} times.\n'.format(count)

if __name__ == "__main__":
    app.run(host="0.0.0.0", debug=True)
```
```
vi requirements.txt
```
**requirements.txt**
```
flask
redis
```
```
vi Dockerfile
```

- **Dockerfile**

```
FROM python:3.4-alpine
ADD . /code
WORKDIR /code
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```
```
vi docker-compose.yml
```

- **docker-compose.yml**

```
version: '3'
services:
  web:
    build: .
    ports:
     - "5000:5000"
  redis:
    image: "redis:alpine"
```
```
$ docker-compose up
```
then, the service is avaliable at : http://0.0.0.0:5000/


