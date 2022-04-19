---
Title | Intel MKL
-- | --
Create Date | `2021-08-03T02:32:35Z`
Update Date | `2022-04-19T06:49:08Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/225)

---
## Reference
- [Spec](https://spec.oneapi.io/versions/latest/index.html)
- [oneMKL Interfaces](https://oneapi-src.github.io/oneMKL/index.html)
- [Intel® oneAPI Math Kernel Library Link Line Advisor](https://www.intel.com/content/www/us/en/developer/tools/oneapi/onemkl-link-line-advisor.html)


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


## UseCase
```
icc  app.obj -L${MKLROOT}/lib/intel64 -lmkl_intel_lp64-lmkl_intel_thread -lmkl_core
```
