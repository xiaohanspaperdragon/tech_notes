---
title: Lecture 32：定积分的计算
tags: 
categories: 
date: 2024-01-23
---
---
## 1.1 定积分的计算
### 1.1.1 概念引入
**变速直线运动中位置函数与速度函数之间的联系**
+ 定积分的定义，直接用于计算很麻烦
	+ $\int_a^bf(x)\operatorname{d}x\mathop{\Delta}\lim_{\lambda\to0}\sum_{i=1}^nf(\xi_i)\Delta x_i$
+ 比如在计算路程时，$v(t)$ 为速度函数，$s(t)$ 为路程函数：
	+ $\int_{T_1}^{T_2}\nu(t)dt=s(T_2)-s(T_1)\quad s^{\prime}(t)=\nu(t)$
	+ 并且，根据不定积分的性质：$s(t)=\int_{t_0}^tv(t)dt\quad s^{\prime}(t)=v(t)$
+ 是否可以转化成，被积函数的原函数在两点之间的相差？

**情况分析：** 设 $f(x)$ 在 $[a,b]$ 上连续，并且 x 是 $[a,b]$ 上的任意一点：
![[Pasted image 20240123140558.png]]
这当中阴影部分的面积，其对应的函数称之为**积分上限的函数**
+ $\Phi(x)=\int_a^xf(t)\mathrm{d}t\quad x\in[a,b]$

**问题：** 这个积分上限的函数，是否在函数区间上可导？
+ 答案：可以，前提是 $f(x)$ 在 $[a,b]$ 上连续；

### 1.1.2 积分上限的函数及其导数
##### **定理**： #积分上限的函数：微积分基本定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{若 }f(x)\text{在 }[a,b]\text{ 上连续，则：}\int_a^xf(t)\mathrm{d}t\text{ 在 }[a,b]$ 上可导，且有 $$(\int_a^xf(t)\mathrm{d}t)^{\prime}=f(x)$$

**解释**
+ 概念：
	+ **对函数的积分求导，等于这一点的函数值**；
	+ 当其中的 x 为常数时，其求出来的是一个定值；
+ 核心：
	+ 微分和积分，互为逆运算；
	+ 解决了原函数存在性；
+ 结论：
	+ $$(\int_{\varphi(x)}^{\psi(x)}f(t)dt)^{\prime}=f(\psi(x))\psi^{\prime}(x)-f(\varphi(x))\varphi^{\prime}(x)$$

##### **定理**： #积分上限函数的奇偶性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. 若 f (x)是奇函数，则 $\int_0^xf(t)dt$ 是偶函数；
> 2. 若 f (x)是偶函数，则 $\int_0^xf(t)dt$ 是奇函数；

**解释**

##### **定理**： #定积分的原函数
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }f(\mathrm{x})\text{在}\left[a,b\right]\text{ 上连续，则}\int_a^xf(t)\mathrm{d}t\text{ 是}f(\mathrm{x})\text{ 在 }\left[a,b\right]$ 上的一个原函数；

**解释**
+ 当被积函数 $f(x)$ 是一个连续函数时，其变上限的积分、作为上限的函数，是 $f(x)$ 在这一点上的原函数；
+ 即：**连续函数一定有原函数**，至少变函数积分一定是其一个原函数；

**推论：** 更加一般化的结论
+ $\text{若 }\varphi(x),\psi(x)\text{ 可导,}f(x)\text{ 连续,则}$：
	+ $\frac d{dx}\int_{\psi(x)}^{\varphi(x)}f(t)dt=f(\varphi(x))\varphi^{\prime}(x)-f(\psi(x))\psi^{\prime}(x)$

### 1.1.3 例题
**例题**：$\text{设 }\Phi(x)=\int_{0}^{x^{2}}e^{-t^{2}}dt,\text{求}\Phi^{\prime}(x)$
+ 分析
	+ 由定积分的原函数的性质，可以用对定积分 $\int_{0}^{x^{2}}e^{-t^{2}}dt$ 的求导，来求 $\Phi^{\prime}(x)$ 的值；
	+ 不能直接对 x 的平方求导，要把它看作是一个复合函数求导；
+ 解析
	+ $\Phi=\int_{0}^{u}e^{-t^{2}}dt$
	+ 其中 $u=x的平方$
	+ 注意：不能直接对 x 的平方求导，要把它看作是一个复合函数求导：
	+ $\bar{\Phi}_{x}^{\prime}(x)=\bar{\Phi}_{u}^{\prime}\cdot U_{x}^{\prime}=e^{-u^2}\cdot2x=e^{-x^4}\cdot2x.$
+ 题型： #定积分的原函数 

**例题**：当函数的上下限都变时： $g(x)=\int_{\sin x}^{x^2}e^{-t^2}dt\quad$，求其导函数；
+ 分析
	+ 可以将其分成两段，从 sinx 到 0，再从 0 到 x 的平方；
	+ 分开求解，相加；
+ 解析
	+ ${\int_0^{x^2}e^{-t^2}dt+\int_{sinx}^0e^{-t^2}dt}$
+ 题型： #定积分的原函数

## 1.2 计算方法
### 1.2.1 牛顿-莱布尼茨公式
##### **定理**： #牛顿莱布尼茨公式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }F(x)\text{ 为连续函数 }f(x)$ $\text{在 }[a,b]\text{ 上的一个原函数,则}$：$\int_{a}^{b}f(x)dx=F(b)-F(a)$，也称之为微积分基本公式；

**解释**
+ 把求解定积分的问题，转变成了找原函数的问题；
+ 并且此公式：沟通了积分学和微分学之间的关系；
 
**推论：** 证明积分中值定理n
+ $\text{若 }f(x)\text{ 在 }[a,b]\text{ 上连续,则}$
+ $\int_a^bf(x)\operatorname{d}x=f(\xi)(b-a)\quad\quad a<\xi<b$
	+ ![[Pasted image 20240123145622.png]]

### 1.2.2 换元法
##### **定理**： #定积分的换元法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\int_{a}^{b}f(x)\operatorname{d}x=\int_{\alpha}^{\beta}f(\varphi(t))\varphi^{\prime}(t)\operatorname{d}t$$

**解释**
+ 注意：被积函数和上下限都要换元；

### 1.2.3 分部积分法
##### **定理**： #定积分的分部积分法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\int_{a}^{b}u\operatorname{d}v=uv\bigg|_{a}^{b}-\int_{a}^{b}v\operatorname{d}u$$

### 1.2.4 其他方法
**方法一：利用奇偶性，周期性** 
+ $$\int_{-a}^af(x)\operatorname{d}x=\begin{cases}0,&f(x)&\text{为奇函数,}\\2\int_0^af(x)\operatorname{d}x,&f(x)&\text{为偶函数}.\end{cases}$$
+ $$\int_a^{a+T}f(x)\operatorname{d}x=\int_0^Tf(x)\operatorname{d}x.$$

**方法二：利用已有公式**
+  $$\begin{aligned}(1)&\int_0^{\frac\pi2}\sin^nx\operatorname{d}x=\int_0^{\frac\pi2}\cos^nx\operatorname{d}x=\begin{cases}\frac{n-1}n\frac{n-3}{n2}\cdots\frac12\frac\pi2,&n\text{偶}\\\frac{n-1}n\frac{n-3}{n-2}\cdots\frac23,&n\text{奇}&\end{cases}\\(2)&\int_0^{\pi}x\cdot f(\sin x)\operatorname{d}x=\frac\pi2\int_0^{\pi}f(\sin x)\operatorname{d}x\end{aligned}$$

### 1.2.2 例题
**例题**：$\int_{0}^{\pi}\sin xdx$
+ 分析
+ 解析
	+ $\int_{0}^{\pi}\sin xdx=\left(-cosx\right)\int_{0}^{\pi}=1-(-1)=2.$
+ 题型： #牛顿莱布尼茨公式 

## 1.3 常考题型
### 题型： #定积分的计算
#### PART 1：解题方法
**五类常用方法**
+ 1. 牛顿-莱布尼茨公式；
+ 2. 换元法
+ 3. 分部积分法；
+ 4. 奇偶性、周期性；
	+ 拿到函数，先观察其奇偶性、周期性；
+ 5. 两个特殊公式；
	+ $$\begin{aligned}(1)&\int_0^{\frac\pi2}\sin^nx\operatorname{d}x=\int_0^{\frac\pi2}\cos^nx\operatorname{d}x=\begin{cases}\frac{n-1}n\frac{n-3}{n2}\cdots\frac12\frac\pi2,&n\text{偶}\\\frac{n-1}n\frac{n-3}{n-2}\cdots\frac23,&n\text{奇}&\end{cases}\\(2)&\int_0^{\pi}x\cdot f(\sin x)\operatorname{d}x=\frac\pi2\int_0^{\pi}f(\sin x)\operatorname{d}x\end{aligned}$$
+ 补充方法：
	+ 使用几何分析：如果函数是某类几何图形，可以画出其图形，观察几何性质；

**不定积分几何常见结论**
+ 1. $$\int_{0}^{a}\sqrt{a^{2}-x^{2}}dx=\frac{\pi a^{2}}{4}(a>0)$$
+ 2. $$\int_{0}^{a}\sqrt{2ax-x^{2}}dx=\frac{\pi}{4}a^{2}$$
+ 3. $$\int_{0}^{2a}\sqrt{2ax-x^{2}}dx=\frac{\pi}{2}a^{2}$$

**带有变上限的定积分**
+ 遇到变上限函数的定积分计算，可以考虑使用分部积分法；

#### PART 2：典型例题

#### PART 3：知识点复盘

### 题型： #变上限定积分
#### PART 1：解题方法
**核心公式**
+ 概念：
	+ $$(\int_a^xf(t)\mathrm{d}t)^{\prime}=f(x)$$
+ 计算：
	+ $$(\int_{\varphi(x)}^{\psi(x)}f(t)dt)^{\prime}=f(\psi(x))\psi^{\prime}(x)-f(\varphi(x))\varphi^{\prime}(x)$$


**变上限定积分三大方法**
+ 方法一：公式计算
	+ 举例： $$(\int_{e^{x}}^{x^{2}}f(t)dt)^{\prime}=f(x^{2})\cdot2x-f(e^{x})e^{x}$$
+ 方法二：提取 x 
	+ 举例： $$\int_{0}^{x}(x-t)f(t)dt;=x\int_{0}^{x}f(t)dt-\int_{0}^{x}tf(t)dt$$
	+ 积分域以及被积式子里面都有 x；
	+ 能提出 x 时：拆项，把 x 提取出来；
+ 方法三：换元法
	+ 举例： $$\int_{0}^{x}cos(x-t)^{2}dt\frac{x-t=u}{}\int_{0}^{x}cos u^{2}du$$
	+ 积分域以及被积式子里面都有 x；
	+ 不能提出 x 时：换元；
		+ 注意：换元时，x 是常数，t 和 u 是被积分变量；
	+ 举例：当出现上下限都没有 x，但被积分式中有 x 时，需要把 x 换元、带入到上下限当中；
		+ 令 $x+t=u$ 后： $$\int_{1}^{2}f(x+t)dt=\int_{x+1}^{x+2}f(u)du$$

**题型：变上限积分 + 求极限**
+ 在极限当中，分子或分母存在变上限积分，此时最常用的是洛必达法则；

**题型：变上限积分 + 隐函数求导**
+ 举例：设可导函数 $y=y(x)$ 由方程 $\int_0^{x+y}\mathbf{e}^{-t^2}\mathbf{d}t=\int_0^xx\sin t^2\operatorname{d}t$ 确定，求 $\frac{\operatorname{d}y}{\operatorname{d}x}_{x=0}$
+ 分析：等数左边是一个关于 x、y 的函数，等式右边是一个关于 x 的函数，因此当需要求 $y=y(x)$ 在 $\frac{\operatorname{d}y}{\operatorname{d}x}_{x=0}$ 上的导数时，本质上是一个有 y 有 x 的隐函数其导数在 0 点的值，因此为隐函数求导问题；
	+ 核心：变上限求导

#### PART 2：典型例题

#### PART 3：知识点复盘