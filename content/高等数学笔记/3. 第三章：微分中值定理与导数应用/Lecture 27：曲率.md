---
title: Lecture 27：不定积分 换元积分法
tags:
  - 数学
  - 不定积分
categories: 
date: 2024-01-15
---
---
## 1.1 曲率的基本概念
**什么是曲率**
+ 字面意思：用极限来描述曲线的某一点，其弯曲的程度；
	+ 和所在的点有关；
+ 本质：描述一条曲线在不同位置点，切线夹角的变化量；
	+ ![[Pasted image 20240115203921.png]]

##### **定义**： #曲率
> <font color="#ccc1d9">描述：</font>弧 $MM^{\prime}$ 的切线转角 $\Delta\alpha$ 与该弧长 $\Delta s$ 之比的绝对值，称作该弧的平均曲率，记作：$\overline{K}=\begin{vmatrix}\frac{\Delta\alpha}{\Delta s}\end{vmatrix}$
> 当 $M^{\prime}$ 沿曲线 L 趋向于 M 时，若弧 $\overline{MM^{\prime}}$ 的平均曲率的极限存在，则称此极限为曲线 L 在点 M 处的曲率，记作 K，即：
>  $K=\lim_{M^{'}\rightarrow M}\left|\frac{\Delta\alpha}{\Delta s}\right|\text{或}K=\lim_{\Delta s\rightarrow0}\left|\frac{\Delta\alpha}{\Delta s}\right|=\left|\frac{d\alpha}{ds}\right|$
>即：$K=\frac{|y^{\prime\prime}|}{(1+{y^{\prime}}^2)^{\frac32}}$


**解释**
+ 用极限来描述曲线的某一点，其弯曲的程度；
+ 曲率：$$K=\frac{|y^{\prime\prime}|}{(1+{y^{\prime}}^2)^{\frac32}}$$
+ 曲率半径： $$R=\frac1K$$

## 1.2 曲率的常见情况
**直线**
+ 直线的曲率为 0；
+ 因为其斜率夹角的变化为 0；

**圆**
+ 圆的曲率就是： 1/半径
