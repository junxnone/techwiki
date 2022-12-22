---
Title | Tools Jupyter CPP
-- | --
Created @ | `2021-10-25T02:11:55Z`
Last Modify @| `2022-12-22T06:14:10Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/189)

---
## Reference
- [jupyter-xeus/xeus-cling](https://github.com/jupyter-xeus/xeus-cling)


## Brief
- jupyter 通过 `xeus-cling kernel` 支持 C++
- 支持 C11/C14/C17

## Install
- 支持 conda/mamba 安装

```
conda create -n cling
conda activate cling
conda install jupyter notebook
conda install  xeus-cling -c conda-forge
```
```
jupyter notebook --ip xxxx --port xxxx
```
```
$ jupyter kernelspec list
  python3    /home/xxx/.local/share/jupyter/kernels/python3
  xcpp11     /home/xxx/miniconda3/envs/cling/share/jupyter/kernels/xcpp11
  xcpp14     /home/xxx/miniconda3/envs/cling/share/jupyter/kernels/xcpp14
  xcpp17     /home/xxx/miniconda3/envs/cling/share/jupyter/kernels/xcpp17
```
