---
Title | OPT PARA OpenMP BindCore
-- | --
Created @ | `2021-08-09T10:13:27Z`
Last Modify @| `2022-12-22T03:50:27Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/201)

---
# 绑定CPU核

## Reference
- [OpenMP Affinity - ](https://www.openmp.org/wp-content/uploads/openmp-examples-4.5.0.pdf)
- [控制 OpenMP 4.0 中的线程关联性](https://docs.oracle.com/cd/E57201_01/html/E58572/gpdpg.html#scrolltoc)
- [影响服务器内存性能的硬件知识](https://decodezp.github.io/2018/12/13/quickwords5-server-memory/)
- [What is Scheduling in OpenMP](https://610yilingliu.github.io/2020/07/15/ScheduleinOpenMP/)
- [OpenMP topic: Affinity](https://pages.tacc.utexas.edu/~eijkhout/pcse/html/omp-affinity.html)

## Brief
- OMP_PLACES - threads/cores/sockets - 指定 `Location Units`
- proc_bind - `绑定方式`  - `OMP_PROC_BIND`
- schedule - `调度方式`

## OMP_PLACES
- OMP_PLACES :  threads/cores/sockets

Grammar | ![image](https://user-images.githubusercontent.com/2216970/129444306-20b327e5-dd67-445e-8cfd-5de05d41e105.png)
-- | --

```
setenv OMP_PLACES threads 
setenv OMP_PLACES "threads(4)" 
setenv OMP_PLACES "{0,1,2,3},{4,5,6,7},{8,9,10,11},{12,13,14,15}" 
setenv OMP_PLACES "{0:4},{4:4},{8:4},{12:4}" 
setenv OMP_PLACES "{0:4}:4:4"
```
## proc_bind

```
#pragma omp parallel proc_bind(master | close | spread) 
```

Mode | Description
-- | --
master | 子线程分配到主线程 Core
close | 
spreed | 

### spread
- **Examples CPU** - 2x Socket/4x Core/`p0,p1,...,p7`
- **4x threads < 8x Core**
  - master_thread@p0 ==> t0 @ p0,p1/t1@ p2,p3/t2@p4,p5/t3@p6,p7
  - master_thread@p2 ==> t0 @ p2,p3/t1@ p4,p5/t2@p6,p7/t3@p0,p1
- **T threads > 8x Core**
  - T/8@p0, 2st-T/8@p1, 3rd-T/8@p2, ... (0,1@p0/2,3@p1,...14,15@p7)



## schedule
```
#pragma omp parallel for schedule(mode [, chunk_size])
```

Mode | Description
-- | --
static | 静态均匀分配 每 chunk_size 分配到一个 Core
dynamic | 运行时 动态调度，Core 运行完  chunk_size xTask 后去领取 chunk_size x Task
guided | chunk_size 逐渐减小
runtime | 运行时根据 `OMP_SCHEDULE` 环境变量决定调用方法<br> `export OMP_SCHEDULE=“DYNAMIC, 4”`
auto | 


## UseCase


- `#pragma omp parallel for schedule(static, 3)`

20 Tasks<br> `@Threads > 7` |![image](https://user-images.githubusercontent.com/2216970/129443095-1706f6d0-2ae5-45d5-9da4-42c51b3d06d1.png)
-- | --
**20 Tasks <br>`@4 Threads`** | ![image](https://user-images.githubusercontent.com/2216970/129443182-27933d85-65ea-4af0-949a-d2ffe021d132.png)


## Intel OMP
- thread
- tile
- core
- group
```
KMP_AFFINITY=[<modifier>,...]<type>[,<permute>][,<offset>]
```

```
// Force the executing thread to execute on logical CPU i
// Returns 1 on success, 0 on failure.
int forceAffinity(int i)
{
kmp_affinity_mask_t mask;

kmp_create_affinity_mask(&mask); 
kmp_set_affinity_mask_proc(i, &mask); 
    
return (kmp_set_affinity(&mask) == 0); 
}
```
