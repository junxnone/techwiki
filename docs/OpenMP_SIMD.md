---
Title | OpenMP SIMD
-- | --
Create Date | `2021-11-03T02:35:24Z`
Update Date | `2021-11-03T02:53:52Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/203)

---

# Reference
- [SIMD Directives](https://www.openmp.org/spec-html/5.0/openmpsu42.html)

# Brief


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
collapse(n) 
order(concurrent)
