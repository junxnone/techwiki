---
Title | Gitlab CICD
-- | --
Create Date | `2021-09-22T07:42:47Z`
Update Date | `2021-09-22T07:42:47Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/131)

---
# Reference
- [GitLab CI介绍——入门篇](https://blog.csdn.net/Choerodon/article/details/97751754)
- [Run GitLab Runner in a container](https://docs.gitlab.com/runner/install/docker.html)
- [Adding the proxy to the Docker containers](https://docs.gitlab.com/runner/configuration/proxy.html#adding-the-proxy-to-the-docker-containers)
- [GitLab CI/CD Variables 中文文档](http://www.ttlsa.com/auto/gitlab-cicd-variables-zh-document/)
- [Gitlab CI 使用高级技巧](https://www.jianshu.com/p/3c0cbb6c2936)
- [Using the never pull policy](https://docs.gitlab.com/runner/executors/docker.html#using-the-never-pull-policy)


# Breif
- gitlab-runner

## gitlab-runner
### use docker image 

```
docker run -d --name gitlab-runner --restart always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /srv/gitlab-runner/config:/etc/gitlab-runner \
  gitlab/gitlab-runner:latest
```

## register Specific Runners

> Shared Runners/Group Runners 注册方式相同
```
docker run --rm -t -i \
  -v /srv/gitlab-runner/config:/etc/gitlab-runner gitlab/gitlab-runner register
```
> input your `url` , `token` to register to gitlab
> - 碰到了网络问题，最后确认是proxy的问题
> - If you change the configuration in config.toml, you might need to restart the runner to apply the change. Make sure to restart the whole container instead of using gitlab-runner restart:


### 编写 `.gitlab-ci.yml`

```
variables:
    TEST_SCRIPT_PATH: "${CI_PROJECT_DIR}/.ci/test_scripts"

stages:
    - env_setup

setup_env:
    stage: env_setup
    tags: ["COMPLIANCE"]

    script:
        - ${TEST_SCRIPT_PATH}/setup_env.sh

    artifacts:
        when: always
        paths:
            - '*_report.txt'

```

- 每次运行pipeline 都会新建一个container 然后执行
>如果不想每次都重装环境，需要设置image

### gitlab-runner config

- **/srv/gitlab-runner/config/config.toml**

```
listen_address = "127.0.0.1:8093"
concurrent = 1
check_interval = 0

pre_clone_script = "git config --global http.proxy $HTTP_PROXY; git config --global https.proxy $HTTPS_PROXY"
environment = ["https_proxy=http://your_proxy:port", "http_proxy=http://your_proxy:port", "HTTPS_PROXY=your_proxy:port", "HTTP_PROXY=your_proxy:port"]

[session_server]
  session_timeout = 1800

[[runners]]
  name = "your_server"
  url = "https://your_url/"
  token = "your_token"
  executor = "docker"
  [runners.custom_build_dir]
  [runners.docker]
    tls_verify = false
    image = "your_image:bandit_pylint"
    privileged = false
    disable_entrypoint_overwrite = false
    oom_kill_disable = false
    disable_cache = false
    volumes = ["/cache"]
    shm_size = 0
    pull_policy = "never"
  [runners.cache]
    [runners.cache.s3]
    [runners.cache.gcs]

```
> ` pull_policy = "never"` 则使用本地image 
