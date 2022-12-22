---
Title | Tools Git proxy
-- | --
Created @ | `2018-12-10T06:05:14Z`
Last Modify @| `2022-12-22T06:47:35Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/57)

---
## Reference
- [一文让你了解如何为 Git 设置代理](https://ericclose.github.io/git-proxy-config.html)

## Brief
- Tools: socat/connect-proxy
- 1 Install `connect-proxy`
- 2 Setup `ssh config`
- 3 Setup `git config`

### 1 SSH proxy setting with `connect-proxy`

- Install `connect-proxy/socat`

```
sudo apt-get install connect-proxy socat
```
### 2 Setup ssh config

- setup `~/.ssh/config`, add the following section

```
host github.com
    ProxyCommand connect -a none -S proxy_ip:proxy_port(1080) %h %p
```


### 3 Setup Git Config gitProxy 

- Create `/usr/bin/git-proxy`
```
#!/bin/sh
if [ $? -eq 0 ]; then
    /usr/bin/connect $@
else
    exec /usr/bin/socat stdio SOCKS:[your_ip_or_url]:$1:$2
fi
```
```
sudo chmod +x /usr/bin/git-proxy
```

- Setup `gitproxy`

```
git config --global core.gitProxy git-proxy
```



