---
title: Lecture 41：隐函数求导
tags:
  - 数学
  - 隐函数
categories: 
date: 2024-02-07
---
---
## 42.1 引入
**和一元函数的关系**
+ 多元函数微分法和一元函数微分法的关系：
+ 一元函数微分法中的问题：
	+ （1）复合函数求导；
	+ （2）隐函数求导；
	+ （3）参数方程
	+ （4）高阶导数
	+ （5）对数求导；
+ 多元函数微分法中的问题：
	+ （1）复合函数微分法；
	+ （2）隐函数微分法；

**考试内容概要**
+ （一）复合函数微分法； 
+ （二）隐函数微分法；

**常考题型与典型例题**
+ 题型一：复合函数的偏导数与全微分
+ 题型二：隐函数的偏导数与全微分

## 42.2 复合函数的微分法
### 42.2.1 多元函数的复合函数求导法
**一元函数**
+ 当 $y=f(u),u=G(x)$ 可导 `->` $y=f(G (x))$ 可导；
+ 链式求导法：$y_{x}^{\prime}=y_{u}^{\prime}\cdot u_{x}^{\prime}$

##### **定理**： #多元复合函数的求导法则
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设 $u=u(x,y),\quad v=v(x,y)$ 在点 $(x,y)$ 处有对 x 及对 $y$ 的偏导数，函数 $z=f(u,\nu)$ 在对应点 $(u,\nu)$ 处有连续偏导数，则 $z=f[u(x,y),v(x,y)]$ 在点 $(x, y)$ 处的两个偏导数存在，且有：
> $$\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial v}{\partial x},\quad\frac{\partial z}{\partial y}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial y}+\frac{\partial z}{\partial\nu}\frac{\partial\nu}{\partial y}$$

**解释**
+ 对内层函数：
	+ $u=u(x,y),\quad v=v(x,y)$ 要求的是**偏导数存在**；
+ 对外层函数：
	+ $z=f(u,\nu)$ 要求的是**偏导数存在**，并且要**连续**；
+ 原因：
	+ 在多元里面，可导不可以推出可微；

**原理**
+ 假设函数和变量的关系：
	+ z
		+ u
			+ x
			+ y
		+ v
			+ x
			+ y
+ 分析：
	+ 由上述求导的树形图可知，其中共有 `x、y` 两个变量；
	+ 对 `x` 自变量而言 `->` 其在 `u` 和 `v` 当中都存在 `->` 因此对 x 的求导：$\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial v}{\partial x}$ `->` 求导的结果为分别对 `u`、`v` 的复合函数求导的和；
	+ 同理对 `y`

### 42.2.2 全微分形式的不变性

##### **定理**： #全微分形式的不变性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设函数 $z=f(u,v),\quad u=u(x,v)$ 及 $\nu=\nu(x,y)$ 都有连续的一阶偏导数，则复合函数 $z=f[u(x,y),v(x,y)]$ 的全微分不变性：$$\mathbf{d}z=\frac{\partial z}{\partial x}\mathbf{d}x+\frac{\partial z}{\partial y}\mathbf{d}y=\frac{\partial z}{\partial u}\operatorname{d}u+\frac{\partial z}{\partial\nu}\operatorname{d}\nu.$$
> 即多元函数也具有微分形式的不变性；
> 由此推导而来：$$\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial\nu}{\partial x},\quad\frac{\partial z}{\partial y}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial y}+\frac{\partial z}{\partial v}\frac{\partial\nu}{\partial y}$$

**解释**
+ 一元时：
	+ 无论当前是对 x 的导数 $dx$ ，还是对 u 的导数 $du$（即无论是自变量还是中间变量），当前都是**对这个变量的导数乘以对这个变量的微分**；
+ 多元时： 
	+ 因为 $z=f(u,v),\quad u=u(x,v)$ 及 $\nu=\nu(x,y)$ 都有连续的一阶偏导数，所以一定可微分；
	+ 微分形式不变 `->` $\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial\nu}{\partial x},\quad\frac{\partial z}{\partial y}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial y}+\frac{\partial z}{\partial v}\frac{\partial\nu}{\partial y}$
	+ 带入
		+ ![[Pasted image 20240203172405.png]]
+ 意义：
	+ `z` 作为其他变量的函数，其中出现的变量、不用管其是中间变量还是自变量，微分形式具有不变性；


### 42.2.3 例题
**情况 1：**$\text{设 }z=f(u,v),u=\varphi(x),v=\psi(x)\text{ 均可微,则}$
+ $\frac{dz}{dx}=\frac{\partial z}{\partial u}\frac{du}{dx}+\frac{\partial z}{\partial\nu}\frac{d\nu}{dx}$
+ 分析：
	+ 因为 u、v 对 z 是偏导数，所以是偏微分 $\partial$
	+ 因为如图所示的关系
		+ ![[Pasted image 20240203161930.png]]
	+ 所以 z 是对 x 的一元函数，所以 u 对 x 是直接求导；

**情况 2：**$\text{设 }w=f(u),u=\varphi(x,y,z)\text{ 均可微},$
+ $\frac{\partial w}{\partial x}=\frac{dw}{du}\frac{\partial u}{\partial x},\frac{\partial w}{\partial y}=\frac{dw}{du}\frac{\partial u}{\partial y},\frac{\partial w}{\partial z}=\frac{dw}{du}\frac{\partial u}{\partial z}$
+ 分析
	+ w 是对 xyz 的三元函数
	+ ![[Pasted image 20240203162158.png]]

**情况 3：**$\text{设 }u=f(x,y,z),z=\varphi(x,y)\text{ 均可微}$
+ $\frac{\partial u}{\partial x}=\frac{\partial f}{\partial x}+\frac{\partial f}{\partial z}\frac{\partial z}{\partial x},\frac{\partial u}{\partial y}=\frac{\partial f}{\partial y}+\frac{\partial f}{\partial z}\frac{\partial z}{\partial y}$
	+ 因为当中等式前面的 u 的含义和后背的 u 的含义不一样，所以在后背写成 f 以表示区分；
+ 分析
	+ ![[Pasted image 20240203162504.png]]

**例题**：$\text{设 }z=f(x+y,xy),\text{ 其中 }z=f(u,v)\text{ 可微,求 }\frac{\partial z}{\partial x},\frac{\partial z}{\partial y}$
+ 分析
+ 解析
	+ $dz=\frac{\partial f}{\partial u}du+\frac{\partial f}{\partial v}dv=\frac{\partial f}{\partial u}(dx+dy)+\frac{\partial f}{\partial V}(ydx+xdy)$
	+ 由不变性可知
	+  = $\frac{\partial f}{\partial x}dx+\frac{\partial f}{\partial y}dy$
	+ 然后因为是分别求 x、y，所以分开得：
	+ ![[Pasted image 20240203173251.png]]
+ 题型： #多元复合函数的求导法则

## 42.3 隐函数的微分法
### 42.3.1 多元函数隐函数基本概念
##### **定义**： #多元函数隐函数
> <font color="#ccc1d9">描述：</font>由方程 $F(x, y)=0$ 确定的隐函数 $y=(x)$，得：$$y^{\prime}=-\frac{F_{x}^{\prime}}{F_{y}^{\prime}}$$

**解释**
+ 什么是隐函数
	+ 形如 $F(x, y)=0$ 的函数叫隐函数；
	+ 将**自变量和因变量放在同一个式子中，隐藏了二者之间的函类关系**，因此称之为隐函数。
+ 什么是显函数
	+ 显函数可以理解为：
	+ 自变量和因变量的函数关系明显的函数，形如 $y=f(x)$ 对应隐函数概念； 

##### **定理**： #隐函数存在定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> 1. $F(x,y)$ 在点 $M_0(x_0,y_0)$ 邻域内连续可偏导；
> 2. $F(x_0,y_0)=0$；
> 3. $F_y\:\prime(x_0,y_0)\neq0$ 
> 则由函数 $F(x,y)$ 在 $M_{0}$ 邻域内唯一确定一个连续可导函数 $y=f(x)$ 使 $y_0=f(x_0)$
> 则： $$\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$$

**解释**
+ 更通俗的解释
	+ $F(x,y)=0,\text{若}x\text{为自变量},F(x,y)=0\Rightarrow y=y(x),\text{求}\frac{dy}{dx}$
	+ 根据要求，x 是自变量，因此理论上可以将 y 变成 x 的一元函数，即将 y 直接看成 y (x)，进而同时两边对 x 求导：
		+ $F_{x}'+F_{y}'\frac{dy}{dx}=0\Longrightarrow\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$
+ 记忆
	+ 1. 一定有负号；
	+ 2. $\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$ 中的 x 和 y 是交错对应的；

**证明**
+ 因为在隐函数 $F(x,y)$ 中：
	+ x 是对于 x 的函数：$x=x$
	+ y 是对于 x 的函数：$y=f(x)$
+ 所以当对 $F(x,y)=0$ 求导时，它们的求导链条为：$F<_{y}^x>x$
+ 所以分别对 x、y 求导后：$\frac{\partial F}{\partial x}+\frac{\partial E}{\partial y}\frac{dy}{dx}=0$
+ 转化位置，得到：$\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$

##### **定理**： #多元隐函数存在定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $F(x,y,z)$ 在点 $M_{0}(x_{0},y_{0},z_{0})$ 邻域内连续可偏导，且 $F(x_{0},y_{0},z_{0})=0,F_{z}\:{\prime}(x_{0},y_{0},z_{0})\neq0$ 则由 $F(x,y,z)=0$ 在 $M_{0}$ 邻域内唯一确定一个连续可导函数 $z=\varphi(x,y)$ 且 $z_0=\varphi(x_0,y_0)$
> 则：$$\frac{\partial z}{\partial x}=-\frac{F_{x}’}{F_{z}’},\frac{\partial z}{\partial y}=-\frac{F_{y}’}{F_{z}’}$$

### 42.3.2 例题
**例题**：$e^xy^3-x^2+2y=1,\text{求}\frac{dy}{dx},\frac{d^2y}{dx^2}$
+ 分析
	+ $\text{依题目知,x为自变量,y为关于x的函数}$
+ 解析：求 $\frac{dy}{dx}$
	+ $$\begin{aligned}&e^{x}y^{3}-x^{2}+2y=1 \\&e^{x}y^{3}+e^{x}3y^{2}{\frac{dy}{dx}}-2x+2{\frac{dy}{dx}}=0 \\&\frac{dy}{dx}=\frac{2x-e^{x}y^{3}}{e^{x}3y^{2}+2}\end{aligned}$$
+ 解析：求 $\frac{d^2y}{dx^2}$
	+ $$
\begin{aligned}
&\text{求}\frac{d^{2}y}{dx^{2}},\text{这里对}e^{x}y^{3}+e^{x}3y^{2}\frac{dy}{dx}-2x+2\frac{dy}{dx}=0\text{再对x求导} \\
&e^{x}y^{3}+e^{x}3y^{2}{\frac{dy}{dx}}+e^{x}3y^{2}{\frac{dy}{dx}}+e^{x}6y({\frac{dy}{dx}})^{2}+e^{x}3y^{2}{\frac{d^{2}y}{dx^{2}}}-2+2{\frac{d^{2}y}{dx^{2}}}=0 \\
&\frac{d^{2}y}{dx^{2}}=\frac{2-e^{x}y^{3}-6e^{x}y^{2}\frac{dy}{dx}+e^{x}6y(\frac{dy}{dx})^{2}}{e^{x}3y^{2}+2} \\
&将{\frac{dy}{dx}}={\frac{2x-e^{x}y^{3}}{e^{x}3y^{2}+2}}{\text{代入}}
\end{aligned}
$$
+ 题型： #隐函数求导

**例题**：已知 $x^{2}+y^{2}-1=0$，当 $(0,1)$ 点处 XXXX，求一阶隐函数求导以及二阶隐函数求导；
+ 分析
	+ 注意是 $F(x,y)=0$
+ 解析：一阶
	+ 设 $F(x,y)=x^{2}+y^{2}-1$
	+ 可得：$F_{x}^{\prime}=2x，F_{y}^{\prime}=2y$
	+ 所以：$F(0,1)=0，F_{y}^{\prime}(0,1)=2\neq0$
	+ 带入公式：$\frac{dy}{dx}=-\frac{F_{x}^{\prime}}{Fy^{\prime}}=-\frac{2x}{2y}=-\frac{x}{y}$
+ 解析：二阶
	+ 对 $-\frac{x}{y}$ 中的 $x$ 再求一次导；
	+ $\frac{d^{2}y}{dx^{2}}=-\frac{y-xy^{\prime}}{y^{2}}=-\frac{y+x\frac{x}{y}}{y^{2}}$
+ 题型： #隐函数求导 

## 42.4 常考题型 

---
### 题型： #复合函数偏导数与全微分 
#### PART 1：解题方法
**题型**：对变上限积分多元复合函数求导
+ （1）将变上限积分带入进去；
+ （2）求导：
	+ 如果对 X 求导，那就把 Y 当成常数。同理对 Y；
	+ 根据 $(\int_a^xf(t)\mathrm{d}t)^{\prime}=f(x)$ 可知，求导就得到函数；
+ 补充：其他方法
	+ 先带后求：带某个特殊值

**题型**：求全微分的值
+ 方法一：
	+ 直接求微分；
	+ 通常要使用**复合函数求导法**；
+ 方法二：
	+ 分别求两个偏导，然后分别乘以 $dx,dy$ 相加，得到微分；
	+ 公式：$$\mathbf{d}z=\frac{\partial z}{\partial x}\mathbf{d}x+\frac{\partial z}{\partial y}\mathbf{d}y$$

**题型**：多元复合函数求高阶导数
+ （1）先求一阶导数 $\frac{dy}{dx}$，并且先不带入复合函数
	+ 比如当 $y=f(e^x,cosx)$ 时，$\frac{dy}{dx}=f_{1}^{\prime}e^{x}+f_{2}^{\prime}(-sinx)$
+ （2）将复合函数以及目标点得值带入一阶导数，可以得到一阶导数的值；
+ （3）再求二阶导数，注意对 $f_{1}^{\prime}$ 以及 $f_{2}^{\prime}$ 求导时的对象；
	+ 因为 `f` 是关于 $e^x,cosx$ 两项得复合函数，所以对 $f_{1}^{\prime}$ 以及 $f_{2}^{\prime}$ 求导时、既要求对 $e^x$ 部分的导数，也要求对 $cosx$ 部分的导数：
	+ $$\frac{d^{2}y}{dx^{2}}=f_{11}^{\prime\prime}e^{2x}+f_{12}^{\prime\prime}(-e^{x}sinx)+f_{1}^{\prime}\cdot e^{x}+f_{22}^{\prime\prime}\sin^{2}x+f_{21}^{\prime\prime}(-e^{x}sinx)-f_{2}^{\prime}\cos x$$
 
**题型**：当题目中 x、y 等自变量之间关系比较复杂时，可以使用复合函数将其代换成简单函数，基于复合函数求导求目标结果
+ 举例：比如当 $z=f(x^y,y^x)$ 时，可以让 $u=x^y,v=y^x$，此时 $z=f(u,v)$，得到以下树形图：
+ z
	+ u
		+ x
		+ y
	+ v
		+ x
		+ y
+ 此时假设求对 x 得偏导：$$\frac{\partial z}{\partial x}=\frac{\partial f}{\partial u}yx^{y-1}+\frac{\partial f}{\partial u}y^{x}luy$$

#### PART 2：典型例题
**例题**：设 $z=\left(1+\frac{x}{y}\right)^{\frac{x}{y}},\text{则求：}dz|_{(1,1)}$
+ 方法一：直接求微分
	+ 因为微分形式的不变性，所以 z 对 u 的微分 $z_{u}^{\prime}\mathrm{d}u$ 等于 z 对 x、y 的微分；
	+ $\frac{x}{y}=u,\quad z=(1+u)^{u},\quad\mathrm{d}z=z_{u}^{\prime}\mathrm{d}u$
	+ 设 $z=e^{u\ln(1+u)},且du=d\frac{x}{y}$ 
	+ 得： $$\quad\mathrm{d}z=e^{u\ln(1+u)}\left[\ln(1+u)+\frac{u}{1+u}\right]\frac{ydx-xdy}{y^2}$$
	+ 得到 $dz$ 得公式后，带入 z 得数值：$dz|_{(1,1)}=2\left[\ln 2+\frac{1}{2}\right](dx-dy)$
+ 方法二：利用两个偏导求微分
	+ 先分别求 $z_x^{\prime}(1,1),\quad z_y^{\prime}(1,1)$，然后分别乘以 `dx、dy` ，得到微分；
	+ 因为是具体点，可以先带后求；
	+ $$\begin{aligned}&z(x,1)=(1+x)^{x}=e^{x\ln(1+x)}\\&z_{x}^{\prime}(x,1)=e^{x\ln(t+x)}\left[\ln(t+x)+\frac{x}{1+x}\right],\quad z_{x}^{\prime}(1,1)=2\left[\ln2+\frac{1}{2}\right]=1+2\ln2\end{aligned}$$
	+ 同理对 `y` 求偏导

**例题**：设 $f(u,v)$ 具有二阶连续偏导数，函数 $g(x,y)=xy-f(x+y,x-y)$，求 $\frac{\partial^2g}{\partial x^2}+\frac{\partial^2g}{\partial x\partial y}+\frac{\partial^2g}{\partial y^2}$
+ $\frac{\partial g}{\partial x}=y-f_{1}^{\prime}-f_{2}^{\prime}$
	+ $\frac{\partial^{2}g}{\partial X^{2}}=-\left[f_{11}^{\prime\prime}+f_{12}^{\prime\prime}\right]-\left[f_{11}^{\prime\prime}+f_{22}^{\prime\prime}\right]$
	+ $\frac{\partial^{2}g}{\partial x\partial y}=1-\left[f_{11}^{\prime\prime}-f_{12}^{\prime\prime}\right]-\left[f_{21}^{\prime\prime}-f_{22}^{\prime\prime}\right]$
+ $\frac{\partial g}{\partial y}=x-f_{1}^{\prime}+f_{2}^{\prime}$
	+ $\frac{\partial^{2}g}{\partial y^{2}}=-\left[f_{11}^{\prime\prime}-f_{12}^{\prime\prime}\right]+\left[f_{21}^{\prime\prime}-f_{22}^{\prime\prime}\right]$
+ 所以求和为：$1-3f_{11}-f_{22}$ 

**例题**：设函数 $f(u)$ 具有二阶连续导数，$z=f(e^x\cos y)$ 满足 $\frac{\partial^{2}z}{\partial x^{2}}+\frac{\partial^{2}z}{\partial y^{2}}=(4z+e^{x}\cos y)e^{2x}$，若 $f(0)=0,f^{\prime}(0)=0$，求 $f(u)$ 的表达式；
+ 分析
+ 解析 
+ 题型：#

#### PART 3：知识点复盘


---
### 题型： #隐函数的偏导数与全微分
#### PART 1：解题方法
**题型**：隐函数求微分
+ 注：
	+ 和显函数求微分一样，也是有两种方法
+ 什么是多元函数的隐函数：
	+ 当前函数是 $z=z(x,y)$，此时 z 就类似于一元函数时的 y，是因变量。当函数式当中除了有 x、y 之外还有 z 时，就是隐函数；
+ 方法一： 
	+ 直接求微分； 
	+ 如果知道了 x、y 的值，需要先把 z 的值求出来，带进方程，然后再求；
+ 方法二：
	+ 利用两个偏导求微分 

**题型**：隐函数求导
+ 方法一：带公式
	+ $$\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$$
+ 方法二：两边求导
	+ 同时对函数得两边求导，注意隐函数中 z 和 x、y 的复合关系；
+ 方法三：微分形式不变性
	+ 
+ 注意：
	+ 方法一中的 ${F_{x}'}$ 是对 x 求导，但是此时是将 $z=f(x, y)$ 中的 z、y 都看作常数；
	+ 方法二中的对两边求导，当对 x 求导时、把 z 看成是 $z=f(x, y)$ 的函数
	
**题型**：复合函数和隐函数的综合题
+ 方法一：链式求导
	+ （1）画出求导的树形图；
	+ （2）根据树形图，确定求导的式子
		+ 比如以下树形图：
			+ u
				+ x
				+ y
					+ x
				+ z
					+ x
		+ 其对应的求导式子：$\frac{\operatorname{d}u}{\operatorname{d}x}=\frac{\partial f}{\partial x}+\frac{\partial f}{\partial y}\frac{\operatorname{d}y}{\operatorname{d}x}+\frac{\partial f}{\partial z}\frac{\operatorname{d}z}{\operatorname{d}x}$
	+ （3）根据隐函数关系，求出其中 $\frac{\operatorname{d}y}{\operatorname{d}x}$ 以及 $\frac{\operatorname{d}z}{\operatorname{d}x}$
+ 方法二：全微分形式不变性
	+ 比如以下树形图： 
		+ u
			+ x
			+ y
				+ x
			+ z
				+ x
	+ 不需要关系 u 和 xyz 是否是中间变量，因为 $u=f(x,y,z)$，所以根据微分形式不变性：
	+ $du=\frac{\partial f}{\partial x}dx+\frac{\partial f}{\partial y}dy+\frac{\partial f}{\partial z}dz$

#### PART 2：典型例题
**例题**：若函数 $z=z(x,y)$ 由方程 $e^{x+2y+3z}+xyz=1\quad\text{确定,则 }dz_{(0,0)}=$
+ 方法一：直接求微分 
	+ 由 $x=0,y=0$ 可知 $z=0$
	+ 对 $e^{x+2y+3z}+xyz=1$ 两端微分
	+ 得到：$e^{x+2y+3z}(dx+2dy+3dz)+yzdx+xzdy+xydz=0$
	+ 将 $x=0,y=0,z=0$ 代入上式得 $dx+2dy+3dz=0$
	+ 最后得到 $dz|_{(0,0)}=-\frac{1}{2}(dx+2dy)$
+ 方法二：分别求偏导
	+ 由 $x=0,y=0$ 可知 $z=0$
	+ 得 $dz|_{(0,0)}=z_{x}(0,0)dx+z_{y}(0,0)dy$
	+ $\text{在 }e^{x+2y+3z}+xyz=1\text{ 中令 }y=0\text{ 得},e^{x+3z}=1,\text{两边对 }x\text{ 求导得}$
		+ $e^{x+3z}(1+3z_{x})=0$
		+ $z_{x}(0,0)=-\frac{1}{3}.$
	+ $\text{同理可得}\quad z_y(0,0)=-\frac23$
	+ 得到 $dz|_{(0,0)}=-\frac{1}{2}(dx+2dy)$

**例题**：已知 $u+\mathbf{e}^{u}=xy,\text{求}\frac{\partial u}{\partial x},\frac{\partial u}{\partial y},\frac{\partial^{2}u}{\partial x\partial y}.$
+ 分析
	+ 因为原式当中有 u、x、y，所以是隐函数，并且因为 u 是 x、y 的函数，所以还需要使用复合函数求导；
+ 解析
	+ 方法一：两边求导
		+ 对 $u+\mathbf{e}^{u}=xy$ 两端对 x 求偏导得：$(1+e^{u})\frac{\partial u}{\partial x}=y$
			+ 右边为对 x 求偏导得结果；
			+ 左边为对复合函数 u 求导得结果。因为是复合函数求导，所以需要乘以 $\frac{\partial u}{\partial x}$
		+ 得到：$\frac{\partial u}{\partial x}=\frac y{1+e^x}$
		+ 同理可得：$\frac{\partial u}{\partial y}=\frac x{1+e^u}$
		+ 求 $$\frac{\partial^2u}{\partial x\partial y}=\frac{(1+e^u)-e^u\frac{\partial u}{\partial y}y}{\left(1+e^u\right)^2}$$
	+ 方法二：带公式
		+ 由公式得： $\frac{\partial y}{\partial x}=-\frac{F_{x}^{\prime}}{F_{x}^{\prime}}=-\frac{-y}{1+e^{u}}$
		+ 由公式得：$\begin{aligned}\frac{\partial u}{\partial y}=-\frac{F_{y}^{\prime}}{F_{u}^{\prime}}&=-\frac{-x}{1+e^{u}}\\&=\frac{x}{1+e^{u}}\end{aligned}$
	+ 方法三：微分形式不变性 
		+ $(1+e^{u})du=ydx+xdy$
		+ 将 $1+e^{u}$ 除到右边去，可以得到 $du=Adx+Bdy$ 是形式


#### PART 3：知识点复盘