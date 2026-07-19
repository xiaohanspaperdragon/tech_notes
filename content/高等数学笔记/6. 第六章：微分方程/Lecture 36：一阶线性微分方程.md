---
title: Lecture 36：一阶线性微分方程
tags:
  - 数学
  - 微分方程
categories: 
date: 2024-02-01
---
---
## 1.1 线性方程
##### **定义**： #线性方程 
> <font color="#ccc1d9">描述：</font>未知函数 $y=y(x)$ 和未知函数的导数 $y^{\prime}$ 都是一次的，因此称之为线性；
> 标准形式：$$y^{\prime}+P(x)y=Q(x)$$

**补充**：如果当式子中的 y 为两阶甚至三阶，但 x 只有一阶时，此时可以考虑将 x、y 对调，利用 $\frac{dx}{dy}$ 进行求解；

##### **定理**： #线性方程的通解公式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$y=e^{-\int p(x)dx}\left[\int Q(x)e^{\int p(x)dx}dx+C\right]$$

**解释**
+ 概念：
	+ 必须得写成线性方程的标准形式后，才可以带入通解公式；
+ 注意：
	+ 1. 对 $p(x)$ 以及 $Q(x)$ 的不定积分，不需要带任意常数 $C$； 
	+ 2. 对 $p(x)$ 位置，如果出现以下形式，不用加绝对值：$\int\frac{1}{x}dx=\ln x$；
+ 方法：
	+ 第一步：将微分方程整理成线性方程的形式；
	+ 第二步：带入通解公式，求出通解；

## 1.2 伯努利方程
### 1.2.1 基本概念
##### **定理**： #伯努利方程
> <font color="#ccc1d9">描述：</font> 在线性微分方程的基础上，在 $Q(x)$ 的右边乘上 $y^{1-\alpha}=u)$：
> $$y^{\prime}+p (x) y=Q (x) y^{\alpha} \quad\quad\quad\quad\quad\quad(\alpha\neq1)\quad(y^{1-\alpha}=u)$$ 

**解释**
+ 求解：
	+ 将 $y$ 设为 $y^{1-\alpha}=u$，使得方程变成一阶微分线性方程；
+ 方法：
	+ 如果 $\alpha$ 等于 0，那就是线性方程；
	+ 如果 $\alpha$ 等于 1，那就直接可以使用可分离变量；
	+ 因此：当前的讨论，都是假设阿法及不等于 0，也不等于 1；
+ 思路：
	+ 思考如何才能化成线性方程；

**处理方法**
+ 已知：$y^{\prime}+p (x) y=Q (x) y^\alpha$
+ 第一步
	+ 把 $y^\alpha$ 除到等式的左边来，和 y 相除，得到：
	+ $y^{1-\alpha}$
+ 第二步：设 z
	+ 令 $y^{1-\alpha}=z$
+ 第三步
	+ 化成线性方程

### 1.2.2 例题
**例题**：$\frac{dy}{dx}+\frac yx=a(\ln x)y^2$
+ 分析
+ 解析
	+ 先将 y 的平方除以过去：
		+ $\frac1{y^2}\frac{\mathrm{d}y}{\mathrm{d}x}+\frac1x\frac1y=a\ln x$
		+ $-\frac{1}{y^{2}}\frac{dy}{dx}=\frac{dt}{dx}$
	+ 然后设 y 的负一次方为 z
		+ $-\frac{\mathrm{d}z}{\mathrm{d}x}+\frac1xz=\mathrm{alnx}$
	+ 左右对 x 求导：
+ 题型： #伯努利方程

## 1.3 全微分方程
### 1.3.1 基本概念
##### **定义**： #全微分方程
> <font color="#ccc1d9">描述：</font> $$dF(x,y)=P(x,y)dx+Q(x,y)dy=0$$

**解释**
+ 概念：
	+ 如果 $P(x,y)dx+Q(x,y)dy=0$ 是某个函数 $F(x,y)$ 的微分，则成此方程为全微分方程；
+ 判断：
	+ 如果两个分别对 $P(y)$ 和 $Q(x)$ 求出来的偏导数相等：
		+ $$\frac{\partial P}{\partial y}=\frac{\partial Q}{\partial x}$$
	+ 则当前方程为全微分方程；
+ 解法：
	+ 1. 偏积分；
	+ 2. 凑微分；
	+ 3. 线积分；


**解释**
+ 多元函数的微分，就是全微分；
	+ 一元函数中的微分，只是考虑了 x 一个自变量导致的变化：
		+ $dy=A\Delta x$
	+ 在二元函数中，则是要将 x、y 两个变量导致的变化都表示出来：
		+ $dz=Adx+Bdy$
+ 偏增量和全增量
	+ 偏增量：$\begin{aligned}\Delta z_{x}=f\left(x_{0}+\Delta x,y_{0}\right)-f\left(x_{0},y_{0}\right)\\\Delta z_{y}=f\left(x_{0},y_{0}+\Delta y\right)-f\left(x_0,y_{0}\right)\end{aligned}$
	+ 全增量：$\Delta z=f(x_{0}+\Delta x,y_{0}+\Delta y)-f(x_{0},y_{0})$

**全微分的两个问题**
+ 二元函数有两个自变量：x、y
+ 一元微分的定义，和二元微分的定义在概念上是十分类似的；
+ 微分的两个问题
	+ 1. 是否可微分
		+ （一元微分）由于可微分就可导，因此可使用导数的性质进行判断；
		+ 二元微分是否有这样的结论？
	+ 2. 微分如何计算
		+ （一元微分）由于 $dy=f^{\prime}(x)dx$，所以可以用导数来求出 $dz=Adx$ 中的 A 的部分；
		+ 把微分的计算归结为导数的计算

### 1.3.2 全微分的性质
##### **定理**： #多元函数可微的必要条件
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>如果函数 $z=f(x,y)$ 在点 $(x,y)$ 处可微，则该函数在点 (x, y)的偏导数 $\frac{\partial z}{\partial x}$ 与 $\frac{\partial z}{\partial y}$ 必定存在，且：$dz=\frac{\partial z}{\partial x}\Delta x+\frac{\partial z}{\partial y}\Delta y$
> 注意：其中 
> 1.  $\frac{\partial z}{\partial x}$ 就是 $dz=Adx+Bdy$ 中的 A；
> 2.  $\frac{\partial z}{\partial y}$ 就是 $dz=Adx+Bdy$ 中的 B；
