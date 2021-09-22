---
Title | cmake install
-- | --
Create Date | `2021-09-22T01:09:49Z`
Update Date | `2021-09-22T01:09:49Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/66)

---
# Install for Linux
## Ubuntu 16.04 Install cmake 3.21.1

```
wget https://cmake.org/files/v3.21/cmake-3.21.1-linux-x86_64.tar.gz
tar zvxf cmake-3.21.1-Linux-x86_64.tar.gz
vi ~/.bashrc
```
```
export PATH="/your/cmake/path/bin:$PATH"
```
```
source ~/.bashrc
```
```
$ cmake --version
cmake version 3.21.1
```
## Build from source code
```
wget https://cmake.org/files/v3.16/cmake-3.16.9.tar.gz
tar zvxf cmake-3.16.9.tar.gz
cd cmake-3.16.9
./configure
make
sudo make install
```

# Install for Windows
- download the [msi](https://cmake.org/download/) and install the package
