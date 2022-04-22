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

**Part A**		介绍了Armv8-A架构，并对AArch64和AArch32的执行状态做了综述。

**Part B**		描述了AArch64执行状态下的应用层视图，该视图从EL0而来。它描述了编程者模型(programmers’ model)和内存模型的应用层视图。

**Part C**		描述了在AArch64执行状态下可用的A64指令集。除对每一条指令集的介绍外，也介绍了一种在无特权情况下执行指令的情况，即在EL0状态下执行指令，并介绍了其精确的效果(precise effects)，包括使用中的限制和在更高级别的异常等级中指令效果的不同。

**Part D**		描述了在AArch64执行状态下的系统层视图。包括详细介绍了系统寄存器(其中大多数无法从EL0下访问)，以及编程者模型(programmers’ model)与内存模型下的系统层视图。这部分还介绍了自托管式(self-hosted debug)调试。

**Part E**		描述了在AArch32执行状态下的应用层视图，该视图从EL0而来。它描述了编程者模型(programmers’ model)和内存模型的应用层视图。

**———— Note ————————**

在AArch32状态下，在EL0下执行就是在用户模式下执行

**———————————————**

**Part F**		介绍了在AArch32执行状态下可用的T32和A32指令集。这些指令集是可以向后兼容早期版本的Arm架构的。本部分描述了在用户模式下，执行每一条指令所产生的precise effects，也被描述为*unprivileged* execution or execution at EL0，也介绍了使用中的限制和在更高级别的异常等级中指令效果的不同。这些信息在生成Arm机器代码时，对创造者和编译器的用户，汇编者和其他程序至关重要。(This information is of primary importance to authors and users of compilers, assemblers, and other programs that generate Arm machine code)

**———— Note ————————**

用户模式是软件执行无特权的唯一模式

**———————————————**

**Part G**		介绍了在AArch32执行状态下的系统层视图，这通常是可以和早期版本的Arm架构兼容的。这部分详细介绍了系统寄存器(其中大多数无法从EL0下访问)，和与这些寄存器的指令接口。本部分同样介绍了编程者模型和内存模型在系统级层面上的视图

**Part I**		描述未与处理机(PE)紧密耦合的体系结构的附加特性，因此，它们可以通过与内存映射的接口进行访问。其中一些特性是可选的。

**Part J**		提供了描述Armv8体系结构的各种特性的伪代码。

**Part K, 附录**		提供额外的信息。一些附录提供的信息不属于Armv8架构需求的一部分。每个附录的封面页都显示了其状态。

**词汇表**		定义在本文档中使用的具有特殊含义的术语。

**———— Note ————————**

在微电子行业中普遍理解的术语不包括在术语表中

**———————————————**







