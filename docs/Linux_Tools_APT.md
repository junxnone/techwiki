---
Title | Linux Tools APT
-- | --
Created @ | `2020-06-03T03:19:10Z`
Last Modify @| `2022-12-18T06:10:10Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/101)

---
# Reference
- [Ubuntu apt man page](http://manpages.ubuntu.com/manpages/bionic/man8/apt.8.html)
- [Apt Guide](https://www.debian.org/doc/manuals/apt-guide/index.en.html)
- [apt repo - Github](https://github.com/Debian/apt/tree/master/doc)

# Brief
- Package Management System
- apt & apt-get
- Tools

## UseCase

Name | Description
-- | --
apt-get |  从验证过的源获取 `package` 和 `information`<br> Install/upgrade/remove `package` & `dependencies`
apt-cache |  查询 `package` 可用信息 
apt-cdrom |  to use removable media as a source for packages
apt-config |  as an interface to the configuration settings
apt-key |  as an interface to manage authentication keys
apt-extracttemplates | 用于 `debconf` 提示配置问题 
apt-ftparchive |  创建用于 `publish` 的 `deb package`
apt-sortpkgs |  is a Packages/Sources file normalizer
apt |  is a high-level command-line interface for better interactive usage

Usecase | cmd
-- | --
Update the source list | `apt update`
Install Package | `apt install xxx`
Search Package | `apt search xxx`
清除软件配置文件 | `apt purge xxx`
删除软件(会保留配置文件) | `apt remove xxx`
删除软件相关所有文件 | `apt-get remove --purge xxx`
建立编译某个软件的环境 | `apt build-dep xxx`
清除已下载的软件包和旧软件包 | `apt clean` && `apt autoclean`


## Examples

- Show Depends
```
$ apt-cache depends build-essential
build-essential
 |Depends: libc6-dev
  Depends: <libc-dev>
    libc6-dev
  Depends: gcc
  Depends: g++
  Depends: make
    make-guile
  Depends: dpkg-dev
```
- Show package information

```
$ apt-cache show build-ensseion
N: Unable to locate package build-ensseion
E: No packages found
serverx@iottrainserver:/usr/bin$ apt-cache show build-essential
Package: build-essential
Architecture: amd64
Version: 12.4ubuntu1
Priority: optional
Section: devel
Origin: Ubuntu
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
Original-Maintainer: Matthias Klose <doko@debian.org>
Bugs: https://bugs.launchpad.net/ubuntu/+filebug
Installed-Size: 20
Depends: libc6-dev | libc-dev, gcc (>= 4:7.2), g++ (>= 4:7.2), make, dpkg-dev (>= 1.17.11)
Filename: pool/main/b/build-essential/build-essential_12.4ubuntu1_amd64.deb
Size: 4758
MD5sum: 4a579fdac0b67fa8acba7d458c7e2af2
SHA1: c7b26a0e9b086afdcd81bb02a4cbe12646dade91
SHA256: bb2ac7aae21544446f45e200aacb961f0dcc42c8caacdc8da37d392b222abfa0
Description-en: Informational list of build-essential packages
 If you do not plan to build Debian packages, you don't need this
 package.  Starting with dpkg (>= 1.14.18) this package is required
 for building Debian packages.
 .
 This package contains an informational list of packages which are
 considered essential for building Debian packages.  This package also
 depends on the packages on that list, to make it easy to have the
 build-essential packages installed.
 .
 If you have this package installed, you only need to install whatever
 a package specifies as its build-time dependencies to build the
 package.  Conversely, if you are determining what your package needs
 to build-depend on, you can always leave out the packages this
 package depends on.
 .
 This package is NOT the definition of what packages are
 build-essential; the real definition is in the Debian Policy Manual.
 This package contains merely an informational list, which is all
 most people need.   However, if this package and the manual disagree,
 the manual is correct.
Description-md5: 90ef0ef86cafda0bd16f746eb621d9da
Build-Essential: yes
Supported: 5y

Package: build-essential
Priority: optional
Section: devel
Installed-Size: 20
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
Original-Maintainer: Matthias Klose <doko@debian.org>
Architecture: amd64
Version: 12.1ubuntu2
Depends: libc6-dev | libc-dev, gcc (>= 4:5.2), g++ (>= 4:5.2), make, dpkg-dev (>= 1.17.11)
Filename: pool/main/b/build-essential/build-essential_12.1ubuntu2_amd64.deb
Size: 4758
MD5sum: 731c3a328f87a14bf4f887ceffc51241
SHA1: 47fa98ef28175a9435b814102923aef0fa734204
SHA256: c73b2015ed4f35adf5c79348de26a53c98478de251c0fcd6b2ce49935308ded1
Description-en: Informational list of build-essential packages
 If you do not plan to build Debian packages, you don't need this
 package.  Starting with dpkg (>= 1.14.18) this package is required
 for building Debian packages.
 .
 This package contains an informational list of packages which are
 considered essential for building Debian packages.  This package also
 depends on the packages on that list, to make it easy to have the
 build-essential packages installed.
 .
 If you have this package installed, you only need to install whatever
 a package specifies as its build-time dependencies to build the
 package.  Conversely, if you are determining what your package needs
 to build-depend on, you can always leave out the packages this
 package depends on.
 .
 This package is NOT the definition of what packages are
 build-essential; the real definition is in the Debian Policy Manual.
 This package contains merely an informational list, which is all
 most people need.   However, if this package and the manual disagree,
 the manual is correct.
Description-md5: 90ef0ef86cafda0bd16f746eb621d9da
Bugs: https://bugs.launchpad.net/ubuntu/+filebug
Build-Essential: yes
Origin: Ubuntu
Supported: 5y
Task: ubuntu-desktop, ubuntu-usb, edubuntu-desktop, edubuntu-usb, ubuntustudio-audio, ubuntukylin-desktop
```
- Show 和其他 Package 更详细的信息
```
apt-cache showpkg xxx
```
