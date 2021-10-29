---
Title | OneAPI
-- | --
Create Date | `2021-10-29T07:37:40Z`
Update Date | `2021-10-29T07:37:40Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/197)

---
# Reference
- [oneapi](https://software.intel.com/content/www/us/en/develop/tools/oneapi.html)

# Brief
- Components
  - [C/C++ Compilers](https://github.com/junxnone/tech-io/issues/1010)
  - DPC++
  - Libraries

## Libraries

Name | Description
-- | --
oneDPL | DPC++ Library
oneDNN | Deep Neural Network Library
oneCCL | Collective Communications Library
Level Zero | low-level direct-to-metal interfaces
oneDAL | Data Analytics Library
oneTBB | Threading Building Blocks
oneVPL | Video Processing Library
one MKL | Math Kernel Library



## Install  with Linux

```
wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB
sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB
echo "deb https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/oneAPI.list
sudo add-apt-repository "deb https://apt.repos.intel.com/oneapi all main"
sudo -E apt install intel-basekit
```

# UseCase

