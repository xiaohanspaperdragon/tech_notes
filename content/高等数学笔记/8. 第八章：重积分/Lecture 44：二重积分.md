---
title: Lecture 44：二重积分
tags: 
categories: 
date: 2024-02-08
---
**本节内容概要**
+ （一）二重积分的概念与性质
+ （二）二重积分计算

**本节常考题型**
+ 题型一：累次积分交换次序及计算
+ 题型二：二重积分计算
---
## 44.0 极坐标基础知识
**基础概念**
+ 概念：
	+ **用角度和长度描述位置的坐标系**；
+ 转换：
	+ $$\left\{\begin{array}{c}x=r\mathrm{cos}\theta\\y=r\mathrm{sin}\theta\end{array}\right.\Leftrightarrow\left\{\begin{array}{c}r=\sqrt{x^2+y^2}\\\theta=\arcsin\frac yr=\arcsin\frac y{x^2+y^2}\end{array}\right.$$
	+ 注意：上述转换方法仅限于二者圆点相同，且极坐标参考系与直角坐标的 𝑥 轴方向相同的情况；
+ 图示：
	+ ![[Pasted image 20240509172033.png]]

## 44.1 二重积分基本概念
### 44.1.1 概念引入
**曲面顶柱体的体积**
+ 在一个曲面顶柱体当中，当 $\lim_{\lambda\to0}\sum_{i=1}^{n}\Delta\sigma_{i}f\left(\xi_{i},y\right)$ 时，其为曲面柱体的二重积分；
+ 其中：$\sigma_{i}$ 为底面积，$f\left(\xi_{i},y\right)$ 为高，$lambda$ 为每一个小区间上，几何图形的直径；

##### **定义**： #二重积分
> <font color="#ccc1d9">描述：</font>如果 $f(x,y)$ 是区域 D 上的有界函数，将区域 D 任意的分成 n 个区域：$\sigma_{1}$ 、$\sigma_{2}$.... $\sigma_{n}$，每个 $\sigma_{n}$ 上任取一点 $(\xi_{i},\eta_{i})$，做 $f(\xi,\eta_{i})\Delta\sigma_{i}$ ，当 $\lambda\to0$ 时：
> 称下式为二重积分： $$\lim_{\lambda\to0}\sum_{i=1}^{n}\Delta\sigma_{i}f\left(\xi_{i},y\right)=\int\int_{D}f(x,y)d\sigma $$

**解释**
+ 区间
	+ 一重积分的积分区域是一个区间，比如 $(3,6)$；
	+ 二重积分的积分区域是一个图，因此通常用一个区域 D 来表示；
+ 注意：
	+ 积分区域不等于定义域，积分区域是要求积分的区域；
+ 面积元素
	+ $d\sigma$ 为面积元素；


### 44.1.2 直角坐标系的面积元素
**二重积分的几何意义**：面积元素
+ 横着分和竖着分；
+ $\sigma_{i}=\Delta x_{i}\cdot\Delta y_{j}$ 
+ 公式：$\int\int_{D}f(x,y)dxdy$

## 44.2 二重积分的性质
### 44.2.1 不等式性质
**二重积分**：性质一
+ 如果在 D 上，$f(x,y)\leq g(x,y)$ ，则有不等式：
+ $$\int\int_Df(x,y)d\sigma\leq\int\int_Dg(x,y)d\sigma $$

**二重积分**：性质二
+ 若在 $D$ 上有 $m\leq f(x,y)\leq M$，则： 
+ $$mS\leq\iint_Df(x,y)\mathrm{d}\sigma\leq MS$$
+ 其中：S 是区域 D 的面积

**二重积分**：性质三
+ 积分的绝对值，小于绝对值的而积分
+ $$\left|\iint_Df(x,y)\mathrm{d}\sigma\right|\leq\iint_D\left|f(x,y)\right|\mathrm{d}\sigma.$$ 

### 44.2.2 中值定理
##### **定理**： #二重积分的中值定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设函数 $f(x,y)$ 在闭区域 D 上连续，S 为区域 D 的面积，则在 D 上至少存在一点 $(\xi,\eta)$，使得：$$\iint_Df(x,y)\mathrm{d}\sigma=f(\xi,\eta)\cdot S$$

**解释**
+ 函数的积分，等于区域 D 上一点的函数值 $f(\xi,\eta)$ 乘以积分域的面积；

### 44.2.3 其他性质
1. 被积函数的常数因子可以提到二重积分的外面，即
$$
\int\int_Dkf(x,y)d\sigma=k\int\int_Df(x,y)d\sigma 
$$
2. 函数和 (或差)的二重积分等于各个函数二重积分的和 (或差), 即
$$
\int\int_D[f(x,y)\pm g(x,y)]d\sigma=\int\int_Df(x,y)d\sigma+\int\int_Dg(x,y)d\sigma 
$$
3. 如果在 D 上，f (x, y)=A, A 是常数，则σ为 D 的面积，则
$$
\sigma=\int\int_DA\cdot d\sigma=A\int\int_Dd\sigma 
$$
4. 如果闭区域 D 被有线条曲线分为有限个部分闭区域，则在 D 上的二重积分等于在各部分区域上
 的二重积分的和，例如 D 被分为两个闭区域 D 1 和 D2，则
$$
\int\int_Df(x,y)d\sigma=\int\int_{D_1}f(x,y)d\sigma+\int\int_{D_2}f(x,y)d\sigma 
$$
+ 几何含义：原本一个几何柱体可以一次二重积分求出来，现在将其一个柱体切分成两个柱体，然后分别对其求二重积分，求和即为完整的体积；

5. 如果 $f(x,y)$ 在区域 D 上的数值恒等于 1，则其二重积分就是
$$
\int_{D}\left(1)  d\sigma=\sigma\times1\right.
$$ 即 1 的二重积分，就是函数的面积；
