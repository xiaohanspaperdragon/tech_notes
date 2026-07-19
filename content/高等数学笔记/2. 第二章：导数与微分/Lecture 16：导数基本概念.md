---
title: Lecture 16：导数基本概念
tags:
  - 数学
  - 导数
categories: 
date: 2023-12-13
---
## 本章常考题型与典型例题
**考试内容**
 + 1. 导数与微分的概念（难点）
 + 2. 导数公式与求导法则（重点）
 + 3. 高阶导数（难点）

**典型例题**
+ 题型一：导数定义 （难点）
+ 题型二：复合函数、隐函数、参数方程求导（重点） 
+ 题型三：高阶导数 （难点）
+ 题型四：导数应用

---
## 1.1 导数的定义
### 1.1.1 基本概念
**为什么需要导数**
导数的本质对于一个点应变量增量与自变量增量的极限，这也就是反应了：在这个点，**应变量随着自变量变化的速度**；
+ 导数就是一个特殊的极限，其实质是一个平均变化率，当范围无穷小时，表达了这一点的变化率；

##### **定义**： #什么是导数
> <font color="#ccc1d9">描述：</font> $\begin{aligned}\text{若 }&\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}&\text{存在，则称 }f(x)\text{ 在 }x_0\text{ 点可导}.\end{aligned}$
> 另一种形式：$f^{\prime}(x_0)=\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0}\frac{f(x)-f(x_0)}{x-x_0}$
> 形式一：$f^{\prime}(x_0)=\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}$
> 形式二：$f^{\prime}(x_0)=\lim_{x\to x_0}\frac{f(x)-f(x_0)}{x-x_0}$

**解释**
+ 等价形式：
	+ 因为 $x_0+\Delta x=x\quad\Delta x=x-x_0.$
	+ 所以 $f^{\prime}(x_0)=\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0}\frac{f(x)-f(x_0)}{x-x_0}$
	+ 其他形式：$f^{\prime}(x_0)=y^{\prime}|_{x=x_0}=\frac{dy}{dx}|_{x=x_0}$
+ 注意：
	+ 1. 一点的导数和 $f(x_0)$ 有关；
	+ 2. $f(x_0)$ 是一个定点，$f(x)$ 是一个动点；
	+ 3. 若极限不存在，则称 $f(x)$ 在 $x_{0}$ 处不可导； 
	+ 4. 若极限为无穷大，则称 $f(x)$ 在 $x_{0}$ 处导数为无穷大（导数为无穷，为不可导）.

**什么是可导**
+ $\frac{dy}{dx}=k$ 。也就是 $\Delta y$ 和 $\Delta x$ 的比值；
+ 若能求出值，就是可导，若不能，就是不可导。

**推导**：假设当前距离函数为 $d(s)=t^3$，当前导数为 $v(t)$，设 $t=3$
+ 对一点附近的变化率推导：$\begin{gathered}\text{Derivative}\\\frac{ds}{dt}(t)=\underbrace{\frac{s(t+dt)-s(t)}{dt}}_{dt\to0}\end{gathered}$
+ 假设在 $t=2$ 的点，求这一点的切线：$\begin{aligned}\frac{ds}{dt}(2)=\frac{\left(2+dt\right)^3-\left(2\right)^3}{dt}\end{aligned}$
+ 此时将 $(2+dt)^3$ 展开，得到：$\begin{aligned}\frac{2^3+3(2)^2dt+3(2)(dt)^2+(dt)^3-2^3}{dt}\end{aligned}$
+ 将其除以 $dt$ 后，得到：$3(2)^2+3(2)(dt)+(dt)^2$
+ 此时，当 $dt$ 趋向于无穷小时，得到： $\frac{ds}{dt}(2)=3(2)^2=12$
+ 如果将当中的 $t=2$ 变为一般式 $t=t$，则可得到：$\frac{ds}{dt}(t)=3(t)^2$

##### **定义**： #左导数与右导数
> <font color="#ccc1d9">描述：</font> $\begin{aligned}&\text{ 左导数: }f_0^{\prime}(x_0)=\lim_{\Delta x\to0^-}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0^-}\frac{f(x)-f(x_0)}{x-x_0}\\&\text{ 右导数: }{f_0^{\prime}(x_0)}=\lim_{\Delta x\to0^+}\frac{f(x_0+\Lambda x)-f(x_0)}{\Delta x}=\lim_{x\to x_0^+}\frac{f(x)-f(x_0)}{x-x_0}\end{aligned}$

**解释**
+ 左导数的函数下面要加负号
+ 右导数的函数下面要加正号

##### **定理**： #左右导数与导数的关系
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $f^{\prime}(x_0)=a\Leftrightarrow f_-^{\prime}(x_0)=f_+^{\prime}(x_0)=a$

**解释**
+ 左右导数的关系：可导 `<-->` **左右导数存在且相等**；

##### **定义**： #区间上可导
> <font color="#ccc1d9">描述：</font>区间上可导 = 区间上的每一点都具有导数；
> 1. $(a,b)$ ：区间上每一点可导；
> 2. $[a,b]$  ：区间上每一点可导，并且 a 点右可导，b 点左可导；


## 1.2 导函数的定义与证明
**区间上可导**
在一个区间内每个点都有导数，称之为区间内可导；
这个导数构成的函数，称之为函数的导函数；

**导函数** 
$f^{\prime}(x)\quad x\in I$

### 1.2.1 证明函数的导数
**题目：**$\left(a^x\right)^{\prime}=a^x\ln a\left(a>0,a\neq1\right)$
+ 证明过程：
	+ $\lim_{\Delta x\to0}\frac{a^{x+\Delta x}-a^x}{\Delta x}=\lim_{\Delta x\to0}\frac{a^x\left[a^{\Delta x}-1\right]}{\Delta x}=a^x\ln a$
+ 其中，第二步的直接变成 lna 的步骤，因为有此等价极限：$\lim_{x\to0}\frac{a^x-1}{x}=\ln a$

**题目**：$(\sin x)^{\prime}=\cos x$
+ 证明过程：
	+ $\lim_{\Delta x\to0}\frac{\sin(x+\Delta x)-\sin x}{\Delta x}=\lim_{\Delta x\to0}\frac{2\sin\frac{\Delta x}{2}\cos\frac{2x+\Delta x}{2}}{4x}$
+ 因为 sinx~x，所以：
	+ $\operatorname*{lim}_{\Delta x\rightarrow0}\frac{2-\frac{\Delta x}{2}\sin\frac{2x+\Delta x}{2}}{\Delta x}=\cos x$

### 1.2.2 导函数的几何意义
**导函数与切线**
+ 定义：
	+ 导数 $f^{\prime}(x_0)$ 在几何上，表示为曲线 $y=f(x)$ 在点 $\left(x_0,f(x_0)\right)\text{处切线的斜率}$
+ 切线与法线：
	+ 切线方程：$y-y_{0}=f^{\prime}(x_{0})(x-x_{0})$
	+ 法线方程：$y-y_0=-\frac1{f^{\prime}(x_0)}(x-x_0)$
+ 图示：
	+ ![[Pasted image 20240314175211.png]]

**导数与切线**
+ 可导一定有切线；
+ 有切线不一定可导；

## 1.3 常考题型

### 题型： #分段函数在分界点讨论可导性
**题型一**：左右导数是否存在
+ 比如在分段函数当中，要求分析在某一点处的左右导数是否存在；
+ 方法：利用定义
+ 一点左导数存在： $f_0^{\prime}(x_0)=\lim_{\Delta x\to0^-}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0^-}\frac{f(x)-f(x_0)}{x-x_0}$
	+ 带入 $x_0$ 点后，计算这一点极限，然后看其值是否等于导数值，导数值是否存在；

**注意**：分段函数，求导导数带值，需要带到点被定义的点，比如 x=1 是分界点，小于等于 1 和大于 1 当中，小于等于 1 的函数部分可以带值；


### 题型： #导数定义
#### PART 1：解题方法
**特点**：出现了类似于 $f^{\prime}(x_0)=-1$ 一点导数存在这种形式，经常考察的是一点的导数定义的题目；

**核心思想**：把当前导数凑成一下类似于导数定义的形式；
+ 形式：$f^{\prime}(x_{0})=\lim_{方框\to0}\frac{f(x_{0}+方框)-f(x_{0})}{方框}$
+ 除法当中的分子式是一个动、一个定，因此要凑成这种形式；
+ 补充：条件解析
	+ 当出现 $x=0\text{ 处可导,且 }f(0)=0$ 时，要用到导数在 0 点的定义式；

**类似题型**：导数零点判定性问题
+ 举例：$\text{下列函数中,在 }x=\mathbf{0}\text{ 处不}\text{可导的是}$
+ 常用结论：设 $f(x)=A(x)x-a$，其中 $A(x)$ 在 x=a 处连续，则 $f(x)$ 在 x=a 处可导的充要条件为：$A(x)=0$

**类似题型**：有类似于导数的定义 $\lim_{方框\to0}\frac{f(x_{0}+方框)-f(x_{0})}{方框}$，此时问某点是否可导；
+ 解题：需要在**方框趋向于 0 正以及 0 负, 并且方框不等于 0**的情况下都可以存在，此时才可以推出这一点导数存在；

#### PART 2：典型例题
**例题**：$\text{已知 }f^{\prime}(x_0)=-1,\text{则}\lim_{x\to0}\frac x{f(x_0-2x)-f(x_0-x)}=？$
+ 分析
	+ 凑成导数定义的形式；
	+ 也可以使用具体函数来带入求值（因为是填空题）；
+ 解析
	+ $\lim_{x\to0}\frac{f(x_{0}-2x)-f(x_{0}-x)}{x}=\lim_{x\to0}\frac{f(x_{0}-2x)-f(x_{0})}{-2x}\cdot\frac{-2x}{x}-\lim_{x\to0}\frac{f(x_{0}-x)-f(x_{0})}{-x}\cdot\frac{-x}{x}$
+ 题型： #导数定义 

**例题**：$\text{已知 }f(x)\text{ 在 }x=0\text{ 处可导,且 }f(0)=0,\text{则}\quad\lim_{x\to0}\frac{x^2f(x)-2f(x^3)}{x^3}$ =？
+ 分析
+ 解析
+ 题型：#

#### PART 3：知识点复盘
**注意**：`导数存在 -> 导数定义的极限存在` 和 `导数定义存在 -> 导数存在` 这两个不是一个问题；
+ 导数存在 `->` 导数定义的极限存在：证明这个极限存在几个；
+ 导数定义存在 `->` 导数存在：需要证明在方框趋向于 0 正以及 0 负, 并且方框不等于 0 这三个情况下都存在，才可以证明导数存在；

### 题型： #导数应用
#### PART 1：解题方法
**题型 1**：导数的几何意义
+ 求切线的斜率：$k_{切}=\frac{dy}{dx}$
+ 求法线的斜率：$k_{法}=-\frac1{k_{切}}$

**题型 2**：相关变化率
+ 1. 建立相关量之间的关系；
+ 2. 式子两边对 t 求导；

#### PART 2：典型例题
**例题**：$\left.\text{曲线 }\left\{\begin{aligned}x&=\arctan t,\\y&=\ln\sqrt{1+t^2},\end{aligned}\right.\text{ 上对应于 }{t=1}\right.$ 的点处的法线方程
+ 分析
+ 解析
+ 题型：#

## 1.4 导数推导
**距离与速度举例**
+ s 为 $s(t)$
+ 距离与速度关系 
	+ ![[Pasted image 20240324194344.png]]
+ 变化量：
	+ ![[Pasted image 20240324194646.png]]
+ 对一点附近的变化率推导：$\begin{gathered}\text{Derivative}\\\frac{ds}{dt}(t)=\underbrace{\frac{s(t+dt)-s(t)}{dt}}_{dt\to0}\end{gathered}$
+ 假设在 $t=2$ 的点，求这一点的切线：$\begin{aligned}\frac{ds}{dt}(2)=\frac{\left(2+dt\right)^3-\left(2\right)^3}{dt}\end{aligned}$
+ 此时将 $(2+dt)^3$ 展开，得到：$\begin{aligned}\frac{2^3+3(2)^2dt+3(2)(dt)^2+(dt)^3-2^3}{dt}\end{aligned}$
+ 将其除以 $dt$ 后，得到：$3(2)^2+3(2)(dt)+(dt)^2$
+ 此时，当 $dt$ 趋向于无穷小时，得到： $\frac{ds}{dt}(2)=3(2)^2=12$
+ 如果将当中的 $t=2$ 变为一般式 $t=t$，则可得到：$\frac{ds}{dt}(t)=3(t)^2$
