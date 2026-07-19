---
title: Lecture 10：求极限
tags:
  - 数学
  - 极限
categories: 
date: 2024-03-04
---
 ---
## 10.1 求极限常用方法
**常用方法：八种**
### 10.1.1 方法 1：利用基本极限求极限
**常用基本极限**
+ $\lim_{x\to0}\frac{\sin x}x=1;$

**幂指数与根号**
+ $\lim_{x\to0}(1+x)^{\frac1x}=e;$
	+ 是 $1^\infty$ 型，且括号内的幂底数是大于 0 的；
	+ $\lim_{x\to0}(1+\frac{1}{x})^{x}$ 不存在，因为 x 趋向于 0 时，还可以是趋向于 0 负；
+ $\lim_{x\to0^+}(1+\frac{1}{x})^{x}=1$ 
+ $\lim_{x\to\infty}(1+\frac1x)^x=e;$
	+ 是 $1^\infty$ 型，且括号内的幂底数是大于 0 的
	+ $\lim_{x\to\infty}(1+x)^{\frac{1}{x}}$
+ $\lim_{x\to+\infty}(1+x)^{\frac{1}{x}}=1$ 
+ $\lim_{x\to0}\frac{a^x-1}x=\ln a;$
+ $\lim_{n\to\infty}\sqrt[n]{n}=1.$
	+ 注意这里是 n ，所以是趋向于正无穷；
+ $\lim_{n\to\infty}\sqrt[n]{a}=1,(a>0).$
	+ 注意这里是 n ，所以是趋向于正无穷；

**分段函数**
+ $\left.\lim_{{x\to\infty}}\frac{a_nx^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0}{{b}_mx^m+b_{m-1}x^{m-1}+\cdots+b_1x+b_0}=\left|\begin{array}{ll}\frac{a_n}{b_m},&n=m,\\0,&n<m,\\\infty,&n>m.\end{array}\right.\right.$
	+ 分子分母这么多项，结果主要取决于最大的数（最高次数）；
	+ 注意 x 是趋向于无穷。
	+ 当 x 趋向于 0 时，此时函数的值应该取决于最小的数（最低次数）；
+ $\lim_{{n\to\infty}}x^n=\begin{cases}\begin{array}{c}\mathbf{0},&|x|<1,\\\infty,&{|x|>1}\\1,&{x=1}.\end{array}\\\text{不存在,}&x=-1.&\end{cases}$
+ $\lim_{n\to\infty}e^{{nx}}=\begin{cases}0,&x<0,\\+\infty,&x>0\\1,&x=0.&\end{cases}$

**1 的无穷大次方**
+ 对 $1^{\infty}$ 而言，其结果是不定式，不一定等于 1；
+ $\text{若 }\lim\alpha(x)=0,\lim\beta(x)=\infty,\text{ 且 }\lim\alpha(x)\beta(x)=A。\text{则 }\lim(1+\alpha(x))^{\beta(x)}=e^A$
	+ 即核心在 $\lim\alpha(x)\beta(x)=A$，看它是否成立；
+ 方法三部曲
	+ 1. 写成标准形式：$\text{原式 }=\mathbf{lim}[1+\alpha(x)]^{\beta(x)}$；
	+ 2. 求极限：$\lim\alpha(x)\beta(x)=A;$
	+ 3. 写结果：$\text{原式}=e^A.$
+ 例题
	+ 题目：$\lim_{x\to\infty}\left(\frac{x^2}{(x-a)(x+b)}\right)^x$
	+ $\lim_{x\to\infty}\left(\frac{x^2}{(x-a)(x+b)}\right)^x=\lim_{x\to\infty}\left(\frac{x_.}{x-a}\right)^x\left(\frac x{x+b}\right)^x=e^a\cdot e^{-b}=e^{a-b}$

#### 题型： 解题技巧 - 任意常数
##### PART 1：问题
+ 当选择题中，出现**可以取任意值的常数的参数**时，可以考虑给常数一个特殊的具体值，带入之后可以消掉某些式子，但不改变原式的含义；
##### PART 2：典型例题
+ $\lim_{x\to\infty}\left(\frac{x^2}{(x-a)(x+b)}\right)^x$ 中，可以将 a 取为 0；

### 10.1.2 方法 2：利用等价无穷小代换求极限
**等价代换的原则**
+ 1. 乘除关系可以换
	+ $\text{若 }\alpha\sim\alpha_1,\beta\sim\beta_1,\text{则}\lim\frac\alpha\beta=\lim\frac{\alpha_1}\beta=\mathbf{lim}\frac\alpha{\beta_1}=\mathbf{lim}\frac{\alpha_1}{\beta_1}$
+ 2. 加减关系在**一定条件**下可以换
	+ 减法
		+ $\text{若 }\alpha{\sim}\alpha_1,\beta{\sim}\beta_1,\text{且 }\lim\frac{\alpha_1}{\beta_1}=A\neq1.\text{ 则 }\alpha{-}\beta{\sim}\alpha_1{-}\beta_1$
		+ 减法换的条件：**两个减法项不等价**，A 不等于 1；
		+ 比如：$sin2x - tanx$ ~ $2x - x$
	+ 加法
		+ $\text{若}\alpha{\sim}\alpha_1,\beta{\sim}\beta_1,\text{且 }\lim\frac{\alpha_1}{\beta_1}=A\neq-1.\text{ 则 }\alpha{-}\beta{\sim}\alpha_1{+}\beta_1$
		+ 减法换的条件：两个加法项不等价，A 不等于 -1；

**常用等价无穷小**
+ 当 x 趋向于 0 时；
+ ${(1+x)^\alpha-1}\sim{\alpha x}$
+ $e^{x}-1\sim x$
	+ 幂指函数的代换；
+ $x\sim\sin x\sim\tan x\sim\arcsin x\sim\arctan x\sim\ln(1+x)\thicksim e^x-1;$
	+ 注意：这里面函数，需要在使用时**保证 x 是趋向于 0** 的；
	+ 变式：$\ln q(x)\sim q(x)-1,q(x)\to1$
+ $a^x-1\sim x\ln a,\quad{(1+x)^\alpha-1\sim\alpha x},\quad1-\cos x\sim\frac12x^2$

**高阶等价无穷小**
+ $x-\sin x\sim\frac16x^3$，$\tan x-x\sim\frac13x^3$
+ $\arcsin x-x\sim\frac16x^3\quad x-\arctan x\sim\frac13x^3$
+ $x-\ln(1+x)\sim\frac12x^2$ 

### 10.1.3 方法 3：利用有理运算法则计算极限
**什么是有理运算法则**
+ 极限的加减乘除运算可以拆开来计算，前提是：**每个被拆开部分的极限需要存在**；
$$
\begin{aligned}
\text{若 }{\lim f(x)=A},\quad\mathrm{lim~g(x)=B},\text{ 那么}: 
&\lim(f(x)\pm g(x))=\lim f(x)\pm\lim g(x) \\
&\lim(f(x)\cdot g(x))=\lim f(x)\cdot\lim g(x) \\
&\lim\left(\frac{f(x)}{g(x)}\right)=\frac{\lim f(x)}{\lim g(x)}\quad(B\neq0)
\end{aligned}
$$

**存在前提**
+ 1. 存在 +/- 不存在 = 不存在；
+ 2. 不存在 +/- 不存在 = 不一定；
+ 3. 存在 ×/÷ 不存在 = 不一定； 
	+ 可以存在、可以不存在；
+ 4. 不存在 ×/÷ 不存在 = 不一定；
	+ 比如：$(-1)^{n}\cdot(-1)^{n}=1$，其中两个单独的时候都是不存在，但是乘以在一起后为存在；

**有理运算法则：常用结论**
+ 1. $\lim f(x)=A\neq0\Rightarrow\lim f(x)g(x)=A\lim g(x);$
	+ 极限非零的因子的极限可以先求出来；
+ 2. $\lim\frac{f(x)}{g(x)}\text{ 存在,}\lim g(x)=0\Rightarrow\lim f(x)=0;$ 
+ 3. $\lim\frac{f(x)}{g(x)}=A\neq0,\lim f(x)=0\Rightarrow\lim g(x)=0;$ 

### 10.1.4 方法 4：利用洛必达法则求极限 
**使用要求**
+ 1. $\lim_{x\to x_0}f(x)=\lim_{x\to x_0}g(x)=0\left(\infty\right);$
+ 2. $f(x)\text{ 和 }g(x)\text{在 }x_0\text{的某去心邻域内可导},\text{且 }g^{\prime}(x)\neq0;$
	+ 洛必达法则是由柯西中值定理证明出来的，所以需要满足这个条件；
+ 3. $\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}\text{ 存在(或  );}$
+ 满足条件则：$\lim_{x\to x_0}\frac{f(x)}{g(x)}=\lim_{x\to x_0}\frac{f^{\prime}(x)}{g^{\prime}(x)}.$
	+ 注意：这个等号是否成立，需要从等式的右边是否存在，才可以知道等式是否成立；

**使用环境**
+ $\frac00;\quad\frac\infty\infty,\quad0\cdot\infty;\quad\infty-\infty;\quad1^\infty;\quad\infty^0;\quad0^0$
+ 实际上都是由 $\frac00;\quad\frac\infty\infty$ 推出来的：
+ 解题思路：
	+ $\frac00,\frac\infty\infty\quad\Leftarrow\begin{cases}\quad ∞-∞\\0\cdot\infty\quad\Leftarrow\begin{cases}1^\infty\\\infty^0\\0^0&\end{cases}&\end{cases}$
+ $0\cdot\infty\quad$
	+ 思路：将 0 或者无穷当中一个放到上面 OR 下面；
+ $1^\infty;\quad\infty^0;\quad0^0$：
	+ 思路：这三种都得改写成 0 乘以无穷大；
	+ 方法： $[f(x)]^{g(x)}=e^{g(x)f(x)}$  -> 改写成 e 的形式；
	+ 核心：求 e 上面的相乘部分的无限；

**总结**
+ 1. 如果条件是函数 f (x) 二阶可导，则使用洛必达法则最多用到一阶导数；
+ 2. N 阶可导 -> n-1 阶可导可以使用；
+ 3. 如果遇到抽象函数求极限，可以考虑使用导数的定义来计算；

### 10.1.5 方法 5：使用泰勒公式求极限
##### **定理**：泰勒定理-带 Peano 余项
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> 1. 带有 Peano 余项的泰勒公式： $\text{设}f(x)\text{ 在 }x_0\text{ 处 }n\text{ 阶可微,则}$ $f(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k+o((x-x_0)^n)$
> 	意义：把一个一般函数，写成一个一般多项式+余项
> 	其中：$$P_n(x)=\sum_{k=0}^n\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k$$
> 	$f(x)$ 在 $x_{0}$ 处的 n 次 Taylor 多项式
> 	$$R_n(x)=o((x-x_0)^n)$$
> 缺点：
 > 1. 只能给出余项的定性描述，不能做定量的分析；
>  2. 只能在 x 0 临近时，才能用，远处无法使用；	

**常用泰勒公式**
+ $$\mathrm{e^x=\sum_{n=0}^\infty\frac1{n!}x^n=1+x+\frac1{2!}x^2+\cdots\in(-\infty,+\infty)}$$
+ $$\sin\mathrm{x=\sum_{n=0}^\infty\frac{(-1)^n}{(2n+1)!}x^{2n+1}=x-\frac1{3!}x^3+\frac1{5!}x^5+\cdots,x\in(-\infty,+\infty)}$$
+ $$\cos\mathrm{x=\sum_{n=0}^\infty\frac{(-1)^n}{(2n)!}x^{2n}=1-\frac1{2!}x^2+\frac1{4!}x^4+\cdots,x\in(-\infty,+\infty)}$$
+ $$\mathrm{ln(1+x)=\sum_{n=0}^\infty\frac{(-1)^n}{n+1}x^{n+1}=x-\frac12x^2+\frac13x^3+\cdots,x\in(-1,1]}$$
+ $$\begin{aligned}&\frac1{1-\mathrm{x}}=\sum_{\mathrm{n=0}}^\infty\mathrm{x^n}=1+\mathrm{x+x^2+x^3+\cdots,x\in(-1,1)}\\&\frac1{1+\mathrm{x}}=\sum_{\mathrm{n=0}}^\infty(-1)^\mathrm{n}\mathrm{x}^\mathrm{n}=1-\mathrm{x}+\mathrm{x}^2-\mathrm{x}^3+\cdots,\mathrm{x}\in(-1,1)\end{aligned}$$
+ $$\mathrm{(1+x)^a=1+\sum_{n=1}^\infty\frac{a(a-1)\cdots(a-n+1)}{n!}x^n=1+ax+\frac{a(a-1)}{2!}x^2+\cdots,x\in(-1,1)}$$


**$\frac{0}{0}$ 常用方法**
+ 等价代换；
+ 洛必达；
+ 泰勒公式； 

**泰勒公式使用到几次项**
+ 1.  $\frac{f(x)}{g(x)}.$
	+ 使用方法：
		+ 1. 使用泰勒展开，展开的阶数上下同幂指数；
			+ 比如：上、下是四次方，下、上也展开为四次方；
		+ 2. 整理项，将同阶的项整理在一起；
+ 2. $f(x)-或+g(x)$
	+ 写到某一次幂指数，找它们相减的最低次项；

### 10.1.6 方法 6：利用夹逼原理求极限
**例题**：$\lim_{n\to\infty}\left[\frac1{n^2+n+1}+\frac2{n^2+n+2}+\cdots+\frac n{n^2+n+n}\right]$
+ 分析
	+ 缩小：所有分母化成最大的分母；
	+ 放大：所有分母化成最小的分母； 
+ 解析
	+ $\frac{\frac{1}{2}n(n+1)}{n^{2}+n+n}\leq[原式]\leq\frac{\frac{1}{2}n(n+1)}{n^{2}+n+1}$
	+ 前后都趋向于 1/2，所以原式=1/2；
+ 题型： #夹逼原理

 **例题**：$\lim_{n\to\infty}\sqrt[n]{a_1^n+{a_2}^n+\cdots+{a_m}^n},\quad\text{其中 }a_i>0,(i=1,2,\cdots m)$
+ 分析
	+ 把最大项放缩成：当前所有项当中的最大项 $\sqrt[u]{ma^{n}}$
	+ 把最小项放缩成也是 a 的结果，如何放缩？只保·留一个 $a^n$ 项：$\sqrt[n]{a^{n}}$
+ 解析
	+ 最大项当中，因为 m 是一个定值，因此最后就是收敛为 a； 
	+ $\sqrt[n]{a^{n}}\leq\sqrt[n]{a_{1}^{n}+a_{1}^{n}+\cdots+a_{m}^{n}}\leq\sqrt[n]{ma_{0}^{n}}$
+ 题型： #夹逼原理 

**方法**： 遇到在根号当中有限项时，只需要找当中最能影响当前总数字大小的项，其极限就是夹逼原理放缩的数值；
+ 举例：$\lim_{n\to\infty}\sqrt[n]{1^n+x^n+(\frac{x^2}2)^n},{(x>0).}$
+ 这其中一共有三项，求它们当中底数最大的：$\max\{1,x,\frac{x^2}2\}$
+ 当 x 趋向于无穷时，$\frac{x^2}2$ 的影响最大；

### 10.1.7 方法 7：利用单调有界准则求极限
**方法**
+ 一般分成两步：
+ 1. 证明存在 `->` 单调有界准则；
+ 2. 等式两边取极限；

**例题**：$\text{设 }x_1>0,x_{n+1}=\frac12\Bigg(x_n+\frac1{x_n}\Bigg),n=1,2,\cdots.\text{求极限}\lim_{n\to\infty}x_n$
+ 分析：
	+ 不等式结论：$2ab\leq a^{2}+b^{2}$
+ 解析
	+ 第一步：证极限存在
		+ 因为 x 1>0，所以 $x_n>0$；
		+ $x_{n+1}=\frac12\left(x_n+\frac1{x_n}\right)=\frac12\left[(\sqrt{x_n})^2+(\frac1{\sqrt{x_n}})^2\right]\geq\frac12\cdot2\sqrt{x_n}\cdot\frac1{\sqrt{x_n}}=1$
		+ $x_{n+1}-x_{n}=\frac{1}{2}\Bigg(\frac{1}{x_{n}}-x_{n}\Bigg)=\frac{1}{2}\cdot\frac{1-x_{n}^{2}}{x_{n}}\leq0$
		+ 因为 $x_{n+1}-x_{n}<0$ 所以单调减少，且函数有下界，所以极限存在；
	+ 第二步：等式两边取极限，求极限
		+ $\lim_{n\to\infty}x_{n}=a.$
		+ $a=\frac12{\left(a+\frac1a\right)}$
		+ $\lim_{n\to\infty}x_n=\mathbf{1}.$
+ 题型： #单调有界准则 

**概念**：单调有界准则使用场合
+ 比较多的用在求递推关系 $x_{n+1}=f(x_n)$ 上

### 10.1.8 方法 8：利用定积分定义求极限
**定积分的概念**
+ 定积分是求一个区间范围内 （比如从 a 到 b 的区间范围），全部项求和积分；
	+ 区间是有规律的分、有规律的取；
+ a、b 区间 n 等分 -> 每一个部分是 $\frac{b-a}{n}$；

**例题**：$\text{求极限 }\lim_{n\to\infty}\left[\frac1{n+1}+\frac1{n+2}+\cdots+\frac1{n+n}\right]$
+ 分析
	+ 这个题目很难使用夹逼原理夹出来；
	+ 定积分也是"和式极限"
+ 解析
	+ 步骤一：提取 1/n （可爱因子~）
		+ 原式 $=\lim_{n\to\infty}{\frac1n}{\left[\frac1{1+\frac1n}+\frac1{1+\frac2n}+\cdots+\frac1{1+\frac nn}\right]}$；
	+ 步骤二：找变化的部分 -> 被积函数是谁
		+ 变化的部分就是函数 x 的位置，变化的范围就是求定积分的范围（从 $\frac1n$ 到 n，n 的数值从 0 到 1）；
		+ 因此变化的部分变成 x： $\int_{0}^{1}\frac{1}{1+x}dx$
	+ 1. 哪里变，哪里就是变量；
	+ 2. X 变化的范围就是区间的范围； 
+ 题型： #定积分定义求极限

**总结：** n 项和问题
+ 一共有两种解法：
+ 1. 夹逼原理；
+ 2. 定积分定义；

## 10.2 求极限方法总结
![[Pasted image 20240324233237.png]]