## 14.1 基本概念 
##### **定义**： #向量空间基本概念
> <font color="#ccc1d9">描述：</font> $\text{若 }\xi_1,\xi_2,\cdots,\xi_n\text{ 是 }n\text{ 维向量空间 }\mathbb{R}^n\text{中的线性无关的有序向量组},\text{ 则任一向量 }\alpha\in\mathbb{R}^n\text{均可由}\xi_1,\xi_2,\cdots,\xi_n\text{线性表示,记为}$：$$a=a_{1}\xi_{1}+a_{2}\xi_{2}+\cdots+a_{n}\xi_{n}$$
> $\text{称有序向量组}\xi_1,\xi_2,\cdotp\cdotp\cdotp,\xi_n\text{是}\mathbf{R}^n\text{的一个基,基向量的个数 }n\text{ 称为向量空间的维数,而}\left[a_1,a_2,\cdotp\cdotp\cdotp,a_n\right]$ $([a_1,a_2,\cdots,a_n]^\mathrm{T})\text{称为向量}\alpha\text{在基}\xi_1,\xi_2,\cdots,\xi_n\text{下的坐标,或称为}\alpha\text{的坐标行(列)向量}.$


## 14.2 基变换与坐标变换 
##### **定理**： #基变换定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{若}\eta_1,\eta_2,\cdots,\eta_n\text{和}\xi_1,\xi_2,\cdots,\xi_n\text{是}\mathbb{R}^n\text{中的两个基,且有关系}$：
> $$[\eta_1,\eta_2,\cdots,\eta_n]=[\xi_1,\xi_2,\cdots,\xi_n]\begin{bmatrix}c_{11}&c_{12}&\cdots&c_{1n}\\c_{21}&c_{22}&\cdots&c_{2n}\\\vdots&\vdots&&\vdots\\c_{n1}&c_{n2}&\cdots&c_{nn}\end{bmatrix}=[\xi_1,\xi_2,\cdots,\xi_n]C,$$
> 1. $\text{则}\left(*\right)\text{式称为由基}\xi_1,\xi_2,\cdots,\xi_n\text{到基}\eta_1,\eta_2,\cdots,\eta_n\text{的基变换公式;}$
> 2. ${矩阵}C\text{称为由基}\xi_1,\xi_2,\cdots,\xi_n\text{到基}\eta_1,\eta_2,\cdots,\\ \eta_n\text{的过渡矩阵},C\text{的第}i\text{列即是}\eta_i\text{在基}\xi_1,\xi_2,\cdots,\xi_n\text{下的坐标},\text{且过渡矩阵}C\text{是可逆矩阵}$

**解释**
+ 在方程中，可以将当前的坐标系的计算、转换为其他坐标系的计算；

**概念**：基坐标变换
+ 举例：
	+ 可以理解为： $\begin{bmatrix}2&&-1\\1&&1\end{bmatrix}$ 矩阵将 `[1,0]` 和 `[0,1]` 基向量进行变换；
	+ 即：变换后的向量仍旧是相同的线性组合，不过使用的是新的基向量；
	+ $\begin{bmatrix}2&&-1\\1&&1\end{bmatrix}\begin{bmatrix}-1\\2\end{bmatrix}=-1\begin{bmatrix}2\\1\end{bmatrix}+2\begin{bmatrix}-1\\1\end{bmatrix}=\begin{bmatrix}-4\\1\end{bmatrix}$
+ 图示： 
	+ ![[Drawing 2024-06-29 19.34.16.excalidraw.png]]

##### **定理**： #坐标变换定理 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设 $\alpha$ 在基 $\xi_1,\xi_2,\cdots,\xi_n$ 和基 $\eta_1,\eta_2,\cdots,\eta_n$ 下的坐标分别是 $x=[x_1,x_2,\cdots,x_n]^{\mathrm{T}},y=[y_1$, $y_{2},\cdots,y_{n}]^{T},即$：$$\alpha=\left[\xi_{1},\xi_{2},\cdots,\xi_{n}\right]x=\left[\eta_{1},\eta_{2},\cdots,\eta_{n}\right]y$$
> $\text{又由基}\xi_1,\xi_2,\cdots,\xi_n\text{到基}\eta_1,\eta_2,\cdots,\eta_n\text{的过渡矩阵为}C,\text{即}$：
> $$[\eta_{1},\eta_{2},\cdots,\eta_{n}]=[\xi_{1},\xi_{2},\cdots,\xi_{n}]C,$$
> 则：$$\alpha=[\xi_{1},\xi_{2},\cdots,\xi_{n}]x=[\eta_{1},\eta_{2},\cdots,\eta_{n}]y=[\xi_{1},\xi_{2},\cdots,\xi_{n}]Cy$$
> 得到坐标变换公式：$x=Cy或y=C^{-1}x$


##### **定理**： #施式正交化
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>原本线性无关的向量，将其变成垂直的向量；
> $$\begin{cases}\beta_{1}=\alpha_{1}\\\beta_{2}=\alpha_{2}-\frac{(\alpha_{2},\beta_{1})}{(\beta_{1},\beta_{1})}\beta_{1}\end{cases}$$

**解释**
