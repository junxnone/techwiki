---
Title | SIMD
-- | --
Create Date | `2021-11-11T05:34:05Z`
Update Date | `2021-11-11T05:34:05Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/213)

---
## Reference
- [Intel Instruction Set](https://software.intel.com/sites/landingpage/IntrinsicsGuide)
- [AVX - baike](https://baike.baidu.com/item/AVX%E6%8C%87%E4%BB%A4%E9%9B%86/8485825?fr=aladdin)
- [AVX - wikipedia](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions)
- [AVX2 - wikipedia](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#AVX2)
- [AVX512 - wikipedia](https://en.wikipedia.org/wiki/AVX-512)

## Brief
- SIMD - `Single Instruction Multiple Data`
- [SIMD 原理](/SIMD_原理) 


## 各种指令集

- MMX - `Multi-Media Extension`
- SSE - `Streaming SIMD Extensions`
- SSE2
- SSE3
- SSE4
- AVX - `Advanced Vector Extensions`
- AVX2
  - AVX2 指令集将大多数整数命令操作扩展到 256 位，并引入了熔合乘法累积（FMA）运算
- [AVX512](https://github.com/junxnone/tech-io/issues/1019)
  - AVX-512 则使用新的 EVEX 前缀编码将 AVX 指令进一步扩展到 512 位


---
![image](https://user-images.githubusercontent.com/2216970/127825959-17d9ada7-b5aa-48f9-9d9c-ba2f3a71c798.png)

## History
- 1996 MMX Pentium
- 1999 SSE Pentium III
- 2001 SSE2 Pentium 4
- 2004 SSE3 Pentium 4EPrescott
- 2006 SSSE3 Core Duo
- 2007 SSE4 Core2 Duo Penryn
- 20008 AVX Sandy Bridge
- 2013 AVX2 Haswell
- 2013 AVX512 Knights Landing


## Tips
- 可以使用 `lscpu|grep avx` 查看支持的 指令集


```
$ lscpu
Architecture:          x86_64
CPU op-mode(s):        32-bit, 64-bit
Byte Order:            Little Endian
CPU(s):                40
On-line CPU(s) list:   0-39
Thread(s) per core:    2
Core(s) per socket:    10
Socket(s):             2
NUMA node(s):          2
Vendor ID:             GenuineIntel
CPU family:            6
Model:                 85
Model name:            Intel(R) Xeon(R) Silver 4114 CPU @ 2.20GHz
Stepping:              4
CPU MHz:               1199.945
CPU max MHz:           3000.0000
CPU min MHz:           800.0000
BogoMIPS:              4391.16
Virtualization:        VT-x
L1d cache:             32K
L1i cache:             32K
L2 cache:              1024K
L3 cache:              14080K
NUMA node0 CPU(s):     0-9,20-29
NUMA node1 CPU(s):     10-19,30-39
Flags:                 fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx pdpe1gb rdtscp lm constant_tsc art arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf pni pclmulqdq dtes64 ds_cpl vmx smx est tm2 ssse3 sdbg fma cx16 xtpr pdcm pcid dca sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm abm 3dnowprefetch epb invpcid_single intel_pt ssbd ibrs ibpb stibp kaiser tpr_shadow vnmi flexpriority ept vpid fsgsbase tsc_adjust bmi1 hle avx2 smep bmi2 erms invpcid rtm cqm mpx avx512f rdseed adx smap clflushopt clwb avx512cd xsaveopt xsavec xgetbv1 cqm_llc cqm_occup_llc cqm_mbm_total cqm_mbm_local dtherm ida arat pln pts hwp hwp_act_window hwp_epp hwp_pkg_req pku flush_l1d
```
> 支持 avx avx2 avx512f avx512cd 的CPU
