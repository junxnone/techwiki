---
Title | Git proxy config
-- | --
Create Date | `2021-09-20T13:35:32Z`
Update Date | `2021-09-20T13:35:32Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/57)

---
# Install connect-proxy

```
sudo apt-get install connect-proxy
```

#  set git-proxy shell script

```
sudo vi /usr/local/bin/git-proxy
```
```
#!/bin/bash
echo $1 | grep "\.someurl\.com$" > /dev/null 2>&1
if [ $?  -eq 0 ]; then
    connect-proxy $0
else
    connect-proxy -S xxx.com:1080 $@
fi
```
```
sudo chmod a+x /usr/local/bin/git-proxy
```

# Config gitProxy 

```
git config --global core.gitProxy git-proxy
```
Modify ~/.gitconfig to ignore the default proxy for “abc.com” servers. Under the [core] section, add:
```
gitproxy = none for abc.com
```

