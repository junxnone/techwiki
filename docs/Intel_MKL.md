---
Title | Intel MKL
-- | --
Create Date | `2021-08-03T02:32:35Z`
Update Date | `2022-04-19T07:16:27Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/225)

---
## Reference
- [Spec](https://spec.oneapi.io/versions/latest/index.html)
- [oneMKL Interfaces](https://oneapi-src.github.io/oneMKL/index.html)
- [Intel® oneAPI Math Kernel Library Link Line Advisor](https://www.intel.com/content/www/us/en/developer/tools/oneapi/onemkl-link-line-advisor.html)
- [Get Started Guide](https://www.intel.com/content/www/us/en/develop/documentation/get-started-with-mkl-for-dpcpp/top.html)
- [Developer Reference C API](https://www.intel.com/content/www/us/en/develop/documentation/onemkl-developer-reference-c/top.html)

## Brief
- MKL - `Math Kernel Library`
- Intel-Optimized Math Library for Numerical Computing
- Functions
  - Linear algebra - 线性代数
    - [[BLAS]] - 基本线性代数
    - [[LAPACK]] - 高级线性代数
    - Sparse solvers
  - FFT - `fast Fourier transforms` - `1D/2D/3D`
  - RNG - `random number generator`
  - Summary Statics
  - data fitting
  - Vector Math
- **Language Support:** 
  - DPCPP - `DPCPP API`
  - CPP/C - `C API`
  - Fortran - `Fortran API`

## API
### BLAS
- Level 1 - `Vector - Vector 操作`
- Level 2 - `Matrix - Vector 操作`
- Level 3 - `Matrix - Matrix 操作`

#### Levle 1

fun | Formula | Description
-- | -- | --
asum | $result = \sum_{i=1}^{n}(|Re(x_i)| + |Im(x_i)|)$ | 计算实数元素之和或者复数实部和虚部之和


## UseCase
```
icc  app.obj -L${MKLROOT}/lib/intel64 -lmkl_intel_lp64-lmkl_intel_thread -lmkl_core
```
