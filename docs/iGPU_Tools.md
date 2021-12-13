---
Title | iGPU Tools
-- | --
Create Date | `2021-12-13T11:35:31Z`
Update Date | `2021-12-13T11:37:44Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/234)

---

## Brief
- inxi
- lspci
- intel_gpu_top

### 查看 iGPU info

```
inxi -G
```
```
ls -al /dev/dri
```

```
sudo lspci -v -s $(lspci | grep VGA | cut -d" " -f 1)
```
```
$ lspci |grep VGA
00:02.0 VGA compatible controller: Intel Corporation Device 9a49 (rev 01)
```


> 9a49 mean `Intel® Iris® Xe Graphics`, others you can found [here](https://dgpu-docs.intel.com/devices/hardware-table.html)


### 查看 iGPU 使用率

```
sudo apt install intel-gpu-tools
sudo intel_gpu_top
```

