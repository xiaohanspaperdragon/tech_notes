---
title: Lecture 47：三重积分
tags:
  - 数学
  - 三重积分
categories: 
date: 2024-02-09
---
---
## 46.1 三重积分
### 46.1.1 基础概念
##### **定义**： #三重积分 
> <font color="#ccc1d9">描述：</font> $\iiint_{\Omega}f(x,y,z)\mathrm{d}\mathbf{v}=\lim_{\lambda\to0}\sum_{k=1}^{n}f(\xi_{k},\eta_{k},\xi_{k})\Delta\nu_{k}$

**解释**
+ 概念：
	+ 一个三元函数，在一个空间体 $\Omega$ 当中的积分；
	+ $\Delta\nu_{k}$ 为第 k 个小区域的几何体的体积；
+ 核心： 
	+ 三重积分部分的核心，就是三重积分的计算；
	+ 而三重积分计算的核心，就是将其转化为定积分或者二重积分的计算；

### 46.1.2 基本计算方法
##### **定理**： #三重积分的直坐标计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. 先一后二：$$\iiint_{\Omega}f(x,y,z)\mathrm{dv}=\iint_{D_{xy}}d\sigma\int_{z_{1}(x,y)}^{z_{2}(x,y)}f(x,y,z)dz$$
> 2. 先二后一：$$\iiint_{\Omega}f(x,y,z)\mathrm{d}\mathbf{v}=\int_{c_{1}}^{c_{2}}dz\iint_{D_{c}}f(x,y,z)dxdy$$

**解释**
+ 先一后二： 
	+ 解释：
		+ 先对 `z` 做定积分；
		+ 在对 `xy` 做二重积分；
	+ 定限方法：
		+ 做当前集合体在 `xy` 轴上的投影面 $D_{xy}$ ，在此投影面上往上做一跟射线、穿过几何体；
		+ 穿到的下面的部分为积分下限 $z=z_1(x,y)$，穿到的上面的部分为积分上限 $z=z_2(x,y)$；
+ 先二后一：
	+ 解释：
		+ 先对 `xy` 做二重积分；
		+ 在对 `z` 做定积分；
	+ 定限方法： 
		+ 将几何体投影到 `z` 轴上，`z` 的上下限就是其在 `z` 轴投影上的最大值和最小值；


## 46.2 柱坐标
### 46.2.1 基础概念
##### **定义**： #柱坐标
> <font color="#ccc1d9">描述：</font> $$\begin{cases}x=r\cos\theta,&\quad0\leq r<+\infty,\\y=r\sin\theta,&\quad0\leq\theta\leq2\pi,\\z=z,&\quad-\infty<z<+\infty.\end{cases}$$

**解释**
+ 概念：
	+ `r`：点到 `z` 轴的距离；
	+ `z`：z 轴上的高度；
	+ `角度`：限制当前线段的角度；
+ 图示：
	+ ![[Pasted image 20240521035217.png]]

### 46.2.2 柱坐标计算方法
##### **定理**： #柱坐标计算方法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 体积微元：$dv=\rho d\rho d\theta dz$
> 计算：$$\iiint_\Omega f(x,y,z)d\nu=\iiint_{\Omega}f(\rho\cos\theta,\rho\sin\theta,z)r\operatorname{d}r\operatorname{d}\theta\operatorname{d}z$$ 

**补充**：柱坐标适用范围
+ 函数角度：
	+ 如果被积函数可以被写成 $g(x)*f(\sqrt{x^2+y^2})$  `->` 适合用柱坐标；
+ 区域角度：
	+ 中心轴为 `z` 轴这样的柱体、偏心柱体、锥体 `->` 适合用柱坐标；

## 46.3 球坐标计算三重积分
### 46.3.1 基本概念 
##### **定义**： #球坐标
> <font color="#ccc1d9">描述：</font> $$\begin{cases}x=r\sin\varphi\cos\theta,&\quad0\leq r<+\infty,\\y=r\sin\varphi\sin\theta,&\quad0\leq\varphi\leq\pi,\\z=r\cos\varphi,&\quad0\leq\theta\leq2\pi.\end{cases}$$

**解释** 
+ 图示：
+ ![[Pasted image 20240521040109.png]]

### 46.3.2 球坐标计算方法
##### **定理**： #球坐标计算方法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 体积微元：$dv=r^{2}\sin\varphi drd\varphi d\theta$
> 计算：$$\iiint_{\Omega}f(x,y,z)d\nu =\iiint_\Omega f (r\sin\varphi\cos\theta, r\sin\varphi\sin\theta, r\cos\varphi) r^2\sin\varphi\operatorname{d}r\operatorname{d}\varphi\operatorname{d}\theta$$

**补充**：球坐标适用范围
+ 函数角度：
	+ 如果被积函数可以被写成 $f(\sqrt{x^2+y^2+z^2})$  `->` 适合用球坐标；
+ 区域角度：
	+ 中心在原点的球体、球面、半球体、曲顶锥体 `->` 适合用球坐标；

## 46.4 三重积分的性质
### 46.4.1 奇偶性
##### **定理**： #三重积分的奇偶性计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\text{若积分域 }\Omega\text{ 关于 }xoy\text{ 坐标面对称}，则\iiint_{\Omega}f(x,y,z)\mathrm{d}V=\begin{cases}2\iiint f(x,y,z)\mathrm{d}V&f(x,y,-z)=f(x,y,z)\\0&f(x,y,-z)=-f(x,y,z)\end{cases}$$

**解释**

### 46.4.2 对称性
##### **定理**： #三重积分的对称性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>

## 46.5 常考题型

---
### 题型： #三重积分的计算 
#### PART 1：解题方法

#### PART 2：典型例题

#### PART 3：知识点复盘
**知识点**：适合先二后一的情况
+ 1. 被积函数仅仅是关于 `z` 的一元函数；
+ 2. 用 `z=z` 去截几何体的面积时，这个面积的公式好求（比如 $x^2+y^2<1-z^2$）；