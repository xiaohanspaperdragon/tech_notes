## 21.1 二次型的定义与矩阵表示
##### **定义**： #二次型 
> <font color="#ccc1d9">描述：</font>n 元变量的二次齐次多项式表达式为：
> $$f(x_1,x_2...x_n)=a_{11}x_1^2+2a_{12}x_{1}x_{2}+\cdots+2a_{1n}x_{1}x_{n}+...$$
> 因为 $x_ix_j=x_jx_i$ 所以：$$\begin{aligned}
f(x_{1},x_{2},\cdots,x_{n})& =a_{11}x_{1}^{2}+a_{12}x_{1}x_{2}+\cdots+a_{1n}x_{1}x_{n}+a_{21}x_{2}x_{1}+a_{22}x_{2}^{2}+\cdots+a_{2n}x_{2}x_{n}+\cdots  \\
&a_{n1}x_{n}x_{1}+a_{n2}x_{n}x_{2}+\cdots+a_{nn}x_{n}^{2} \\
&=\sum_{i=1}^n\sum_{j=1}^na_{ij}x_ix_j ,
\end{aligned}
$$
  其中 `(*)` 式称为完全展开式，`(**)` 式称为和式 .令：$$A=\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{m}\end{bmatrix}, x=\begin{bmatrix}x_{1}\\x_{2}\\\vdots\\x_{n}\end{bmatrix},$$得到 $f\left(x\right)=x^{\mathrm{T}}Ax.$

**解释**
+ 举例：二次型对应的非对称矩阵
	+ $f(x_1,x_2,x_3)=x_1^2+x_2^2+x_3^2+4x_1x_2,$
	+ $f\left(x_{1}, x_{2}, x_{3}\right)=\left[x_{1}, x_{2}, x_{3}\right]\left[\begin{matrix}1&4&0\\0&1&0\\0&0&1\end{matrix}\right]\left[\begin{matrix}x_{1}\\x_{2}\\x_{3}\end{matrix}\right]$
+ 举例：二次型对应的对称矩阵 
	+ $f\left(x_{1},x_{2},x_{3}\right)=2x_{1}^{2}+2x_{2}^{2}+2x_{3}^{2}-2x_{1}x_{2}-2x_{2}x_{3}+2x_{1}x_{3}$
	+ $f(x)=(x_{1}x_{2}x_{3})\begin{pmatrix}2&-1&1\\-1&2&-1\\1&-1&2\end{pmatrix}\begin{pmatrix}x_{1}\\x_{2}\\x_{3}\end{pmatrix}$
	+ 其中，矩阵 A 的秩就是 $f(x)$ 的秩；
+ 注意：
	+ 一个二次型可以有不同的写法，例如三元二次型；
+ 概念： 
	+ 写对称阵具有唯一性，并且一定可以相似对角化，并且一定可以使用正交矩阵进行相似对角化；
+ 一个额外的规定： 
	+ 一个二次型可以有不同的写法，代表二次型的矩阵就不唯一了，不利于研究二次型问题； 
	+ 现在我们立了“规矩”，规定二次型的矩阵必须是对称矩阵，代表二次型的矩阵就是唯一的, 所以只有对称矩阵才是二次型的矩阵；

---

## 21.2 合同变换
### 21.2.1 线性变换的定义与合同变换 
##### **定义**： #线性变换 
> <font color="#ccc1d9">描述：</font> $对于n元二次型f\left(x_{1},x_{2},\cdots,x_{n}\right),若令$：
> $$\begin{cases}x_{1}=c_{11}y_{1}+c_{12}y_{2}+\cdots+c_{1n}y_{n},\\x_{2}=c_{21}y_{1}+c_{22}y_{2}+\cdots+c_{2n}y_{n},\\\cdots\cdots\\x_{n}=c_{n1}y_{1}+c_{n2}y_{2}+\cdots+c_{nn}y_{n},\end{cases}$$
> 则：$$\begin{aligned}\text{记}x=\begin{bmatrix}x_1\\x_2\\\vdots\\x_n\end{bmatrix}, C=\begin{bmatrix}c_{11}&c_{12}&\cdots&c_{1n}\\c_{21}&c_{22}&\cdots&c_{2n}\\\vdots&\vdots&&\vdots\\c_{n1}&c_{n2}&\cdots&c_{nn}\end{bmatrix}, y=\begin{bmatrix}y_1\\y_2\\\vdots\\y_n\end{bmatrix}, \text{则}(*)\text{式可写为}\\x=Cy,\end{aligned}$$
> 其中 `(*)` 式成为线性变换；
> 若线性变换的系数矩阵 `C` 可逆，即 `C≠0`，则称为**可逆线性变换**；
> 现在给出 $f(x)=x^TAx$，令 $x=Cy$，则得到：$$
f\left(x\right)=\left(Cy\right)^{T}A\left(Cy\right)=y^{T}\left(C^{T}AC\right)y=y^{T}By=g(y).
$$
  其中：$B=C^TAC$ 称之为合同变换；

**解释**
+ 解释： 
	+ 线性变换在函数当中，就是换元法；
	+ 将 `y->x`
	+ 变换的数字是线性的乘法； 
+ 合同变换： 
	+ 对于 `n` 元的

### 21.2.1 矩阵合同的定义和性质
##### **定义**： #合同二次型 
> <font color="#ccc1d9">描述：</font>设 `A, B` 为 `n` 阶矩阵，若存在可逆矩阵 `C`，使得：$$C^TAC=B$$
> 则称 `A` 与 `B` 合同，记作 `A~=B`；此时称其对应的二次型 $f(x)$ 与 $g(y)$ 为合同二次型；

**解释**
+ 解释： 
	+ A 表征的是 $f(x)=x^TAx$ 下的形态；
	+ B 表征的是 $g(x)=y^TBy$ 下的形态； 
	+ 但 $f(x)=g(x)$，所以 A 和 B 其实只是代表了不同的形态：即不同的基向量的坐标系下，看到的同一个事物的不同形态；
+ 概念： 
	+ 从一个表达式变成另外一个表达式，只要中间是可逆线性变换，则称这个变换为合同；
+ 注意： 
	+ 考研研究的合同，都是在 `A、B` 均是在对称矩阵的条件下的；
	+ 因为我们讨论都是在二次型的条件下的 `->` 是对称阵的；
+ 意义： 
	+ 为什么需要“合同”：
		+ 如果 A 和 B 是和合同的，则 A 和 B 是秩相同的 `<-` 合同一定是等价的；
		+ 可逆线性变换不改变矩阵的秩序（二次型也）
	+ 其中 $A=A^T$ 
		+ 则$B^{T}=\left(C^{T}AC\right)^{T}=C^{T}A^{T}C=C^{T}AC=B$
+ 举例： 
	+ ![[Pasted image 20240704170125.png]]

## 21.3 二次型的标准型、规范型
### 21.3.1 定义 
##### **定义**： #标准型 
> <font color="#ccc1d9">描述：</font>若二次型中只含有平方项，没有交叉项 (即所有交叉项的系数全为零)，即形如：$d_{1}x_{1}^{2}+d_{2}x_{2}^{2}+\cdots+d_{n}x_{n}^{2}$
> 进一步可以把标准型写成规范型：$\text{若标准形中,系数}d_i\left(i=1,2,\cdots,n\right)\text{的取值范围为}\left\{1,-1,0\right\},即形如\square\left(x_{1}^{2}+\cdots+x_{p}^{2}-x_{p+1}^{2}-\cdots-x_{p+d}^{2}\right)$ 
> 的二次型称之为规范型；

**解释**
+ 一般型： 
	+ 如果有交叉项，则称之为一般型；
+ 解释： 
	+ 通过伸缩变换，可以把标准型化为规范型，即若干个系数为 `1` 或 `-1`；
	+ 且任何一个二次型，都一定可以化为一个规范型；
	+ 并且只要二次型定了，则一定对应一个唯一的规范型；
+ 目的： 
	+ 规范型就是二次型的最佳表现形态；
	+ 其实标准型就是了，所以一般化为标准型就够了；

### 21.3.1 相关定理
##### **定理**： #二次型定理1配方法 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{任何二次型}f(x)=x^TAx\text{均可通过配方法}(\text{作可逆线性变换}x=Cy)\text{化成标准形及规范形}；$
> 矩阵语言描述：$\text{任何实对称矩阵}A\text{,必存在可逆矩阵}C\text{,使得}C^\mathrm{T}AC=\Lambda\text{,其中}$
> $$A=\begin{bmatrix}d_1&&&\\&d_2&&\\&&\ddots&\\&&&d_n\end{bmatrix}\quad或\quad\Lambda=\begin{bmatrix}1&&&\\&-1&&\\&&\ddots&\\&&&0\end{bmatrix}$$

**解释**
+ 概念： 
	+ 并且化成标准型是 $\Lambda$ ，因为对角线对应的就是非交叉项；
	+ 这里的 $C^T$ 不一定可逆，因此其不是由特征向量构成的；
+ 注意：
	+ 这里的 C 不称之为 A 的特征值；
	+ 因为 $C^\mathrm{T}AC$ 中 $C^T$ 不一定是 C 的逆，因此此时就不能相似对角化，此时 C 就是不是由特征向量组成的； 
	+ 如果 $C$ 是正交矩阵，则此时一定可以相似对角化：$C^{-1}=C^T$； 

##### **定理**： #二次型定理2正交变换法  
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{任何二次型}f\left(x\right)=x^{\intercal}Ax\text{也可以通过正交变换 }x=Qy\text{化成标准形,用矩阵语言表述:任何}是对成矩阵A，一定存在正交矩阵Q，使得：$
> $$Q^{-1}AQ=Q^{T}AQ=\Lambda$$
> 其中：$$\Lambda=\begin{bmatrix}\lambda_1\\&\lambda_2\\&&\ddots\\&&&\lambda_n\end{bmatrix}.$$

**解释**
+ 注意： 
	+ Q 不唯一；
	+ $Q$ 和 $A$ 是合同；
+ 概念： 
	+ 并且因为 $Q$ 可逆，所以此时 Q 是 A 的合同、 Q 与 A 相似，此时就是一件事情了；
	+ 这里面的 $\Lambda$ 一定是 $A$ 的特征值； 