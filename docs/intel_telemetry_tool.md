---
Title | intel-telemetry-tool
-- | --
Create Date | `2021-09-22T07:19:53Z`
Update Date | `2021-09-22T07:19:53Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/123)

---
# Reference
- [intel-telemetry-tool](https://github.com/Xiaogang-Li/intel-telemetry-tool)

# Brief
- CPU/GPU evaluate calculation capability Tool Kit

## Build & Install

```
git clone https://github.com/Xiaogang-Li/intel-telemetry-tool.git
cd intel-telemetry-tool/build
./prebuild.sh
cd ..
./build.sh
sudo cp telemetry /usr/bin/
```


## UseCase

```
sudo telemetry
```
 - s : show statistics

![image](https://user-images.githubusercontent.com/2216970/61400059-09259f00-a902-11e9-8162-a1f2f7aa5cd3.png)


