---
Title | OpenMP
-- | --
Create Date | `2021-05-20T03:29:59Z`
Update Date | `2021-11-05T08:49:01Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/199)

---
## Reference
- [OpenMP API Specification](https://www.openmp.org/spec-html/5.1/openmp.html)
- [OpenMP Reference Guide](https://www.openmp.org/resources/refguides/)
- [OpenMP Compilers & Tools](https://www.openmp.org/resources/openmp-compilers-tools/)
- [OpenMP sample code](https://github.com/OpenMP/Examples/tree/main/sources)
- [OpenMP学习笔记](https://blog.csdn.net/qq_40379678/article/details/107788716)
- [并行计算 - 华东师范大学 ](http://math.ecnu.edu.cn/~jypan/Teaching/ParaComp/) 
  - [lect04_OpenMP01_C.pdf](https://github.com/junxnone/tech-io/files/6613360/lect04_OpenMP01_C.pdf)
  - [lect04_OpenMP02_C.pdf](https://github.com/junxnone/tech-io/files/6613361/lect04_OpenMP02_C.pdf)
  - [lect04_OpenMP03_C.pdf](https://github.com/junxnone/tech-io/files/6613363/lect04_OpenMP03_C.pdf)
- [OpenMP并行编程.pdf -  中科院计算机网络信息中心](https://github.com/junxnone/tech-io/files/6986206/OpenMP.pdf)
- [C/C++ openMP并发编程](https://blog.csdn.net/qq_30024069/article/details/93355022)
- [OpenMP Training video](https://www.youtube.com/watch?v=nE-xN4Bf8XI&list=PLLX-Q6B8xqZ8n8bwjGdzBJ25X2utwnoEG)
- [OpenMP Internal Control Variables](https://www.openmp.org/spec-html/5.0/openmpse13.html)
- [HPC.NRW OpenMP Online Tutorial](https://hpc-wiki.info/hpc/OpenMP_in_Small_Bites)
- [OpenMP Tutorial - Lawrence Livermore National Laboratory](https://hpc.llnl.gov/tuts/openMP/)


## Brief
- OpenMP 是一个写 `shared memory parallel` 应用的规范
- 规范定义的内容
  - Compiler Directives - 编译指令
  - Runtime routines - API
  - 环境变量
- 具体实现由编译器实现, 不同厂家的编译器对 OpenMP 的支持不一样
  - MSVC 目前只支持 2.0 & 部分 4.0 feature (SIMD)(`@20211105`)
  - ICC/GCC 目前支持 4.5 & 部分 5.x (`@20211105`)
- OpenMP采用fork-join（分叉-合并）并行执行模式
- 线程遇到并行结构时，就会创建由其自身及其它一些线程组成的线程组
  - 主线程
  - 从线程
- 默认并行线程数为CPU核数
- [OpenMP API](/OpenMP_API)
- [OpenMP - 绑核](/OpenMP_Bind_Core)
- [OpenMP SIMD](/OpenMP_SIMD)
- [OpenMP Offload](/OpenMP_Offload)
- [OpenMP ICV(Internal Control Variables)]()

## Shared Memory Model
- OpenMP 是为 多核/多处理器 共享内存的机器设计的
- 支持 UMA/NUMA - `Uniform Memory Access` / `Non-Uniform Memory Access`

UMA | NUMA
-- | --
![image](https://user-images.githubusercontent.com/2216970/140483477-716ad3cc-12a6-49f5-ad7a-08b364c39d9c.png) | ![image](https://user-images.githubusercontent.com/2216970/140483485-14c6cc24-5b70-486f-83ca-cb26f930357e.png)






## UseCase

- 头文件
```
include <omp.h>
```
- 格式
```
#pragma omp <编译关键字> [ 子句[ [,] 子句]…… ]
```

### 对变量的声明

Keyword | Description
-- | --
private | 其列出来的变量对于线程私有
firstprivate |  `private` + 对于线程局部存储的变量，其初值是进入并行区之前的值
lastprivate | `private` + 并行区里的值在最后会赋值给并行区前面的变量
default | 自定义一个并行区的默认的变量的作用范围
shared |其列出来的变量对于所有线程共享(**默认值**)
reduction | 对于各个线程私有的变量，在并行区结束时通过某种运算归一




### 常用方法

- for
```
#pragma omp parallel
#pragma omp for
```
```
#pragma omp parallel for
```
- sections
```
#pragma omp parallel sections
```
- single
- task

## History

- 1997 OpenMP 1.0 for FORTRAN
- 1998 OpenMP 1.0 for C and C++
- 1999 OpenMP 1.1 for FORTRAN
- 2000 OpenMP 2.0 for FORTRAN
- 2002 OpenMP 2.0 for C and C++
- 2005 OpenMP 2.5 now includes both programming languages.
- 05/2008 OpenMP 3.0
- 07/2011 OpenMP 3.1
- 07/2013 OpenMP 4.0
- 11/2015 OpenMP 4.5
- 11/2018 OpenMP 5.0


