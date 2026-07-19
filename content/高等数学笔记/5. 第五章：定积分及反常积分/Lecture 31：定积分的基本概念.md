---
title: Lecture 31：定积分的基本概念
tags:
  - 数学
  - 定积分
categories: 
date: 2024-01-21
---
---
## 本章常考题型与典型例题
**考试内容**
+ (一)定积分概念 
+ (二)定积分的性质 
+ (三)积分上限的函数 
+ (四)定积分的计算 

**常考题型**
+ 题型一：定积分的概念、性质及几何意义 
+ 题型二：定积分计算 （重点）
+ 题型三：变上限定积分（重点）

## 1.1 定积分基本概念
### 1.1.1 定积分的定义
##### **定义**： #定积分
> <font color="#ccc1d9">描述：</font> $f(x)$ 在 $[a,b]$ 上有界，在 $[a,b]$ 上任意插入分点，分成 n 个小区间 $\Delta x_{1}\Delta x_{2}\cdots\Delta x_{n}$ ，任取一点 i，有：$$\int_{a}^{b}f(x)dx=\lim_{λ\to0}\sum_{x=1}^{n}f(\xi_{i})\Delta x_{i}$$
>  
> 其中：$$\lambda=\max\{\Delta x_{1}\cdots\Delta x_{n}\}$$

**解释**
+ 概念：
	+ 定积分就是 $f(x)$ 在 $[a,b]$ 上的**和式极限**；
	+ 1. 分：将 $[a,b]$ 区间分成若干段；
		+ 设函数 $f(x)$ 在区间 $[a, b]$ 上连续，将区间 $[a, b]$ 分成 n 个子区间 $[x_0,x_1]$,($x_1,x_2],(x_2,x_3],\ldots,(x_{n-1},x_n]$, 其中 $x_0 = a$，$x_n = b$
	+ 2. 匀：从中取出一段 $[x_{i-1},x_i]$；
	+ 3. 积：将所有的小段求和：$\sum_{x=1}^{n}f(\xi_{i})\Delta x_{i}$
	+ 4. 精：将每一个小段趋向于无穷小：$\lim_{λ\to0}\sum_{x=1}^{n}f(\xi_{i})\Delta x_{i}$
+ 总结：
	+ 定积分是一种特殊的极限；
	+ 定积分的存在性问题 `->` 极限的可积性问题；
+ 分段：
	+ $\lambda=\max[-x_1,-2x_2,\ldots,-2x_n\}$ （即λ是最大的区间长度） 
	+ 如果当 λ→0 时，积分和的极限存在，则这个极限叫做函数 f (x) 在区间 $[a, b]$ 的定积分，记为 $\int_a^bf(x)dx$，并称函数 f (x)在区间 $[a, b]$ 上可积；
+ 注意：
	+ 1.  $\lambda\to0\text{ 与 }n\to\infty\text{ 不等价}$；
	+ 2. $\int_a^bf(x)dx\text{ 仅与 }f(x)\text{和 }[a,b]\text{有关}$；
	+ 3. $\text{极限 }\lim_{\lambda\to0}\sum_{i=1}^nf(\xi_i)\Delta x_i\text{ 与 }\xi_i\text{ 的取法和区间 }[a,b]\text{ 的分法无关}$
		+ 因为和分法无关，因为等分最简单，所以使用等分；
		+ $$\int_{0}^{1}f(x)\operatorname{d}x=\lim_{\lambda\to0}\sum_{i=1}^{n}f(\xi_{\iota})\Delta x_{i}=\lim_{n\to\infty}\frac{1}{n}\sum_{i=1}^{n}f(\frac{i}{n})$$
		+ 这样就可以把求一个和式的极限，变成求其定积分；
		+ 其中：$\frac{1}{n}$ 称之为**可爱因子**；
	+ 4. 定积分求出来的是一个具体的数，且只和被积分函数以及积分区间有关，与积分变量无关；


### 1.1.2 定积分存在条件
##### **定理**： #定积分存在性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. 条件 1：$f(x)$ 在 $[a,b]$ 上连续 -> 可积；
> 2. 条件 2：$f(x)$ 在 $[a,b]$ 上有界，且有有限个间断点 -> 可积；
> 3. 条件 3：$f(x)$ 在 $[a,b]$ 上仅有有限个第一类间断点；

**解释**
+ 其中 1 和 3 用的比较多；
+ 必要条件：
	+ 可积 `->` 有界；
	+ 但有界不能推出可积存在；
+ 总结：
	+ 有界是定积分存在的必要条件；
	+ 可积是定积分存在的充分条件；

### 1.1.3 定积分的几何含义
**函数值有正有负**
+ 概念：
	+ 定积分等于几何上的函数的图形面积；
	+ 当函数值有正有负时，当前定积分的值会等于 A 和 C 部分的面积和，减去 B 部分的面积大小；
	+ 不知道正负，求了才知道； 
+ 图示：
	+ ![[Pasted image 20240121212018.png]]

## 1.2 定积分的性质
### 1.2.1 基础性质：不等式
**性质 1**：不等式性质
+ $\text{若 }f(x)\leq g(x),\text{ 则}\int_a^bf(x)\operatorname{d}x\leq\int_a^bg(x)\operatorname{d}x$ 
+ 注意：
	+ a 需要小于等于 b

**性质 2**：估值性
+ $m(b-a)\leq\int_a^bf(x)\operatorname{d}x\leq M(b-a)$
+ 定积分在最大值和最小值之间；

**性质 3**：绝对值
+ $\left|\int_a^bf(x)\mathbf{d}x\right|\leq\int_a^b\lvert f(x)\rvert\mathbf{d}x.$


### 1.2.2 基础性质：中值定理
**性质 1**
+ 若 $f(x)$ 在 $[a,b]$ 上连续，则
	+ $$\int_a^bf(x)\operatorname{d}x=f(\xi)(b-a),a<\xi<b$$

**性质 2**
+ $\text{若 }f(x),g(x)\text{ 在}\left[a,b\right]\text{上连续,}g(x)\text{ 不变号,则}$
	+ $$\int_a^bf(x)g(x)\operatorname{d}x=f(\xi)\int_a^bg(x)\operatorname{d}x,a<=\xi<=b$$

**应用**
+ 1. 积分的证明题；   
+ 2. 求与积分有关的极限；

### 1.2.2 其他性质
**两条规定**
+ 1. 如果 b = a 时，从 a 到 a 的定积分等于 0；
+ 2. 从 a 到 b 的定积分，等于从 b 到 a 的定积分的相反数；
	+ $\int_{a}^{b}f\left(x\right)dx=-\int_{b}^{a}f\left(x\right)dx$
	+ 交换上下限；

**性质 1：**$\int_{a}^{b}(\alpha f(x)+\beta g(x))dx=\alpha\int_{a}^{b}f(x)dx+\beta\int_{a}^{b}g(x)dx$

**性质 2：** 
+ 如果 $a<c<b$ （c 在里头）
	+ 则 $\int_{a}^{b}f\left(x\right)dx=\int_{a}^{c}f\left(x\right)dx+\int_{c}^{b}f\left(x\right)dx$
+ 如果 $a<b<c$（c 在外头）
	+ 则 $\int_{a}^{b}f(x)dx=\int_{a}^{c}f(x)dx-\int_{b}^{c}f(x)dx$ $=\int_{a}^{c}f\left(x\right)dx+\int_{c}^{b}f\left(x\right)dx$
+ 所以，最终结论：$\int_{a}^{b}f\left(x\right)dx=\int_{a}^{c}f\left(x\right)dx+\int_{c}^{b}f\left(x\right)dx$

**性质 3：** $\begin{aligned}f(x)\equiv1；\int_{a}^{b}1dx=b-a\\\int_{a}^{b}kdx=k(b-a)\end{aligned}$

**性质 4：** M，m 分别为最大值、最小值，因此 $m(b-a)\leq\int_{a}^{b}f(a)dx\leq M(cb-a)$

## 1.3 常考题型
### 题型： #定积分的概念、性质及几何意义
#### PART 1：解题方法
**题型：n 项和相加**
+ 思路：
	+ 1. 使用夹逼定理；
	+ 2. 使用定积分定义；
+ 定积分求解：
	+ 步骤 1：先提出可爱银子 $1/n$ 
		+ 需要保证：提出之后的元素是 $1/n$ ，不可以被不可爱因子抵消；
		+ 因为可爱银子就是 $\int_{a}^{b}f(x)dx=\lim_{λ\to0}\sum_{x=1}^{n}f(\xi_{i})\Delta x_{i}$ 中的 $\Delta x_{i}$
	+ 步骤 2：观察被提出后的式子，找变量 -> 哪里变哪里就是变量；
	+ 步骤 3：得到区间 -> 从哪变到哪 -> 找到定积分的上下限；
+ 如何判断：
	+ 一般先使用夹逼定理，然后如果用不了再使用定积分定义；

**题型：定积分的几何意义**
+ 注意：
	+ 当要求上下限区间为负的部分，比如 $(-3,0)$ 这一部分的定积分的值时，需要注意：定积分上限不可以小于定积分下限；
	+ 比如 $F(-2)=\int_{0}^{-2}f(t)dt$ 这种式子是错的，因为上限不能小于下限。得使用这种形式：$F(-2)=-\int_{-2}^{0}f(t)dt$
+ 图示：
	+ ![[Pasted image 20240410173857.png]]

#### PART 2：典型例题

#### PART 3：知识点复盘