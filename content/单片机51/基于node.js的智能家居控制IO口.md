---
title: 基于node.js的智能家居web控制系统的I/O
author:
  - 潇寒
  - 潇寒paper龙
tags:
  - 单片机
  - 51
  - 虚拟串口
  - node.js
created: 2026-7-05
draft: false
---

## 基于node.js的智能家居web控制系统
用web通过虚拟串口控制单片机AT89C55

前端用原生HTML+CSS+Javascript实现，三个代码分开编写
css用现代的组件库
后端用node.js负责与串口通信

单片机的各模块功能分别封装为.h文件

---

### 模块一 ：门锁
P2.0分配给元件MOTOR-PWMSERVO的非电源端和非接地端

### 模块二：温湿度
P2.1接到元件DHT11的DATA脚

### 模块三：音响
P2.2接到SOUNDER

### 模块四：安防
P2.3接到元件HCSR04的TR脚（3脚）
P2.4接到元件HCSR04的ECHO脚（2脚）
P2.6通过电阻接到2N2222的基极，2N2222的发射极接地，2N2222的集电极接BUZZER的负极，BUZZER的正极接电源+5V并且接到HCSR04的VCC

### 模块五：地热
P2.5通过电阻接到2N1711的基极，2N1711的发射极接地，2N1711的集电极接LPLY1COILSPDT元件，LPLY1COILSPDT元件接到OVEN元件的一端

### 模块六：窗帘
一个L298电机驱动芯片
P0.0接到L298的5脚IN1
P0.1接到L298的7脚IN2
P0.2接到L298的10脚IN3
P0.3接到L298的12脚IN4
L298的OUT1(2脚)和OUT2（3脚）接电机1
L298的OUT3(13脚)和OUT4（14脚）接电机2

### 模块七：灯光
P1.0-P1.7分别分配给八个LED灯

---



