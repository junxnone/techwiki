---
Title | Docker Dockerfile
-- | --
Create Date | `2021-09-22T02:49:54Z`
Update Date | `2021-09-22T02:49:54Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/82)

---
# Reference
- [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)


# UseCase

## examples

- **bandit/pylint gitlab-runner image**

```
FROM ubuntu:18.04

ENV http_proxy=http://your.proxy:port
ENV https_proxy=http://your.proxy:port

ENV HTTP_PROXY=http://your.proxy:port
ENV HTTPS_PROXY=http://your.proxy:port

RUN apt update && \
    apt install python3.6 python3-pip python3-distutils -y
ADD requirements.txt .
RUN pip3 install -r requirements.txt && \
    pip3 install bandit pylint
```
