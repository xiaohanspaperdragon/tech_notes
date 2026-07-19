---
title: Lecture 6：函数极限的性质
tags:
  - 数学
  - 极限
categories: 
date: 2024-02-28
---
---
## 6.1 极限性质
### 6.1.1 有界性
**数列**
+ $\text{如果数列 }\left\{x_n\right\}\text{收敛,那么数列 }\left\{x_n\right\}\text{一定有界}$
+ 收敛数列必有界；
+ **有界数列未必收敛**；
	+ 例子：$(-1)^n$

**函数**
+ $\text{若 }\lim_{x\to x_0}f(x)\text{ 存在,则 }f(x)\text{ 在 }x_0\text{ 某去心邻域}$ 有界（即局部有界）；
+ **极限是函数的一个局部性态**；
+ 但局部有界时，不一定有极限；
	+ 例子： $\lim_{x\to0}\sin\frac1x$，其在趋向于 0 时一直局部震荡；

### 6.1.2 保号性
 **数列**
+ 设 $\lim_{n\to\infty}x_n=A$：
	+ 1.  $\text{如果 }A\text{>0(或 }A<0\text{),则存在 }N>0,\text{ 当 }n>N\text{ 时},x_n>0\text{(或 }x_n<0)$；
		+ 即：当 N 大到一定程度时，一定会有数列的项和 A 保持一样的正负号 -> 保号性；
	+ 2.  $\text{如果存在 }N>0,\text{ 当 }n>N\text{ 时,}x_n\geq0\text{(或 }x_n\leq0\text{ 则 }A\geq0\text{(或 }A\leq0)$；
		+ 注意这里是大于等于符号； 
		+ $\mathrm{X_n\geqslant0\longrightarrow A\geqslant0}$
		+ 但只是大于时，不能推出 A 也是大于 0；
		+ $\mathrm{X_{n>0}\longrightarrow×\longrightarrow A>0}$
 
**函数**
+ 设 $\lim_{x\to x_0}f(x)=A$
	+ 1. 如果 $A>0$ (或 $A<0)$,则存在 $\delta>0$,当 $x\in U(x_0,\delta)$ 时，$f(x)>\mathbf{0}$ (或 $f(x)<\mathbf{0})\:.$ 
	+ 2. $\text{如果存在 }\delta>\mathbf{0},\text{ 当 }x\in U(x_0,\delta)\text{ 时, }f(x)\geq0$，$(\text{或 }f(x)\leq0\text{),那么 }A\geq0\text{(或 }A\leq0)$

### 6.1.3 补充：选择题之排除法的解题思路
**什么时候用排除法**
+ 解高等数学的题目时，出现一般函数时可以使用排除法；

**如何用排除法**
+ 当出现抽象的 $f(x)$ 函数时，可以考虑待一个具体函数进去，利用这个具体函数，判断每个选项是否正确；

## 6.2 极限与无穷小的关系
**关系**：$\lim f(x)=A\Leftrightarrow f(x)=A+\alpha(x)\quad\text{其中}\quad\lim\alpha(x)=0$；
+ $f(x)$ 以 A 为极限的充要条件 -> $f(x)$ 等于 A 加上无穷小；