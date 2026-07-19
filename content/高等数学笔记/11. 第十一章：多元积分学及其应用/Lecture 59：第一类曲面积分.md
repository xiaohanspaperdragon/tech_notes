---
title: Lecture 51：对面积的曲面积分
tags:
  - 数学
  - 曲面积分
categories: 
date: 2024-02-12
---
---
## 59.1 第一类曲面积分：对面积的曲面积分
**引例**：已知曲面构件具有连续面密度ρ(x, y, z)，求其质量 M；
+ 图示
	+ ![[Pasted image 20240212143059.png]]
+ 用每一个小面积上的密度乘以其面积，然后全部求和，得到完整的质量：$M=\lim_{\lambda\to0}\sum_{k=1}^n\rho(\xi_k,\eta_k,\zeta_k){\Delta S_k}$

##### **定义**： #第一类曲面积分
> <font color="#ccc1d9">描述：</font> $\text{设}\sum\text{为光滑曲面},f(x,y,z)\text{ 是定义在}\sum\text{上的一}\text{个有界函数,若对}\Sigma\text{ 做任意分割和局部区域任意取点},$ 可以得到
> 乘积和式极限：$\lim_{\lambda\to0}\sum_{k=1}^nf\left(\xi_k,\eta_k,\zeta_k\right)\Delta S_k$ 都存在，则称此极限为函数 $f(x,y,z)$ 在曲面 $\Sigma$ 上对面积的曲面积分；
> 记作：$$\iint_{\Sigma}f(x,y,z)dS=\lim_{\lambda\to0}\sum_{i=1}^{n}f(\xi_{i},\eta_{i},\zeta_{i})\Delta S_{i}$$

**解释**
+ 概念：
	+ $ds$ 相当于小曲面的面积；
	+ $f(x,y,z)$ 相当于曲面的密度；
	+ $f(x,\gamma,z)\operatorname{d}S$ 表示求一小块的质量；
	+ $\iint_{\Sigma}f(x,\gamma,z)\operatorname{d}S$ 表示对整个面上，每个小块求和极限；
	+ $\Sigma$ 称之为积分曲面；
+ 解释：
	+ 每个点的函数值，乘以这个点的小区域的面积，求和、取极限，得到对面积的面积分 `->` 和曲面的方向没关系，因为面积和方向无关系；
+ 性质：
	+ 1. 积分曲面无关性：$$\iint_{\Sigma}f(x,y,z)dS=\iint_{-\Sigma}f(x,y,z)dS$$
	+ 2. 曲面积分存在性：$若 f(x,y,z)\text{在光滑曲面}\sum\text{ 上连续}$，则对面积的曲面积分存在；
	+ 3. 对积分域的可加性：若 $\sum$ 是分片光滑的，则有：$\iint_{\Sigma}f(x,y,z)\operatorname{d}S=\iint_{\Sigma_{1}}f(x,y,z)\operatorname{d}S+\iint_{\Sigma_{2}}f(x,y,z)\operatorname{d}S$
	+ 4. 对积分的线性性质：$$\begin{aligned}\iint_{\Sigma}[k_1f(x,y,z)\pm k_2g(x,y,z)]&\operatorname{d}S=k_1\iint_{\Sigma}f(x,y,z)\operatorname{d}S\pm k_2\iint_{\Sigma}g(x,y,z)\operatorname{d}S\end{aligned}$$

## 59.2 对面积的曲面积分的计算
### 59.2.1 直接法
##### **定理**： #第一类曲面积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 有光滑曲面，其 $\Sigma:z=z(x,y),(x,y)\in D_{xy}，f(x,y,z)\text{ 在 }\sum\text{上连续}$
> 则曲面积分 $\iint_{\Sigma}f(x,y,z)dS\text{存在},\text{且有}$：
> $$\iint_{\Sigma}f(x,y,{z}){\mathrm{d}S}=\iint_{D_{xy}}f(x,y,z(x,y))\sqrt{1+{z_x}^2(x,y)+{z_y}^2(x,y)}\mathrm{d}x\mathrm{d}y$$

**解释**
+ 本质：
	+ 把**难求的曲面面积，投影成一个对 x、y 上的平面二重积分**来完成计算；
	+ 即把曲面 $\sum$ 投影到 $D_{xy}$ 上，化成 `D` 上的一个二重积分；；
	+ ${\text{若曲面由方程 }x}=x(y,z){\text{或 }\operatorname*{y}}=y(z,x)\text{ 给出,也可类似地把对面积的面积分化为相应}\text{的二重积分}$；
+ 转化：
	+ 将 z 用关于 xy 的式子带进去，得到二重积分；
+ 注意：
	+ 当出现类似 $x^2+y^2=1$ 这种中心轴为 `z` 轴的形式，则无法直接做；
	+ 此时应该使用 $y=y(x,z)$ `->` $\iint_{\Sigma}f(x,y,{z}){\mathrm{d}S}=\iint_{D_{xy}}f(x,y=y(x,z),z)\sqrt{1+{z_x}^2(x,z)+{z_z}^2(x,z)}\mathrm{d}x\mathrm{d}z$
	+ 同理对于 $x=x(y,z)$ 的形式；

### 59.2.2 奇偶性与对称性
##### **定理**： #第一类曲面积分的奇偶性    
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若曲面 $\sum$ 关于 $xoy$ 对称，则：
> $$\iint_{\Sigma}f(x,y,z)\mathrm{d}S=\begin{cases}2\iint_{\sum_{z>0}} f(x,y,z)\mathrm{d}S,&f(x,y,-z)=f(x,y,z)\\0&f(x,y,-z)=-f(x,y,z)\end{cases}$$


**知识点**：对称性
+ $x^2+y^2+z^2=1$ 具有很好的对称性；
+ 所以可以利用对称性简化计算： $\iint_{\Sigma}(x^2+y^2)ds=(\frac{2}{3})\iint (x^2+y^2+z^2)ds=(\frac{2}{3})\iint 1ds=\frac{2}{3}4\pi$

## 59.3 常考题型 

---
### 题型： #第一类面积分的计算 
#### PART 1：解题方法

#### PART 2：典型例题
**例题**：$\Sigma=\{(x,y,z)\mid x+y+z=1,x\geq0,y\geq0,z\geq0\}，则\iint_\Sigma y^2dS$
+ 分析
	+ 图示：
		+ ![[Pasted image 20240523230436.png]]
	+ 可以将其化成再 `Dxy` 上的投影域上的二重积分；
	+ 因为 $ds=\sqrt{1+{z_x}^2(x,y)+{z_y}^2(x,y)}dxdy$

#### PART 3：知识点复盘