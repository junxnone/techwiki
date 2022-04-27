---
Title | Cache Line Optimization
-- | --
Create Date | `2022-04-27T02:59:04Z`
Update Date | `2022-04-27T03:07:47Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/275)

---
## Reference
- [CPU Cache Optimization](https://zzqcn.github.io/perf/cpu_cache.html)


## Brief
- [[Cache]]
- Optimization
  - 剔除结构体中的无用变量

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

### 变量排列顺序
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


