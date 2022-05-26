---
Title | AVX Compiler
-- | --
Created @ | `2022-05-26T09:24:29Z`
Last Modify @| `2022-05-26T09:24:29Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/288)

---
## Reference
- [Accelerating Compute-Intensive Workloads with Intel® AVX-512](https://devblogs.microsoft.com/cppblog/accelerating-compute-intensive-workloads-with-intel-avx-512/) [[windows code](https://github.com/intel/Developer-Tools-Runtimes-Blogs)]

## C++ 文件编译
- gcc compiler the code
```
g++ example.cpp -std=c++17 -mavx512f -mavx2 -mfma -O
```
