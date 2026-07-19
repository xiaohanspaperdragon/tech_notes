---
title: Lecture 34：定积分的应用
tags:
  - 数学
  - 定积分
categories: 
date: 2024-01-24
---
---
## 常考题型与典型例题
**常考内容**
+ (一)几何应用
+ (二)物理应用

**常考题型与典型例题**
+ 题型一：几何应用
+ 题型二：物理应用

## 1.1 概念引入
**什么问题适合用定积分求解**
+ 1)非均匀连续分布在 $[a,b]$ 
+ 2)所求量对区间有可加性

**方法**
+ 先找范围
+ 找出微小范围内，它的微分的极小的值（近似值，找微元）
+ 进行积分，求 a-b 范围上函数的积分

## 1.2 几何应用
### 1.2.1 平面图形的面积
#### 1.2.1.2 基本概念
**概念**
+ 情况一：平面坐标
	+ 若平面域 $D$ 由曲线 $y=f(x),y=g(x)(f(x)\geq g(x))$, $x=a,\quad x=b\quad(a<b)$ 所围成，则：
	+ $$S=\int_{a}^{b}[f(x)-g(x)]dx$$
	+ 平面上求一个区域 D，
+ 情况二：极坐标
	+ 若平面域 $D$ 由曲线 $\rho=\rho(\theta),\theta=\alpha,\theta=\beta(\alpha<\beta)$ 所围成，则： 
	+ $$S=\frac 12\int_\alpha^\beta\rho^2 (\theta)\mathrm{d}\theta$$

**更一般的公式**
+ 公式：
	+ $$S=\int\int_{D}^{S}1db$$
+ 例题：用二重积分，先 x 后 y
	+ $\text{设 }D\text{ 是由曲线 }xy+1=0\text{ 与直线 }$ $y+x=0及y=2围成的有界区域，则D的面积为$ 
	+ 求解：$\begin{aligned}S&=\int_{0}^{1}db\\&=\int_{1}^{2}dy\int_{0}^{-\frac{1}{y}}dx\end{aligned}=\int_{1}^{2}(y-\frac{1}{y})dy=(\frac{1}{2}y^{2}-2,y)|_{1}^{2}$

 
#### 1.2.1.2 例题
**例题**：求曲线 $y^2=x$ 与 $y=x^2$ 所围面积. 
+ 分析
	+ ![[Pasted image 20240131142232.png]]
	+ 可以对 x 积分
	+ 也可以对 y 积分
+ 解析 1：对 x 积分
	+ 第一步：找范围
		+ ![[Pasted image 20240131142306.png]]
	+ 第二部：找微元
		+ x 和 x+dx
		+ ![[Pasted image 20240131142332.png]]
	+ 第三步：积分
		+ 从 0-1 积分
		+ $\delta=\int_{0}^{1}\left(dx-x^{2}\right)dx=\frac{2}{3}-\frac{1}{3}=\frac{1}{3}$
+ 题型： #定积分的几何应用

**例题**：$\text{求心形线 }\rho=a(1+\cos\theta)\left(a>0\right)\text{所围面积}.$
+ 分析
	+ 极坐标的题型；几何图形的坐标用极坐标给出；
	+ 第一步：它的范围；是 ![[Pasted image 20240131150018.png]]
	+ 第二步：求它在微小的区间上，对应图形如何求出对应面积：
		+ ![[Pasted image 20240131150049.png]]
		+ 可以近似看出一个扇形；
		+ 微元：
			+ ![[Pasted image 20240131150113.png]]
	+ 第三步：求积分
		+ ![[Pasted image 20240131150129.png]]
+ 解析
	+ 第一步：确定范围
		+ 可以先画图 -> 画图需要先画一些**特殊点**；
		+ ![[Pasted image 20240131150311.png]]
		+ 因为 conx 的特点；
		+ 确定范围：为 0 到 Π
			+ 因为下面一半和上面一半一样，因此只需要求上面一半然后乘以 2 即可；
			+ ![[Pasted image 20240131150353.png]]
			+ ![[Pasted image 20240131150416.png]]
	+ 第三步：求解定积分
		+ ![[Pasted image 20240131150658.png]]
		+ 因为直接求 conx 在 0 到 PI 上无法求出，但求 0 到二分之 PI 上很简单，因此进行定积分代换：
			+ 设：
			+ ![[Pasted image 20240131150652.png]]
		+ 因此：
			+ ![[Pasted image 20240131150832.png]]
+ 题型： #定积分的几何应用 

### 1.2.2 旋转体的体积
#### 1.2.2.1 基本概念
**图示**
+ 图示：绕 X 轴旋转
	+ ![[Pasted image 20240131151121.png]]

##### **定理**： #定积分旋转体体积公式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. 绕 X 轴旋转时： $$V_{x}=\pi\int_{a}^{b}f^{2}(x)\operatorname{d}x$$
> 2. 绕 Y 轴旋转时： $$V_y=2\pi\int_a^bxf(x)\operatorname{d}x$$

**解释**
+ 只能算其饶坐标轴算，不可以解决其他情况；
+ 第一步：带入原式中的公式
+ 第二步：把公式中的 y、x 都用和 t 相关的公式代入进去，化成和 t 相关的定积分

**更一般的情况**
+ 情况： 
	+ 任意平面 $D$ 绕任意直线 $ax+b^y+c=0$
+ 二重积分公式：
	+ 这个是更加一般化的公式，旋转体体积问题、这个公式什么时候都可以使用：
	+ $$V=2\pi\int\int_{D}r(x,y)db$$
+ $V_{x}=\pi\int_{a}^{b}f^{2}(x)\operatorname{d}x$ 和 $V_y=2\pi\int_a^bxf(x)\operatorname{d}x$ 是此公式的特例；

**公式选择**
+ 如果是绕 X、Y 时，可以使用 $V_{x}=\pi\int_{a}^{b}f^{2}(x)\operatorname{d}x$ 和 $V_y=2\pi\int_a^bxf(x)\operatorname{d}x$
+ 如果是绕任意轴时，可以使用 $V=2\pi\int\int_{D}r(x,y)db$


#### 1.2.2.2 例题
**例题**：计算由 $\frac{x^2}{a^2}+\frac{y^2}{b^2}=1$ 所围成的图形绕 X 轴旋转一周所形成的旋转体的体积；
+ 分析  
	+ 椭圆的图形
		+ 只需要计算上面的一半就可以了；
		+ 不止，只需要计算四分之一部分就可以了；
		+ ![[Pasted image 20240131152357.png]]
+ 解析
	+ 由原式得 y 的公式：
		+ ![[Pasted image 20240131152437.png]]
	+ 由体积公式可知：
		+ $V_{x}=\pi\int_{a}^{b}f^{2}(x)\operatorname{d}x$
	+ 且，因为只需要求四分之一
		+ 因此只需要求 $[0,a]$ 范围上，它旋转的面积
	+ 因此，带入可得：
		+ ![[Pasted image 20240131152648.png]]
+ 题型： #定积分的几何应用 

**例题**：计算由摆线 $\begin{cases}x=a(t-\sin t)\\y=a(1-\cos t)&\end{cases}(0\leq t\leq2\pi)$ 与 X 图形分别绕 X 轴、Y 轴所称的旋转体的体积；
+ 分析
	+ 第一步：带入原式中的公式
	+ 第二步：把公式中的 y、x 都用和 t 相关的公式代入进去，化成和 t 相关的定积分
+ 解析：求 X 
	+ 求求旋转体的体积公式可知：
		+ 其中因为把 y 变成 y 和 x 的函数这一过程很麻烦，因此在下面的变化中，直接把 y 和 x 分别变成了和 t 的式子，带入：
		+ ![[Pasted image 20240131153411.png]]
	+ 继续求解，其中令 u=t/2
		+ ![[Pasted image 20240131153609.png]]
+ 题型： #定积分的几何应用 

### 1.2.3 平面曲线的弧长
#### 1.2.3.1 基本概念
##### **定义**： #弧长
> <font color="#ccc1d9">描述：</font> $$s_n=\sum_{i=1}^n\left\|\overline{M_{i-1}M_i}\right\|$$

**解释**
+ $s_n=\sum_{i=1}^n\left\|\overline{M_{i-1}M_i}\right\|$
	+ ![[Pasted image 20240131160512.png]]
	+ 很多个小段线段的求和
+ 弧长的极限：$s=\lim_{\lambda\to0}s_n=\lim_{\lambda\to0}\sum_{i=1}^n\left\|\overline{M_{i-1}M_i}\right\|$

##### **定理**： #弧长的计算
> <font color="#ccc1d9">描述：</font> $$\begin{aligned}
&1)C:y=y(x),\quad a\leq x\leq b,\quad s=\int_a^b\sqrt{1+{y^{\prime}}^2}dx \\
&2)C:\begin{cases}x=x(t)\\y=y(t)\end{cases}\alpha\leq t\leq\beta.\quad s=\int_\alpha^\beta\sqrt{x^{\prime2}+y^{\prime2}}dt \\
&3)C:\rho=\rho(\theta),\alpha\leq\theta\leq\beta.\quad s=\int_{\alpha}^{\beta}\sqrt{\rho^{2}+{\rho^{\prime}}^{2}}d\theta 
\end{aligned}$$

**解释**
+ 弧长都是弧微分积分

#### 1.2.3.2 例题
**例题**：$\text{计算旋轮线一拱}\quad x=a(t-\sin t),y=a(1-\cos t)\quad(0\leq t\leq2\pi)$ 的弧长
+ 分析
	+ 这种题是第二种形式：
		+ ![[Pasted image 20240131162204.png]]
+ 解析
	+ 将函数带入：
	+ ![[Pasted image 20240131162350.png]]
+ 题型： #定积分的几何应用 


### 1.2.4 旋转体侧面积 
##### **定理**： #旋转体侧面积计算
> 1 $S=2\pi\int_{a}^{b}f(x)\sqrt{1+f^{\prime2}(x)}dx$

**解释**  
+ 图示： 
	+ ![[Pasted image 20240415204510.png]]

## 1.3 物理应用 
### 1.3.1 变力做功 
**核心**
+ 不同深度的水，抽出去做的**功 = 位移 × 力** = 位移 × 密度 × $g$ × $dv$
+ 力 = 密度 × $g$ × $dv$
+ 对这个式子积分，即可得到功大小；

**例题分析**：一容器的内侧是由图中曲线绕 $y$ 轴旋转一周而成的曲面，该曲线由 $$x^{2}+y^{2}=2y(y\geq\frac{1}{2})\:\text{与}\:x^{2}+y^{2}=1(y\leq\frac{1}{2})$$ 连接而成，
+ 问题：(1) 求容器的容积； (II) 若将容器内盛满的水从容器顶部全部抽出，至少需要做多少功？
+ 图示：
	+ ![[Pasted image 20240415213032.png]]
+ 解析：第一问
	+ 上下圆的体积一样，因此只需要算当中一个圆绕轴转的体积即可；
	+ 求下半部分圆的面积微分：
		+ 假设现在从 $y$ 到 $y+dy$ 切一个很薄的平面，此时此平面的长为 $x^2\pi$ ；
		+ 将其乘以宽：$x^2{\pi}dy$，此时 $x^2{\pi}dy$ 代表的就是从 $y$ 到 $y+dy$ 的面积；
	+ 然后将此微分在-1 到 1/2 范围上积分，得到面积：
		+ $\pi\int_{-1}^{\frac{1}{2}}x^{2}\operatorname{d}y$
	+ 将此面积乘以 2，代换，得到：
		+ $V=2\pi\int_{-1}^{\frac{1}{2}}x^{2}\mathrm{d}y=2\pi\int_{-1}^{\frac{1}{2}}(1-y^{2})\mathrm{d}y=\frac{9\pi}{4}$
+ 解析：第二问 
	+ 因为力的大小不变，因此 功 = 力 × 位移
		+ 其中：力的大小不变，因此主要和当前位移下的面积有关（因为图形是个葫芦形）
		+ 力又等于其体积，因此就是体积乘以其密度，加上乘以 g；
	+ 位移：$2-y$
	+ $W=10^3\int_0^{\frac12}\pi(1-y^2)(2-y)g\operatorname{d}y+10^{3}\int_{\frac{1}{2}}^{2}\pi[2y-y^{2})](2-y)gdy)$
+ 核心：
	+ 一个小薄层的水抽出去做的功，等于位移 × 力 = 位移 × g × 密度 × $dv$ 
	+ g × 密度 × $dv$ = 力
 
### 1.3.2 压力问题 
**压强问题**
+ 公式：压强 $${p}=g\cdotρ\cdot h$$
+ 公式：压力 $$P=p\cdot A$$
	+ 其中：p 为压强，A 为面积

**例题分析**：某闸门的形状与大小如图所示，其中 y 轴为对称轴，闸门的上部为矩形 ABCD, DC=2 m, 下部由二次抛物线与线段 4 B 所围成，当水面与闸门的上端相平时，欲使闸门矩形部分承受的水压力与闸门下部承受的水压力之比为5:4，闸门矩形部分的高 h 应为多少 ？
+ 图示：
	+ ![[Pasted image 20240415215603.png]]
+ 分析：
	+ 深度的微小变化：
		+ 压强：p=gρ(h+1-y)
		+ 压力：p=gρ(h+1-y) 2 dy
	+ 式子：上半部分：
		+ $$P_1=2\int_1^{h+1}\rho g(h+1-y)\operatorname{d}y=2\rho g\biggl[(h+1)y-\frac{y^2}2\biggr]_1^{h+1}=\rho gh^2$$
	+ 下半部分：
		+ $p=gp(h+1-y)$
	+ 式子：下半部分：
		+ $$P_{2}=2\int_{0}^{1}\rho g(h+1-y)\sqrt{y}\mathrm{d}y=2\rho g\biggl[\frac{2}{3}(h+1)y^{\frac{3}{2}}-\frac{2}{5}y^{\frac{5}{2}}\biggr]_{0}^{1}$$

