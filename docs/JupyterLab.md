---
Title | JupyterLab
-- | --
Create Date | `2021-09-22T09:29:03Z`
Update Date | `2021-09-22T09:29:03Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/155)

---
# Reference
- [Docs](https://jupyterlab.readthedocs.io/en/stable/)
- [Jupyterlab 使用手册：号称要取代 Jupyter Notebook](https://cloud.tencent.com/developer/article/1509069)
- [Jupyter Widgets](https://ipywidgets.readthedocs.io/en/stable/user_install.html)

# Brief
- Feature
  - 折叠单元格
  - 拖动单元格(单notebook/多notebook)
  - tab 自动补全
  - 灵活布局
  - 文件管理
  - 虚拟环境
  - Dark 主题
  - 查看图片/pdf/csv
  - 交互计算
  - `new view for notebook` -同时打开同一notebook 方便查看长 notebook
  - 
## Install
```
pip install jupyterlab
```
## Set password
```
from notebook.auth import passwd
passwd()
Enter password:
Verify password:
Out[2]: 'sha1:8d5a8952ba7c:e8a57dd1fbb776267e7cee5922f53xxxxxxxxxx'
```

## UseCase

UseCase | Commands
-- | --
指定ip/host/port | `jupyter lab --ip=xxxxx.xx --port 8899`
Work with virtualenv | `workon yourvirtualenv`<br>`pip install ipykernel`<br>`ipython kernel install --user --name=yourvirtualenv`<br>`jupyter lab xxxx`
Enable tqdm | `pip install ipywidgets` <br> `jupyter nbextension enable --py widgetsnbextension` <br> `jupyter labextension install @jupyter-widgets/jupyterlab-manager`

> ipywidgets 需要在相应的 `kernel` 中安装和 `enable`

## Plugin
- nodejs >= 12.0

```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install nodejs
```
- github 
```
jupyter labextension install @jupyterlab/github
```
> `@20210114`  最新版本不支持，jupyterlab 降到 2.3.0a1 安装成功
```
An error occured.
ValueError: The extension "@jupyterlab/github" does not yet support the current version of JupyterLab.
```
- drawio
```
jupyter labextension install jupyterlab-drawio
```
- git
```
jupyter labextension install @jupyterlab/git
pip install jupyterlab-git
jupyter serverextension enable --py jupyterlab_git
```
