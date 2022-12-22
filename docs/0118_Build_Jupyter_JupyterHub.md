---
Title | Build Jupyter JupyterHub
-- | --
Created @ | `2019-05-11T07:10:33Z`
Last Modify @| `2022-12-22T06:13:28Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/118)

---
# Reference
- [Github](https://github.com/jupyterhub/jupyterhub)
- [Docs](https://jupyterhub.readthedocs.io/en/stable/)
- [JupyterHub的安装与配置——让Jupyter支持多用户](https://www.cnblogs.com/crxis/p/9078278.html)
- [Using sudo to run JupyterHub without root privileges](https://github.com/jupyterhub/jupyterhub/wiki/Using-sudo-to-run-JupyterHub-without-root-privileges)
- [Docker部署JupyterHub并开启Lab跟Github授权](http://blog.minws.com/dockerbu-shu-jupyterhubbing-kai-qi-labgen-githubshou-quan/)

# Brief
- **多用户 jupyter notebook**


## Install
### Install on host
```
pip3 install jupyterhub
sudo -E npm install -g configurable-http-proxy
```
### Install with Docker
```
docker run -d -p 8000:8000 --name jupyterhub jupyterhub/jupyterhub jupyterhub
```

## Configure

### Host
**Create jupyterhub user, Install sudospawner to use PAM**
```
sudo useradd jupyterhub
sudo pip install sudospawner
sudo visudo
```
**To make PAM works, add this lines:**
```
Cmnd_Alias JUPYTER_CMD = /usr/local/bin/sudospawner
%jupyterhub ALL=(jupyterhub) /usr/bin/sudo
jupyterhub ALL=(%jupyterhub) NOPASSWD:JUPYTER_CMD
```
```
sudo adduser -G jupyterhub your_username
```
**Generate the config file**
```
jupyterhub --generate-config -f config/jupyterhub_config.py
```
```
sudo -u jupyterhub jupyterhub --JupyterHub.spawner_class=sudospawner.SudoSpawner \
-f ./config/jupyterhub_config.py
```
**diff with the origin config file**
```
< #c.JupyterHub.admin_access = False
---
> c.JupyterHub.admin_access = True
48a49
> c.JupyterHub.admin_users = {'name','name','name'}
167c168
< #c.JupyterHub.data_files_path = '/usr/local/share/jupyterhub'
---
> #c.JupyterHub.data_files_path = '/home/name/.local/share/jupyterhub'
318c319
< #c.JupyterHub.ip = ''
---
> c.JupyterHub.ip = 'your_ip'
356c357
< #c.JupyterHub.port = 8000
---
> c.JupyterHub.port = 8000
464c465
< #c.JupyterHub.statsd_prefix = 'jupyterhub'
---
> c.JupyterHub.statsd_prefix = 'jupyterhub'
636a638
> c.Spawner.env_keep.append('LD_LIBRARY_PATH')
820a823
> c.Authenticator.admin_users = {'name','name','name','name'}
933a937
> c.Authenticator.whitelist = {'name','name','name','name','name','name'}
```
> name is your users
