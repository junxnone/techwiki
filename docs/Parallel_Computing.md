---
Title | Parallel Computing
-- | --
Create Date | `2021-09-24T03:42:54Z`
Update Date | `2021-09-24T07:45:35Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/166)

---
# Reference
- [Parallel Computer Architecture and Programming - CMU Course](http://www.cs.cmu.edu/afs/cs/academic/class/15418-s20/www/lectures/)
- [Microprocessor Trend Data](https://github.com/karlrupp/microprocessor-trend-data)

# Brief
- ILP - `instruction-level parallelism`
- CPI - `Cycles Per Instruction`
- `Fast` != `Efficient`
- 限制
  - 多处理器通信的消耗
  - 多处理器任务均衡



## `SuperComputer` VS `Cloud System`(Data Center)

VS | SuperComputers | Cloud System(Data Center Clusters)
-- | -- | --
目标应用 | Few, Big tasks | Many small tasks
硬件 | - 定制化<br>- 高可靠性<br>- 低延迟连接 | - 消费级<br>- 低成本<br>- 吞吐量优化连接
Run-Time System | - Minimal<br>- 静态调度 | - 高可靠性<br>- 动态调度
Application Programming | - Low-level, processor-centric model<br>- Programmer manages resources | - High level, data-centric model<br>- Let run-time system manage resources

## Hardware
- CPU
- GPU
- FPGA
- VPU

### CPU Execute Instruction

- 1. **Fetch** – get the next instruction from memory
- 2. **Decode** – figure out what to do & read inputs
- 3. **Execute** – perform the necessary operations
- 4. **Commit** – write the results back to registers / memory


### History of CPU

- 1970s 超级计算机用于科学计算
- 1990s 数据库/Web服务/交易
- 2004 CPU 频率升级到达技术瓶颈
- 2019 云计算


[Microprocessor Trend Data](https://github.com/karlrupp/microprocessor-trend-data) |
-- |
![image](https://user-images.githubusercontent.com/2216970/134624585-0f72cb55-a779-4615-ab14-3f5dfa8e3bf1.png)



