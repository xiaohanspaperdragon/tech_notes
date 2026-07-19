## 18.1 基本概念 
##### **定义**： #同解方程组 
> <font color="#ccc1d9">描述：</font>方程组 $A_{m*n}x=0$ 和 $B_{s*n}x=0$ 有完全相同的解，则称它们为同解方程组；
> 于是：`Ax=0,Bx=0` 是同解方程组；

**解释**
+ 意义：
	+ 证明 `r(A)<r(B)` `->` 用向量组；
	+ 证明 `r(A)=r(B)` `->` 用方程组来证明 `->` 同解；
+ 概念： 
	+ 解代入： 
		+ `Ax=0` 的解满足 `Bx=0`，且 `Bx=0` 的解满足 `Ax=0` (互相把解代入求出结果即可)
	+ 判别法： 
		+ `r(A)=r(B)`，且 `Ax=0` 的解满足 `Bx=0` (或 `Bx=0` 的解满足 `Ax=0`)
	+ 三秩相同： 
		+ $r\left(A\right)=r\left(B\right)=r\left(\left[\begin{matrix}A\\\\B\end{matrix}\right]\right)$
+ 解释： 
	+ `Ax=0` 与 `Bx=0` 同解 
	+ `<->` 两个解的向量组等价：$\xi_1,\xi_2,\cdots,\xi_s=\eta_{1},\eta_{2}\cdots\eta_{s}$ 
	+ `<->` $r(\xi_1,\xi_2,\cdots,\xi_s)=r(\eta_{1},\eta_{2}\cdots\eta_{s})$ 且第一个向量组可以被第二个向量组线性表示；
	+ `<->` `r(A)=r(B)=r(A|B)` 
	+ `<->` `r(A)=r(B)` 且 `Ax=0` 的解为 `Bx=0` 的解；
	+ `<->` $r\left(A\right)=r\left(B\right)=r\left(\left[\begin{matrix}A\\\\B\end{matrix}\right]\right)$
+ 结论： 
	+ $r(AA^{T})=r(A^{T})=r(A)=r(A^{T}A)$