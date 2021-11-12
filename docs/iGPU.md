---
Title | iGPU
-- | --
Create Date | `2021-11-10T17:21:22Z`
Update Date | `2021-11-12T05:56:53Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/212)

---
## Reference
- [Intel® Processors with Integrated Graphics](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-gpu-optimization-guide/top/gen-arch.html)
- [Intel® graphics processor table](https://dgpu-docs.intel.com/devices/hardware-table.html)
- [Install Ubuntu Drivers](https://dgpu-docs.intel.com/installation-guides/ubuntu/ubuntu-focal.html)

## Brief
- Slice/SubSlice/EU/ALU
- GRF - `general-purpose registers`



## Arch

Module | Arch
-- | :--:
Slice | ![image](https://user-images.githubusercontent.com/2216970/141405977-200c4977-23ce-4ebe-8198-f1a81b245054.png)
SubSlice | ![image](https://user-images.githubusercontent.com/2216970/141405952-23e3a489-4f2a-4165-b533-43c6bb7cce87.png)
EU | ![image](https://user-images.githubusercontent.com/2216970/141405945-dbf2689a-b650-4df2-b808-989fce52a9e1.png)




Generations | Threads per EU | EUs per SubSlice | SubSlices | Total Threads | Total Operations
-- | -- | -- | -- | -- | --
Gen9 (BDW) | 7 | 8 | 3 | 168 | 1344
Intel Iris Xe (Gen11) | 7 | 8 | 8 | 448 | 3584
Intel Iris Xe (Gen12) | 7 | 16 | 6 | 672 | 5376




## UseCase
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

## Issues

### Ubuntu Cannot Access iGPU

- 非 root 用户无法访问 iGPU

```
sudo usermod -aG video $UserName
```
