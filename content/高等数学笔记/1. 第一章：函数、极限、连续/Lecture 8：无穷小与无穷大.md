---
title: Lecture 8：无穷小与无穷大
tags:
  - 数学
categories: 
date: 2024-03-01
---
---
## 8.1 无穷小
### 8.1.1 基本概念
##### **定义**： #无穷小
> <font color="#ccc1d9">描述：</font>若函数 $f(x)$ 当 $x\to x_0($ 或 $x\to\infty)$ 时的极限为零，则称 $f(x)$ 为 $x\to x_0($ 或 $x\to\infty)$ 时的无穷小量.

### 8.1.2 无穷小的比较
+ **同阶**无穷小： $\alpha(x)和\beta(x)$ 相除结果为**常数 C**（C 不等于 0）；
+ **等价**无穷小： $\alpha(x)和\beta(x)$ 相除结果为**常数 1**；
+ 高阶无穷小： $\alpha(x)和\beta(x)$ 相除结果为 0；可记为：$\alpha(x)=o(\beta(x))$
+ 低阶无穷小： $\alpha(x)和\beta(x)$ 相除结果为无穷；
+ $\text{若}\lim\frac{\alpha (x)^{\color{red}{}}}{\left[\beta (x)\right]^{k}\color{red}}=C\neq 0,\text{称}$ α为β的 k 阶无穷小；

### 8.1.3 无穷小的性质
+ **性质 1：** **有限**个无穷小的和仍然是无穷小；
+ **性质 2：** **有限**个无穷小的积仍然是无穷小；
+ **性质 3：** 无穷小量与**有界量**的**积**任然是无穷小；

## 8.2 无穷大
### 8.2.1 基本概念
##### **定义**： #无穷大
> <font color="#ccc1d9">描述：</font>若函数 $f(x)$ 当 $x\to x_0($ 或 $x\to\infty)$ 时的极限无穷，则称 $f(x)$ 为 $x\to x_0($ 或 $x\to\infty)$ 时的无穷大量.

**解释**
+ 若对任意给定的 $M>0$ ,总存在 $\delta>0$ ,当  $0<\mid x-x_0\mid<\delta\text{ 时,恒有}\mid f(x)\mid>M.$

### 8.2.2 常见无穷大的比较
**概念**：函数极限
+ 当 x 趋向于无穷大时：
+ $$\ln^{\alpha}x<<x^{\beta}<<a^{x}$$
+ 其中 $\alpha>0,\beta>0,a>1$
+ 举例： 
	+ 所以 $\lim_{x\to+\infty}\frac{\ln x}{x}=0$；

**概念**：数列极限
+ 数列极限：$n\to\infty$
+ $$\ln^\alpha n<<n^\beta<<a^n<<n!<<n^n$$
+ 其中 $\alpha>0,\beta>0,a>1$；

### 8.2.3 无穷大的性质
+ **性质 1：** 有限个正无穷大的和是无穷大；
+ **性质 2：** 有限个无穷大的**积**仍然是无穷大；
+ **性质 3：** 无穷大量与**有界变量**的和仍然是无穷大量；

### 8.2.4 无穷大量与无界变量的关系
+ 1. $\text{数列 }\left\{x_n\right\}\text{是无穷大量}$：$\forall\boldsymbol{M}>\boldsymbol{0},\exists N>\boldsymbol{0},\text{当 }n>N\text{ 时,恒有 }|x_n|>\boldsymbol{M}$
	+ $|x_n|$ 在 N 之后的数值，全部都很大；
+ 2. $\text{数列 }\left\{x_n\right\}\text{是无界变量}$：$\forall\boldsymbol{M}>\boldsymbol{0},\exists N>\boldsymbol{0},\text{ 使 }|x_N|>\boldsymbol{M}$
	+ $|x_n|$ 存在一个 n 时的值，大于 M，但不一定有非常多项大于 M； 
	+ 举例：$x_n=\begin{cases}n,&n\text{为奇数}\\\mathbf{0},&n\text{为偶数}\\\end{cases}$ 是一个无界变量，但是不是无穷大；
+ 1 可以推出 2，2 不能推出 1；
+ $\text{无穷大量 }\Rightarrow\textbf{ 无界变量}$

## 8.3 无穷大和无穷小的关系
+ 在同一个极限过程中，如果 $f(x)$ 是无穷大，则 $1 / f(x)$ 是无穷小；
+ 在同一个极限过程中，如果 $f(x)$ 是无穷小，且 $f(x)$ 不等于 0，则 $1 / f(x)$ 是无穷大；