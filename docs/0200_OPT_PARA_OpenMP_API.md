---
Title | OPT PARA OpenMP API
-- | --
Created @ | `2021-08-07T03:56:52Z`
Last Modify @| `2022-12-22T03:48:34Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/200)

---
## Reference
- [OMP 函数](https://docs.microsoft.com/zh-cn/cpp/parallel/openmp/reference/openmp-functions?view=msvc-160)
- [OpenMP-API-Specification-5.0](https://www.openmp.org/wp-content/uploads/OpenMP-API-Specification-5.0.pdf)

## Brief
- API 分类
  - 环境设定获取
  - 锁定
  - 计时

## 环境变量获取

函数 | 描述
-- | --
omp_set_num_threads | 设置即将发生的并行区域中的线程数，除非由 num_threads 子句重写。
omp_get_num_threads | 返回并行区域中的线程数。
omp_get_max_threads | 返回一个整数，该整数等于或大于当在代码中没有定义 num_threads 的并行区域时可使用的线程数。
omp_get_thread_num | 返回线程团队内执行的线程的线程号。  ID [0, 1, 2, ...]
omp_get_num_procs | 返回调用函数时可用的处理器数。
omp_in_parallel | 如果从并行区域内调用，则返回非零值。
omp_set_dynamic | 指示可在即将推出的并行区域中使用的线程数进行调整。
omp_get_dynamic | 返回一个值，该值指示是否可以在运行时调整即将存在的并行区域中的可用线程数。
omp_set_nested | 启用嵌套并行度。
omp_get_nested | 返回一个值，该值指示是否启用嵌套并行度。

## 锁定

函数 | 描述
-- | --
omp_init_lock | 初始化简单锁。
omp_init_nest_lock | 初始化锁。
omp_destroy_lock | 取消锁。
omp_destroy_nest_lock | 取消 a.17 锁。
omp_set_lock | 阻止线程的执行，直到有可用锁为止。
omp_set_nest_lock | 阻止线程的执行，直到有可用锁为止。
omp_unset_lock | 释放锁。
omp_unset_nest_lock | 释放一个 a.17 锁。
omp_test_lock | 尝试设置锁，但不阻止线程的执行。
omp_test_nest_lock | 尝试设置 a.17 锁，但不会阻塞线程的执行。


## 计时

函数 | 描述
-- | --
omp_get_wtime | 返回一段时间内所用时间的值（以秒为单位）。
omp_get_wtick | 返回处理器时钟计时周期之间的秒数。

