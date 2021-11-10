---
Title | iGPU
-- | --
Create Date | `2021-11-10T17:21:22Z`
Update Date | `2021-11-10T17:29:50Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/212)

---


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
```
sudo apt install intel-gpu-tools
sudo intel_gpu_top
```



## 查看使用率

```

```


## Ubuntu Access iGPU

- 非 root 用户无法访问 iGPU

```
sudo usermod -aG video $UserName
```
