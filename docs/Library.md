---
Title | Library
-- | --
Create Date | `2021-12-22T06:00:12Z`
Update Date | `2022-01-05T03:42:11Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/237)

---
## Reference
- [windows中静态库lib和动态dll的区别及使用方法](https://blog.csdn.net/dxzysk/article/details/66477147)
- [什么是 DLL](https://docs.microsoft.com/zh-cn/troubleshoot/windows-client/deployment/dynamic-link-library)

## Brief
- 静态库 - `*.o` 文件压缩打包集合
- 动态链接库/动态加载库
- Linux (`*.a` & `*.so`)
- Windows (`*.lib` & `*.dll`)
- [Library Tools](/Library_Tools)


## Linux

### 静态库
- **命名规则** - `lib[name].a`
- **生成**
  - **生成 `*.o`** - `gcc/g++ -c code_file.c/cpp`
  - **打包成 `*.a`** - `ar -crv lib[name].a code_file.o`
- **使用** - `gcc/g++ main.cpp -L[/path/to/lib] -l[name]`



### 动态库
### Tools
- ldd
- objdump
- readelf
- nm

## Windows
- 静态库 (`*.lib`)  - 仅链接时使用
- 动态库 (`*.lib` & `*.dll`)
  -  **引入库文件 (`*.lib`)** - 包含 `*.dll` 文件导出的函数和变量的符号名, `*.dll` 文件中办好实际函数和数据


Status/库 | 静态库(`*.lib`) | 动态库 (`*.lib` & `*.dll`)
-- | -- | --
**链接** | 复制到函数和数据到可执行文件 | 仅链接引入库(`*.lib`)
**发布** | 不需要发布 | 需要发布动态库
**运行** | 不依赖于静态库 |  需要加载动态库 (`*.dll`)


### 动态库
- 显示链接 (`*.dll`) - `加载时动态链接`
  - 必须链接导入库(`*.lib`)
- 隐式链接 (`*.h` & `*.lib` & `*.dll`) - `运行时动态链接`
  - `LoadLibrary()` & `LoadLibraryEx()`

#### 导出 DLL 函数
- 函数关键字声明导出导入函数

```
// File: SampleDLL.h
//
#ifndef INDLL_H
    #define INDLL_H
    #ifdef EXPORTING_DLL
        extern __declspec(dllexport) void HelloWorld();
    #else
        extern __declspec(dllimport) void HelloWorld();
    #endif
#endif
```

- 模块定义文件声明导出的 DLL 函数
```
// SampleDLL.def
//
LIBRARY "sampleDLL"
EXPORTS HelloWorld
```


### Tools

- dumpbin 
- lib
