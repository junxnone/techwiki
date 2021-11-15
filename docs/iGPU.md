---
Title | iGPU
-- | --
Create Date | `2021-11-10T17:21:22Z`
Update Date | `2021-11-14T14:50:07Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/212)

---
## Reference
- [Intel® Processors with Integrated Graphics](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-gpu-optimization-guide/top/gen-arch.html)
- [Intel® graphics processor table](https://dgpu-docs.intel.com/devices/hardware-table.html)
- [Install Ubuntu Drivers](https://dgpu-docs.intel.com/installation-guides/ubuntu/ubuntu-focal.html)
- [Shared Local Memory](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-gpu-optimization-guide/top/kernels/slm.html)
- [DPC++ Thread Hierarchy and Mapping](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-gpu-optimization-guide/top/thread-mapping.html)
- [INTEL® GPU Occupancy Calculator](https://oneapi-src.github.io/oneAPI-samples/Tools/GPU-Occupancy-Calculator/index.html)

## Brief
- Slice/SubSlice/EU/ALU
- GRF - `general-purpose registers`



## Arch

Module | Arch
-- | :--:
Slice | ![image](https://user-images.githubusercontent.com/2216970/141405977-200c4977-23ce-4ebe-8198-f1a81b245054.png)
SubSlice | ![image](https://user-images.githubusercontent.com/2216970/141405952-23e3a489-4f2a-4165-b533-43c6bb7cce87.png)
EU | ![image](https://user-images.githubusercontent.com/2216970/141405945-dbf2689a-b650-4df2-b808-989fce52a9e1.png)
Tiger Lake Iris X | ![image](https://user-images.githubusercontent.com/2216970/141686187-0d20ab0b-2e9b-46c7-87c3-fe7094aa2b41.png)




Generations | Threads per EU | EUs per SubSlice | SubSlices | Total Threads | Total Operations
-- | -- | -- | -- | -- | --
Gen9 (BDW) | 7 | 8 | 3 | 168 | 1344
Intel Iris Xe (Gen11) | 7 | 8 | 8 | 448 | 3584
Intel Iris Xe (Gen12) | 7 | 16 | 6 | 672 | 5376

- 每个 EU 包含两个 ALU
- 每个 ALU 可以执行 4xFP32/8xFP16
- 每个 EU 可以执行 8xFP32
- `Total Threads = SubSlices x EUs x Threads`
- `Total Operations = Total Threads x SIMD Width`

### Subslice & SLM 
- `Instruction Cache`
- `Local Thread Dispatcher`
- `Read-Only Texture/Image Sampler` - 64B/Cycle
- `Dataport` - 64B/Cycle
- SLM  - `Shared Local Memory` - 64KB/Subslice
- 每个 Subslice 执行的 `work-items` = `Eus x Threads x SIMD Width`
- SLM: 是在 Subslice 所有 `work-items` 内共享 `atomic data`
  - 如果 work-group 内包含同步操作, 需要分配在同一个 Subslice
- `work-groups` < 16


### ND-Range/work-group/sub-group/work-items


![image](https://user-images.githubusercontent.com/2216970/141645331-c69a9cdb-ae77-40c5-83c4-182faaf7c234.png)



Summary | EUs | Threads | Operations | Maximum Work Group Size | Maximum Work Groups
-- | -- | -- | -- | -- | --
Each SubSlice | 16 |  7x16=112 | 112x8=896   | 512 | 16
Total | 16x6=96  |  112x6=672 | 896x6=5376  | 512 |  16x6=96

> Intel® Iris® Xe Graphics (TGL) GPU



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