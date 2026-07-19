---
title: Lecture 5：函数极限的概念
tags:
  - 数学
  - 函数
  - 函数极限
categories: 
date: 2024-02-29
---
---
## 5.1 函数的极限
### 5.1.1 情况 1：自变量趋向于无穷大
##### **定义**： #函数趋向于正无穷
> <font color="#ccc1d9">描述：</font> $\lim_{x\to+\infty}f(x)=A$： $\forall\boldsymbol{\varepsilon}>\boldsymbol{0},\exists\boldsymbol{X}>\boldsymbol{0},\boldsymbol{当}x>\boldsymbol{X}\text{时,恒有}|f(x)-A|<\varepsilon.$

**解释**
+ 函数在 x 趋向于正无穷时的极限，和函数趋向于无穷的关系：

**函数极限和数列极限的关系**
+ ${\lim_{x\to+\infty}f(x)=A}{\rightarrow}{\operatorname*{}}\quad\lim_{u\to\infty}f(u)=A$
+ 由**函数极限可以推导出数列极限**的值，数列极限不能反过来证明函数极限的值；
+ 数列极限就是函数极限的特殊值：函数极限从 0 开始取正数，然后趋向于无穷（趋向于正无穷）；

##### **定义**： #函数趋向于负无穷
> <font color="#ccc1d9">描述：</font> $\lim_{x\to-\infty}f(x)=A$： $\forall\boldsymbol{\varepsilon}>\boldsymbol{0},\exists\boldsymbol{X}>\boldsymbol{0},\boldsymbol{当}x<\boldsymbol{-X}\text{时,恒有}|f(x)-A|<\varepsilon.$

##### **定义**： #函数趋向于无穷
> <font color="#ccc1d9">描述：</font> $\lim_{x \to \infty}f(x) = A \Leftrightarrow \forall \xi >0,\exists X>0,\lvert x \rvert >X \ \mbox{时有},\lvert f(x) - A\rvert < \xi$

**解释**
+ 意思是：x 的绝对值趋向于无穷；

##### **定理**： #函数无穷与正负无穷的关系
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\boxed{\lim_{x \to \infty}f (x)=A\begin{cases} \lim\limits_{x \to +\infty}f (x)=A\\ \lim\limits_{x \to -\infty}f (x)=A\\ \end{cases}}$

**解释**
+ 只有 $f(x)$ 的正负无穷相等时，才可以证明 $\lim_{x \to \infty}f (x)$ 存在；
+ 注意点：
	+ 在数列极限中，x 趋向于无穷 = x 趋向于正无穷；
	+ 在函数极限中，x 趋向于无穷 = x 的绝对值趋向于无穷；

### 5.1.2 情况 2：自变量趋向于有限值
##### **定义**： #自变量趋向于有限值的极限
> <font color="#ccc1d9">描述：</font> ${\lim_{x\to x_0}f(x)=A}$，$\forall\varepsilon>0,\exists\delta>0\text{,当 }0<|x-x_0|<\delta\text{ 时,恒有 }|f(x)-A|<\varepsilon.$

**解释**
+ x 趋向于靠近 $x_0$ 附近的邻域：$A-\varepsilon<f (x)<A+\varepsilon$；
+ 注意：x 趋向于 0 与 $f(x)$ 趋向于 0；
	+ $x\to x_0,\text{但}x\neq x_0$
	+ 但是对 $f(x)$ 而言，它有时是 $f(x)\rightarrow A$，有时是 $f(x)=A$，得看这一点的性质；
	+ 比如 $\lim_{x\to0}\frac{\sin x}x=1$，x 不能等于 0，但 f (x)趋向 0 后等于 1；

**结论**
+ 函数在 $x_0$ 点的极限，和函数的 $f(x_0)$ 无关；
+ $\lim_{x->x_0}f(x)与f(x_0)\text{ 无关}$，只和去心领域的定义有关；

## 5.2 单侧极限
### 5.2.1 左右极限
##### **定义**： #左极限与右极限
> <font color="#ccc1d9">描述：</font>  1. 左极限： $\lim_{x\to x_0^-}f(x)=f(x_0^-)=f(x_0-0)$；2. 右极限：$\lim_{x\to x_0^+}f(x)=f({x_0}^+)=f(x_0+0)$

+ 左极限 
$$
\lim_{x \to x_{0}^{-}}f(x) = A \Leftrightarrow\begin{cases} \hspace{1em} \forall \xi >0,\exists \delta>0,x_{0}-\delta <x<x_{0} \ \mbox{时有},\\ \hspace{1em} \lvert f(x) - A\rvert < \xi \\ \end{cases}
$$
+ 右极限
$$
\lim_{x \to x_{0}^{+}}f(x) = A \Leftrightarrow\begin{cases} \hspace{1em} \forall \xi >0,\exists \delta>0,x_{0}<x<x_{0}+\delta \ \mbox{时有},\\ \hspace{1em} \lvert f(x) - A\rvert < \xi \\ \end{cases}
$$

![[Pasted image 20240302002004.png]]
##### **定理**： #极限与单侧极限的关系
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\lim_{x\to x_0}f(x)=A\Leftrightarrow\lim_{x\to x_0^-}f(x)=\lim_{x\to x_0^+}f(x)=A$

**解释**
+ 极限存在 = 左右极限都存在；
+ 左右极限都存在**并相等** = 极限存在；

**常见需要区分左右极限的三种情况**
+ 1. 分段函数在**分界点**处的极限（在分界点的左右两侧，函数表达式不同）；
+ 2. $e^{\infty}$ 型极限（$\lim_{x\to0}e^{\frac1x},\lim_{x\to\infty}e^x,\lim_{x\to\infty}e^{-x}$）
	+ e 的指数趋向于无穷；
	+ 举例：
		+ (1) $\lim_{x\to\infty}e^x$
			+ $\begin{aligned}\lim_{x\to\infty}e^x&=+\infty\\\lim_{x\to-\infty}e^x&=0\end{aligned}$
		+ (2)  $\lim_{x\to0}e^{\frac1x}$
			+ $\lim_{x\to 0^+}e^{\frac 1 x}=+\infty$
			+ $\lim_{x\to0^{-}}e^{\frac{1}{x}}=0$
	+ 出现 e 指数是无穷时，一定要注意是正无穷还是负无穷，并需要分开讨论做右极限；
		+ 因为 $\begin{aligned}e^{+\infty}&=+\infty\\e^{-\infty}&=0\end{aligned}$
+ 3. $\arctan(\infty)$ 型极限
	+ $\lim_{x\to0}\arctan\frac{1}{x}$
	+ 例：已知 $\lim_{x\to0}\left[a\arctan\frac1x+\left(1+|x|\right)^{\frac1x}\right]$ 存在，求 a 的值；
		+ 因为出现了 $arctan \infty$ ，而且还出现了 x 的绝对值（分段函数），所以直接分左右讨论；
		+ $\begin{aligned}&\lim_{k\to0^+}\left[\arctan\frac1k+(1+x)^{\frac1k}\right]=\frac\pi2a+e\\&\lim_{k\to0^-}\left[\arctan\frac1k+(1-x)^{\frac kk}\right]=-\frac\pi2a+e^{-1}\end{aligned}$
		+ 所以 $\begin{aligned}&\color{red}{\frac\pi2}\color{red}{a+e}\\&\color{red}{||}\\&\color{red}{-\frac\pi2}\color{red}{a+e^{-1}}\end{aligned}$
		+ 可以解出 a 的值；

**补充：$\arctan$ 的定义**
+ $\tan(\arctan x)= x$
+ 图示
	+ ![[Pasted image 20240301003959.png]]
+ 表格
	+ ![[Pasted image 20240301004243.png]]

