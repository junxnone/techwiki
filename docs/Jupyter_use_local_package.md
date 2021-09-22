---
Title | Jupyter use local package
-- | --
Create Date | `2021-09-22T08:57:40Z`
Update Date | `2021-09-22T08:57:40Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/138)

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
