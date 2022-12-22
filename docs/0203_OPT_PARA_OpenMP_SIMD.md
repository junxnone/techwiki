---
Title | OPT PARA OpenMP SIMD
-- | --
Created @ | `2021-11-03T02:35:24Z`
Last Modify @| `2022-12-22T03:50:46Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/203)

---
# Reference
- [SIMD Directives](https://www.openmp.org/spec-html/5.0/openmpsu42.html)
- [openmp simd 扩展 - msvc](https://docs.microsoft.com/zh-cn/cpp/parallel/openmp/openmp-simd?view=msvc-160)
- [Introduction to the SIMD Data Layout Templates](https://www.intel.com/content/www/us/en/develop/documentation/cpp-compiler-developer-guide-and-reference/top/compiler-reference/libraries/introduction-to-the-simd-data-layout-templates.html)

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
