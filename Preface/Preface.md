[TOC]

# 序言

* 序言对本文档做了介绍。包含以下部分：
* 关于本文档
* 使用本文档
* 公约
* 拓展阅读
* 反馈

## 关于本文档

本手册描述了Armv8结构。该架构描述了Armv8-A的操作处理机（*Procession element*, PE），本手册还描述了：

* 两种执行状态，AArch64和AArch32。

* 指令集

  −    在AArch32状态，支持A32和T32两套指令集，并且兼容早期版本的Arm架构。

  −    在AArch64状态，支持A64指令集。

* 决定PE是如何工作的状态有两种，一种是当前的异常等级和安全状态，另一种是在AArch32状态中的PE模式。

* 异常模型(The Exception model)

* 交互处理模型(The interprocessing model)，支持AArch64状态和AArch32状态之间的转换

* 内存模型(The memory model)，定义了内存顺序(memory ordering)和内存管理

* 编程模型(The programmers’ model)，包括用于控制大多数PE和内存系统特性的系统寄存器接口，和提供状态信息

* 高级的单指令多数据(Single Instruction Multiple Data, SIMD)和浮点型指令，可以提供高性能：

  −    单精度，半精度和双精度浮点操作

  −    在双精度，单精度以及半精度浮点数据之间转换

  −    在所有的指令集中，支持整型，单精度浮点型和半精度浮点型矢量运算

  −    在A64指令集中，支持双精度浮点型矢量运算

* 安全模型（The security model），提供两种安全状态以支持安全应用程序

* 虚拟化模型（The virtualization model）

* 调试架构（The Debug architecture），提供软件调试功能（provides software access to debug features）

本手册在描述指令时会采用汇编语法，汇编语法会以文本的形式展现。然而，本手册除了介绍一些基本的汇编语言外，不会过多的介绍Arm汇编语言。为了高效使用 Arm 汇编语言，请阅读所使用的汇编程序随附的文档。

本手册分为如下几个部分：

**Part A**







