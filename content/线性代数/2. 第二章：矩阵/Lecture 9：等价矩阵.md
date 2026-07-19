## 9.1 等价矩阵和矩阵的等价标准型
##### **定义**： #等价矩阵
> <font color="#ccc1d9">描述：</font> $$\begin{aligned}&\text{设}A,B\text{ 均是}m\times n\text{矩阵,若存在可逆矩阵}P_{mon},Q_{mon},\text{ 使得 }PAQ=B\text{,则称 }A,B\text{ 是等价矩阵,记作}\\&A\cong B.\end{aligned}$$

**解释**

##### **定义**： #矩阵的等价标准型
> <font color="#ccc1d9">描述：</font> 
> 1.  $A\text{ 是一个 }m\times n\text{ 矩阵,则}A\text{ 等价于形如}\begin{bmatrix}E_r&0\\0&0\end{bmatrix}\text{的矩阵}(E_r\text{ 中的 }r\text{ 恰是}r(A))\text{,后者称为}A\text{ 的等价标准型}$
> 2. $\text{等价标准形是唯一的,即若 }r(A)=r\text{,则存在可逆矩阵}P,Q\text{,使得:}PAQ=\begin{bmatrix}E_r&0\\0&0\end{bmatrix}$

**解释**
+ 意义：
	+ 虽然一个 `m*n` 型的矩阵不能变成标准的单位阵，但是可以通过行变换和列变换、将其变成一个分块的、某个块的单位阵，其他阵则是 `0`；
	+ 最简单的形式：$PAQ=\begin{bmatrix}E_r&0\\0&0\end{bmatrix}$
+ 解释： 
	+ 其中的 `r` 是 `A` 矩阵的秩 `->` 吧 $E_r$ 扩展到了不同阶时的情况 `->` $PAQ=\begin{bmatrix}E_r&0\\0&0\end{bmatrix}$ 是等价标准型；
	+ `P`：若干次初等行变换；
	+ `Q`：若干次初等列变换；
	+ `PAQ=B`：化成最简型之前的任意一个过程的状态，最终都会走向 $PAQ=\begin{bmatrix}E_r&0\\0&0\end{bmatrix}$；
+ 概念：什么是 `AB` 等价
	+ 这两个矩阵、最终的归宿是一样的，它们最终都能化成最终的一样的最简标准型 `<->` 等价标准型一样；
