---
Title | Tools Jupyter UseLocalPackage
-- | --
Created @ | `2019-10-29T03:46:44Z`
Last Modify @| `2022-12-22T06:15:36Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/138)

---
```
import os
import sys
sys.path.insert(0, os.path.abspath('../module-subdirectory'))
```

# UseCase

## OpenVINO
```
sys.path.insert(0, os.path.abspath('/opt/intel/openvino/python/python3.6'))
```
> 需要运行jupyter notebook 之前 `source /opt/intel/openvino/bin/setupvars.sh`
