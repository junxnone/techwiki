---
Title | Programing Library Tools
-- | --
Created @ | `2021-12-22T07:48:41Z`
Last Modify @| `2022-12-22T03:33:24Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/236)

---
## Reference

- [dumpbin - ms](https://docs.microsoft.com/zh-cn/cpp/build/reference/dumpbin-options?view=msvc-170)
- [lib - ms ](https://docs.microsoft.com/zh-cn/cpp/build/reference/overview-of-lib?view=msvc-170)

## Brief
- Linux
  - ldd
  - objdump
  - readelf
  - nm
- Windows
  - [dumpbin](#dumpbin)
  - [lib](#lib)


## Linux
### ldd
- ldd 查看 [`可执行文件/库`] 的依赖
```
$ldd app/lib
```

## Windows

### dumpbin

- <kbd>VS2019</kbd>--><kbd>工具</kbd>--><kbd>命令行</kbd>--><kbd>开发者命令提示</kbd>

```
$ dumpbin
Microsoft (R) COFF/PE Dumper Version 14.28.29915.0
Copyright (C) Microsoft Corporation.  All rights reserved.

用法: DUMPBIN [选项] [文件]

  选项:

   /ALL
   /ARCHIVEMEMBERS
   /CLRHEADER
   /DEPENDENTS
   /DIRECTIVES
   /DISASM[:{BYTES|NOBYTES}]
   /ERRORREPORT:{NONE|PROMPT|QUEUE|SEND}
   /EXPORTS
   /FPO
   /HEADERS
   /IMPORTS[:文件名]
      /LINENUMBERS
   /LINKERMEMBER[:{1|2}]
   /LOADCONFIG
   /NOLOGO
      /NOPDB
      /OUT:filename
   /PDATA
   /PDBPATH[:VERBOSE]
   /RANGE:vaMin[,vaMax]
   /RAWDATA[:{NONE|1|2|4|8}[,#]]
   /RELOCATIONS
   /SECTION:名称
   /SUMMARY
   /SYMBOLS
   /TLS
   /UNWINDINFO
```
#### UseCase

UseCase | 命令
-- | --
查询依赖动态库 |  `dumpbin -dependents your_app.exe/your_lib.dll`


### lib

- <kbd>VS2019</kbd>--><kbd>工具</kbd>--><kbd>命令行</kbd>--><kbd>开发者命令提示</kbd>

```
$ lib
Microsoft (R) Library Manager Version 14.28.29915.0
Copyright (C) Microsoft Corporation.  All rights reserved.

用法: LIB [选项] [文件]

  选项:

   /DEF[:文件名]
   /ERRORREPORT:{NONE|PROMPT|QUEUE|SEND}
   /EXPORT:符号
   /EXTRACT:成员名
   /INCLUDE:符号
   /LIBPATH:目录
      /LINKREPRO:dir
      /LINKREPROTARGET:filename
   /LIST[:文件名]
   /LTCG
      /MACHINE:{ARM|ARM64|ARM64EC|EBC|X64|X86}
   /NAME:文件名
   /NODEFAULTLIB[:库]
   /NOLOGO
   /OUT:文件名
   /REMOVE:成员名
   /SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
         EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|
         NATIVE|POSIX|WINDOWS|WINDOWSCE}[,#[.##]]
   /VERBOSE
   /WX[:NO]
```


#### UseCase


