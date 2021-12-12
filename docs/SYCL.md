---
Title | SYCL
-- | --
Create Date | `2021-07-29T01:50:29Z`
Update Date | `2021-12-12T03:36:31Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/194)

---
## Reference
- [SYCL](https://www.khronos.org/sycl/)
- [SYCL - Specification](https://www.khronos.org/registry/SYCL/specs/sycl-2020/html/sycl-2020.html#introduction)
- [SYCL - Reference](https://sycl.readthedocs.io/en/latest/)
- [sycl.tech](https://sycl.tech/learn/)
- [A Comparative Study of SYCL, OpenCL, and OpenMP](https://www.researchgate.net/publication/312964923_A_Comparative_Study_of_SYCL_OpenCL_and_OpenMP)
- [Investigation of the OpenCL SYCL Programming Model](https://static.epcc.ed.ac.uk/dissertations/hpc-msc/2013-2014/Investigation%20of%20the%20OpenCL%20SYCL%20Programming%20Model.pdf)


## Brief
- SYCL - High-Level C++ 抽象层 - 一个标准
- 可以使用 OpenCL backend，也可以用其他库作为后端 (CUDA/OpenMP/OpenCL+PTX/CUDA+PTX)
- [SYCL Concepts](/SYCL_Concepts)
- [SPIR](/SPIR)
- SYCL 标准的一些实现
  - [DPCPP - Intel](https://github.com/intel/llvm)
  - [ComputeCpp - codeplay](https://github.com/codeplaysoftware/computecpp-sdk)
  - [TriSYCL - Xilinx](https://github.com/triSYCL/triSYCL)
  - [hipSYCL - Heidelberg University](https://github.com/illuhad/hipSYCL)
  - neoSYCL - Tohoku
- 一些使用 SYCL 的库
  - Eigen (基于 ComputeCpp)


## SYCL 定位

![image](https://user-images.githubusercontent.com/2216970/127418990-8e05f4ee-c310-4648-b4e6-f7a3cc83fae1.png)

## SYCL 实现
- DPCPP - intel
- ComputeCpp - codeplay
- triSYCL - XILINX
- hipSYCL - AMD
- neoSYCL - Tomoku


![image](https://user-images.githubusercontent.com/2216970/127419004-037235d4-8a43-47b6-bf3f-73a1d81fea30.png)


## SYCL VS OpenCL

Name | Description
-- | --
SYCL | - High-Level<br> - 单一文件<br> - 编译为 SPIR
OpenCL | - Low-Level<br> - Host + Device Code


![image](https://user-images.githubusercontent.com/2216970/127421283-39437ea0-bc47-4736-8f23-4fde10aa56ec.png)


