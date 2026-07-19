## 19.1 特征值与特征向量定义
### 19.1.1 基本概念 
##### **定义**： #特征值与特征向量 
> <font color="#ccc1d9">描述：</font> $设A是n阶矩阵,\lambda 是一个数,若存在n维非零列向量\xi,使得：$
> $$A\xi=\lambda\xi$$
> 则称：
> 1. $\lambda$ 为特征值；
> 2. $\xi$ 是 A 的对应于特征值 $\lambda$ 的特征向量；

**解释**
+ 特征： 
	+ 反应 A 矩阵的某一个性质；
+ 解释：特征值
	+ 比如 A 是一个矩阵时，当 A 作用到一个向量上时，其结果可以用一个数来表示（用一个数来对这个向量进行放缩），此时这个数就是特征值；
	+ 在空间上，可以体现空间中的最值、相近等性质；
+ 概念： 
	+ `n` 阶的矩阵，就会有 `n` 个特征值，通过看这一个数、就可以知道 `A` 矩阵的某些特性；
+ 解释：$\xi$
	+ $\xi$ 一定是不等于 0 的；
	+ 因为如果 $\xi$ 等于 0，则表示当前矩阵只有唯一零解，即 `S=r(A)` ，此时将 A 作用在 $\xi$ 上是，体现不出来 A 的作用，因为矩阵作用在零向量上还是 0，因此在这里 $\xi$ 是非零向量；
	+ 能体现出来效果，这样才能知道特征值的作用；
+ 含义： 
	+ ![[Pasted image 20240701195431.png]]

**分析**：对 $A\xi=\lambda\xi$ 进行分析
+ 步骤：
	+ `->` $\lambda\xi-A\xi=0$  // $\xi$ 为非零向量
	+ `->` $(\lambda E-A)\xi=0$ // 提取公因式
	+ `->` $(\lambda E-A)X=0$ 
		+ // 把 $\xi$ 设置为是当前方程组的解；
		+ // 因为 `X` 是 $\xi$，而 $\xi$ 是非零向量，而当前式子等于 0 `->` 也就代表当前的方程是齐次方程；
		+ // 因为是齐次方程，所以当前矩阵 $\lambda E-A$ 是线性相关的 `<-` 线性相关定理 4：[[Lecture 11：向量与向量组的线性相关性]]；
		+ // 因为 $\lambda E-A$ 是线性相关的，所以当前方程组 `S=n-r(A)<n`，即方程的秩小于 n；
		+ // 根据 $n\text{个}n\text{维列向量}a_1,a_2,\cdots,a_n\text{线性相关}\Leftrightarrow\left|a_1,a_2,\cdots,a_n\right|=0$ ，所以得到 $|\lambda E-A|=0$ 
	+ `->` $|\lambda E-A|=0$ 
		+ // 这里可以求出 $\lambda_i(i=1,2,3...)$
+ 图示： 
	+ ![[Drawing 2024-07-01 19.50.31.excalidraw.png]]

##### **定义**： #特征方程
> <font color="#ccc1d9">描述：</font> $$\begin{vmatrix}\lambda E-A\end{vmatrix}=\begin{vmatrix}\lambda-a_{11}&-a_{12}&\cdots&-a_{1n}\\-a_{21}&\lambda-a_{22}&\cdots&-a_{2n}\\\vdots&\vdots&&\vdots\\-a_{n1}&-a_{n2}&\cdots&\lambda-a_{nn}\end{vmatrix}=0$$

**解释**
+ $|\lambda E-A|$：称之为特征方程

### 19.1.2 几何解释 
**概念**：特征值与特征向量的几何解释
+ 概念： 
	+ 在基向量被变换后，有一些解变换后以及变换前只对应于比例的变换，而角度位置未发生改变；
	+ 用于描述特征向量的变换比例的值，称之为特征值；
	+ 特征向量就是那些在变换后、依然停留在原本的直线上的向量；
+ 图示： 
	+ ![[Pasted image 20240701194822.png]]

**概念**：特征值为负值时
+ 图示： 
	+ ![[Pasted image 20240701195210.png]]

## 19.2 求法 
### 19.2.1 求特征值与特征向量的方法
**方法**：求特征值   
+ 第一步：写特征方程 $|\lambda E-A|$
	+ $A=\begin{bmatrix}2&2&-2\\2&5&-4\\-2&-4&5\end{bmatrix}$
	+ $|\lambda E-A|=\left|\begin{matrix}\lambda-2&-2&2\\-2&\lambda-5&4\\2&4&\lambda-5\end{matrix}\right|$
+ 第二步：计算特征方程的行列式，得到关于 $\lambda$ 的方程；
	+ 最后肯定会得到一个类似于 $\lambda^3+a\lambda^2+b\lambda+c=0$ 的方程，然后化成求根的形式；
+ 第三步：求出几个特征根；

**方法**：求特征向量
+ 第一步：将求得的特征值带入到 $(\lambda E-A)=0$ 的 $\lambda$ 当中，得到 $\lambda E-A$ 的矩阵；
+ 第二步：求秩以及基础解系
	+ 2.1 将得到的矩阵化为阶梯型矩阵，得到秩后，根据 `S=n-r(A)`，计算其基础解系（受约束自由变量的 `S` 个向量）；
		+ 这 `S` 个解出来的向量，构成了解的空间，这个二维平面上的所有向量、都是当前代入得 $\lambda_i$ 对应得特征向量；
		+ 除了零向量；
	+ 2.2 如果不能根据化简得到阶梯型矩阵，还可以根据 `行列式=0` 对秩得限制、以及当前矩阵 $\lambda E-A$ 中无关项向量得个数，知道其当前得秩，并得到其极大无关组；
+ 第三步：根据第二步，得到当前 $\lambda=某个值$ 时，得到 $\xi=k_1\xi_1+k_2\xi_2$
	+ 其中看 `k1`、`k2` 不能同时为 0；
+ 第四步：如果还有其他 $\lambda_i$，继续按照以上步骤求特征向量 $\xi$；

### 19.2.2 求根
**补充**：找根方法
+ 如果在 $\lambda^3+a\lambda^2+b\lambda+c=0$ 当中没有常数项，则 $\lambda=0$ 肯定是它得根；
+ 如果 $\lambda^3+a\lambda^2+b\lambda+c=0$ 其中，$a+b+c=0$，则 $\lambda =1$ 肯定是它们得根： $(\lambda -1)$
+ 如果 $\lambda^3+a\lambda^2+b\lambda+c=0$ 中偶次项系数之和等于奇次项系数之和，则 $f(-1)=0$，所以 $-1$ 是它的根；  

**方法**：试根法 
+ 概念： 
	+ 利用找根方法得到某一个根之和，使用多项式得带余除法，计算器二次项式；
+ 举例：
	+ $$\begin{aligned}
\lambda^{2}-2\lambda-8 \\
\begin{aligned}\lambda-1\sqrt{\lambda^{3}-3\lambda^{2}-6\lambda+8}\\\frac{\lambda^{3}-\lambda^{2}}{-2\lambda^{2}-6\lambda}\end{aligned} \text{.}  \\
\frac{-2\lambda^{2}+2\lambda}{-8\lambda+8} \\
\frac{-8\lambda+8}{0}
\end{aligned}$$

##### **定理**： #多项式求根
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设以下式子是系数 $a_i$ 都是整数的多项式： $$f\left(x\right)=1·x^{k}+a_{k-1}x^{k-1}+\cdots+a_{1}x+a_{0}$$ 
> 则 $f(x)=0$ 的有理根都是整数，且 $a_0$ 的因子；

**解释**
+ 方程的解是 $a_0$ 的因子
+ 因此可以先框定它的因子，然后知道了因子后、就确定了它的范围；

## 19.3 重要性质与结论 
### 19.3.1 特征值的性质与结论 
**概念**：性质一
+ $$\lambda_0是A的特征值<=>|\lambda_0 E-A|=0(建立方程求参数或证明行列式|\lambda_0 E-A|=0$$
+ 同理：$$\lambda_0\text{不是}A\text{ 的特征值}\Leftrightarrow|\lambda_0E-A|\neq0\text{(矩阵可逆,满秩)}$$
+ 补充： 
	+ 若 $|aA+bE|=0$（或者 $aA+bE$ 不可逆），`a` 不等于 0，则称 $-\frac{b}{a}$ 是 `A` 的特征值；

**概念**：性质二
+ 性质： 
	+ 若 $\lambda_1,\lambda_2,\cdots,\lambda_n\text{是}A\text{的}n\text{个特征值,则}$：
	+ $$\begin{cases}\left|A\right|=\lambda_{1}\lambda_{2}\cdots\lambda_{n},\\\mathrm{tr}\left(A\right)=\lambda_{1}+\lambda_{2}+\cdots+\lambda_{n}.\end{cases}$$
+ **结论一**：
	+ 1. 有特征值为 `0` 的矩阵，其行列式一定为 `0`
	+ 2. $\lambda_{1}+\lambda_{2}+\cdots+\lambda_{n}$ 特征值的和，等于当前矩阵 `A` 的主对角线元素之和 `tr(A)`
+ **结论二**：基于结论一和证明
	+ 由式子（1）和式子（2）可得：
	+ $$\begin{cases}a_{11}+a_{22}+a_{33}=\lambda_{1}+\lambda_{2}+\lambda_{3},\\A_{11}+A_{22}+A_{33}=\lambda_{2}\lambda_{3}+\lambda_{1}\lambda_{3}+\lambda_{1}\lambda_{2},\\\left|A\right|=\lambda_{1}\lambda_{2}\lambda_{3}.\end{cases}$$
	+ 且 `k` 阶主子式之和 = 任意 `k` 个特征值乘积之和；
+ 证明：三阶时，用行列式的性质、把 $|\lambda_0 E-A|$ 拆成了一个一元三次多项式；
	+ $$式子(1)\quad|\lambda_0 E-A|=\begin{vmatrix}\lambda-a_{11}&-a_{12}&-a_{13}\\-a_{21}&\lambda-a_{22}&-a_{23}\\-a_{31}&-a_{32}&\lambda-a_{33}\end{vmatrix}=\begin{vmatrix}\lambda-a_{11}&0-a_{12}&0-a_{13}\\0-a_{21}&\lambda-a_{22}&0-a_{23}\\0-a_{31}&0-a_{32}&\lambda-a_{33}\end{vmatrix}=\lambda^{3}-\left(a_{11}+a_{22}+a_{33}\right)\lambda^{2}+\left(A_{11}+A_{22}+A_{33}\right)\lambda-\left|A\right|$$
	+ $$式子(2)\quad\left|\lambda E-A\right|=\left(\lambda-\lambda_1\right)\left(\lambda-\lambda_2\right)\left(\lambda-\lambda_3\right)=\lambda^3-(\lambda_1+\lambda_2+\lambda_3)\lambda^2+(\lambda_1\lambda_2+\lambda_1\lambda_3+\lambda_2\lambda_3)\lambda-\lambda_1\lambda_2\lambda_3$$
+ 补充：主子式
	+ 主子式一定是行列式，并且最左上方和最右下方的元素的**下标**一定是相同的 `<-` 同行同列的；
	+ 三维时，一共有三个主子式：$\begin{vmatrix}a_{22}&a_{23}\\a_{32}&a_{33}\end{vmatrix}=A_{11},\begin{vmatrix}a_{11}&a_{13}\\a_{31}&a_{33}\end{vmatrix}=A_{22},\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}=A_{33}$

### 19.3.2 特征向量的性质与结论
**概念**：性质一
+ $$\xi\left(\neq\mathbf{0}\right)\text{是}A\text{ 的属于 }\lambda_0\text{ 的特征向量}\Leftrightarrow\xi\text{是}\left(\lambda_0E-A\right)x=\mathbf{0}\text{ 的非零解}$$

**概念**：结论一
+ `k` 重特征值 $\lambda$，至多只有 `k` 个线性无关的特征向量；

**概念**：结论二
+ $若\xi_1,\xi_2$ 是 `A` 的属于不同特征值 $\lambda_1,\lambda_2$ 的特征向量，则 $\lambda_1,\lambda_2$ 线性无关；

**总结**：$\text{矩阵}A\begin{cases}\lambda_{1}\neq\lambda_{2}\Rightarrow\xi_{1},\xi_{2}\text{线性无关}\\\lambda_{1}=\lambda_{2}\Rightarrow\xi_{1},\xi_{2}\text{可能}\begin{cases}\text{线性相关}\\\text{线性无关}\end{cases}\end{cases}$

**概念**：结论三
+ $\text{若}\xi_1,\xi,\text{是}A\text{ 的属于同一特征值}\lambda\text{的特征向量,则非零向量}k\xi_1+k_2\xi_2\text{仍是}A\text{ 的属于特征值}\lambda\text{的}$ 特征向量. (常考其中一个系数 (如 $k_2$)等于 `0` 的情形)；

**概念**：结论四
+ $\text{若}\xi_1,\xi_2\text{是}A\text{ 的属于不同特征值}\lambda_1,\lambda_2\text{的特征向量,则当}k_1\neq0,k_2\neq0\text{时,}k_1\xi_1+k_2\xi_2\text{不是}A\text{ }$ 的任何特征值的特征向量. ( 常考 $k_1=k_2=1$ 的情形) 

**概念**：结论五
+ 设 $\lambda_1,\lambda_2$ 是 A 的两个不同的特征值，$\xi$ 是对应于 $\lambda_1$ 的特征向量，则 $\xi$ 不是对应于 $\lambda_2$ 的特征向量（即一个特征向量不能属于两个不同的特征值）

### 19.3.3 常用矩阵的特征值与特征向量 
**总结**：常用矩阵的特征值与特征向量
+ 图示： 
	+ ![[Pasted image 20240627205621.png]]

**概念**：矩阵为 $f(A)$ 
+ 重要公式 - 当 `A` 是一个多项式等于 `0`
+ 公式： 
	+ $$A\xi=\lambda \xi \rightarrow f(A)\xi=f(\lambda)\xi$$
+ 证明： 
	+ 比如：$A^2\xi=\lambda A\xi=\lambda^2\xi$
+ 举例： 
	+ 当 $A^2-2A+3E$ 的 $\lambda$：$\lambda^2-2\lambda+3$
+ 注意： 
	+ 由 $A$ 的多项式，获得的关于 $\lambda$ 的方程，只是代表了在当前 A 的多项式条件下、$\lambda$ 可能的取值（满足什么关系、范围 ），而不代表当前特征方程的不同 $\lambda$；

**概念**：矩阵为 $A^*$
+ 公式： 
	+ 当矩阵为 $A^*$ 时，其特征值等于 $\frac{|A|}{\lambda}$；
	+ 并且因为 $|A|=\lambda_1\lambda_2\lambda_3$，所以 $\frac{|A|}{\lambda}=\lambda_1\lambda_2或\lambda_1\lambda_3或\lambda_2\lambda_3$

**补充**：$P^{-1}AP$ 时，其特征值没发生变化 `->` 相似；但特征向量发生了变化：$P^{-1}\xi$； 

**概念**：秩 1 矩阵的结论 
+ 当 `r(A)=1` 时，矩阵 $A_{n*n}$ 一定可以化为两个非零行列向量：$\alpha\beta^{T}$ 它们两者的乘积；
+ 并且：$\lambda_1=\lambda_2=\lambda_3=...=\lambda_{n-1}=0$
+ 并且：$\lambda_n=tr(A)=\beta^T\alpha$