---
title: Lecture 23：泰勒公式
tags: 
categories: 
date: 2024-01-12
---
---
泰勒公式的作用：建立高阶导数和函数之间的关系，使用高阶导数研究函数；
## 1.1 什么是泰勒公式
+ 科普文：[(99+ 封私信 / 85 条消息) 如何通俗地解释泰勒公式？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/21149770)
**什么是泰勒公式**
+ 本质：就是用多项式函数，去逼近光滑函数
+ 解释：复杂的方程用一系列简单可计算的方程近似模拟。比如把求一个无规律的图形的面积变成、转化成求一系列（很多个）正方形的面积，然后加在一起；

### 1.1.1 泰勒公式定义
##### **定理**：泰勒定理 - 带 Peano 余项
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 带有 Peano 余项的泰勒公式： $\text{设}f(x)\text{ 在 }x_0\text{ 处 }n\text{ 阶可微,则}$ $$f(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k+o((x-x_0)^n)$$
	

**解释**
+ 意义：
	+ 把一个一般函数，写成一个 `一般多项式+余项`；
+ 余项：   
	+ $$P_n(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k$$
+ $f(x)$ 在 $x_{0}$ 处的 n 次 Taylor 多项式：
	+ $$R_n(x)=o((x-x_0)^n)$$
+ 缺点：
	+ 1. 只能给出余项的定性描述，不能做定量的分析； 
	+ 2. 只能在 x 0 临近时，才能用，远处无法使用；

**补充**
+ 首先是函数和微分的关系
	+ $\text{若 }f(x)\text{ 在 }x_0\text{ 处可微,则 }\Delta y\approx dy$
	+  $f(x)\approx f(x_0)+f^{\prime}(x_0)(x-x_0)$
+ 此时是约等于，因为在几何上，$f^{\prime}(x_0)(x-x_0)$ 实际上是使用直线来模拟曲线的值；
+ 所以可以在进行一次微分，用高阶无穷小进一步近似曲线的值，即 f (x)的值
	+ $f(x)=f(x_0)+f^{\prime}(x_0)(x-x_0)+o(x-x_0)$
+ 若 $f(x)$ 在 $x_0$ 处 n 阶可导，是否存在 n 次多项式  $P_n(x)=a_0+a_1(x-x_0)+a_2(x-x_0)^2+\cdots+a_n(x-x_0)^n$ 使得：
	+  $f(x)=P_n(x)+o((x-x_0)^n)$
+ 因此，可得 $a_0=f(x_0),\quad a_k=\frac{f^{(k)}(x_0)}{k!}\quad k=1,2\cdots n$
+ 所以：$P_n(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k$

##### **定理**：泰勒公式 - Lagrange
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }f(x)\text{ 在区间 }I\text{ 中 }n+1\text{ 阶可导},$ $x_0\in I,\text{ 则 }\forall x\in I,\exists\xi\in I\quad(\xi\text{ 在 }x_0\text{ 与 }x\text{ 之间),使}$ $$f(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}\big(x-x_0\big)^k+\frac{f^{(n+1)}(\xi)}{(n+1)!}\big(x-x_0\big)^{n+1}$$ 
> 带有拉格朗日余项的泰勒公式：
> $$R_{n}(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_{0})^{n+1}$$

**解释**
+ 给出了余项的具体表达式
+ 可以在给定条件下，进行定量分析；
	+ 可以保证误差，在 x 0 趋向于 0 时，误差为零；

**推论 1**：零点的泰勒公式
$\begin{gathered}\text{若 }x_0=0\text{ , 则} \\F (x)=f (0)+f^{\prime}(0) x+\frac{f^{\prime\prime}(0)}{2!}x^2+\cdots+\frac{f^{(n)}(0)}{n!}x^n+\frac{f^{(n+1)}(\theta x)}{(n+1)!}x^{n+1} \\上式称为  f (x)\text{ 的 Maclaurin 公式} \end{gathered}$

**推论 2**：几个初等函数的 Maclaurin 公式
+ $e^x=1+x+\frac{x^2}{2!}+\cdots+\frac{x^n}{n!}+\frac{x^{n+1}}{(n+1)!}e^{\theta x}\quad\quad x\in(-\infty,+\infty)$
	+ 因为 e 的导数还是自己，就是各阶导数就使用 1 带进去；
+ $\sin x=x-\frac{x^3}{3!}+\cdots+\left(-1\right)^{m-1}\frac{x^{2m-1}}{\left(2m-1\right)!}+\left(-1\right)^m\frac{\cos\theta x}{\left(2m+1\right)!}x^{2m+1}$
+ $\begin{aligned}(1+x)^\alpha&=1+cx+\cdots+\frac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!}x^n\\&+\frac{\alpha(\alpha-1)\cdots(\alpha-n)(1+\beta x)^{x-n-1}}{(n+1)!}x^{n+1}\quad x\in(-1,+\infty)\end{aligned}$

## 1.2 内容小结
### 1.2.1 共同点
**共同点**
+ 1. 使用多项式的简单函数来逼近一般函数；
+ 2. 函数和高阶导数联系起来；
+ 结论：
	+ 1. 当题目当中是需要**研究高阶导数时**，经常要使用泰勒公式；
	+ 2. 如果研究的是局部性态 `->` Peano 余项的泰勒公式；
	+ 3. 如果研究的是全局性态 `->` Lagrange 余项的泰勒公式

**核心**：两个泰勒公式，都是把 f(x)写成 **一个多项式 + 一个余项**；
+ Peano 余项
	+ $R_n(x)=o((x-x_0)^n)$
+ Lagrange 余项
	+ $R_n(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}$

**本质**：使用多项式，来逼近 f (x)的值 `->` 用已知点信息，表示未知点；
+ 为什么？因为多项式的求解简单

### 1.2.2 两种泰勒公式使用情况分析
**不同点**
+ 余项不同

**Peano**：定性、局部的描述 `->` 研究函数的局部形态，使用 Peano 公式
+ 1. 研究函数趋向于一点的极限；
+ 2. 研究函数的极值；

**Lagrange**：定量，整体的描述
+ 1. 研究最大/最小值；
+ 2. 证明不等式 `->` 研究一个区间；

**补充**：拉格朗日中值定理时泰勒定理的特例；
+ 四大中值定理：
	+ 前三个建立 $f(x)$ 和一阶导数的关系；
	+ 泰勒定理研究 $f(x)$ 和高阶导数的关系
+ 共同点：研究函数和导数的关系，为**使用导数研究函数奠定基础**；

## 1.3 例题
**例题**：$\text{求极限 }\lim_{x\to0}\frac{\cos x-e^{-\frac{x^2}2}}{x^4}$
+ 分析
	+ 0/0 型，但是无法使用洛必达
	+ 所以可以考虑使用泰勒
	+ 因为是极限，所以使用局部泰勒公式
	+ 因为 x 是四次方，所以写成四项；
+ 解析
	+ 解答过程：
	+ $cos x=1-\frac{x^2}{2!}+\frac{x^4}{4!}+o\left(x^4\right)$
	+ 因为：
		+ $\mathbb{e}^x=1+x+\frac{\mathbb{x}}{2_1^2}$
		+ 得：$e^{-\frac{X^{2}}{2}}=1-\frac{X^{2}}{2}+\frac{1}{2!}\left(-\frac{X^{2}}{2}\right)^{2}+o(X^{4})$
	+ 所以有原式 = 
		+ $\operatorname*{lim}_{x\rightarrow0}\frac{-\frac{1}{12}x^{4}+0(x^{4})}{x^{4}}=-\frac{1}{12}$
