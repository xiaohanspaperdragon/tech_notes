---
title: Lecture 52：傅里叶级数
tags:
  - 傅里叶级数
categories: 
date: 2024-05-16
---
**本节内容概要**
+ (一) 傅里叶系数与傅里叶级数
+ (二) 收敛定理
+ (三) 函数展开为傅里叶级数

**常考题型与典型例题**
+ 题型一：有关收敛定理的问题
+ 题型二：将函数展开为傅里叶级数
---
## 52.0 基础知识 
#### 三角函数的正交性
**概念**：三角函数的正交性
+ 概念：三角函数系集合 
	+ $(0,1,\sin x,\cos x,\sin 2x,\cos 2x...)$
+ 正交性： 
	+ 两个函数的内积，积分为 0 时、表述两个函数正交
+ 三角函数的正交性： 
	从三角函数系中，取两个不同的、范围在 $[-\pi,\pi]$ 上的函数进行内积，得到的积分为 0；
+ 举例： 
	+  不同时：
		+ $$\int_{-\pi}^{\pi}\sin nx \cos mx \mathrm{d}x =0\quad n\neq m$$
		+ $$\int_{-\pi}^{\pi}\sin nx\sin mxdx=0\quad n\neq m$$
	+ 相同时： 
		+ $$\int_{-\pi}^{\pi}\cos nx·\cos nx dx=\pi $$

**概念**：周期为 $2\pi$ 的函数展开 
+ 用函数表达周期为 $2\pi$ 的函数  
	+ $$f(x) = \sum_{n=0}^{\infty}a_{n}\cos nx + \sum_{n=0}^{\infty}b_{n}\sin x$$
	+ 把 `n=0` 拿出来：$$=a_{0}\cos 0x+\sum_{n=1}^{\infty}a_{n}\sin x+b_{0}\sin 0x+\sum_{n=1}^{\infty}b_{n}\sin nx$$
	+ 即得到 $$a_{0} + \sum_{n=1}^{\infty}a_{n}\cos nx+\sum_{n=1}^{\infty} b_{n}\sin nx$$
	+ 且 $$a_{0} = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x) dx$$
+ 求系数： 
	+ ![[Pasted image 20240904144914.png]]
	+ $$a_{n}=\frac{1}{\pi}\int_{-\bar{n}}^{\pi}f(x)\cos nx dx$$


## 52.1 傅里叶系数与傅里叶级数 
### 52.1.1 基本概念
##### **定义**： #傅里叶系数
> <font color="#ccc1d9">描述：</font> $$a_{n}=\frac1\pi\int_{-\pi}^xf(x)\cos nx\mathrm{d}x\quad n=0,1,2\cdots\quad\quad\\b_{n}=\frac1\pi\int_{-\pi}^xf(x)\sin nx\mathrm{d}x\quad\quad n=1,2\cdots $$

**解释**
+ 可以利用上述公式，来求给定 n 式的系数；

##### **定义**： #傅里叶级数
> <font color="#ccc1d9">描述：</font>`f` 的傅里叶级数：$$f(x)\sim\frac{a_0}2+\sum_{n=1}^\infty(a_n\cos nx+b_n\sin nx)$$

**解释**
+ 概念：
	+ 以上式子是否能展开、取决于上述式子中的 `~` 是否能写成等号；
	+ 而其是否能展开、需要使用收敛定理来判断；
+ 解释：
	+ `~`
		+ 意味着除开某些有限点外（间断点、端点），其他点都符合公式中的性质；
	+ $\frac{a_0}2$
		+ 在波动当中，表示直流分量；
	+ $(a_n\cos nx+b_n\sin nx)$：
		+ 在波动当中，表示交流分量；
		+ 注意：偶函数展开式只有余弦项，奇函数展开式只有正弦项；
+ 作用：
	+ 比如：
		+ 原本一个代表高低电平的信号，此时可以使用一个 `sinx` 来逼近它；
		+ 加一个 `sinx` 时是 `1 harmonic`，加三个 `sinx` 时是 `3 harmonic`，越加越多时、其值越来越接近谐波；
	+ 总结：
		+ 此例子体现了傅里叶级数的作用：用一个周期的级数展开式，来逼近一个周期性的量：
	+ 图示：
		+ ![[Pasted image 20240517001116.png]]

### 52.1.2 收敛定理
##### **定理**： #狄利克雷定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 设 $f(x)$ 在 $[-\pi,\pi]$ 上连续或有有限个第一类间断点，且只有有限个极值点，则 $f(x)$ 的傅里叶级数在 $[-π,π]$ 上处处收敛，且收敛于： 
> $$1)\quad S(x)=f(x)\quad\text{当}x\text{ 为 }f(x)\text{ 的连续点}.$$
> $$2)\quad S(x)=\frac{f(x^-)+f(x^+)}2\quad\text{当 }x\text{ 为 }f(x)\text{ 的间断点}.$$
> $$3)\quad S(x)=\frac{f((-\pi)^+)+f(\pi^-)}2\quad\text{当 }x=\pm\pi.$$

**解释**
+ 概念：
	+ 核心：
		+ 此定理揭示了傅里叶级数能够展开的前提条件：除开收敛到**端点**和**有限个间断点**外，其他都是收敛**连续**函数 $f(x)$ `->` 几乎处处收敛为 `f(x)`；
	+ 解释：
		+ （1） `->` 连续点时，展开后的级数就是收敛于函数 `f(x)`；
		+ （2） `->` 间断点时，展开后的级数收敛于间断点的左右函数值的平均值；
		+ （3） `->` 左右端点时，展开后的级数收敛于两个端点的平均值；
+ 作用：
	+ 将函数展开为傅里叶级数的要求更低；
	+ 在幂级数当中，需要函数为可导、可积，而在傅里叶级数这里只需要函数连续 `->` 适用范围更广；
+ 适用范围对比：
	+ 傅里叶级数 `->` 主要作用于研究周期性的量，如工程领域里面的波动理论；
	+ 幂级数 `->` 主要用于数值计算，如微积分当中；

## 52.2 函数展开为傅里叶级数 
**目的**：研究函数展开为傅里叶级数时，系数的情况

### 52.2.1 周期函数的展开：特殊情况
**概念介绍**：周期为 $2\pi$ 的函数展开
+ （1）在 $[-\pi,+\pi]$ 上展开：一般展开
	+ $$a_{n}=\frac1\pi\int_{-\pi}^xf(x)\cos nx\mathrm{d}x\quad n=0,1,2\cdots\quad\quad\\b_{n}=\frac1\pi\int_{-\pi}^xf(x)\sin nx\mathrm{d}x\quad\quad n=1,2\cdots $$
+ （2）在 $[-\pi,+\pi]$ 的展开：奇偶函数的展开
	+ 1. $f(x)$ 为奇函数：
		+ $$a_{n}=0\quad n=0,1,2\cdots\quad\quad\\b_{n}=\frac2\pi\int_{0}^xf(x)\sin nx\mathrm{d}x\quad\quad n=1,2\cdots $$
		+ 解释：因为 $\cos x$ 是偶函数，并且在 $a_n$ 中，所以当 $f(x)$ 为奇函数时，`奇函数*偶函数=奇函数`，所以 $a_n$ 变为 0，$b_n$ 变为两倍。其他情况同理；
	+ 2. $f(x)$ 为偶函数：
		+ $$a_{n}=\frac2\pi\int_{0}^xf(x)\cos nx\mathrm{d}x\quad n=0,1,2\cdots\quad\quad\\b_{n}=0\quad\quad n=1,2\cdots $$
+ （3）在 $[0,+\pi]$ 上展开：展开为正弦或余弦
	+ 分析：
		+ 这种是在半个周期上的展开，所以在分析时，需要做**延拓**；
		+ 奇函数展开：只有正弦项。因为如果只给了 $[0,+\pi]$ ，则如果需要在 $[-\pi,+\pi]$ 上做奇函数展开、只有正弦项 `->` **奇延拓**；
		+ 在展开为正弦时，理论上需要做奇延拓，但实际上直接使用奇函数的展开式即可；
		+ 同理偶延拓；
	+ 1. 展开为正弦：
		+ $$a_{n}=0\quad n=0,1,2\cdots\quad\quad\\b_{n}=\frac2\pi\int_{0}^xf(x)\sin nx\mathrm{d}x\quad\quad n=1,2\cdots $$
	+ 2. 展开为余弦：
		+ $$a_{n}=\frac2\pi\int_{0}^xf(x)\cos nx\mathrm{d}x\quad n=0,1,2\cdots\quad\quad\\b_{n}=0\quad\quad n=1,2\cdots $$

### 52.2.2 周期函数的展开：一般情况 
**概念介绍**：周期为 $2l$ 的函数展开
+ （1）在 $[-l,+l]$ 上展开
	+ $$a_n=\frac1l\int_{-l}^lf(x)\cos\frac{n\pi x}l\mathrm{d}x\quad\quad n=0,1,2\cdots\quad\quad \\b_n=\frac1l\int_{-l}^lf(x)\sin\frac{n\pi x}l\mathrm{d}x\quad\quad n=1,2\cdots $$
+ （2）在 $[-l,+l]$ 上展开：奇偶函数
	+ $$\text{i)}f(x)\text{ 为奇函数}.\quad\quad \\a_n=0,n=0,1,2\cdots\quad\quad \\b_n=\frac2l\int_0^lf(x)\sin\frac{n\pi x}l\mathrm{d}x\quad\quad n=1,2\cdots $$
	+ $$\begin{aligned}&\text{ii)}f(x)\text{ 为偶函数}.\\&{a_n}=\frac2l\int_0^lf(x)\cos\frac{n\pi x}l\mathrm{d}x&&n=0,1,2\cdots\\&b_{n}=0&&n=1,2\cdots\end{aligned}$$
+ （3）在 $[0,l]$ 上展开：展开为正弦或余弦
	+ $$\begin{aligned}&\text{i)展为正弦}\\&a_{n}=0,&&n=0,1,2\cdots\\&b_{n}=\frac2l\int_0^lf(x)\sin\frac{n\pi x}l\mathrm{d}x&&n=1,2\cdots\end{aligned}$$
	+ $$\begin{aligned}&\text{ii)展为余弦.}\\&a_{n}=\frac{2}{l}\int_{0}^{l}f(x)\cos\frac{n\pi x}{l}\mathrm{d}x&n=0,1,2\cdots\\&b_{n}=0&n=1,2\cdots\end{aligned}$$

## 52.3 常考题型 

---
### 题型： #狄利克雷收敛定理
#### PART 1：解题方法
**题型**：已知 $b_n$ 和 $S(x)$ 的函数，求在某点处、$S(x)$ 收敛于什么值
+ 概念：因为需要求收敛于和函数的什么位置，所以需要先使用收敛定理判断、是否满足收敛定理的条件；
+ 注意：如果是在 $(0,l)$ 或 $(0,\pi)$ 上时，注意是否要延拓；

#### PART 2：典型例题

#### PART 3：知识点复盘


---
### 题型： #将函数展开为傅里叶级数
#### PART 1：解题方法
**知识点**：展开傅里叶级数的步骤
+ 1. 求 $a_0$ 、算系数，写出其傅里叶级数：$\frac{a_0}2+\sum_{n=1}^\infty(a_n\cos nx+b_n\sin nx)$；
+ 2. 利用收敛定理，判断傅里叶级数在哪些地方可以和原函数画等号，哪些不能、收敛到什么地方；

#### PART 2：典型例题 
**例题**：将 $f(x)=x-1$  `(x<=x<=2)` 展开为周期为 `4` 的余弦级数；
+ 分析
	+ 因为 `T=4` `->` $l=2$
+ 解析
	+ 第一步：写出傅里叶级数
		+ $$a_0=\frac22\int_0^2(x-1)dx=0$$
		+ $$a_n=\frac22\int_0^2(x-1)\cos\frac{n\pi x}2dx=\frac2{n\pi}\int_0^2(x-1)d\sin\frac{n\pi x}2=-\frac2{n\pi}\int_0^2\sin\frac{n\pi x}2dx \left.=\frac4{n^2\pi^2}[\left(-1\right)^n-1]=\left\{\begin{matrix}0,&n=2k,\\-\frac8{\left(2k-1\right)^2\pi^2},&n=2k-1\end{matrix}\right.\right.(k=1,2,\cdots).$$
		+ $$f(x)=-\frac8{\pi^2}\sum_{n=1}^\infty\frac1{\left(2n-1\right)^2}\cos\frac{(2n-1)\pi x}2$$
+ 注意： 
	+ 用收敛定理，是在延拓之后的 $(-l,+l)$ 函数上进行的；

#### PART 3：知识点复盘
**知识点**：求常数项级数的和 `->` 三种方法；
+ （1）常数项级数的定义；
+ （2）幂级数；
+ （3）傅里叶级数；