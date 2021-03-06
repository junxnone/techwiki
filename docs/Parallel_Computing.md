---
Title | Parallel Computing
-- | --
Create Date | `2021-09-24T03:42:54Z`
Update Date | `2021-09-24T08:52:12Z`
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

- **Fetch** – get the next instruction from memory
- **Decode** – figure out what to do & read inputs
- **Execute** – perform the necessary operations
- **Commit** – write the results back to registers / memory

![Inkedchrome_k49UtilsYB_LI](https://user-images.githubusercontent.com/2216970/134641857-12563821-6c02-4628-986e-d656c8f76b82.jpg) | Pipeline
-- | --
![Inkedchrome_lKvXLJsrqG_LI](https://user-images.githubusercontent.com/2216970/134646854-ac0014f9-d3e9-4263-a6a2-a0c652f192b3.jpg) | 当后一条指令需要用到前一条指令的寄存器时会填充 `NOP` 指令, 以等到前一条指令 `commit`


### History of CPU

- 1970s 超级计算机用于科学计算
- 1990s 数据库/Web服务/交易
- 2004 CPU 频率升级到达技术瓶颈
- 2019 云计算


[Microprocessor Trend Data](https://github.com/karlrupp/microprocessor-trend-data) |
-- |
![image](https://user-images.githubusercontent.com/2216970/134624585-0f72cb55-a779-4615-ab14-3f5dfa8e3bf1.png)



