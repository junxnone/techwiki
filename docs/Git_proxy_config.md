---
Title | Git proxy config
-- | --
Created @ | `2018-12-10T06:05:14Z`
Last Modify @| `2022-05-26T07:59:14Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/57)

---
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

