---
Title | virtualenvwrapper
-- | --
Create Date | `2021-09-20T13:28:45Z`
Update Date | `2021-09-20T13:28:45Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/55)

---
# Reference
- [Docs](https://virtualenvwrapper.readthedocs.io/en/latest/index.html)
- [windows下安装Virtualenvwrapper](https://blog.csdn.net/a549416598/article/details/80881235)
- [virtualenvwrapper-powershell](https://github.com/regisf/virtualenvwrapper-powershell)

# Install

```
pip install virtualenvwrapper
```

- **Add setup script to  bashrc**

```
vi ~/.bashrc
```
```
source ~/.local/bin/virtualenvwrapper.sh
```
- **Windows Install**

```
pip install virtualenvwrapper-win
```

- **Powershell Issue**:  command line 可以运行，但是 powershell 不可以，需要设置脚本执行权限

管理员身份运行 powershell，执行以下操作, 选择 `Y`

```
Set-ExecutionPolicy RemoteSigned
```
此时可以在 powershell 下 进入 虚拟环境目录执行 `activate.ps1`


# UseCase

Usecase | cmd
-- | --
Create new virtualenv | `mkvirtualenv newvenv`
Open virtualenv | `workon newvenv`
使用特定python | `mkvirtualenv env  --python=python2.7`
退出虚拟环境 | `deactivate`
Remove the venv | `rmvirtualenv newvenv`
List all venv | `lsvirtualenv`


