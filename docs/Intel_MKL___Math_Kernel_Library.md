---
Title | Intel MKL - Math Kernel Library
-- | --
Create Date | `2021-11-19T15:28:00Z`
Update Date | `2021-11-19T15:28:00Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/225)

---
## Reference
- []()

## Brief
- MKL - `Math Kernel Library`
- Intel-Optimized Math Library for Numerical Computing
- Functions
  - Linear algebra 
    - [BLAS](https://github.com/junxnone/tech-io/issues/1023) 
    - [LAPACK](https://github.com/junxnone/tech-io/issues/1024)
    - Sparse solvers
  - FFT - `fast Fourier transforms` - `1D/2D/3D`
  - RNG - `random number generator`
  - summary statics
  - data fitting
  - vector math

## UseCase
```
icc  app.obj -L${MKLROOT}/lib/intel64 -lmkl_intel_lp64-lmkl_intel_thread -lmkl_core
```
