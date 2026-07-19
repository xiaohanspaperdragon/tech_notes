---
title: Lecture 45：二重积分的计算
tags:
  - 数学
  - 二重积分
categories: 
date: 2024-02-09
---
---
## 45.1 二重积分的计算
**核心思想**：把二重积分转化成一元定积分的计算，简化计算方法；

**方法选择**
+ 根据以下内容进行方法选择：
+ 1. 被积函数；
+ 2. 积分区域；

**适合极坐标**
+ （1）适合用极坐标计算的被积函数
	+ 公式：
		+ $$f(x^2+y^2),f(\sqrt{x^2+y^2}),f(\frac yx),f(\frac xy)$$
	+ 原因：
		+ $\sqrt{x^2+y^2}$ 在直角坐标系下比较复杂，但是在极坐标下就代表 `ρ`
		+ $\frac yx$ 在极坐标系就是表示角度
+ （2）适合用极坐标的积分域
	+ $$x^{2}+y^{2}\leq R^{2};\quad\quad\quad r^{2}\leq x^{2}+y^{2}\leq R^{2};\quad\quad\quad\\x^{2}+y^{2}\leq2ax;\quad\quad\quad x^{2}+y^{2}\leq2by;$$
	+ 注意：
		+ 当圆心不在原点时，可以将 $x-x_0$ 设为 $\rho\sin\theta$，同理对 $y-y_0$
+ 其中，如果（1）和（2）发生矛盾，以（1）为主

## 45.2 利用直角坐标系计算
##### **定理**： #基于直角坐标系的二重积分计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> （1）先 `Y` 后 `X`：$$\int\int_D{f(x,y)d\sigma = \int_{a}^{b}[\int_{y_{1}(x)}^{y_{2}(x)}f(x,y)dy]dx}$$
> 区域：$\begin{aligned}\varphi_1(x)&\leq y\leq\varphi_2(x)\cdot\\a&\leq x\leq b\end{aligned}$
> 其中 $\varphi_1(x)\leq y\leq\varphi_2(x)$ 代表的是 x 的取值范围，是 x 关于 y 的函数，$\varphi_1(x)$ 就是实际的 y 等于的值；
> （2）先 `X` 后 `Y`：$$\iint_Df(x,y)\mathrm{d}\sigma=\int_c^ddy\int_{\psi_1(y)}^{\psi_2(y)}f(x,y)dx$$
> 区域：$\begin{aligned}\Psi(y)&\leq X\leq\Psi_2(y)\\c&\leq y\leq d\end{aligned}$

**方法**：确定积分限；
+ 先 Y 后 X 时：
	+ `dy` 的积分上限与下限 `->` **从下往上**画一条射线，射线的下端为 `dy` 积分下限，射线的上端为 dy 的积分上限；
	+ `dx` 的积分上限与下限 `->` 观察图像，看 x 的取值范围；
+ 先 X 后 Y 时：
	+ `dx` 的积分上限与下限 `->` **从左往右**画一条射线，射线的左端为 `dx` 积分下限，射线的上端为 `dx` 的积分下限；
	+ `dy` 的积分上限与下限 `->` 观察图像，看 `y` 的**取值范围**；

**解释**
+ 概念：
	+ 这两种都可以使用，就看哪种计算起来更方便，就用哪个；
+ 先 `Y` 后 `X`：
	+ 概念：
		+ $\int_{a}^{b}[\int_{y_{1}(x)}^{y_{2}(x)}f(x,y)dy]dx$ 或 $\int_a^b\mathbf{d}x\int_{y_1(x)}^{y_2(x)}f(x,y)\operatorname{d}y.$
	+ 推理： 
		+ 1. 先求横截面面积：$S(x)=\int_{y_1(x)}^{y_2(x)}f(x,y)\mathsf{d}y.$
		+ 2. 再对曲边体型面积求解：$V=\int_a^bS(x)\operatorname{d}x$
		+ 3. 两者合并：$\int_{a}^{b}[\int_{y_{1}(x)}^{y_{2}(x)}f(x,y)dy]dx$
	+ 图示：
		 + 二维：
			 + ![[Pasted image 20240209014016.png]]
		+ 三维：
			+ ![[Pasted image 20240209014221.png]]
+ 先 `X` 后 `Y`：
	+ 前提：$(\sigma)=\{(x,y)\mid x_1(y)\leq x\leq x_2(y),c\leq y\leq d\}$
	+ 图示：
		+ ![[Pasted image 20240209015118.png]]
	+ 化成先 x 后 y 的两次一重定积分；
	+ 公式：$\begin{aligned}\iint_{(\sigma)}f(x,y)\operatorname{d}\sigma&=\int_c^d[\int_{x_1(y)}^{x_2(y)}f(x,y)dx]\operatorname{d}y\\\\&=\int_c^d\operatorname{d}\left.y\right]_{x_1(y)}^{x_2(y)}f(x,y)\operatorname{d}x.\end{aligned}$
+ 非 X 非 Y 区域
	+ 图示
		+ ![[Pasted image 20240209015436.png]]
	+ 概念：
		+ 一个复杂的、非 X 非 Y 的图形的二重积分；
	+ 方法：
		+ 可以**通过分割的方式转化为：多个 X 型以及多个 Y 型的求和**；

## 45.3 利用极坐标计算
##### **定理**： #基于极坐标的二重积分计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>$$\text{先 }\rho\text{ 后 }\theta\quad\iint_Df (x, y)\mathrm{d}\sigma=\int_\alpha^\beta d\theta\int_{\varphi_1 (\theta)}^{\varphi_2 (\theta)}f (\rho\cos\theta,\rho\sin\theta)\rho d\rho$$
> 区域：$\begin{aligned}\varphi_1(0)&\leq p\leq\varphi_2(0)\\\alpha&\leq\theta\leq\beta.\end{aligned}$
> 

**解释**
+ 注意：
	+ 对 $\rho$ 积分的时候，式子中的 $\theta$ 可以被看成是常数。同理对 $\theta$ 积分时；
+ 补充：  
	+ 可以将函数中的内容，分到两个积分上进行计算；
	+ $\iint_D\frac{x\sin (\pi\sqrt{x^2+y^2})}{x+y}dxdy=\int_0^{\frac\pi 2}\frac{\cos\theta}{\cos\theta+\sin\theta}d\theta\cdot\int_1^2\rho\sin (\pi\rho) d\rho$
	+ $\Delta\sigma=\frac12[(\rho+\Delta\rho)^2\Delta\theta-\rho^2\Delta\theta]$ = $\rho\Delta\rho\Delta\theta+\frac12(\Lambda\rho)^2\Delta\theta.$

## 45.4 利用对称性和奇偶性计算
### 45.4.1 奇偶性
**概念**：关于 `Y` 对称的时候看 `X`，关于 `X` 对称的时候看 `Y`； 

**性质一**：若积分 `D` 关系 `Y` 轴对称，则函数关于 `X` 有奇偶性：
+ 如果关于 `X` 的函数是偶函数，则加倍；如果关于 `X` 的函数是奇函数，则为 `0`；
+ $$\iint\limits_{D}f(x,y)d\sigma=\begin{cases}2\iint\limits_{D_{x\geq0}}f(x,y)\mathrm{d}\sigma;&f(-x,y)=f(x,y)\\0;&f(-x,y)=-f(x,y)\end{cases}$$

**性质二**：若积分 `D` 关系 `X` 轴对称，则函数关于 `Y` 有奇偶性：
+ $$\iint\limits_{D}f(x,y)d\sigma=\begin{cases}2\iint\limits_{D_{y_{z_0}}}f(x,y)\mathrm{d}\sigma&f(x,-y)=f(x,y)\\0&f(x,-y)=-f(x,y)\end{cases}$$

### 45.4.2 对称性
##### **定理**： #二重积分的变量对称性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\text{若 }D\text{ 关于 }y=x\text{ 对称,则}\quad\iint_Df(x,y)\mathrm{d}\sigma=\iint_Df(y,x)\mathrm{d}\sigma $$

**解释**
+ 积分域一样，自变量做出了对调；
+ 因为 $(x,y)$ 关于 `y=x` 对称的点为 $(y,x)$


**推论**：更一般化的结论
+ $$\int\int_{D(x,y)} f(x,y)\mathrm{d}x\mathrm{d}y=\int\int_{D(u,v)} f(u,v)\mathrm{d}u\mathrm{d}v=\int\int_{D(y,x)} f(y,x)\mathrm{d}y\mathrm{d}x$$

## 45.5 常考题型

---
### 题型： #累次积分交换次序或计算
#### PART 1：解题方法
**解题步骤**：举例 $\text{交换累次积分 }\int_0^1dx\int_{x^2}^{2-x}f(x,y)dy\text{ 的次序}$
+ 第一步：画出域
	+ ![[Pasted image 20240508210257.png]]
+ 第二步：按照画出域后，根据另外的次序，定域
	+ 交换次序，重新定线： 
	+ $$\int_0^1dy\int_0^{\sqrt{y}}f(x,y)dx+\int_1^2dy\int_0^{2-y}f(x,y)dx$$
+ 补充：如果交换次序后也不好计算，考虑用极坐标；

**题型**：极坐标下的累次积分
+ 举例：
	+ $$\int_{0}^{\frac{\pi}{2}}\mathrm{d}\theta\int_{0}^{\cos\theta}f(\rho\cos\theta,\rho\sin\theta)\rho\mathrm{d}\rho $$
+ 步骤：
	+ （1）画域；
	+ （2）画限，将极坐标方程化成直角坐标方程；

**题型**：计算累次积分
+ 


#### PART 2：典型例题 

#### PART 3：知识点复盘


---
### 题型： #二重积分的计算 
#### PART 1：解题方法
**题型**：二重积分的计算 
+ 先根据 D 的函数，画图
+ 先观察形式，分析：
	+ 1. 是否可以使用奇偶性、对称性 `->` 简化待积分式；
	+ 2. 观察式子，适合用直角坐标系还是极坐标系；
+ 计算：
	+ 利用二重积分计算规则，计算；

**题型**：二重积分与不等式
+ 基本思想：被积函数谁大，谁的积分值就大；

#### PART 2：典型例题
**例题**：设 $D=\{(x,y)|x^2+y^2\leq1\}$，则 $\iint_D(x^2-y)dxdy=$
+ 分析
	+ 直接计算 $x^2-y$ 的二重积分不好计算，所以考虑分析奇偶性和对称性；
+ 解析
	+ 由奇偶性可知：$\int\int ydxdy=0$
	+ 由对称性可知：$原式=\int\int y^2dxdy=\int\int x^2dxdy=\frac{1}{2}\int\int(x^{2}+y^{2})db$


#### PART 3：知识点复盘