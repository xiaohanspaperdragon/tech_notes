---
title: ��Ƭ�����a
---
![[Pasted image 20260701141004.png]]
### **TCON（Timer/Counter Control Register�?* 定时控制寄存器各位英文全称及含义�?
| 位名�?| 英文全称 | 中文含义 |
|--------|---------|----------|
| **TF1** | **Timer 1 Overflow Flag** | 定时�?溢出标志 |
| **TR1** | **Timer 1 Run Control** | 定时�?运行控制 |
| **TF0** | **Timer 0 Overflow Flag** | 定时�?溢出标志 |
| **TR0** | **Timer 0 Run Control** | 定时�?运行控制 |
| **IE1** | **Interrupt 1 Edge Flag** | 外部中断1触发标志 |
| **IT1** | **Interrupt 1 Trigger Mode** | 外部中断1触发方式选择 |
| **IE0** | **Interrupt 0 Edge Flag** | 外部中断0触发标志 |
| **IT0** | **Interrupt 0 Trigger Mode** | 外部中断0触发方式选择 |

---

### **IE（Interrupt Enable）中断允许控制寄存器**各位的英文全称及含义�?
| 位序 | 位地址 | 位名�?| 英文全称 | 中文含义 |
|------|--------|--------|---------|----------|
| �? | AFH | **EA** | **Enable All** | 总中断允许位 |
| �? | AEH | �?| (Reserved) | 保留位（未用�?|
| �? | ADH | �?| (Reserved) | 保留位（未用�?|
| �? | ACH | **ES** | **Enable Serial** | 串行口中断允许位 |
| �? | ABH | **ET1** | **Enable Timer 1** | 定时�?中断允许�?|
| �? | AAH | **EX1** | **Enable External 1** | 外部中断1允许�?|
| �? | A9H | **ET0** | **Enable Timer 0** | 定时�?中断允许�?|
| �? | A8H | **EX0** | **Enable External 0** | 外部中断0允许�?|

---


### **IP（Interrupt Priority）中断优先级控制寄存�?* 
**IP = Interrupt Priority Register**（中断优先级控制寄存器）

| 位序 | 位地址 | 位名�?| 英文全称 | 中文含义 |
|------|--------|--------|---------|----------|
| �? | BFH | �?| (Reserved) | 保留位（未用�?|
| �? | BEH | �?| (Reserved) | 保留位（未用�?|
| �? | BDH | �?| (Reserved) | 保留位（未用�?|
| �? | BCH | **PS** | **Priority Serial** | 串行口中断优先级控制 |
| �? | BBH | **PT1** | **Priority Timer 1** | 定时�?中断优先级控�?|
| �? | BAH | **PX1** | **Priority External 1** | 外部中断1优先级控�?|
| �? | B9H | **PT0** | **Priority Timer 0** | 定时�?中断优先级控�?|
| �? | B8H | **PX0** | **Priority External 0** | 外部中断0优先级控�?|

---

### **TMOD = Timer/Counter Mode Register**（定时器/计数器模式控制寄存器�?
| 位序 | 位名�?| 英文全称 | 中文含义 |
|------|--------|---------|----------|
| �? | **GATE1** | **Gate Control 1** | 定时�?门控�?|
| �? | **C/T1** | **Counter/Timer 1** | 定时�?计数/定时模式选择 |
| �? | **M11** | **Mode 1 bit 1** | 定时�?模式选择�? |
| �? | **M10** | **Mode 1 bit 0** | 定时�?模式选择�? |
| �? | **GATE0** | **Gate Control 0** | 定时�?门控�?|
| �? | **C/T0** | **Counter/Timer 0** | 定时�?计数/定时模式选择 |
| �? | **M01** | **Mode 0 bit 1** | 定时�?模式选择�? |
| �? | **M00** | **Mode 0 bit 0** | 定时�?模式选择�? |

---

### `Tcy` 的英文全称是 **`Tcy = Machine Cycle`**，即 **机器周期**�?
---

### `interrupt` —�?最核心的关键字

 基本语法
```c
void 函数�?) interrupt 中断�?{
    // 中断服务代码
}
```

 中断号对照表

| 中断�?   | 中断�?  | 中断向量地址 |
| ------ | ----- | ------ |
| 外部中断 0 | **0** | 0003H  |
| 定时�?0  | **1** | 000BH  |
| 外部中断 1 | **2** | 0013H  |
| 定时�?1  | **3** | 001BH  |
| 串行�?   | **4** | 0023H  |

---

### **SCON** �?**Serial Port Control Register**（串行口控制寄存器）的缩写，用于设定串行口的工作方式、接�?发送控制以及状态标志�?
其各位英文全称及功能如下表所示（地址�?`0x98`，可位寻址）：

| 位序 | 位地址 | 位符�?| 英文全称 | 中文含义 |
| :--- | :--- | :--- | :--- | :--- |
| **�?7** | `9FH` | **SM0** | **Serial Port Mode Select bit 0** | 串行口工作方式选择�?0 |
| **�?6** | `9EH` | **SM1** | **Serial Port Mode Select bit 1** | 串行口工作方式选择�?1 |
| **�?5** | `9DH` | **SM2** | **Serial Port Mode Select bit 2 / Multiprocessor Communication Enable** | 多机通信控制�?/ 方式选择�?2 |
| **�?4** | `9CH` | **REN** | **Receiver Enable** | 接收允许控制�?|
| **�?3** | `9BH` | **TB8** | **Transmitter Bit 8** | 发送数据的�?9 位（方式 2/3 中） |
| **�?2** | `9AH` | **RB8** | **Receiver Bit 8** | 接收数据的第 9 位（方式 2/3 中） |
| **�?1** | `99H` | **TI** | **Transmit Interrupt Flag** | 发送中断标�?|
| **�?0** | `98H` | **RI** | **Receive Interrupt Flag** | 接收中断标志 |


![[Pasted image 20260701155711.png]]


---

![[Pasted image 20260701185929.png]]


---

![[Pasted image 20260701211439.png]]
