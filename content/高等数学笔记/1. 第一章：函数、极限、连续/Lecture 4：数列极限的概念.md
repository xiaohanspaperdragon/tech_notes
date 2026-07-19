---
title: Lecture 4：极限基础
tags:
  - 数学
  - 极限
categories: 
date: 2024-02-28
---
---
## 4.1 极限的基本概念
+ 主要是两种
	+ 1. 数列极限；
	+ 2. 函数极限；

### 4.1.1 数列极限 
##### **定义**： #数列极限
> <font color="#ccc1d9">描述：</font>对 $\lim_{n\to\infty}x_n=a$ 而言：$\forall\varepsilon>0,\exists N>0,\text{ 当 }n>N\text{ 时, 恒有 }|x_n-a|<\varepsilon$

**解释**
+ $\varepsilon>0$ ：函数的接近程度；
+ 几何意义：$x_n$ 在 $\varepsilon$ 前后的小领域内；
+ N：大 N 项之后的所有数字，都落在了 $|x_n-a|<\varepsilon$ 的范围内，而 N 是一个无穷多的项，N 之前的数字是一个有限项；
	+ 有限项总是有界的；  
	+ 数列 $\left\{x_n\right\}$ 的极限**和前有限项无关**；

**概念**：结论 1
+ $$\lim_{n\to\infty}x_n=a\Leftrightarrow\lim_{k\to\infty}x_{2k-1}\overset{\color{red}{}}{\operatorname*{=}}\lim_{k\to\infty}x_{2k}=a.$$
+ 如果**一个数列以 a 为极限，则其子数列都以 a 为极限**；

**概念**：结论 2
+ 1. $$\text{若 }\lim_{n\to\infty}x_n=a,\text{则}\lim_{n\to\infty}\lvert x_n\rvert=\lvert a\rvert,\text{ 但反之不成立}$$
+ 2. $$\lim_{n\to\infty}x_n=0\text{ 的充分必要条件是 }\lim_{n\to\infty}|x_n|=\mathbf{0}$$

**概念**：结论 3
+ 一个数列的子数列如果满足以下两个条件，则可以推出完整数列的值：
	+ 1. 子数列的值全部都相等；
	+ 2. 几个子数列取遍了原数列的所有情况；
