---
Title | pip
-- | --
Created @ | `2018-11-25T09:47:54Z`
Last Modify @| `2022-11-29T04:09:15Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/261)

---
## Reference
- [pip configuration](https://pip.pypa.io/en/latest/user_guide/#configuration )
- [Python 生成requirement 使用requirements.txt](https://blog.51cto.com/meyangyang/2094937)

## Brief
- Python Package 管理工具


## UseCase

UseCase | Comandline
-- | --
Install | `sudo apt install python3-pip`<br>`sudo apt install python-pip`
Install with non-root user | `wget https://bootstrap.pypa.io/get-pip.py`<br>`python get-pip.py --user`<br>`export PATH=~/.local/bin:$PATH`
**Install Package** |
Install your package | `pip3 install your_package`
Install from requirement.txt | `pip3 install -r requirements.txt`
Install with mirror | `pip3 install your_package -i https://pypi.tuna.tsinghua.edu.cn/simple`
Export requirements.txt | `pip freeze > requirements.txt`




## Config
### Config default Mirrors
```
vi ~/.config/pip/pip.conf
```
or
```
vi ~/.pip/pip.conf
```
```
[global]  
timeout = 6000
index-url = https://pypi.douban.com/simple/

[install]
use-mirrors = true
mirrors = https://pypi.douban.com/simple/
trusted-host = pypi.douban.com
```
```
unset all_proxy && unset ALL_PROXY && unset http_proxy && unset https_proxy
```

## Issues

### No module named _internal
```
Traceback (most recent call last):   
File "/usr/bin/pip", line 9, in <module>     
from pip._internal import main 
ImportError: No module named _internal
```

- **Solution**

```
sudo apt install python-pip --reinstall
```
or

```
python -m pip install --upgrade pip
```

### Pip install package on Limited Resource Device

- Device - RAM/Disk 比较小的系统上会出现此类问题

#### Memory 不足, kswapd 进程 卡住
- 当 memory不足时，会导致`pip install` 卡住 ，`kswapd` 进程卡在最前面
- 如果 没有 swap, [增加 swap](/Increase_Swap) 
 
#### `/tmp`  No space left on device
- tmp 分区比较小，编译时空间不足
  - `export TMPDIR` 指定 tmp 目录
  - `-b` 指定 build 目录
```
export TMPDIR=your_tmp_dir
```
> `your_tmp_dir` 最好使用绝对路径, `matplotlib` 使用相对路径时出错
