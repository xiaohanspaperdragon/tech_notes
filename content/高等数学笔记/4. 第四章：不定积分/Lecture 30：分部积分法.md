---
title: Lecture 30：分部积分法
tags: 
categories: 
date: 2024-01-19
---
---
## 1.1 分部积分法
### 1.1.1 基本概念
##### **定义**： #分布积分法
> <font color="#ccc1d9">描述：</font>设 $u(x),\nu(x)$ 有连续一阶导数，则 $\int udv=uv-\int vdu$

**解释**
+ 其中：有时候是 $udv$ 简单，有时候是 $vdu$ 简单
+ v、u 的选取是其核心点；

### 1.1.2 例题
**例题**：$\int xe^xdx$
+ 分析
	+ 由于 $ex$ 的积分比较好求，所以需要考虑如何把 ex 放到 vdu 的位置上；
	+ 但也可以考虑把 x 放到 vdu 的位置上，但是要更难做一些；
+ 解析
	+ $\int xe^xdx=\int x\operatorname{de}^x=xe^x-\int e^x\operatorname{dx}$
	+ $\int\mathrm{e}^{\mathrm{x}}\mathrm{d}\mathrm{x}=\times\mathrm{e}^{\mathrm{x}}-\mathrm{e}^{\mathrm{x}}+\mathrm{d}$
+ 题型： #分部积分法

**例题**：$\int x sin xdx$
+ 分析
+ 解析
	+ 原式的等于： $-\int xdcosx=-\left[x\cos x-\int\cos dx\right]$
+ 题型： #分布积分法 

**例题**：$\int sec^3 xdx$
+ 分析
	+ 
+ 解析
	+ 原式： $\int\sec^{3}xdx=\int\sec xd\tan x=\sec xdx-\int\tan^{2}x\sin xdx$ $=\sec x\tan x-\int\sec^3xdx+\int\sec xdx$
	+ 此时，由于原式的右边也出现了一个 sec 3 xdx 的负，所以可以将其放到右边去
	+ $\int sec^3x\mathrm{~d}x=\frac12\left[secxtanx+\ln|\sec x+\ln x|\right]+\mathrm{C}$
		+ 其中的 1\2 是因为右边的 sec 移到左边去了；
+ 题型： #分部积分法 

## 1.2 分部积分法总结
**总结**
+ 概念：把之前求导时候的乘法公式过程，倒转过来，形成分布积分法；

**何时用**
+ 适用于**两类不同函数相乘**；
+ 1. $\int xe^{x}dx$
+ 2. $\int x\sin xdx$
+ 3. $\int e^{x}\sin xdx$
  
**如何用**
+ 八类典型分部积分规律；
+ 多项函数 × 指数|三角：
	+ 1. $\int p_n(x)e^{ax}\operatorname{d}x$
		+ 凑指数
	+ 2. $\int p_n(x)\sin ax\operatorname{d}x$
		+ 凑三角
	+ 3. $\int p_n(x)\cos axdx$
		+ 凑三角
+ 多项函数 × 对数|反三角：
	+ 4. $\int P_n(x)\ln xdx$
		+ 凑多项式
	+ 5. $\int P_n(x)\arctan xdx$
		+ 凑多项式
	+ 6. $\int P_n(x)\arcsin xdx$
		+ 凑多项式
+ 指数 × 三角
	+ 7. $\int e^{\alpha x}\sin\beta xdx$
		+ 凑谁都行
	+ 8. $\int e^{\alpha x}\cos\beta xdx$
		+ 凑谁都行
