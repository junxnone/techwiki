---
Title | Library
-- | --
Create Date | `2021-12-22T06:00:12Z`
Update Date | `2022-01-05T02:02:49Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/237)

---
## Reference
- [windows中静态库lib和动态dll的区别及使用方法](https://blog.csdn.net/dxzysk/article/details/66477147)
- [什么是 DLL](https://docs.microsoft.com/zh-cn/troubleshoot/windows-client/deployment/dynamic-link-library)

## Brief
- 静态库/动态链接库/动态加载库
- Linux (`*.a` & `*.so`)
- Windows (`*.lib` & `*.dll`)

## Linux
- **Tools**
  - ldd

## Windows
- 静态库 (`*.lib`)  - 仅链接时使用
- 动态库 (`*.lib` & `*.dll`)
  -  **引入库文件 (`*.lib`)** - 包含 `*.dll` 文件导出的函数和变量的符号名, `*.dll` 文件中办好实际函数和数据
- **Tools**: 
  - dumpbin 
  - lib

Status/库 | 静态库(`*.lib`) | 动态库 (`*.lib` & `*.dll`)
-- | -- | --
**链接** | 复制到函数和数据到可执行文件 | 仅链接引入库(`*.lib`)
**发布** | 不需要发布 | 需要发布动态库
**运行** | 不依赖于静态库 |  需要加载动态库 (`*.dll`)


### 动态库
- 显示链接 (`*.dll`)
- 隐式链接 (`*.h` & `*.lib` & `*.dll`)

