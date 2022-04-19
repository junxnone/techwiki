---
Title | Intel MKL
-- | --
Create Date | `2021-08-03T02:32:35Z`
Update Date | `2022-04-19T05:11:15Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/225)

---
## Reference
- []()

## Brief
- MKL - `Math Kernel Library`
- Intel-Optimized Math Library for Numerical Computing
- Functions
  - Linear algebra - 线性代数
    - [BLAS](https://github.com/junxnone/tech-io/issues/1023) - 基本线性代数
    - [LAPACK](https://github.com/junxnone/tech-io/issues/1024) - 高级线性代数
    - Sparse solvers
  - FFT - `fast Fourier transforms` - `1D/2D/3D`
  - RNG - `random number generator`
  - Summary Statics
  - data fitting
  - Vector Math

## UseCase
```
icc  app.obj -L${MKLROOT}/lib/intel64 -lmkl_intel_lp64-lmkl_intel_thread -lmkl_core
```
