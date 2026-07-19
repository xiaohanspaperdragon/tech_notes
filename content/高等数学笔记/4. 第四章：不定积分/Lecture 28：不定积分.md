---
title: Lecture 28：不定积分
tags:
  - 数学
  - 不定积分
categories: 
date: 2024-01-17
---
---
## 本章常考题型与典型例题
**考试内容**
+ (一)不定积分的概念与性质
+ (二)不定积分基本公式 
+ (三)三种主要积分法
+ (四)三类常见可积函数的积分

**常考题型**
+ 求不定积分 (换元、分部)

## 1.1 什么是不定积分
**知识点分布**
+ 2+3+3
+ 2：两个概念 `->` 1. 原函数； 2. 不定积分；
+ 3：三种方法：两类换元+分布；
+ 3：三类常见积分

**重点**：三种方法 `->` 两类换元+分布；

**尺度**：基本的不定积分方法掌握即可；

### 1.1.1 基本概念
**原函数**
+ 概念：
	+ $F^{\prime}(x)=f(x)$
	+ $G^{\prime}(x)=f(x)$
+ 则：$G(x)-F(x)=C$ 

##### **定义**： #不定积分
> <font color="#ccc1d9">描述：</font>一个函数 $f(x)$ 的不定积分（或者说是原函数）是一个导数等于 $f(x)$ 的函数 $F(x)$ ，即 $F′(x) = f (x)$，或写成 $[F (x)+c]^{\prime}=f (x)$
> 或者：$\int f(x)dx=F(x)+C$

**解释**
+ 概念：
	+ 不定积分就是 $f(x)$ 原函数的一般表达式；
+ 举例：
	+ 比如在 $\int f_{(x)}dx=F_{(x)}+C$ 中：
	+ 设 $F(x)$ 是函数 $f(x)$ 的一个原函数；
	+ 把函数 $f(x)$ 的所有原函数 $F(x)+C$ 叫做函数 $f(x)$ 的不定积分，又叫做函数 $f(x)$ 的反导数；
+ 符号：
	+ $\int$ ：积分号；
	+ $f(x)$：被积函数；
	+ $dx$：积分变量；
	+ $f(x)dx$：被积式
	+ $C$：积分常数；

**不定积分的几何意义**
+ 一组在 Y 轴上相差常数大小的曲线；
### 1.1.2 原函数存在性
##### **定理**： #原函数存在定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. 若 $f(x)$ 在区间 $I$ 上连续, 则 $f(x)$ 在区间 $I$ 上一定存在原函数；
> 2. 若 $f(x)$ 在区间 $I$ 上有第一类间断点，则 $f(x)$ 在区间 $I$ 上没有原函数；

**解释**
+ 关系：
	+ 连续的函数，一定存在原函数;
	+ 连续 `->` 存在原函数；
	+ 存在原函数 `-X>` 连续；
+ 结论：
	+ 不连续的函数可能会有原函数，但此函数不可以有第一类间断点，可以为第二类间断点；

**举例**
+ $g(x)=\operatorname{sgn}x=\begin{cases}-1,&x<0,\\0,&x=0,\\1,&x>0.&\end{cases}$ 有跳跃间断点 `->` 属于第一类间断点 `->` 没有原函数；
+ 原因：此函数在 $x=0$ 处的原函数为 $|x|+c$ ，而此函数不可导 `->` 零点这里就没有原函数；

### 1.1.3 不定积分基本性质
**性质 1**：
+  $(\int f(x)\mathrm{d}x)^{\prime}=f(x)$
+ $\mathrm{d}\int f(x)\mathrm{d}x=f(x)\mathrm{d}x$

**性质 2**：
+ $\int f^{\prime}(x)\operatorname{d}x=f(x)+C$
+ $\int\operatorname{d}f(x)=f(x)+C$

**性质 3**：
+ $\int[f(x)\pm g(x)]\operatorname{d}x=\int f(x)\operatorname{d}x\pm\int g(x)\operatorname{d}x$

**性质 4**：
+ $\int kf(x)\operatorname{d}x=k\int f(x)\operatorname{d}x$



## 1.2 常见积分公式
### 1.2.1 积分公式
$1、\int adx=ax+C\:,\:a$ 是常数 
$2、\int x^{a}dx=\frac{x^{a+1}}{a+1}+C$ ,其中 a 为常数，且 $a\neq-1$
$3、\int\frac{1}{x}dx=\ln|x|+C$
$4、\int e^{x}dx=e^{x}+C$ 
$5、\int a^{x}dx=\frac{1}{\ln a}a^{x}+C$ ,其中 $a>0\:,\:目a\neq1$
$6、\int\sin xdx=-\cos x+C$
7、$\int\cos xdx=\sin x+C$ 
$8、\int\sec^{2}xdx=\tan x+C$ 
$9、\int\csc^{2}xdx=-\cot x+C$ 
$10、\int\tan xdx=-\ln|\cos x|+C$
$11、\int\cot xdx=\ln\lvert\sin x\rvert+C$
$12、\int\sec xdx=\ln\lvert\sec x+\tan x\rvert+C$
$13、\int\csc xdx=-\ln\lvert\csc x+\cot x\rvert+C$
$14、\int\frac{dx}{1+x^2}=\arctan x+C$
$15、\int\frac1{\sqrt{a^2-x^2}}dx=\arcsin\frac xa+C$
$16、\int\frac1{x^2-a^2}dx=\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|+C$
$17、\int\frac{dx}{\sqrt{1-x^2}}=\arcsin x+C$
$18、 \int\frac 1{a^2+x^2}dx=\frac 1 a\arctan\frac xa+C$ 
$19、\int\frac{dx}{\sqrt{x^2+a^2}}=\ln (x+\sqrt{x^2+a^2})+C$
$20、\int\frac{dx}{\sqrt{x^2-a^2}}=\ln\left|x+\sqrt{x^2-a^2}\right.|+C$

**常见“积不出”函数**
+ $\begin{aligned}&\int\mathrm{e}^{x^2}\mathrm{d}x\\&\int\frac{\sin x}x\mathrm{d}x\\&\int\frac{\cos x}x\mathrm{d}x\end{aligned}$

### 1.2.2 三角函数总结
**三角函数基础**
+ 倒数关系：
	+ $$\tan\alpha\cot\alpha=1、\sin\alpha\csc\alpha=1、\cos\alpha\sec\alpha=1$$
+ 商数关系： 
	+ $$\tan\alpha=\frac{\sin\alpha}{\cos\alpha}、\cot\alpha=\frac{\cos\alpha}{\sin\alpha}$$
+ 平方关系：
	+ $$ \sin^{2}\alpha+\cos^{2}\alpha=1、1+\tan^{2}\alpha=\sec^{2}\alpha、1+\cot^{2}\alpha=\csc^{2}\alpha$$
+ 二倍角公式：
	+ $$\sin2\alpha=2\sin\alpha\cos\alpha$$
	+ $$\cos2\alpha=2\cos^2\alpha-1=1-2\sin^2\alpha$$
	+ $$\tan2\alpha=\frac{2\tan\alpha}{1-\tan^2\alpha}=\frac{2\cot\alpha}{\cot^2\alpha-1}=\frac{2}{\cot\alpha-\tan\alpha}$$
+ 降次公式：
	+ $$\cos^{2}\alpha=\frac{1+\cos2\alpha}{2},\sin^{2}\alpha=\frac{1-\cos2\alpha}{2},tan^2\alpha=\frac{1-cos2\alpha}{1+cos2\alpha}$$
+ 反三角函数：
	+ $$x=a\sin t { 时}，t=\arcsin\frac xa.$$
	+ $$\text{x=a sect}时,t=\mathrm{arc}\cos\frac{a}{x}$$

**三角函数求导合集**
+ 正弦、余弦：
	+ $$(\sin x)^{\prime}=\cos x、(\sin x)^{\prime}=-\cos x$$
+ tan、cot、sec、csc： 
	+ $$\begin{aligned}(\tan x)^{\prime}&=\sec^2x&(\cot x)^{\prime}&=-\csc^2x\\\\(\sec x)^{\prime}&=\sec x\tan x&(\csc x)^{\prime}&=-\csc x\cot x\end{aligned}$$
+ 反三角函数：
	+ $$\begin{aligned}&(\arcsin x)^{\prime}=\frac1{\sqrt{1-x^2}}&&(\arccos x)^{\prime}=-\frac1{\sqrt{1-x^2}}\\&(\arctan x)^{\prime}=\frac1{1+x^2}&&(arccot x)^{\prime}=-\frac1{1+x^2}\end{aligned}$$

**常见三角函数积分**
+ 和求导一一对应：
+ $$\int\sin xdx=-\cos x+C、\int\cos xdx=\sin x+C$$
+ $$\int\tan xdx=-\ln|\cos x|+C、\int\cot xdx=\ln\lvert\sin x\rvert+C$$
+ $$\int\sec xdx=\ln\lvert\sec x+\tan x\rvert+C、\int\csc xdx=-\ln\lvert\csc x+\cot x\rvert+C$$
+ $$\int\sec^{2}xdx=\tan x+C、\int\csc^{2}xdx=-\cot x+C$$
+  $$\int\tan x secx=\sec x+C、\int{\cot x\,\csc x}\,dx=-csc x+C$$

**常见反三角函数积分**
+ $$\int\frac{dx}{\sqrt{1-x^2}}=\arcsin x+C$$
+ $$\int\frac1{\sqrt{a^2-x^2}}dx=\arcsin\frac xa+C$$
+ $$\int\frac{dx}{1+x^2}=\arctan x+C$$
+ $$\int\frac 1{a^2+x^2}dx=\frac 1 a\arctan\frac xa+C$$

## 1.3 三类常见可积函数积分 
**1. 有理函数积分**
+ 积分：$\int R(x)\operatorname{d}x$
+ 有理函数：$R(x)$
+ （1）一般方法（部分分式法）；
+ （2）特殊方法（加项减项拆 + 凑微分绛幂）
	+ 加项、减项、拆举例：
		+ $\int\frac1{t^2-1}\cdot\frac1{t+1}\mathrm{d}t.$
		+ 得到：$\int\frac1{(t^2-1)(t+1)}\mathrm{d}t=\frac12\int\frac{(t+1)-(t-1)}{(t^2-1)(t+1)}\mathrm{d}t=\frac14\ln\left|\frac{t-1}{t+1}\right|+\frac1{2(t+1)}+C$

**2. 三角有理式积分**
+ 积分：$\int R(\sin x,\cos x)\mathrm{d}x$
+ 解释：表示 $sinx$ 和 $conx$ 经过有理运算得到；
+ 一般方法：万能代换
	+ 令 $\tan\frac x2=t$
	+ $\int R(\sin x,\cos x)\operatorname{d}x=\int R(\frac{2t}{1+t^2},\frac{1-t^2}{1+t^2})\frac2{1+t^2}dt$
+ 特殊方法（三角变形、换元、分部）
	+ 1. $\text{若 }R(-\sin x,\cos x)=-R(\sin x,\cos x)$，则令 $u=\cos x$
	+ 2. $\text{若 }R(\sin x,-\cos x)=-R(\sin x,\cos x)$，则令 $u=\sin x$
	+ 3. $\text{若 }R(-\sin x,-\cos x)=R(\sin x,\cos x)$，则令 $u=\tan x$
+ 举例：
	+ 特殊方法：$\int\frac{\operatorname{d}x}{1+\sin x}=\int\frac{1-\sin x}{\cos^2x}\mathrm{d}x=\tan x-\frac1{\cos x}+C.$
	+ 一般方法：设 $\tan\frac x2=t$，则 $\begin{aligned}\text{原式}& =\int\frac 1{1+\frac{2 t}{1+t^2}}\cdot{\frac 2{1+t^2}dt}  \\&=\int\frac{2 dt}{\left (1+t\right)^2}=-\frac 2{1+t}+C\end{aligned}$

**3. 简单无理式积分**
+ 积分形式：
	+ $$\int R(x,\sqrt[n]{\frac{ax+b}{cx+d}})\operatorname{d}x$$
+ 解释：
	+ 举例：$\int\frac{dx}{(2-x)\sqrt{1-x}}$ 的两个函数当中：
	+ 1. 一般函数的部分：$(2-x)$
	+ 2. 根号函数的部分：$\sqrt{1-x}$
+ 一般方法：
	+ $$\text{令 }\sqrt[n]{\frac{ax+b}{cx+d}}=t$$
+ 举例：
	+ $\int\frac1x\sqrt{\frac{x+1}x}dx$
	+ $\text{令}\sqrt{\frac{x+1}x}=t\text{,则}\quad x=\frac1{t^2-1},dx=-\frac{2t}{\left(t^2-1\right)^2}dt,\int\frac1x\sqrt{\frac{x+1}x}dx=\int(t^2-1)t\frac{-2t}{(t^2-1)^2}dt=-2\int\left(1+\frac1{t^2-1}\right)dt$

## 1.4 常考题型
### 题型： #求不定积分之换元、分部
#### PART 1：解题方法
**关于两类换元法**
+ 很多题目既可以使用第一类换元法、凑微分来解决，也同时可以使用第二类换元法、使用 t 复合函数来解决；
+ 能用第一类换元法时，优先使用第一类换元法；

**关于分段函数求不定积分**
+ 注意：在 0 点、分段函数分段点是否可以求导，观察其连续性；
	+ 不连续 -> 不可导 -> 错误的原函数；
+ 方法：
	+ 1. 分段函数求不定积分，先正常求不定积分，然后在写 C 时写上 $C1、C2$；
	+ 2. 分别求解两个函数在分段点的**带 C 结果**；
	+ 3. 根据分界点连续的要求，两个函数的带 C 结果要一样，因此求出 C 1 和 C 2 的关系； 
	+ 4. 将 C1、C 2 以 C 的形式带入原函数； 
+ 补充：一个隐含的前提
	+ 只要被积函数是一个分段的连续函数，只要保证了连续性，则也可以保证可导性；

**两个不同函数相乘**
+ 当遇到两类不同函数相乘时，都可以考虑**分布积分法**；
+ 把不难弄的一部分凑到 dx 里面去；

**已知原函数题目**
+ 当题目为已知原函数，求 $f(x)$ 在不定积分中的内容，并且不定积分中有导数时，可以直接把导数提取到 dx 中，从而直接把原函数的求导结果带入；

#### PART 2：典型例题
**例题**：$\text{设 }f(x)=\begin{cases}&e^x,&x\geq0,\\&\cos x,&x<0,&\end{cases}\text{则}\int f(x)dx=$
+ 分析
	+ $\left.\int f(x)dx=\left\{\begin{array}{l}{{e^{x}+c_{1}},}&{{{x\geq0}}}\\{{\sin^{\prime}x+c_{2}^{\prime}}}&{{x<0}}\\\end{array}\right.\right.$
	+ 此时，当 x 分别趋向正 0 和负 0，得到：$1+C_1=C_2$
	+ 所以令 $C_1=C$，则 $C_2=1+C$，带入原式；
	+ $\left.\int f(x)dx=\left\{\begin{array}{ll}{{e^{x}+c,\quad x\geq0}}\\{{sinx+1+c.\quad x<0}}\\\end{array}\right.\right.$
+ 解析
+ 题型：#

**例题**：$\text{计算 }\int\frac{x^2}{\sqrt{a^2-x^2}}dx(a>0).$
+ 分析
	+ 总结：当 $x=a*sint 时，此时 sint*cost=\frac{x}{a} * \sqrt{1-\frac{x^{2}}{a^{2}}}$
	+ 其中 $\frac{x}{a}$ 为 sint ，$\sqrt{1-\frac{x^{2}}{a^{2}}}$ 为使用 $\sin^{2}\alpha+\cos^{2}\alpha=1$ 公式计算得到的结果
+ 解析
+ 题型：#

**例题**：已知 $\frac{\sin x}x$ 是 f(x) 的一个原函数，求 $\int x^3f^{\prime}(x)\operatorname{d}x$ 
+ 分析
	+ 直接将 $\int x^{3}f'(x)\mathsf{d}x=\int x^{3}df(x)$ 然后直接分部；
	+ $=x^3f(x)-3\int x^2\mathrm{d}\left(\frac{\sin x}x\right)$
+ 解析 
+ 题型：#
#### PART 3：知识点复盘
总结：
+ 当 $x=a*sint 时，此时 sint*cost=\frac{x}{a} * \sqrt{1-\frac{x^{2}}{a^{2}}}$
+ 其中 $\frac{x}{a}$ 为 sint ，$\sqrt{1-\frac{x^{2}}{a^{2}}}$ 为使用 $\sin^{2}\alpha+\cos^{2}\alpha=1$ 公式计算得到的结果