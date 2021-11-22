---
Title | conda
-- | --
Create Date | `2020-01-10T08:28:17Z`
Update Date | `2021-11-22T07:00:16Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/88)

---
## Reference
- [conda docs](https://docs.conda.io/projects/conda/en/latest/index.html#)
- [miniconda docs](https://docs.conda.io/en/latest/miniconda.html)
- [Anaconda Documentation](https://docs.anaconda.com/)
- [Github repo](https://github.com/conda)
- [anaconda conda切换成国内源](https://blog.csdn.net/qq_24056913/article/details/88068362)
- [conda 常用命令](https://docs.conda.io/projects/conda/en/latest/commands.html#conda-general-commands)

## Brief

- conda 包和环境管理系统


版本 | 包含内容
-- | --
miniconda | includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others. 
anaconda  | conda + 基础 + 常用的 packages

## Use Case 


UseCasse | Command
-- | --
Install | [Download the Install Package](https://docs.conda.io/en/latest/miniconda.html#linux-installers)<br>`bash Anaconda-latest-Linux-x86_64.sh` <br>`bash Miniconda3-latest-Linux-x86_64.sh`
查看 conda 信息 | `conda info`
**虚拟环境 管理** | 
Create  | `conda create -n your_envs`
Into  | `conda activate your_envs`<br>`source activate your_envs`
Exit  | `conda deactivate`
List All | `conda env list`<br>`conda info --envs`
Remove | `conda remove -n your_envs --all`
Copy| `conda create -n new_envs --clone old_envs`
Export | `conda env export> env.yml`
Import | `conda env create -f env.yml`
**Package 管理** | 
Search | `conda search tensorflow-gpu`
Install | `conda install tensorflow-gpu`<br>`conda install tensorflow-gpu=x.x.x`<br>`conda install --yes --file requirements.txt` <br>安装不在 conda 仓库中的 package `pip3 install your_package`
List All | `conda list`
Remove | `conda remove your_envs your_packages`
Export | `conda list -e > requirements.txt`
环境管理 |


## Others Config

- 源/channel 更换

```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
conda config --set show_channel_urls yes
```

**或者直接更改 `~/.condarc`**

```
channels:
  - https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
  - https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  - defaults
show_channel_urls: true
```

- **Setup Proxy**

```
vi ~/.condarc
```
```
proxy_servers:
  http: http://your_proxy:xxx
  https: http://your_proxy:xxx
```


## Tips

- conda 会自动安装 cuda & cudnn 依赖
- 当使用 `conda` 环境下的 `cuda` `cudnn` 编译 `darknet`时，需要更改 `Makefile` 中的 `-L cudnn` 路径
```
conda install cudatoolkit
conda install cudnn
```
