---
Title | OpenMP SIMD
-- | --
Create Date | `2021-11-03T02:35:24Z`
Update Date | `2021-11-03T11:04:31Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/203)

---
# Reference
- [SIMD Directives](https://www.openmp.org/spec-html/5.0/openmpsu42.html)
- [openmp simd 扩展 - msvc](https://docs.microsoft.com/zh-cn/cpp/parallel/openmp/openmp-simd?view=msvc-160)


# Brief
- OpenMP 使用 SIMD 优化

```
#pragma omp simd [clause[ [,] clause] ... ] new-line 
   for-loops
```

Name | Description
-- | --
if([simd :] scalar-expression) 
safelen(length) 
simdlen(length) 
linear(list[ : linear-step]) 
aligned(list[ : alignment]) 
nontemporal(list) 
private(list) 
lastprivate([ lastprivate-modifier:] list) 
reduction([ reduction-modifier,]reduction-identifier : list) 
collapse(n) | 把多层循环拆解(n - 拆解层数)
order(concurrent)
