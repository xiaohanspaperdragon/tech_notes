---
title: Lecture 7：极限存在准则
tags:
  - 数学
categories: 
date: 2024-03-01
---
---
## 7.1 极限存在准则基本概念
### 7.1.1 数列极限的存在准则
##### **定理**： #数列极限的夹逼准则
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{若存在 }N,\text{当 }n>N\text{ 时, }x_n\leq y_n\leq z_n$，$\lim_{n\to\infty}x_n=\lim_{n\to\infty}z_n=a,\text{则}\lim_{n\to\infty}y_n=a$

**使用情况**：n 项和
+ 举例：$\lim_{n\to\infty}\left[\frac n{n^2+1}+\frac n{n^2+2}+\cdots+\frac n{n^2+n}\right]$
+ 放大：$\frac n{n^2+n}$
+ 缩小：$\frac n{n^2+1}$
+ 使用：$\frac{n^2}{n^2+n}\leq\left[\frac n{n^2+1}+\frac n{n^2+2}+\cdots+\frac n{n^2+n}\right]\leq\frac{n^2}{n^2+1}$

**使用情况**：取整函数
+ 举例：$\lim_{x\to0^+}x[\frac1x]$
+ 大小：$\frac1x-1<[\frac1x]\leq\frac1x$
 
##### **定理**： #数列的单调有界准则
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>单调有界数列必有极限；
> 1. 单调增、有上界的数列必有极限；
> 2. 单调减、有下界的数列必有极限；
