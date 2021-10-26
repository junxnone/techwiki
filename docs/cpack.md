---
Title | cpack
-- | --
Create Date | `2021-10-26T02:34:17Z`
Update Date | `2021-10-26T02:40:57Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/190)

---
# Reference
- [CPack 入门指南](https://zhuanlan.zhihu.com/p/141956373)


# Breif
- cpack - cmake 内置打包工具
- **支持的打包格式**
  - 7Z (7-Zip file format)
  - **DEB (Debian packages)**
  - External (CPack External packages)
  - IFW (Qt Installer Framework)
  - NSIS (Null Soft Installer)
  - NSIS64 (Null Soft Installer (64-bit))
  - NuGet (NuGet packages)
  - **RPM (RPM packages)**
  - STGZ (Self extracting Tar GZip compression
  - TBZ2 (Tar GZip compression)
  - TXZ (Tar XZ compression)
  - TZ (Tar Compress compression)
  - ZIP (ZIP file format)

![image](https://user-images.githubusercontent.com/2216970/138799118-45ae1e3f-6919-4281-a1bb-9d703ae8ebd7.png)


## 添加 script

preinst：安装前脚本文件
postinst：安装后脚本文件
prerm：卸载前文件
postrm：卸载后文件
