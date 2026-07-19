---
title: Lecture 52：对坐标的曲面积分
tags:
  - 数学
  - 曲面积分
categories: 
date: 2024-02-12
---
---
## 60.1 有向曲面及曲面元素的投影
### 60.1.1 基本曲面分类
**双侧曲面**
+ 有两侧

**只有一侧**
+ 莫比乌斯带

**指定了侧的曲面，称之为有向曲面，其方向用法向量指向表示**
![[Pasted image 20240212153621.png]]
+ $\text{设 }\Sigma\text{为有向曲面},\text{其面元 }\Delta S\text{ 在 }xOy\text{ 面上的投影记为}\left(\Delta S\right)_{xy}$

## 60.2 第二类曲面积分：对坐标的曲面积分
##### **定义**： #第二类曲面积分
> <font color="#ccc1d9">描述：</font> $$\iint_{\Sigma}R(x,y,z)dxdy=\lim_{\lambda\to0}\sum_{i=1}^nR(\xi_i,\eta_i,\zeta_i)(\Delta S_i)_{xy}$$

**解释**
+ 注意：第二类曲面积分有方向
+ 概念：什么是曲面的方向
	+ 曲面的方向就是曲面侧向的方向，法向方向朝上、则侧朝上，法向方向朝下、则侧朝下；
+ 解释：
	+ 一点的函数值 $R(\xi_i,\eta_i,\zeta_i)$ 乘以它在 `xy` 上的投影： $(\Delta S_i)_{xy}$
	+ 如果是 $dxdy$ `->` 在 `xy` 上的投影；
	+ 如果是 $dzdx$ `->` 在 `xz` 上的投影；
+ 性质：与积分曲面的方向有关
	+ 改变曲面的方向，其值相反；
	+ $$\iint_{\Sigma}Pdydz+Qdzdx+Rdxdy=-\iint_{-\Sigma}Pdydz+Qdzdx+Rdxdy$$

## 60.3 对坐标的曲面积分的计算
### 60.3.1 直接法
##### **定理**： #第二类曲面积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. $\text{设光滑曲面 }\Sigma:z=z(x,y),(x,y){\in}D_{xy}\text{ 取上侧}R(x,y,z)\text{是 }\Sigma\text{ 上的连续函数, 则}$：
> $$\iint_{\Sigma}R(x,y,z)\operatorname{d}x\operatorname{d}y=\pm\iint_{D_{xy}}R(x,y,z(x,y))\operatorname{d}x\operatorname{d}y$$
> 2. $\text{设光滑曲面 }\Sigma:x=z(y,z),(y,z){\in}D_{yz}\text{ 取上侧}R(x,y,z)\text{是 }\Sigma\text{ 上的连续函数, 则}$：
> $$\iint_{\Sigma}P(x,y,z){\mathrm{d}y\mathrm{d}z}=\pm\iint_{D_{yz}}P[x(y,z),y,z]\mathrm{d}ydz$$
> 3. $\text{设曲面: }\Sigma:y=y (z, x),\quad (z, x)\in D_{zx}$，则：$$$$

**解释**
+ 解释：
	+ 把 `dxdy` 的二型面积分，化成了 `Dxy` 投影域上的面积分；
+ 正负号的选择：
	+ 若是在 `xy` 上投影： 
		+ 上侧做积分 `->` 正号；
		+ 下侧做积分 `->` 负号；
	+ 若是在 `yz` 上投影： 
		+ `yoz` 的前侧 `->` 正号；
		+ `yoz` 的后侧 `->` 负号；
	+ 若是在 `xz` 上投影： 
		+ `xoz` 的右侧 `->` 正号；
		+ `xoz` 的左侧 `->` 负号；
+ 注意： 
	+ 若是在 `z=f(x,y)` 时：
	+ 若 `x` 为常数 `->` 投影域就是直线，此时积分就是等于 `0`；
	+ 若 `y` 为常数 `->` 投影域也是直线，此时积分也是等于 `0`；

### 60.3.2 高斯公式 
##### **定理**： #高斯公式 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\oint\oint_{\Sigma_{\text{外}}}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}zdx+R\mathrm{d}x\mathrm{d}y=\iiint_{\Omega}\left(\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}\right)\mathrm{d}V$$

**解释**
+ 概念： 
	+ 建立一个封闭曲面外侧的二型面积分，跟这个曲面所围成区域上空间体的三重积分的关系；
	+ 实际上，它是跟曲线积分里边的格林公式是完全类似的结论；
	+ 格林公式是建立一个平面封闭曲线的的线积分和这个封闭曲线所围成区域上二重积分的关系；

**补充**：补面用高斯公式
+ 曲面不封闭时，补一个面，使用高斯公式；
+ 然后用高斯公式计算的结果 `-` 补上的部分； 

## 60.4 两类曲面积分的联系 
**概念**：两类曲面积分的联系
+ 公式：$$\iint_{\Sigma}(P\cos\alpha+Q\cos\beta+R\cos\gamma)\mathrm{d}S=\iint_{\Sigma}(P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}z\mathrm{d}x+R\mathrm{d}x\mathrm{d}y)$$
+ 解释： 
	+ 右端是一个二型面积分；
	+ 左端是一个一型面积分；
	+ $(\cos\alpha+\cos\beta+\cos\gamma)$ 是这一点上，曲面的法线向量的方向余弦；

