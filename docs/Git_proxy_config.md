---
Title | Git proxy config
-- | --
Create Date | `2018-12-10T06:05:14Z`
Update Date | `2021-11-04T15:30:09Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/57)

---
## SSH proxy setting with `connect-proxy`

- Install `connect-proxy`

```
sudo apt-get install connect-proxy
```

- setup `~/.ssh/ocnfig`, add the following section

```
host github.com

ProxyCommand connect -a none -S proxy_ip:proxy_port(1080) %h %p
```


## Config gitProxy 

```
git config --global core.gitProxy git-proxy
```
Modify ~/.gitconfig to ignore the default proxy for “abc.com” servers. Under the [core] section, add:
```
gitproxy = none for abc.com
```

