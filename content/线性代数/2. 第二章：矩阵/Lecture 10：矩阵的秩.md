## 10.1 秩的定义 
##### **定义**： #矩阵的秩 
> <font color="#ccc1d9">描述：</font>设 A 是 $m*n$ 的矩阵，若存在 k 阶子式不为零，且任意 `k+1` 阶子式（如果有的话）全为零，则 `r(A)=k`，且若 A 为 `n*n` 矩阵，则得到：$$r\left(A_{n\times n}\right)=n\Leftrightarrow\left|A\right|\neq0\Leftrightarrow A\text{可逆}$$

**解释**
+ 子式： 
	+ 子式一定是行列式；
+ `k` 阶子式： 
	+ 当矩阵为 $\left(\begin{matrix}1&2&3\\4&5&6\end{matrix}\right)$ 时，其 `k=2` 的二阶子式为 $\left|\begin{matrix}1&3\\4&6\end{matrix}\right|$
	+ 其一共有三个二阶子式；
+ 意义：若存在 k 阶子式不为零，且任意 `k+1` 阶子式（如果有的话）全为零
	+ 假设当前为 `k=2` 二阶情况下，此时其二阶子式因为表示行列式 `->` 面积；
	+ 当其不为零时，向量之间互相都不能表示 `->` k 个线性无关向量；
+ 意义：`r(A)=k`
	+ 存在 `k` 个无关向量；
	+ 任意 `k+1` 个向量都相关；
	+ 此时 `r(A)=k` 就是组成矩阵线性无关的向量的个数；

**补充**：秩的几何含义
+ 意义： 
	+ 秩，代表经过 `A` 矩阵的变换后，变换后的空间的维数；
	+ 变换后的基向量张成的空间，就是所有可能的变换结果 `->` 即：变换后的基向量，其所张成的空间的维数；
+ 举例： 
	+ 当出现 `3*2` 的矩阵 $A_{3*2}$ 时，其表示将一个二维的图形映射到三维的空间中；因为 A 有两个基向量，并且这两个基向量现在是三维的 `[x,y,z]`；
	+ 当出现 `2*3` 的矩阵 $A_{3*2}$ 时，其表示将一个三维的图形映射到二维的空间中；因为 A 有三个基向量，并且这三个基向量现在是二维的 `[x,y]` 基向量；

## 10.2 求矩阵的秩
**方法**：求矩阵的秩
+ 将 `A` 用初等行变换化为行阶梯形矩阵，其非零行数便为 `A` 的秩；

**方法**：求矩阵的秩 - 举例
+ 题目：若 $\begin{bmatrix}1&2&-1&1\\2&0&t&0\\0&-4&5&-2\end{bmatrix}$ 的秩为 2，则求 `t`
+ 分析： 
	+ $A\rightarrow\left(\begin{matrix}1&2&-1&1\\0&-4&t+2&-2\\0&-4&5&-2\end{matrix}\right)\rightarrow\left(\begin{matrix}1&2&-1\\0&-4&t+2&-2\\0&0&3-t&0\end{matrix}\right)$
	+ 此时已经是一个行阶梯形矩阵了；
	+ 并且因为矩阵秩是 2，所以下面的都是 0 行，所以 `3-t=0`
	+ 所以 `t=3`

## 10.3 有关秩的几个重要式子
**概念**：设 A 是 `m*n` 矩阵，`B` 是满足有关矩阵运算要求的矩阵，则：
+ （1）${1}0\leqslant r(A)\leqslant\min\{m,n\}($ 由定义 )
	+ 任何一个矩阵的秩最低为 0，并且 `r(a)=0` 则矩阵一定等于 `0`：`A=0`
	+ 并且 $r(A)\leqslant\min\{m,n\}$ `<-` 因为行列式是方的，而矩阵的子式是行列式，所以必须为 `n*n` 
+ （2）${2}r(kA)=r(A)(k\neq0)($ 由定义 )
+ （3）$r\left(AB\right)\leqslant\min\left\{r\left(A\right),r\left(B\right)\right\}$
	+ 矩阵越乘，秩序=越多越的‘‘’’
+ （4）$r(A+B)<=r(A)+r(B)$
+ （5）$r\left(A^{*}\right)=\begin{cases}n,&r\left(A\right)=n,\\1,&r\left(A\right)=n-1,\\0,&r\left(A\right)<n-1,\end{cases}$
+ （6）设 A= `m*n` 的矩阵，`P、Q` 分别为 m 阶、n 阶的可逆矩阵，则：`r(A)=r(PA)=r(AQ)=r(PAQ)`
	+ 在过程当中，所有中间矩阵都是等价的：$r\left(\begin{matrix}E_{r}&0\\0&0\end{matrix}\right)$
+ （7）若 $A_{m\times n}B_{m\times s}=O,则r\left(A\right)+r\left(B\right)\leqslant n$；
	+ `n` 为 `A` 的列数；
+ （8）格拉姆矩阵：$r\left(A\right)=r\left(A^{T}\right)=r\left(A^{T}A\right)=r\left(AA^{T}\right)$
	+ $r\left(A^{T}A\right)=r\left(AA^{T}\right)$ 一定有解，并且一定是最佳近似解；
	+ 对于任何一个矩阵，其转置的秩等于其 $r\left(A^{T}A\right)=r\left(AA^{T}\right)$；

