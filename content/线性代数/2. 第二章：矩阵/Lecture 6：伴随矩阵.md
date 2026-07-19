 ## 6.1 伴随矩阵的定义 
### 6.1.1 定义
##### **定义**： #伴随矩阵的定义 
> <font color="#ccc1d9">描述：</font>将行列式 $|A|$ 的 $n^2$ 个元素的代数余子式按如下形式排成的矩阵，称为 $A$ 的伴随矩阵, 记作 $A^*$：$$A^*=\begin{bmatrix}A_{11}&A_{21}&\cdots&A_{n1}\\A_{12}&A_{22}&\cdots&A_{n2}\\\vdots&\vdots&&\vdots\\A_{1n}&A_{2n}&\cdots&A_{nn}\end{bmatrix}$$
> 且有：$$AA^{*}=A^{*}A=\left|A\right|E$$ 

**解释**
+ 概念：
	+ 伴随矩阵的产生，就是来自于点积当中的一行乘一列的积的；
	+ 从 $A^*=\left(\begin{matrix}A_{11}&A_{21}\\A_{12}&A_{22}\end{matrix}\right)\rightarrow A=\left(\begin{matrix}a_{11}a_{12}\\a_{21}a_{22}\end{matrix}\right)$  
	+ 所以：$AA^{*}=\left(\begin{matrix}|A|&0\\0&|A|\end{matrix}\right)=\left(\begin{matrix}1&0\\0&1\end{matrix}\right)|A|=E|A|$
+ 计算：二阶
	+ 从 A 矩阵求 $A^*$
		+ 核心：**主对调，副变号**
		+ 举例：$A=\begin{bmatrix}a&b\\c&d\end{bmatrix}\rightarrow A^*=\begin{bmatrix}d&-b\\-c&a\end{bmatrix}$
		+ 结论：二阶时 $(A^*)^*=A$ 
	+ 从 $A^*$ 求 $A^{-1}$
		+ 举例：$\frac{1}{|A|}A^{*}=\frac{1}{ad-bc}(\begin{matrix}a&-b\\-c&a\end{matrix})=A^{-1}$
+ 计算：三阶 
	+ 从 A 矩阵求 $A^*$： 
		+ 老老实实算每项代数余子式；
	+ 从 $A^*$ 求 $A^{-1}$ 
		+ $A^{-1}=\frac{1}{A}A^{*}$

### 6.1.2 伴随矩阵与可逆矩阵 
**总结**：可交换矩阵
+ $$\begin{aligned}&A\cdot kE=kE\cdot A\\&AA^{-1}=A^{-1}A=E\\&AA^{*}=A^{*}A=|A|E\end{aligned}$$

**推论**：$$A^{*}=|A|A^{-1}$$
+ 意义：得到了伴随矩阵与可逆矩阵的关系；

**推论**：$AA^{*}A^{-1}=|A|EA^{-1}\rightarrow A^{*}=|A|A^{-1}$

**结论**：求可逆的一个方法：
+ 方法：
	+ 当 `A` 可逆时，$A^{*}和A^{-1}$ 只差了一个非零的倍数而已； 
+ 意义：
	+ 给了伴随，想到**可逆矩阵** `->` 即在向量的视角下，伴随矩阵和可逆矩阵只是伸缩的关系 `->` 伴随矩阵和可逆矩阵的性质是一致的；


## 6.2 伴随矩阵的性质与公式 
**概念**：运算总结
+ 运算就是四种：行列式、求逆、求转置、求伴随；
+ 下面的性质就是这几种性质的互相使用、结合、交换；

**性质一**：对任意 $n$ 阶方阵 $A$, 都有伴随矩阵 A $^{*}$,且有公式: $$AA^{*}=A^{*}A=\left|A\right|E,\left|A^{*}\right|=\left|A\right|^{n-1}$$

**性质二**：$当|A|\neq0时A^{*}=\left|A\right|A^{-1},A^{-1}=\frac{1}{\left|A\right|}A^{*},A=\left|A\right|\left(A^{*}\right)^{-1};$
+ 前提：A 的测度为 0；
+ 先求行列式，再求伴随矩阵，再求 $\frac{1}{{|A|}}A^*$ 

**性质三**：$(kA)(kA)^{*}=\left|kA\right|E$

**性质四**：$(A^T)^*=(A^*)^T$

**性质五**：$A^{-1}\left(A^{-1}\right)^{*}=\left|A^{-1}\right|E$

**性质六**：$A^*\left(A^*\right)^*=\left|A^*\right|E$
+ 原因：$\left(A^*\right)^*=|A|^{n-2}A$

**性质七**：（穿脱原则）$\left(AB\right)^{*}=B^{*}A^{*}$

**补充**：关于数乘的交换
+ $$\begin{aligned}&|kA|=k^{n}|A|\\&(kA)^{T}=kA^{T}\\&(kA)^{-1}=\frac{1}{k}A^{-1}\\&(kA)^{*}=k^{n-1}A^{*}\end{aligned}$$

**补充**：总结 - 运算的自运算
+ $$\begin{aligned}&|A^{-1}|=|A|^{-1}&&(A^{*})^{-1}=(A^{-1})^{*}\\&(A^{-1})^{T}=(A^{T})^{-1}&&|A^{*}|=|A|^{n-1}\\&|A^{T}|=|A|^{T}\\&(A^{*})^{T}=(A^{T})^{*}\end{aligned}$$

**补充**：总结 - 运算的叠加
+ $$\begin{aligned}&||A||=|A|\\&(A^{T})^{T}=A\\&(A^{-1})^{-1}=A\\&(A^{*})^{*}=|A|^{n-2}A\end{aligned}$$
**补充**：穿脱原则 
+ $$\begin{aligned}&|AB|=|B||A|\\&(AB)^{T}=B^{T}A^{T}\\&(AB)^{-1}=B^{-1}A^{-1}\\&(AB)^{*}=B^{*}A^{*}\end{aligned}$$
+ 注意：$\left(A+B\right)^{*}\neq A^{*}+B^{*}$
+ 其他：$\begin{aligned}&|A+B|\neq|A|+|B|\\&(A+B)^{-1}\neq A^{-1}+B^{-1}\\&(A+B)^{T}=A^{T}+B^{T}\end{aligned}$

## 6.3 用伴随矩阵求可逆矩阵的逆矩阵 
##### **定理**： #伴随矩阵求可逆矩阵的逆矩阵 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$A^{-1}=\frac{1}{\left|A\right|}A^{*}=\frac{1}{\left|A\right|}\begin{bmatrix}A_{11}&A_{21}&\cdots&A_{n1}\\A_{12}&A_{22}&\cdots&A_{n2}\\\vdots&\vdots&&\vdots\\A_{1n}&A_{2n}&\cdots&A_{nn}\end{bmatrix}$$

**解释**
+ 步骤：
	+ 第一步：先求当前矩阵的行列式的值，看起是否等于 `0`，如果等于零就无法继续往下计算了；
	+ 第二步：求 A 的伴随；
	+ 第三步：求 $A^{-1}=\frac{1}{|A|}A^{*}$
+ 注意：
	+ $注意A_{ij}的位置及正、负号$

## 6.4 求伴随矩阵的方法
**方法一**：定义法。先求 $A_{ij}$ ，再拼成 $A^*$

**方法二**：用公式；若 A 可逆，则 $A^*=|A|A^{-1}$ 
+ 遇到和伴随矩阵相关的计算时，先考虑一下有没有公式、化简一下，对公式进行一些运算，然后再开始计算；

