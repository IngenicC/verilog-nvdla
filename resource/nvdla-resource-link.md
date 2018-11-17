【NVDLA学习笔记】参考资料汇总
-------------------------------

## 0. 版本记录


|日期       | 描述    | 
|-----|-----|
|2018-11-17  | 初版，汇总nvdla相关资源 |


## 1. 官方在线文档

http://nvdla.org

文档采用`reStructuredText`格式，使用`Sphinx`转为html格式。源码仿真github上。

主要分为以下几个类别：

### 1.1 开源

- http://nvdla.org/license.html
协议

- http://nvdla.org/updates.html
更新

### 1.2 简介

- http://nvdla.org/primer.html 

软硬件基本介绍，给出了NVDLA在不同配置下的面积和性能参考数据。提供了一些深度学习的参考链接。

- http://nvdla.org/glossary.html

缩写词语表

### 1.3 IP集成

注意v1和v2的区别。

- http://nvdla.org/hw/v1/integration_guide.html

集成文档：接口信号，环境搭建，仿真环境，综合环境

- http://nvdla.org/hw/v2/environment_setup_guide.html

使用`tmake`构建环境的命令介绍

- http://nvdla.org/hw/v2/verif_guide.html

NVDLA Verification Suite User Guide ：基于uvm的验证环境文档


### 1.4 硬件设计

注意v1和v2的区别。

- http://nvdla.org/hw/v1/hwarch.html

Hardware Architectural Specification：介绍硬件架构设计，模块划分，接口信号时序图，以及配置寄存器列表。

- http://nvdla.org/hw/v1/ias/unit_description.html

各个子模块的详细设计文档。

- http://nvdla.org/hw/format.html

In-memory data formats：详细介绍数据在DDR中的存储格式，包括pixel data，feature map，weight，bias/prelu/bn/ew等不同数据类型。针对weight压缩，winograd卷积有单独介绍。存储格式与硬件运算单元密切相关，要参考对应的硬件设计。

- http://nvdla.org/hw/v1/ias/precision.html

数据处理精度：介绍各个模块的数据处理功能，以及对应的硬件位宽(bit数)，给出了数据流位宽精度图。

- http://nvdla.org/hw/v1/ias/lut-programming.html

介绍LUT配置方法，实现非线性函数功能：Sigmoid/TanH/LRN

### 1.5 硬件配置

- http://nvdla.org/hw/v1/hwarch.html

配置寄存器列表。注意v1和v2的区别，实际寄存器列表是根据硬件配置生成的，源码基于`hw/spec/manual/*.rdl`，生成结果在`/outdir/nv_small/spec/`。

- http://nvdla.org/hw/v1/ias/programming_guide.html

各个子模块的软件配置介绍。可以参考`sw/kmd/firmware`对应代码。

- http://nvdla.org/hw/v2/scalability.html

Scalability parameters and ConfigROM

### 1.6 软件文档

- http://nvdla.org/sw/contents.html

软件文档简介

- http://nvdla.org/sw/compilation_tool.html

parser和compiler简介

- http://nvdla.org/sw/runtime_environment.html

Runtime environment，API接口函数

- http://nvdla.org/sw/test_application.html

参考测试程序简介


### 1.7 Virtual platform

- http://nvdla.org/vp.html

> The NVDLA virtual platform provides a register-accurate system on which software can be quickly developed and debugged. The virtual platform is based on GreenSocs QBOX, a solution for co-simulation with QEMU and SystemC. Fig. 89 below shows the top level diagram of the NVDLA virtual simulator. A QEMU emulator of ARMv8 ‘virt’ SoC board is included to provide high performance CPU emulation and generic devices. The emulator is wrapped inside a standard SystemC module with a set of TLM-2.0 interfaces to interact with other SystemC modules.

- http://nvdla.org/vp_fpga.html

> Virtual Platform (1. Overview) can run on Amazon Web Services (AWS) FPGA platform


## 2. NVDLA项目github地址

https://github.com/nvdla

|repo     | description     | 
|----------|----------------|
|doc  | 在线文档(源文件) |
|hw  | rtl，验证环境，综合环境 |
|sw  | 参考软件(KMD+UMD)  |
|vp  | 虚拟平台(基于QBOX，QEMU+SystemC) |


## 3. 其他参考资源

### 3.1 OpenDLA 

https://github.com/opendla

包括nvdla代码的阅读笔记，框图(visio格式)。这些资料发布于2017年，针对nvdlav1版本。

### 3.2 Sifive nvidia-dla-blocks

https://github.com/sifive/nvidia-dla-blocks

关注RISC-V与NVDLA的结合。

### 3.3 nvdla_compiler

https://github.com/icubecorp/nvdla_compiler

官方的compiler没有开源，这是一个开源版本的实现，完成从Caffe网络模型到loadable文件格式的转换。

### 3.4 JunningWu的学习笔记

https://github.com/JunningWu/Learning-NVDLA-Notes


### 3.5  基于Chisel的NVDLA实现

https://github.com/redpanda3/soDLA

## 4. 微信公众号文章 

-【矽说】黄教主的开源NVDLA，“核”爆还是“核”平？ 

https://dwz.cn/imtjB0fP

-【StarryHeavensAbove】从Nvidia开源深度学习加速器说起 

https://dwz.cn/XXK57WX0

-【子棐之GPGPU】入门NVDLA  

上篇：https://dwz.cn/02yrq0I5

下篇：https://dwz.cn/PIG1h5Xw


