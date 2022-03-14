# PA1

## 导言

> 指导学生实现一个经过简化但功能完备的x86/mips32/riscv32(64)模拟器NEMU(NJU EMUlator), 最终在NEMU上运行游戏"仙剑奇侠传", 来让学生探究"程序在计算机上运行"的基本原理.

本课的目标在于

1. 实现一个功能完备的操作系统
2. 遵从某种规范——**指令集体系结构（ISA）**

ISA的概念比较抽象，wiki的定义如下

> In [computer science](https://en.wikipedia.org/wiki/Computer_science), an **instruction set architecture** (**ISA**), also called **[computer architecture](https://en.wikipedia.org/wiki/Computer_architecture),** is an [abstract model](https://en.wikipedia.org/wiki/Abstract_model) of a [computer](https://en.wikipedia.org/wiki/Computer). A device that executes instructions described by that ISA, such as a [central processing unit](https://en.wikipedia.org/wiki/Central_processing_unit) (CPU), is called an *implementation*.

可见ISA规定了计算机该实现什么功能

计组知识告诉我们，计算机实现功能的核心硬件cpu，是依靠指令工作的，一系列的指令的集合就是指令集。一个ISA中可能包含了多个指令集，且ISA描述了CPU应该支持的每条指令是做什么事的，即指令的功能。

另一个比较容易混淆的概念是**微体系结构（Micro-Architecture）**，它是由芯片制造厂商设计的，它规定了计算机的硬件该怎样实现ISA中规定的功能，微体系结构必须能够实现ISA规定的功能，同一种ISA可以有不同的计算机组成。

通过一张图表，我们可以清晰地看见计算机自顶向下从软件到硬件地架构，当然，值得注意的一点是，ISA与微体系结构都仅仅是抽象的规范

|       应用       |
| :--------------: |
| 高级语言程序代码 |
|  编译器/汇编器   |
|     操作系统     |
|       ISA        |
|    微体系结构    |
|       电路       |

