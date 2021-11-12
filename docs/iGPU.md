---
Title | iGPU
-- | --
Create Date | `2021-11-10T17:21:22Z`
Update Date | `2021-11-12T03:49:33Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/212)

---
## Reference
- [Intel® Processors with Integrated Graphics](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-gpu-optimization-guide/top/gen-arch.html)

## Brief
- Slice/SubSlice/EU/ALU

Module | Arch
-- | --
Slice | ![image](https://user-images.githubusercontent.com/2216970/141405977-200c4977-23ce-4ebe-8198-f1a81b245054.png)
SubSlice | ![image](https://user-images.githubusercontent.com/2216970/141405952-23e3a489-4f2a-4165-b533-43c6bb7cce87.png)
EU | ![image](https://user-images.githubusercontent.com/2216970/141405945-dbf2689a-b650-4df2-b808-989fce52a9e1.png)





## 查看 Device

```
inxi -G
```
```
ls -al /dev/dri
```

```
sudo lspci -v -s $(lspci | grep VGA | cut -d" " -f 1)
```




## 查看使用率

```
sudo apt install intel-gpu-tools
sudo intel_gpu_top
```


## Ubuntu Access iGPU

- 非 root 用户无法访问 iGPU

```
sudo usermod -aG video $UserName
```
