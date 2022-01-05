---
Title | Library
-- | --
Create Date | `2021-12-22T06:00:12Z`
Update Date | `2022-01-05T06:39:26Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/237)

---
## Reference
- [windows中静态库lib和动态dll的区别及使用方法](https://blog.csdn.net/dxzysk/article/details/66477147)
- [什么是 DLL](https://docs.microsoft.com/zh-cn/troubleshoot/windows-client/deployment/dynamic-link-library)
- [在 C++ 类中使用 dllimport 和 dllexport](https://docs.microsoft.com/zh-cn/cpp/cpp/using-dllimport-and-dllexport-in-cpp-classes?view=msvc-170)


## Brief
- 静态库 - `*.o` 文件压缩打包集合
- 共享库/动态链接库/动态加载库
- Linux (`*.a` & `*.so`)
- Windows (`*.lib` & `*.dll`)
- [Library Tools](/Library_Tools)


库 | 优点 | 缺点
-- | -- | --
静态库 | 无依赖 | 占用空间大 
共享库/动态库 | 占用空间少 <br> 更新库不需要重新编译应用

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
- 显示链接 (`*.dll`) - `运行时动态链接`
  - `LoadLibrary()` & `LoadLibraryEx()`
- 隐式链接 (`*.h` & `*.lib` & `*.dll`) - `加载时动态链接`
  - 必须链接导入库(`*.lib`)

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
### dll 位置搜索顺序

1. 应用程序文件夹
2. 当前文件夹
3. 系统Windows文件夹 (`GetSystemDirectory 函数返回系统Windows的路径`)
4. "Windows"文件夹 (`GetWindowsDirectory 函数返回文件夹Windows路径`)


### Tools

- dumpbin 
- lib
- Dependency Walker
