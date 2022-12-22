---
Title | OPT PARA OpenMP Directives
-- | --
Created @ | `2021-11-16T03:37:52Z`
Last Modify @| `2022-12-22T03:51:46Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/218)

---
## Reference
- [OpenMP spec 5.0](https://www.openmp.org/spec-html/5.0/openmpch2.html#x30-290002)

## Brief
- loop
- offload 相关
- teams
- simd



### Format
- 使用 `#pragma omp` 开头

```
#pragma omp directive-name [clause[ [,] clause] ... ] new-line
```

### 常用编译指令


Name | Description
-- | --
parallel
for 
teams
simd
target
distribute
critical


