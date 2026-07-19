---
title: Lecture 48：对弧长的曲线积分
tags:
  - 数学
  - 曲线积分
categories: 
date: 2024-02-11
---
---
## 57.1 对弧长的曲线积分
### 57.1.1 基本概念
##### **定义**： #平面上对弧长的线积分
> <font color="#ccc1d9">描述：</font> $$\int_{L}f(x,y)ds=\lim_{\lambda\to0}\sum_{i=1}^{n}f(\xi_{i},\eta_{i})\Delta s_{i}$$

**解释**
+ 一个二元函数，沿着一个二维的曲线段的积分；
+ 把曲线分成 n 个小端，将曲线的函数值乘以小弧段的长度，将每一段求和、取极限，如果这个极限存在，则线积分存在；

##### **定理**： #线积分的性质
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\int_{L(AB)}f(x,y)ds=\int_{L(BA)}f(x,y)ds$$

**解释**
+ 含义：线积分和路径的方向无关；

**推论**
+ 1.  $\int_{L_{1}+L_{2}}f(x,y)ds=\int_{L_{1}}f(x,y)ds+\int_{L_{2}}f(x,y)ds$；
+ 2. $\int_{L}[df(x,y)+\beta g(x,y)]ds=\alpha\int_{L}f(x,y)ds+\beta\int_{L}g(x,y)ds$；
+ 3. $\int_{C}f(x,y)ds=\int_{C_{1}}f(x,y)ds+\int_{C_{2}}f(x,y)ds$；
+ 4. $f(x,y)<=g(x,y) ; \int_{L}f(x,y)ds\leq\int_{L}g(x,y)ds$

## 57.2 曲线积分的计算
### 57.2.1 基本法
##### **定理**： #第一类曲线积分的计算：直接法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>假设 L 的参数方程为 $\begin{cases}x=\varphi(t),\\y=\psi(t),&\end{cases}(\alpha\leqslant t\leqslant\beta)$，则： $$\int_{L}f(x,y)\mathrm{d}s=\int_{\alpha}^{\beta}f(\varphi(t),\psi(t))\sqrt{\varphi'(t)^2+\psi'(t)^2}\mathrm{d}t$$

**解释**
+ 注意：
	+ `ds` 是曲线的弧微分；
	+ 上下限是弧长从小到大；

##### **定理**： #第一类曲线积分的计算：直角方程
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{若 }C:y=y(x),\quad a\leq x\leq b$，则：
> $$\int_{}f(x,y)\mathrm{d}s=\int_{a}^{b}f(x,y(x))\sqrt{1+y'^2(x)}\mathrm{d}x$$

**解释**
+ 相当于把 `x` 看作为参数；

##### **定理**： #第一类曲线积分的计算：极坐标方程
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{若 }C:\rho=\rho (\theta)\quad\alpha\leq\theta\leq\beta$，则：
> $$\int_{C}f(x,y)ds=\int_{\alpha}^{\beta}f(\rho(\theta)\cos\theta,\rho(\theta)\sin\theta)\sqrt{\rho^{2}(\theta)+\rho^{\prime2}(\theta)}d\theta $$

**解释**

### 57.2.2 奇偶性与对称性
##### **定理**： #积分曲线的奇偶性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\int_{C}f(x,y)\mathrm{d}s=\begin{cases}2\int_{C_{x>4}}f(x,y)\mathrm{d}s,&f(-x,y)=f(x,y)\\0,&f(-x,y)=-f(x,y)\end{cases}$$

**解释**

##### **定理**： #对称性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>一般情况：$\int_{c}f(x,y)\mathrm{d}s=\int_{c}f(y,x)\mathrm{d}s$
> 特别：$\int_Cf(x)ds=\int_Cf(y)ds$

