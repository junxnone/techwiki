---
Title | Programing Compiler GCC UbuntuInstall
-- | --
Created @ | `2020-06-03T02:29:48Z`
Last Modify @| `2022-12-22T07:38:22Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/12)

---
# Reference
- [ ] [如何在Ubuntu 18.04上安装GCC编译器](https://www.linuxidc.com/Linux/2019-06/159059.htm)

# Brief
- Install OS Default Gcc Tools
- Install The Specified version GCC Tools

## Install Default GCC Tools
```
sudo apt update
sudo apt install build-essential
```
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
Task: ubuntu-desktop, ubuntu-usb, edubuntu-desktop, edubuntu-usb,
 ubuntustudio-audio, ubuntukylin-desktop

```

## Install The Specified version GCC Tools
```
sudo apt install software-properties-common
sudo -E add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt install gcc-7 g++-7 gcc-8 g++-8 gcc-9 g++-9
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 90 --slave /usr/bin/g++ g++ /usr/bin/g++-9
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 80 --slave /usr/bin/g++ g++ /usr/bin/g++-8
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 70 --slave /usr/bin/g++ g++ /usr/bin/g++-7
```
```
$ sudo update-alternatives --config gcc
There are 4 choices for the alternative gcc (providing /usr/bin/gcc).

  Selection    Path              Priority   Status
------------------------------------------------------------
* 0            /usr/bin/gcc-7     70        auto mode
  1            /usr/bin/gcc-4.8   48        manual mode
  2            /usr/bin/gcc-4.9   49        manual mode
  3            /usr/bin/gcc-6     60        manual mode
  4            /usr/bin/gcc-7     70        manual mode

Press <enter> to keep the current choice[*], or type selection number: 3

$ gcc --version
gcc (Ubuntu 6.5.0-2ubuntu1~18.04) 6.5.0 20181026
Copyright (C) 2017 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

```
