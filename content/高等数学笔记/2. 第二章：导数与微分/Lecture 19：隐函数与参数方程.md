---
title: Lecture 19：隐函数与参数方程
tags:
  - 数学
categories: 
date: 2023-12-21
---
 ---
## 1.1 隐函数的导数
### 1.1.1 隐函数基本概念
**显函数**
y 可以用 x 一个解析式全部表达出来；

**隐函数**
+ 隐函数：$3y+x+1=0$
	+ 显函数化（显化）：$y=-\frac{x+1}3$
	+ 但并不是所有的隐函数都很好显化
+ 难显化的隐函数：$y-x-\varepsilon\sin y=0\quad(0<\varepsilon<1)$
 
**一般形式**
隐函数的一般形式（用二元函数表示）： $F(x,y)=0\Rightarrow y=f(x)$

**隐函数求导方法**
隐函数变成以下形式：
+ $F(x,f(x))\equiv0$ 
+ 两边对 x 进行求导，然后把导数部分提出来得到导数的等式；

**易错点**：隐函数求导计算
+ 图示： 
	+ ![[Pasted image 20240706152937.png]]

### 1.1.2 例题
**例题**：$\text{求由方程 }y^5+2y-x=0\text{ 确定的隐函数 }y=f(x)\text{ 的导数}$
+ 因为是加号，所以三项分别求导：$5y^4y^{\prime}+2y^{\prime}-1=0$
+ 然后提出导数的部分：$y^\prime=\frac1{5y^4+2}$

**例题**：$\text{设 }y=f(x)\text{ 由 }y=1+xe^y\text{ 所确定,求 }y^{\prime\prime}(0)$
先把 x = 0 带到原方程，求出 0 点时候的 y 的值，得到当时 y 等于 1；
然后对两边求导，得到一阶导数：
+ $y^{\prime}=\mathrm{e}^{y}+\mathrm{x}{e}^{y}{y}$
然后得知一阶导数在 y=1 时，其导数值为 e；
然后的二阶导数、再带入：$y^{\prime\prime}=e^{y}y^{\prime}+e^{y}y^{\prime}+x(e^{y}y^{\prime})^{\prime}$
最后得到结果：$y^{\prime\prime}(0)=e^{2}+e^{2}+0,\quad y^{\prime\prime}(0)=2e^{2}$

**例题**：$\text{设 }y=(1+x^2)^{\sin x}\text{ 求 }y^{\prime}$
+ 第一步：观测到是幂指类型函数，因此两边取 ln：
	+ $\ln y=\sin\ln(1+\mathrm{x}^2)$
+ 然后：$\frac{y^{\prime}}y=\left[\cos x ln(1+x^2)+\frac{2x\sin x}{1+x^2}\right]$
+ 得到结果：$y^{\prime}=(1+x^{2})^{4x}\left[4x\ln(1+x)+\frac{2x\sin x}{1+x^{2}}\right]$

**解题方法**：对数求导法
#对数求导法
+ 当观测到函数类型幂指类型的函数时，两边可以同时取对数；

## 1.2 参数方程确定函数导数
### 1.2.1 基本概念
平面曲线可以用参数方程表示；其中就可能牵扯到参数方程的求导；

##### **定理**： #参数方程一阶导数
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\text{设 }x=\varphi(t),y=\psi(t)\text{ 在(}\alpha,\beta)\text{上可导},\varphi^{\prime}(t)\neq0\text{,则}\frac{dy}{dx}=\frac{\psi^{\prime}(t)}{\varphi^{\prime}(t)}$$

**解释**
+ 因为： $\varphi^{\prime}(t)\neq0$，所以有导数，所以
	+ ${t=\varphi^{-1}(x)}$
	+ ${y=\psi(t)}$
+ $\frac{dy}{dx}=\frac{dy}{dt}\frac{dx}{dx}$
+ 最终得到：$\frac{dy}{dx}=\frac{\psi^{\prime}(t)}{\varphi^{\prime}(t)}$
	+ 解析：y 对 x 求导，结果就是 y 对 t 的导数，除上 x 对 t 的导数；

##### **定理**： #参数方程二阶导数
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\frac{d^{2}y}{dx^{2}}=\frac{\psi^{\prime\prime}(t)\varphi^{\prime}(t)-\varphi^{\prime\prime}(t)\psi^{\prime}(t)}{\varphi^{\prime3}(t)}$$

**分析**：求带 t 式子的二阶导数
+ 注意：求二阶导数时，要遵循以下步骤，不能跳步
+ 求导图示：
	+ ![[Pasted image 20240319215159.png]]
### 1.2.2 例题
**例题**：$\text{设}\quad\begin{cases}y=\ln(1+t^2)\\x=\arctan t.&\end{cases}\quad\text{求}\quad y^{\prime},y^{\prime\prime}$
第一步：求一阶导数-> $\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{\frac{2t}{1+t^{2}}}{\frac{1}{1+t^{2}}}=2t$
然后要求二阶导数，因此需要**左右同时对 x 求导**（注意是 x 不是 t）
+  $\frac{d^2y}{dx^2}=\color{red}{2\cdot\frac{dt}{dx}}$ = $\frac{2}{\frac{1}{1+t^{2}}}=2(1+t^{2})$
	+ 注意右边也是对 x 求导

**例题**：已知摆线 (旋轮线)的参数方程为 $x=a(t-\sin t)$ $y=a(1-\cos t)$，求摆线在 $t=\frac\pi2$ 处的切线方程与法线方程；
因为是求切线，因此肯定需要得出在此点的斜率 -> 斜率就是变化率；
+ 求斜率： $k=\frac{dy}{dx}=\frac{a\sin t}{a(1-\cos t)}\Bigg|_{t=\frac{\pi}{2}}=1$
+ 然后：$x_0=a\left(\frac\pi2-i\right),\quad y_0=a.$
+ 得到切线和法线；

## 1.3 相关变化率
### 1.3.1 基本概念
**相关变化率-基本概念**
已知：$x=x(t)\quad y=y(t)\quad F(x,y)=0$
表示 x 和 t 相关，y 和 t 相关，x 和 y 之间又满足一定的关系；
若**知道 x、y 当中一个与 t 的变化率关系，然后要求去求另一个与 t 的变化率关系**，即表示求相关变化率；

**一般方法**
+ 1. 建立 $F(x,y)=0$ ：即两个相关量之间的关系，
+ 2. 等式两边对 t 求导；


### 1.3.2 例题
**例题**：设有一个倒置的圆锥形容器其底面圆直径为 10 cm, 高为 5 cm。现以每秒 3 cm 给容器中加水，试求 t = 1 秒时水面上升的速率；
1. 第一步：建立两个相关量之间的关系：水的体积与高度
	+  $V(t)=\frac\pi3h^2(t)h(t)=\frac\pi3h^3(t)$ 
2. 等式两边对 t 求导：
	+ $V^{\prime}(t)=\pi h^2(t)\frac{dh}{dt}$
	+ 其中 V（t）的导数，就是 3 cm 每秒，因此就是 3；
	+ $3=\pi h(1)\frac{\mathrm{d}h}{\mathrm{d}t}$
+ 3. 得出结果：$h(1)=\sqrt{\frac{9}{\pi}}$
