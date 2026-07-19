---
title: Lecture 26：函数图形的绘制
tags:
  - 数学
categories: 
date: 2024-01-15
---
---
## 1.1 描述函数图形的步骤
**具体步骤**
+ 1. 确定函数 $y= f(x)$ 的定义域，并考虑其奇偶性以及周期性；
+ 2. 求出一阶导数和二阶导数，并求出一阶导数和二阶导数为 0 以及不存在的点 `->` 找极值点和拐点、增减区间、凹凸区间；
+ 3. 列表判别增减以及凹凸区间，求出极值和拐点；
+ 4. 求渐近线；
+ 5. 确定某些特殊点，绘制图形图像；

### 1.1.1 渐近线的基本概念
##### **定义**： #曲线的渐近线
> <font color="#ccc1d9">描述：</font>
> 1）水平渐近线：若 $\lim_{x\to\infty}f(x)=A\left(\lim_{x\to-\infty}f(x)=A\right.$,或 $\lim_{x\to+\infty}\overline{f(x)=A}$)，那么 $x\to+\infty$ 或 $x\to-\infty$ 时，$y=A\text{ 是曲线 }y=f(x)\text{ 的水平渐近线}.$
> 2）垂直渐近线：若 $\lim_{x\to x_0}f(x)=\infty$ ,那么 $x=x_0$ 是 $y=f(x)$ 的垂直渐近线；
> 3）斜渐近线：若 $\lim_{x\to\infty}\frac{f(x)}x=a\mathrm{~,~}b=\lim_{x\to\infty}(f(x)-ax)\mathrm{~,~}\text{那么 }\mathrm{~}y=ax+b\mathrm{~}\text{是}$ $y=f(x)\text{ 的斜渐近线}.$

**解释**
+ 当 d ``->`` 0 时，称其为渐近线；
	+ ![[Pasted image 20240115194536.png]]

### 1.1.2 例题
**例题**：求曲线 $y=\frac{(x-1)e^x}{e^x-1}$ 的渐近线；
+ 分析
	+ 先分析是否有水平渐近线；
	+ 然后分析是否有垂直渐近线；
+ 解析
	+ 水平
		+ 当 x`->` -无穷，此时分子上的 ex 时趋向于零的，分母也是，本质上是无限乘以 0，难以判断；
		+ $\operatorname*{lim}_{x\rightarrow\infty}xe^{x}=\operatorname*{lim}_{x\rightarrow\infty}\frac{x}{e^{-x}}=\operatorname*{lim}_{x\rightarrow\infty}\frac{1}{-e^{-x}}$
	+ 垂直
		+ 因为： $\lim_{x\to 0}y=\infty$
		+ 所以 $x=0$ 为其垂直渐近线；
	+ 斜
		+ $\lim_{x\to\infty}\frac{y}{x}=\lim_{x\to\infty}\frac{(x-1)e^{x}}{x(e^{x}-1)}=\lim_{x\to+\infty}\frac{1-\frac{1}{x}}{1-\frac{1}{x}}=1=a$
		+ 斜渐近线为 $y=x-1$；
+ 题型： #求渐近线

**例题**：$\text{设 }y=\frac{x^3+4}{x^2},\text{求}$ (1) 函数的增减区间及极值；(2) 函数图像的凹凸区间及拐点；(3) 渐近线；(4) 作出其图形。 
+ 分析
	+ 按照绘制图形的顺序，依次求解；
+ 解析
	+ 1. 求定义域
		+ $\text{定义域(-,0)}\cup(0,+\infty).\text{ 当 }x=-\sqrt[3]{4}\text{ 时, }y=0$
	+ 2. 找为 0 以及不存在的点 
		+ $y^{\prime}=1-\frac8{x^3}\text{ ,故驻点为 }x=2$
		+ $y^{\prime}(0)$ 不存在
		+ 所以 $所以，$ (-\infty, 0)$ 及 $(2,+\infty)$ 为增区间，(0,2) 为减区间，$x=2$ 为极小点，极小值为 $y=3$ $
	+ 3. 求凹凸区间
		+ $y^{\prime\prime}=\frac{24}{x^4}>0$
		+  $(-\infty,0)\left(0,+\infty\right)$ 均为凹区间，无拐点；
	+ 4. 求渐近线； 
		+ 其没有水平渐近线
		+ 有垂直渐近线
			+ $\lim_{x\to0}\frac{x^3+4}{x^2}=+\infty\quad\color{red}{x=0}$
		+ 斜渐近线 
			+ $\lim_{x\to\infty}\frac yx=\lim_{x\to\infty}\frac{x^2+4}{x^3}=1=a\quad\lim_{x\to\infty}(y-ax)=\lim_{x\to\infty}\left(\frac{x^3+4}{x^2}-x\right)=0=b$
	+ 5. 画图
		+ 1. 先画渐近线
		+ 2. 从 $-\infty$ 开始，到达渐近线、增减更改的点，然后一直往 x`->` $\infty$ 走；画出全部图像；
		+ ![[Pasted image 20240115201603.png]]
+ 题型： #函数图形绘制

### 题型： #求渐近线
#### PART 1：解题方法
**判断曲线是否有渐近线**
+ 1. 判断水平渐近线 `->` 当 x `->` 无穷时，y 趋向于有限值；
+ 2. 判断垂直渐近线 `->` 当 x `->` 某一点（有限值），y 趋向于无穷；
+ 3. 判断斜渐近线 
	+ `->` $\lim_{x\to\infty}\frac{f(x)}x=a$ 有限值；
	+ `->` $\lim_{x\to\infty}(f(x)-ax)=b$ 存在
	+ 此时有斜渐近线；

**快速判断方法** 
+ 推断：
	+ 斜渐近线和函数的关系：当 x `->` 无穷时，$y=f(x)$ 和 $y=ax+b$ 的距离趋于零；
		+ ![[Pasted image 20240326174937.png]]
	+ 在 x `->` 无穷时，当 $y=ax+b+α(x)$ 中无穷小 α(x) `->` 0，则此就等于斜渐近线 $y=ax+b$，因此斜渐近线存在；
+ 总结
	+ 当函数的形式为 $y=ax+b+α(x)$ ，其中 α(x) `->` 0，则此函数有斜渐近线；


#### PART 2：典型例题

#### PART 3：知识点复盘
**注意**：当求渐近线条数时，考虑水平渐近线时，除了要考虑 x `->` 负无穷，还要考虑 x `->` 正无穷；

**注意**：题目要求分析区间（比如凹凸、增减）时，一定注意当前函数的定义范围，是否有无定义的点；
+ 1. 零不可以做分母；
+ 2. 注意 $Inx$ 的范围；
+ 3. 注意 $e^x$ 的范围；