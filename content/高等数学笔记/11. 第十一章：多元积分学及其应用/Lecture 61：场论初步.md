## 61.1 方向导数 
### 61.1.1 方向导数基本概念
 ##### **定义**： #方向导数 
> <font color="#ccc1d9">描述：</font> $$\frac{\partial f}{\partial l}\Bigg|_{(x_0,y_0)}=\lim_{t\to0^+}\frac{f(x_0+t\cos\alpha,y_0+t\cos\beta)-f(x_0,y_0)}t$$

**解释**
+ 作用：
	+ 对 x 以及对 y 的偏导反映了函数沿着 x 或者 y 方向上的变化；
	+ 但如果需要描述函数沿着其他方向上的变化时，就需要使用方向导数；
+ 概念：
	+ 1. $\cos \alpha$ 和 $\cos\beta$ 表示了直线方向；
	+ 2. $x_0+t\cos\alpha,y_0+t\cos\beta$ 表示了直线方向上的一点；
	+ 3. $\frac{f(x_0+t\cos\alpha,y_0+t\cos\beta)-f(x_0,y_0)}t$：一点的方向值减去以函数值后除以 `t`，当 `t->0` 时，表示了这一点的方向导数值；
+ 注意：
	+ `t` 只能趋向于 `0` 正；

### 61.1.2 方向导数的可微性判断
##### **定理**： #方向导数的存在性判定
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若 $z=f(x,y)$ 可微，则这一点沿着任何方向上的方向导数都存在，且方向导数等于两个偏导数、乘以其方向余弦，如下式：
> $$\frac{\partial f}{\partial l}=\frac{\partial f}{\partial x}\cos\alpha+\frac{\partial f}{\partial y}\cos\beta $$

**解释**：可微 `->` 任意方向可导；

## 61.2 梯度
##### **定义**： #梯度
> <font color="#ccc1d9">描述：</font> $\text{设 }f(x,y)\text{ 在点 }P(x_0,y_0)\text{ 有连续一阶偏导数}$，则：$$\mathrm{grad}u=f_x(x_0,y_0)\mathbf{i}+f_y(x_0,y_0)\mathbf{j}$$

**解释**：梯度的意义
+ 每个点有无限个方向导数，但**梯度方向上的方向导数最大**；
+ 方向导数的最大值，就是**梯度的模**；

## 61.3 散度与旋度
##### **定义**： #散度 
> <font color="#ccc1d9">描述：</font>设有向量场 $A(x,y,z)=({P,Q,R})$ ，则：
> $$\mathbf{divA}=\frac{\partial P}{\partial x}+\frac{\partial Q}{\partial y}+\frac{\partial R}{\partial z}$$

**解释**
+ 散度是一个数；

##### **定义**： #旋度
> <font color="#ccc1d9">描述：</font> 设有向量场 $A(x,y,z)=({P,Q,R})$ ，则：
> $$\mathbf{rotA}=\begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\\frac\partial{\partial x}&\frac\partial{\partial y}&\frac\partial{\partial z}\\P&Q&R\end{vmatrix}$$

**解释**
+ 旋度是一个向量；