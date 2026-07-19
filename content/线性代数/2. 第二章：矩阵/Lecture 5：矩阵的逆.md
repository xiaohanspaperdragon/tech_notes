## 5.1 逆矩阵的定义
##### **定义**： #逆矩阵 
> <font color="#ccc1d9">描述：</font>`A`、`B` 是 `n` 阶方阵，`E` 是 `n` 阶单位矩阵；若 `AB=BA=E`，则称 `A` 是可逆矩阵，并称 `B` 是 `A` 的逆矩阵，且逆矩阵是唯一的，记为 $A^{-1}$   

**解释**
+ 矩阵和其逆矩阵相乘等于单位阵；

##### **定义**： #逆矩阵的充分必要条件 
> <font color="#ccc1d9">描述：</font>A 可逆的充分必要条件是 $|A|$ 不等于 `0`； 

**解释**
+ 矩阵的测度不等于 `0`，那么就有逆矩阵；
+ 因为 $a^{-1}=\frac{1}{a}$，而分母不能等于零，所以逆矩阵的充分必要条件为测度不为 0；

##### **定义**： #互逆
> <font color="#ccc1d9">描述：</font>一阶： $$A^{-1}A=E$$

**解释**

## 5.2 逆矩阵的性质和重要公式 
**性质**：逆矩阵的性质
+ 1. $(A^{-1})^{-1}=A$
+ 2. 若 k 不等于 0，则 $(kA)^{-1}=\frac{1}{k}A^{-1}$
	+ 转置矩阵时：$(kA)^T=kA^T$
	+ 转置矩阵时：$|kA|=k^n|A|$ 
+ 3. `AB` 也可逆，且 $(AB)^{-1}=B^{-1}A^{-1}$
+ 4. $A^{\mathrm{T}}\text{也可逆,且}(A^{\mathrm{T}})^{-1}=(A^{-1})^{\mathrm{T}}$ 
+ 5. $\left|A^{-1}\right|=|A|^{-1}$
	+ 因为：$|A^{-1}A|=|E|\rightarrow|E|=|A^{-1}||A|$ 即：$|A^{-1}|$ 和 $|A|$ 互为倒数；

**注意**：$A+B\text{不一定可逆,且}\left(A+B\right)^{-1}\neq A^{-1}+B^{-1}$
+ $\left(A+B\right)^{T}=A^{T}+B^{T}$
+ $\vert A+B\vert$ 不等于 $\vert A\vert+\vert B\vert$  

**补充**：逆矩阵与分块矩阵结论
+ $$\left.\left(\begin{matrix}a&0\\0&b\end{matrix}\right.\right)^{-1}=\left(\begin{matrix}a&-1&0\\0&b^{-1}\end{matrix}\right)\left(\begin{matrix}A&0\\0&B\end{matrix}\right)^{-1}=\left(\begin{matrix}A&-1&0\\0&B^{-1}\end{matrix}\right)\\\left(\begin{matrix}0&a\\b&0\end{matrix}\right)^{-1}=\left(\begin{matrix}0&b^{-1}\\a^{-1}&0\end{matrix}\right)\left(\begin{matrix}0&A\\B&0\end{matrix}\right)^{-1}=\left(\begin{matrix}0&B^{-1}\\A^{-1}&0\end{matrix}\right)$$

## 5.3 用定义法求可逆矩阵的逆矩阵 
### 5.3.1 方法一：定义法
**方法**：定义进行求解，即求一个矩阵 `B`，使 `AB=E`，则 `A` 可逆，且 $A^{-1}=B$

### 5.3.2 方法二：乘积法
**方法**：将 `A` 分解成若干个可逆矩阵的乘积. 因两个可逆矩阵的积仍是可逆矩阵，即若 `A=BC`，其中，`B、C` 均可逆，则 `A` 可逆，且：
+ $$A^{-1}=(BC)^{-1}=C^{-1}B^{-1}$$
