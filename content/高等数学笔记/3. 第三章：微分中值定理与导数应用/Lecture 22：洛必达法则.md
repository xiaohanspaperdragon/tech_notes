---
title: Lecture 22：洛必达法则
tags:
  - 数学
categories: 
date: 2023-12-27
---
---
## 1.1 什么是洛必达法则
### 1.1.1 洛必达法则基本概念
**为什么需要洛必达**
+ **利用导数来计算具有不定型的极限的方法**，这一方法主要运用于分数形式的未定型极限的计算；
	+ $\underline{{f^{\prime}}}(x)$ 不严格的说，洛必达法则就是在 $0/0$ 型和 $\infty/\infty$ 型时，有 $\lim_{x\to x_0}\frac{f(x)}{g(x)}=\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}$
+ 因此，洛必达法则最犀利的是大大简化了极限运算。这种化繁为简的技术手段从来都是深受喜爱的。

**更通俗的解释**
通俗地讲，求极限的本质是分子与分母“比阶”，比谁的速度快。
就像分子分母在跑道上进行趋于0或者无穷的赛跑，我们旁观者想搞清楚他们
1. 谁赢了？（极限是大于一还是小于一？） 
2. 他们是差不多同时撞线还是领先者领先好几个身位到达终点？（同阶还是高阶？）同时撞线差了多少？（同阶的话极限到底是几？）
+ 问题在于
	+ 我们肉眼的判断能力有限，只知道两人的运动情况（函数在某点附近的表达式）。洛必达法则告诉我们，在一定的条件下，我们可以用放慢镜头的办法（分子分母公平降阶）判断出两者谁跑得快，快多少；
	+ 每求一次导相当于镜头慢了一倍，这样慢下去，两者冲线的情况最终就越来越清晰；
+ 当然这种放慢镜头的办法不是每次都灵的。如果因为技术原因慢镜头在冲线前后不能放（函数不存在一个可导的邻域），或者放了慢镜头后因为什么原因分辨不出来（洛必达完了极限反而不存在）或者他们中间摔倒了根本没有冲线（不是0比0或者无穷比无穷），那么再去放慢镜头也对知道比赛结果无济于事。

##### **定理**：洛必达法则
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若满足以下条件：
> 1）$\lim_{x\to x_0}f(x)=\lim_{x\to x_0}g(x)=0;$     
> 2）$f(x)\text{ 和 }g(x)\text{在 }\overset{\circ}{\operatorname*{U}}(x_0,\delta)\text{ 内可导,且 }g^{\prime}(x)\neq0;$
> 3）$\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}\text{ 存在(或 }\infty)$
> 若满足以上条件，则：$\lim_{x\to x_0}\frac{f(x)}{g(x)}=\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}$

**解释**
+ 简而言之，就是 0/0 型的极限；

**证明**：使用柯西中值定理
+ $\lim_{x\to x_{0}}\frac{f(x)}{f(x)}=\lim_{x\to x_{0}}\frac{f(x)-f(x_{0})}{g(x)-g(x_{0})}=\lim_{x\to x_{0}}\frac{f^{\prime}(\xi)}{g(\xi)}$
+ 因此就等于 $\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}$

**推论 1**：一些二级结论
+ $x-\sin x\sim\frac{1}{6}x^{3}$
+ ${\tan-x\sim\frac13x^3}$

**推论 2**：当 x 趋向于无穷时，增长速度：$\log_{a}x\ll x^{\alpha}\ll a^{\alpha}$

### 1.1.2 例题
**例题**：$\text{求极限}\lim_{x\to0}\frac{x^2+2\cos x-2}{\left(e^x-1\right)^2\ln(1+x^2)}$
+ 分析
	+ 当原式比较复杂时，首先应该考虑如何化简；
+ 解析
	+ 因为 $\begin{aligned}&\mathrm{e^x-1\sim x}\\&{\ln(1+x^2)\sim x^2}\end{aligned}$
	+ 所以原式= $\lim_{x\to x_0}\frac{x^{2}+2\cos x-2}{x^{4}}$
	+ 然后上下求导，得到：$\operatorname*{lim}_{x\rightarrow0}\frac{2x-2\sin x}{4x^{3}}=\frac{1}{2}\operatorname*{lim}_{x\rightarrow0}\frac{x-\sin x}{x^{3}}$
	+ 此时：
		+ 可以选择用洛必达；
		+ 可以选择用等价代换；
	+ 此时使用等价代换。得到最后结果为 1/12；

**例题**：$\text{求}\lim_{x\to+\infty}\frac{\log_ax}{x^\alpha}\text{ 与 }\lim_{x\to+\infty}\frac{x^\alpha}{a^x}.(\alpha>1,\alpha,\beta>0)$
+ 分析
	+ 此例题为**无穷比无穷型**；
	+ 也可以正常使用洛必达；
+ 解析
	+ 1. 原式= $\lim_{x\to\infty}\frac{\frac{1}{x\log a}}{x^{α-1}}=\frac{1}{x\log a}\lim_{x\to\infty}\frac{1}{x^{α}}$
	+ 2. 原式= $\lim_{x\to+\infty}\frac{αx^{α-1}}{a^{x}\log a}$
		+ 因为当前式子依然是趋向于无穷，因此依然可以使用洛必达法则，使用 $α-2$ 次
+ 结论
	+ 当 x 趋向于无穷时，增长速度：$\log_{a}x\ll x^{\alpha}\ll a^{\alpha}$

**例题**：$\text{求}\lim_{x\to0}[\frac1{\ln(1+x)}-\frac1x]$
+ 分析
	+ 此题行为**无穷减去无穷**的提醒，但是可以通过分母同分，将其转化为
	+ 无穷比无穷型，然后使用洛必达
+ 解析
	+ $\operatorname*{lim}_{x\rightarrow0}\frac{x-\ln(1+x)}{x\ln(1+x)}$ 此时从无穷减去无穷变成无穷比无穷
	+ $\lim_{x\to0}\frac{x-\ln(x+x)}{x^2}=\lim_{x\to0}\frac{1-\frac1{1+x}}{2x}=\lim_{x\to0}\frac{\frac1x}{2x}=\lim_{x\to0}\frac{\frac1{1+x}}{2}=\frac12$
+ 结论
	+ **无穷减无穷**的题目，如果有分母，可以考虑同分为**无穷比无穷**型；

**例题**：$\lim_{x\to0^+}(x)^{\sin x}$
+ 分析
	+ 分析过程：由于题目是**零的零次方**，此时
	+ 转变为**以 e 为底**的指数函数，然后接下来只算指数的部分，求指数的极限；
	+ 
+ 解析
	+ 解答过程：由原式 = $\lim_{x\to0^+}e^{\sin x\ln x}$
	+ 然后求指数的极限：$\lim_{x\to0^+}\sin x\ln x$ ，然后利用等价替换，把 sinx~x；
		+ $\lim_{x\to0^{+}}x\ln x=\lim_{x\to0^{+}}\frac{\log x}{\frac{1}{x}}=\lim_{x\to0^{+}}\frac{\frac{1}{x}}{-\frac{1}{x^{2}}}=0$
+ 结论
	+ 1. **零的零次方**型（包括 1 的无穷次方型），将其转变为**以 e 为底**的指数函数，求指数部分的极限；
	+ 2. **0 × 无穷**型，将 0 的部分变为分母，然后倒置，变成分母，变成无穷比无穷；

## 1.2 洛必达法则使用场合
### 1.2.1 使用场合
**使用分析**：$\frac00;\quad\frac\infty\infty;\quad0\cdot\infty;\quad\infty-\infty;\quad1^\infty;\quad\infty^0;\quad0^0$；
+ 其中，$\frac00;\quad\frac\infty\infty;$ 可以直接使用洛必达；
+ 然后，$\quad0\cdot\infty;\quad\infty-\infty;\quad1^\infty;\quad\infty^0;\quad0^0$ 需要先换成前两种，再使用洛必达；

**转换规则**：
+ $\mathbf{0}\cdot\infty\quad\Leftarrow\begin{cases}\mathbf{1}^{\infty}\\\infty^{0}\\\mathbf{0}^{0}&\end{cases}$
+ $\frac00,\frac\infty\infty\quad\Leftarrow\begin{cases}0\cdot\infty&\Leftarrow\begin{cases}1^\infty\\\infty^0\\0^0&\end{cases}&\end{cases}$
+ ![[Pasted image 20240111174212.png]]

### 1.2.2 注意事项
+ 1. 需要先化简
	+ 通过使用等价代换，把其换成更简单的形式；
+ 2. 注意条件 3
	+ $\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}\text{ 存在(或 }\infty)$
	+ 比如：$\operatorname*{lim}_{x\rightarrow+\infty}\frac{1-\cos x}{1+\cos x}$ 当中，因为 x->无穷时，cos x 没有意义，所以不能使用洛必达； 