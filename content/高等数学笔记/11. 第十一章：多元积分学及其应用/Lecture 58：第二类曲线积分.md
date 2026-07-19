---
title: Lecture 49：对坐标的曲线积分
tags:
  - 数学
  - 曲线积分
categories: 
date: 2024-02-11
---
---
## 58.1 对坐标的曲线积分
**解释**：方法选择
+ 封闭区间：
	+ 格林公式
+ 非封闭区间：
	+ 判断：看是否与路径无关 `->` 利用偏导数是否相等
	+ 是与路径无关
		+ 改换路径 
		+ 利用原函数 
	+ 不是与路径无关
		+ 直接算方便 `->` 直接算
		+ 直接算不方便 `->` 补线格林 

### 58.1.1 基本概念
 ##### **定义**： #第二类曲线积分 
> <font color="#ccc1d9">描述：</font> $$\int_{L}P(x,y)dx+Q(x,y)dy=\lim_{\lambda\to0}\sum_{i=1}^{n}[P(\xi_{i},\eta_{i})\Delta x_{i}+Q(\xi_{i},\eta_{i})\Delta y_{i}]$$

**解释**
+ 把曲线任意划分成 n 个小端，每一个有方向的小弧段在 x 轴上的投影乘以

**性质**：曲线有方向，改变方向、变符号
+ $$\int_{L(AB)}Pdx+Qdy=-\int_{L(BA)}Pdx+Qdy$$
## 58.2 计算方法
### 58.2.1 方法一：直接法
##### **定理**： #第二类曲线积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>当前参数方程为 $\begin{cases}x=\varphi(t)\\y=\psi(t)\end{cases}$，从起点 A 到终点 B 中，t 从 α 到 β：$$\int_{L}P(x,y)dx+Q(x,y)dy = \int_{\alpha}^{\beta}[p(\psi(t),\psi(t))\psi(t)+Q(\varphi(t),\psi(t))\psi^{\prime}(t)]dt$$

**解释**
+ 概念：
	+ 写出参数方程、带进去，化成定积分的计算；
+ 注意：
	+ 上下限是从起点的参数 `->` 终点的参数，而不是按照大小而来的；

### 58.2.2 方法二：格林公式
**引入**
+ 在一个平面闭区域 `D` 的二重积分上，是否可以只求边界曲线 `L` 上值得相差，而不计算曲面上的所有点的值；
+ 这个作用由格林公式达成；

##### **定义**： #单连通区域 
> <font color="#ccc1d9">描述：</font>假设在 `D` 平面区域内，`D` 内任意一闭曲线围成的部分都居于 `D`；否则则称之为复连通区域；


**解释**
+ **无洞无眼**；

##### **定理**： #格林公式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>闭区域 `D` 上由分段光滑的曲线 `L` 围成的，$P(x,y)、Q(x,y)$ 在 `D` 上有一阶连续偏导；则：
>     $$\iint_{D}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\mathrm{d}\sigma =\oint_{L}Pdx+Qdy$$


**解释**
+ 注意：
	+ 格林公式使用的范围 `->` 必须是在闭区域上：即曲线是封闭的；
	+ 正负方向是相对于当前区域而言的；
+ 其中：
	+ `L` 是区域 `D` 的正方向的边界曲线；

**补充**：补线用格林
+ 因为格林公式只能使用在封闭区域，因此当需要在非封闭区域使用时，可以进行补线，将非封闭区域补线为封闭区域，然后对封闭区域使用格林公式后再减去补线的部分，得到结果；

##### **定理**： #利用线积分与路径无关
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> $\text{i)判定:}\frac{\partial P}{\partial y}=\frac{\partial Q}{\partial x} (区域D单连通))$
> $ii)计算:$
> 	(a)改换路径：先改成更简单的（一般是沿着坐标轴的）的路径
> 	(b)利用原函数：$\int_{(x_{1},y_{1})}^{(x_{2},y_{2})}P\mathrm{d}x+Q\mathrm{d}y=F(x_{2},y_{2})-F(x_{1},y_{1})$
> 	求原函数的方法：1. 偏积分；2. 凑微分；

## 28.3 两类线积分的联系
##### **定理**： #两类线积分的联系
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\int_{L}P\mathbf{d}x+Q\mathbf{d}y=\int_{L}(P\cos\alpha+Q\cos\beta)\mathbf{d}s$$

## 28.4 计算方法：空间
### 28.4.1 直接法
##### **定理**： #第二类曲面积分的空间计算 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $设L:x=x(t),y=y(t),z=z(t),\quad t\in[\alpha,\beta]$
> $$\int_{L}P(x,y,z)dx+Q(x,y,z)dy+R(x,y,z)dz\\=\int_{a}^{\beta}\{P[x(t),y(t),z(t)]x^{\prime}(t)+Q[x(t),y(t),z(t)]y^{\prime}(t)+\\R[x(t),y(t),z(t)]z^{\prime}(t)\}dt$$

**举例**：$\text{设 }L\text{ 是柱面 }x^2+y^2=1\text{ 与平面 }y+z=0的交线，从z轴正向往z轴负向看去为逆时针方向，则曲线积分\int_{L}z\operatorname{d}x+y\operatorname{d}z$
+ 设 $x=\cos t,y=\sin t,z=-\sin t$，代入得到定积分：$I=\int_{0}^{2x}(\sin^{2}t-\sin t\cos t)dt$

### 28.4.2 斯罗克斯公式
##### **定理**： #斯托克斯公式 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\int_{L}P(x,y,z)\mathrm{d}x+Q(x,y,z)\mathrm{d}y+R(x,y,z)dz=$$![[Pasted image 20240521214413.png]]

**解释**
+ 平面时：选第一种
+ 其他时候：选第二种

