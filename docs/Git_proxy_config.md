---
Title | Git proxy config
-- | --
Created @ | `2018-12-10T06:05:14Z`
Last Modify @| `2022-05-26T08:02:31Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/57)

---
## Reference
- [一文让你了解如何为 Git 设置代理](https://ericclose.github.io/git-proxy-config.html)

## Brief
- 1 Install `connect-proxy`
- 2 Setup `ssh config`
- 3 Setup `git config`

### 1 SSH proxy setting with `connect-proxy`

- Install `connect-proxy`

```
sudo apt-get install connect-proxy
```
### 2 Setup ssh config

- setup `~/.ssh/config`, add the following section

```
host github.com
    ProxyCommand connect -a none -S proxy_ip:proxy_port(1080) %h %p
```


### 3 Setup Git Config gitProxy 

```
git config --global core.gitProxy git-proxy
```
Modify ~/.gitconfig to ignore the default proxy for “abc.com” servers. Under the [core] section, add:
```
gitproxy = none for abc.com
```

