---
Title | Cache Line Optimization
-- | --
Create Date | `2022-04-27T02:59:04Z`
Update Date | `2022-04-27T05:40:02Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/275)

---
## Reference
- [CPU Cache Optimization](https://zzqcn.github.io/perf/cpu_cache.html) [[code](https://github.com/zzqcn/storage/tree/main/code/c/cache_opt)]
- [伪共享（False Sharing）](https://zhuanlan.zhihu.com/p/55917869)


## Brief
- [[Cache]]
- 结构体定义导致的每次 Cache 读取效率低
  - 结构体中包含无用变量
  - 结构体中的数据类型混排对齐
  - 数据行列访问
- **False Sharing**: 多个线程访问同一 `cache line` 的不同数据


## Optimization 
### 无用变量
- 结构体中包含无用变量，导致读取到的有用数据减少，需要更多的读取时间

```
struct DATA1
{
    int a;
    int b;
    int c;
    int d;
};

struct DATA2
{
    int a;
    int b;
};
```

Define | 排列
-- | --
Data1 | ![image](https://user-images.githubusercontent.com/2216970/165431054-a23459e3-f278-4ff8-a14c-cda0587790ff.png)
Data2 | ![image](https://user-images.githubusercontent.com/2216970/165431060-4206bb0b-3b15-4cda-8df5-0e658f90fcb4.png)

### 数据类型混排对齐
- 数据类型对齐导致的空间浪费，导致需要读取更多次数

```
struct DATA3
{
    char a;
    int b;
    char c;
};
struct DATA4
{
    int b;
    char a;
    char c;
};
```


Define | 排列
-- | --
Data3 | ![image](https://user-images.githubusercontent.com/2216970/165431251-4c3ae17d-b3c3-4635-b7d2-cec6292a81dc.png)
Data4 | ![image](https://user-images.githubusercontent.com/2216970/165431256-d95e1ad9-61d9-44e4-87a7-697eee6f8d53.png)


### 数据行列访问
- 内存以行存储数据, 按行访问数据，每次 Cache 读取能够取到更多有效数据

```
// 按列访问
char * p;
p = new char[SIZE];
for (long x=0; x<sRowSize; x++) {
    for (long y=0; y<nbRows; y++) {
        p[x+y*sRowSize]++;
    }
}
```
```
// 按行访问
char * p;
p = new char[SIZE];
for (long y=0; y<nbRows; y++) {
    for (long x=0; x<sRowSize; x++) {
        p[x+y*sRowSize]++;
    }
}
```

Mode | 按列访问 | 按行访问
-- | -- | --
Cache Line 读取区域 | <img width=200 src="https://user-images.githubusercontent.com/2216970/165432374-f045fb72-6d56-4b93-be94-b4f8493d0ca7.png"> | <img width=200 src="https://user-images.githubusercontent.com/2216970/165432478-0e33ef14-8511-4c15-a2cb-7f1600210b34.png">


### False Sharing

![image](https://user-images.githubusercontent.com/2216970/146132953-0c21c3c2-18c1-4041-a452-0ed3f7c148a3.png)

