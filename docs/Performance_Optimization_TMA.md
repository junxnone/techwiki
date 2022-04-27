---
Title | Performance Optimization TMA
-- | --
Create Date | `2022-04-27T01:48:41Z`
Update Date | `2022-04-27T09:38:28Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/274)

---
## Reference
- [TMA_自顶向下的CPU架构性能瓶颈分析方法](https://zhuanlan.zhihu.com/p/60569271)
- [《A Top-Down Method for Performance Analysis and Counters Architecture》阅读笔记](https://andrewei1316.github.io/2020/12/20/top-down-performance-analysis/)
- [自顶向下的微架构分析方法 - Intel](https://www.intel.com/content/www/us/en/develop/documentation/vtune-cookbook-zh-cn/top/methodologies/top-down-microarchitecture-analysis-method.html)
2014 **TMA** [A Top-Down method for performance analysis and counters architecture.pdf](https://github.com/junxnone/linuxwiki/files/8559242/A.Top-Down.method.for.performance.analysis.and.counters.architecture.pdf)
- [Pipeline Slots](https://www.intel.com/content/www/us/en/develop/documentation/vtune-help/top/reference/cpu-metrics-reference/pipeline-slots.html)

## Brief
- TMA - `Top-Down Microarchitecture Analysis`
- **Retiring**: 正常退出的 μOps 比例
- **Bad Speculation**: Cancelled ( `Mispredicted branches`/`Incorrect data speculation`)
- **Front-End Bound**: front-end 导致的 pipeline slots 不能被充分使用
- **Back-End Bound**: back-end 导致的 pipeline slots 不能被充分使用

![image](https://user-images.githubusercontent.com/2216970/165234008-d2226b5f-9fee-4eb7-8b2a-2fa14a24ddc4.png)

## 相关名词
- **μOps**: `micro-ops/micro-operations` 微指令

### Pipeline Slots
- **Pipeline Slots**: 处理一个 μOps 需要的硬件资源
  - 对于每个 `CPU Core`, 在每个时钟周期, 有多个可用的 `Pipeline Slots`, 数量称为 `Pipeline Width`

40 Pipeline Slots = 4-wide CPU X 10 Clock cycles | Retiring(50%) = SlotsRetired/TotalSlots
-- | --
![image](https://user-images.githubusercontent.com/2216970/165475906-e72622c8-af6f-4f73-8982-a12051fde74e.png) | ![image](https://user-images.githubusercontent.com/2216970/165475920-9ef67a82-8bbb-4fc9-b090-8da041b85dd4.png)


