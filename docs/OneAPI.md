---
Title | OneAPI
-- | --
Create Date | `2021-06-23T06:24:28Z`
Update Date | `2022-04-19T05:12:01Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/197)

---
## Reference

- [oneapi](https://software.intel.com/content/www/us/en/develop/tools/oneapi.html)

## Brief
- Components
  - [Intel Compiler](/Intel_Compiler)
  - [DPC++](/DPCPP)
  - Libraries

## Libraries

Name | Description
-- | --
[oneDPL](/oneDPL) | DPC++ Library(Hight-Level API)
oneDNN | Deep Neural Network Library
oneCCL | Collective Communications Library
Level Zero | low-level direct-to-metal interfaces
oneDAL | Data Analytics Library
oneTBB | Threading Building Blocks
oneVPL | Video Processing Library
[one MKL](/Intel_MKL) | Math Kernel Library



## Install  with Linux

```
wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB
sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB
echo "deb https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/oneAPI.list
sudo add-apt-repository "deb https://apt.repos.intel.com/oneapi all main"
sudo -E apt install intel-basekit
```


