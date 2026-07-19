---
title: Lecture 33：定积分的应用
tags:
  - 数学
  - 反常积分
categories: 
date: 2024-01-24
---
---
## 常考题型与典型例题
**常考内容**
+ (一)无穷区间上的反常积分
+ (二)无界函数的反常积分

**常考题型与典型例题**
+ 题型一：反常积分的敛散性
+ 题型二：反常积分的计算

## 1.1 无穷限的的反常积分
### 1.1.1 基本概念
**引入**
+ 定积分的基本条件：$[a,b]$ 有限，且 $f(x)$ 有界；
+ 当需要求从 $a$ 到无限的积分时：$\int_{a}^{+\infty}f(x)dx$
+ 此时可以先设一个 $b$，然后让 b 趋向于极限；

##### **定义**： #反常积分
> <font color="#ccc1d9">描述：</font>积分区间无限或被积函数无界的积分，称为反常积分；又称之为广义积分；

**解释**
+ 当趋于无限时，极限有值，则称积分收敛；

**上下界都是无穷时**
+ 求 ：从负无穷到正无穷的所有值：
	+ $\int_{-\infty}^{+\infty}f(x)dx=\int_{-\infty}^{0}f(x)dx+\int_{0}^{+\infty}f(x)dx$
	+ 必须这两个极限都存在、都收敛，此时当前上下界反常积分才收敛；

**推论：广义牛顿-莱布尼茨公式**
+ $\int_{-\infty}^{+\infty}f(x)dx=F(x)|_{-\infty}^{+\infty}$

##### **定义**： #无穷区间上的反常积分
> <font color="#ccc1d9">描述：</font> 
> 1. 定义一： $$\int_{a}^{+\infty}f(x)dx=\lim_{t\to+\infty}\int_{a}^{t}f(x)dx$$ 若这个极限存在，则称这个反常积分是收敛的；反之则为发散的；
> 2. 定义二：$$\int_{-\infty}^{b}f(x)dx=\lim_{t\to-\infty}\int_{t}^{b}f(x)dx$$ 与定义一同理；
> 3. 定义三：$$\int_{-\infty}^{+\infty}f(x)dx=\int_{-\infty}^{0}f(x)dx+\int_{0}^{+\infty}f(x)dx$$ 若这两个都收敛，则收敛；否则发散；

**解释**
+ 无穷区间上的积分，使用**有穷区间上积分的极限来定义**的；
+ 收敛时可以求值；

### 1.1.2 计算方法
##### **定理**： #比较判别法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>用于判断反常积分的敛散性；
> $$\text{设 }f (x), g (x)\text{ 在 }[a,+\infty)\text{ 上连续, 且 }0\leq f (x)\leq g (x)\text{, 则}$$
> $$1)\int_{a}^{+\infty}g(x)dx\text{收敛}\Rightarrow\int_{a}^{+\infty}f(x)dx\text{收敛}$$
> $$2) \int_{a}^{+\infty}f(x)dx\text{发散}\Rightarrow\int_{a}^{+\infty}g(x)dx\text{发散}$$

**解释**
+ 大的收敛，小的一定收敛；大的发散，小的不一定发散；
+ 小的发散，大的一定发散；小的收敛，大的不一定收敛；

**补充：放大缩小的初步判断**
+ 观察函数中变量 x 的次数，如 $\frac{\sqrt{x}}{1+x^2}$ 中分母 x 为 $3/2$，及收敛；

**使用举例**
+ 例题： $\int_1^{+\infty}\frac{\sqrt{x}}{1+x^2}dx.$
+ 将分母放大，使其符合常用结论的形式 `->` $\frac{\sqrt{x}}{1+x^{2}}<\frac{\sqrt{x}}{x^{2}}=\frac{1}{x^{3/2}}$
+ 因为 `P>1` ，所以收敛 `->` $\int_1^{+\infty}\frac{\sqrt{x}}{1+x^2}dx.$ 收敛；

##### **定理**： #比较判别法的极限形式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> 比较判别法： $$\text{设 }f(x),g(x)\text{ 在 }[a,+\infty)\text{ 非负连续},\lim_{x\to+\infty}\frac{f(x)}{g(x)}=\lambda\text{,则}$$
> $$1)当\lambda>0时,\int_{a}^{+\infty}f(x)dx\text{与}\int_{a}^{+\infty}g(x)dx\text{同敛散;}$$
> $$2)当\quad\lambda=0\text{ 时,}\int_{a}^{+\infty}g(x)dx\text{ 收敛 }\Rightarrow\int_{a}^{+\infty}f(x)dx\text{ 收敛}$$
> $$3)当\lambda=+\infty 时,\int_{a}^{+\infty}g(x)dx\text{发散}\Rightarrow\int_{a}^{+\infty}f(x)dx\text{发散}.$$
> 常用结论：$$\int_{a}^{+\infty}\frac{1}{x^{P}}dx\begin{cases}P>1&\text{收敛}\\P\leq1&\text{发散}\end{cases}(a>0)$$

### 1.1.3 例题
**例题**：求  $\int_{-\infty}^{+\infty}\frac{dx}{1+x^{2}}$ 
+ 分析
+ 解析
	+ 原式 $=andanx|_{-\infty}^{+\infty}$ $=\frac{\pi}{2}-(-\frac{\pi}{2})=\pi$
+ 题型： #反常积分 


## 1.2 无界函数的反常积分
### 1.2.1 基本概念
##### **定义**： #无界函数的反常积分
> <font color="#ccc1d9">描述：</font>
> 1. 定于一：如果函数 $f(x)$ 在点 a 的任意邻域内都无界，则点 a 为函数 $f(x)$ 的瑕点：$$\int_a^bf(x)dx=\lim_{t\to a^+}\int_t^bf(x)dx$$
> 2. 定义二：设点 b 为函数 $f(x)$ 的瑕点：$$\int_{a}^{b}f(x)dx=\lim_{t\to b^{-}}\int_{a}^{t}f(x)dx.$$
> 3. 定义三：设点 c 为函数 $f(x)$ 的瑕点 $(a<c<b)$：$$\int_{a}^{b}f(x)dx=\int_{a}^{c}f(x)dx+\int_{c}^{b}f(x)dx$$

##### **定理**： #比较判别法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> $$\text{设 }f (x), g (x)\text{ 在 }(a,b]\text{ 上连续, 且 }0\leq f (x)\leq g (x)\text{, 则}$$
> $$1)\int_{a}^{b}g(x)dx\text{收敛}\Rightarrow\int_{a}^{b}f(x)dx\text{收敛}$$
> $$2) \int_{a}^{b}f(x)dx\text{发散}\Rightarrow\int_{a}^{b}g(x)dx\text{发散}$$

##### **定理**： #比较判别法的极限形式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> 比较判别法： $$\text{设 }f (x), g (x)\text{ 在 }(a, b]\text{ 非负连续},\lim_{x\to a^1}\frac{f (x)}{g (x)}=\lambda\text{ ,则}$$
> $$\text{1)当}{\lambda>0}_{a}\text{时,}\int_{a}^{b}f(x)dx\text{与}\int_{a}^{b}g(x)dx{\text{同敛散};}_{a}\\\text{2)当}\lambda=0\text{ 时,}\int_{a}^{b}g(x)dx\text{收敛}\Rightarrow\int_{a}^{b}f(x)dx^{1}\text{收敛};\\\text{3)当}\lambda=+\infty\text{时,}\int_{a}^{b}g(x)dx\text{发散}\Rightarrow\int_{a}^{b}f(x)dx\text{发散}.$$
> 常用结论：$$\int_a^b\frac1{\left(x-a\right)^P}dx,\int_a^b\frac1{\left(b-x\right)^P}dx\quad\begin{cases}{P}<1&\text{收敛}\\P\geq1&\text{发散}\end{cases}$$


**概念引入**
+ 假设当前函数为 $y=1/x$，然后当前要求函数从 0 到 1 的积分；
	+ 此时在 0 点因为极限无定义，此点又被称作瑕点；
+ 这种无界函数的反常积分又被称之为瑕积分；

**瑕积分的欺骗性**
+ 只看求定积分的上下限，无法判断当前积分是否是瑕积分；
+ 需要看当前函数存在的条件，是否符合；

## 1.3 常考题型

### 题型： #反常积分的收敛性 
#### PART 1：解题方法
**判断敛散性方法**
+ 1. 定义法；
	+ 根据当前被积分式，求出其原函数，求原函数在被积分区间上的极限，看起极限值是否收敛；
+ 2. 比较判别法；
	+ 比较法；  
	+ 比较法的极限形式；
+ 3. P 积分；
	+ 注意：
		+ 无穷限反常积分 `->` $P>1$ 时收敛，$P<1$ 时发散
		+ 无界函数的反常积分 `->` $P<1$ 时收敛，$P>1$ 时发散
+ 哪个方便用哪个；

**注意**：涉及 $\mathrm{e}^{\infty}$ 要注意分左右；

#### PART 2：典型例题
**例题**：$\int_{2}^{+\infty}\frac{1}{\sqrt{x}}dx$
+ 分析
	+ 方法一：用定义
	+ 方法二：用 P 级数
+ 解析
	+ 方法一： 
		+ $\int_{2}^{+\infty}\frac{1}{\sqrt{x}}dx$ 求原函数 -> 就是 2 根号 x，此时直接求其极限； 
	+ 方法二： 
		+ 因为根号 x 是 P 级数中的二分之一，所以发散；
+ 题型： #反常积分的敛散性 

**例题**：$\text{反常积分 }\int_{0}^{+\infty}\frac1{x^a(1+x)^b}dx{\text{收敛,则}}$
+ 分析
	+ $\int_{0}^{+\infty}\frac{1}{x^{a}(i+x)^{b}}dx=\int_{0}^{1}\frac{1}{x^{a}(i+x)^{b}}dx+\int_{1}^{ts}\frac{1}{x^{a}(i+x)^{b}}dx$
	+ 这两个都需要收敛； 
	+ 对左边的分析：
		+ 使用比较法：$\lim_{x\to0^{+}}\frac{\frac{1}{x^{a}(x+x)^{b}}}{\frac{1}{x^{a}}}=1$
		+ 所以和 P 积分同敛散性 `->` $a<1$ 
	+ 对右边的分析：
		+ $\frac1{x^{a+b}(1+\frac1x)^b}$
		+ 因为趋向于无穷，所以 1+1/x 就是 1，所以只用看 $a+b$
		+ 使用比较法的极限形式：$\lim_{x\to\infty}\frac{\frac1{x^{a}(x)^{b}}}{\frac1{x^{a+b}}}$ `->` $a+b>1$ 
+ 解析
+ 题型：#

#### PART 3：知识点复盘

### 题型： #反常积分的计算 
#### PART 1：解题方法
**什么是反常积分的计算**
+ 定义：  
	+ 算个定积分 + 算个极限；
+ 方法： 
	+ 方法一：换元法 
	+ 方法二：分部法

#### PART 2：典型例题
**例题**：$\int_{2}^{+\infty}\frac{\mathrm{d}x}{(x+7)\sqrt{x-2}}=$
+ 分析
	+ 解法一：换元法
		+ 令 $\sqrt{k-2}=t,\quad x-2=t^{2}$
		+ 所以：$\int_{0}^{+\infty}\frac{2t}{t(t^{2}+9)}dt=2\int_{0}^{+\infty}\frac{dt}{9+t^{2}}$
		+ $=\frac{2}{3}\arctan\frac{\pi}{3}|_{0}^{+\infty}=\frac{2}{3}\left[\frac{\pi}{2}-0\right]$
	+ 解法二：凑微分     
		+ 原式 = $\int_{2}^{+\infty}\frac{2d\sqrt{x-2}}{9+(\sqrt{x-2})^{2}}$
		+ 
+ 解析
+ 题型：#

#### PART 3：知识点复盘