---
Title | Ubuntu shadowsocks
-- | --
Create Date | `2019-06-29T08:35:42Z`
Update Date | `2021-11-05T02:51:16Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/117)

---
## Reference
- [shadowsocks readme](https://github.com/shadowsocks/shadowsocks/tree/master#install)
- [ShadowsocksR服务端伪装成 正常网站流量，以更好的欺骗流量匹配](https://doubibackup.com/hi10k-7p-5.html)

## Brief
- shadowsocks - F**K the GFW

## Install
```
pip install git+https://github.com/shadowsocks/shadowsocks.git@master
```
> 此命令会安装3.0.0, `pip install shadowsocsk` 会安装2.8.2, 被迫停止维护的版本

## Build from source -  shadowsocks-libev
```
# Installation of basic build dependencies
## Debian / Ubuntu
sudo apt-get install --no-install-recommends gettext build-essential autoconf \
libtool  libpcre3-dev asciidoc xmlto libev-dev libc-ares-dev automake \
libmbedtls-dev libsodium-dev

# Installation of libsodium
export LIBSODIUM_VER=1.0.16
wget https://download.libsodium.org/libsodium/releases/libsodium-$LIBSODIUM_VER.tar.gz
tar xvf libsodium-$LIBSODIUM_VER.tar.gz
pushd libsodium-$LIBSODIUM_VER
./configure --prefix=/usr && make
sudo make install
popd
sudo ldconfig

# Installation of MbedTLS
export MBEDTLS_VER=2.6.0
wget https://tls.mbed.org/download/mbedtls-$MBEDTLS_VER-gpl.tgz
tar xvf mbedtls-$MBEDTLS_VER-gpl.tgz
pushd mbedtls-$MBEDTLS_VER
make SHARED=1 CFLAGS="-O2 -fPIC"
sudo make DESTDIR=/usr install
popd
sudo ldconfig

# Start building
./autogen.sh && ./configure && make
sudo make install
```

## Error
```
aead.c:274: undefined reference to `crypto_aead_xchacha20poly1305_ietf_decrypt'
ss_local-aead.o: In function `cipher_aead_encrypt':
```
**Solution**
删除其他libsoduim library
> in my case
```
find /usr/lib/x86_64-linux-gnu/ -name libsodium.*|xargs sudo rm
```
