## 1.1 大纲介绍
**引言**
+ 基础内容：
	+ 行列式
	+ 矩阵
+ 主题：
	+ 向量组
	+ 方程组
+ 应用：
	+ 特征值；
		+ 至少五分；
	+ 二次型；
		+ 有了特征值就可以分析二次型；
		+ 为了研究空间里面的图形，需要使用二次型的技术 `->` 图形里面的最大值和最小值 `->` 最值的问题；

## 1.2 课程介绍
### 1.2.1 方向、工具与手段
**概念**：研究方向与工具
+ 研究方向：
	+ 研究的内容是**向量**：`Vector`
	+ 向量的个数，就是其维度；
	+ 行列式：
		+ $$\begin{vmatrix}\mathrm{m}&&\mathrm{n}\\\mathrm{a}&&\mathrm{b}\end{vmatrix}=\mathrm{mb}-\mathrm{an}$$
+ 研究工具：
	+ 1. 线性运算 `->` 数乘和加法；
	+ 2. 点积运算 `->` 在线性代数里面，点积运算本质上还是一个线性运算；
		+ $(a_{1}a_{2})(\begin{matrix}b_{1}\\b_{2}\end{matrix})=a_1b_1+a_2b_2$
		+ $(a_1a_2)\begin{pmatrix} b_1 & c_1 \\ b_2 & c_2 \end{pmatrix}=(a_{1}b_{1}+a_{2}b_{2},a_{1}c_{1}+a_{2}c_{2})$
		+ $\begin{pmatrix} a_1 & a_2 \\ b_1 & b_2 \end{pmatrix}(c_1c_2)=\begin{pmatrix} a_1c_1+a_2c_2  \\ b_1c_1+b_2c_2 \end{pmatrix}$

**概念**：研究手段
+ 概念：
	+ 核心 `->` 线性变换；
	+ 矩阵 `->` 表达系统信息
		+ 矩阵中的数据不能随便乱动，不然系统信息就被破坏了；
+ 线性变换：
	+ 分析：
		+ $(\begin{matrix}1&0\\0&-1\end{matrix})(\begin{matrix}1\\1\end{matrix})=(\begin{matrix}1\\-1\end{matrix})$
		+ 其中 $(\begin{matrix}1&0\\0&-1\end{matrix})$ 是矩阵，对应了高等数学里面的函数 `f`
		+ 其中 $(\begin{matrix}1\\1\end{matrix})$ 代表变量，对应高等数学里面的 `x`；
		+ 其中 $(\begin{matrix}1\\-1\end{matrix})$ 对应结，对应高等数学里面的 `y`；
		+ 其中输入的内容是一个向量；
	+ 举例： 
		+ 举例：对称变换
			+ 矩阵：$(\begin{matrix}1&0\\0&-1\end{matrix})$
		+ 举例：伸缩变换
			+ 矩阵：向右伸缩 $(\begin{matrix}2&0\\0&1\end{matrix})$
			+ 矩阵：向上伸缩 $(\begin{matrix}1&0\\0&2\end{matrix})$
		+ 举例：剪切变换
			+ 矩阵：$(\begin{matrix}1&-1\\0&1\end{matrix})$
			+ 矩阵：$(\begin{matrix}-1&1\\0&1\end{matrix})$

### 1.2.2 分析：方程组与线性变换
**分析**：方程组与线性变换
+ 举例：$\begin{cases}x_{1}+2x_{2}=3\\4x_{1}+7x_{2}=10\end{cases}$ 
+ 传统方法：消元法
+ 线性变换：
	+ 因为 $x_{1}+2x_{2}$ 以及 $4x_{1}+7x_{2}=10$ `->` 这是点积的结果；
	+ 所以可以把其变成线性变换的形式：$\left.\left(\begin{matrix}1&2\\4&7\end{matrix}\right.\right)\left(\begin{matrix}x_{1}\\x_{2}\end{matrix}\right)=\left(\begin{matrix}3\\10\end{matrix}\right)$
	+ 所以就是基于此线性变换，求其中的 $x_1x_2$
	+ 求解法：对等式两边乘以矩阵的逆矩阵，假设 $A=(\begin{matrix}1&2\\4&7\end{matrix})$ ，则同时在两边乘以 $A^{-1}$
	+ 所以得到 $Ax=B$ `->` $AA^{-1}x=BA^{-1}$ `->` $x=BA^{-1}$ 
	+ 即可以得到 `x` 的求解；

## 1.3 补充：点积 
**概念**：什么是点积
+ 线性变换角度： 
	+ 公式： 
		+ $$\overbrace{\begin{bmatrix}1&-2\end{bmatrix}}^{\text{Transform}}\underbrace{\begin{bmatrix}4\\3\end{bmatrix}}_{\begin{array}{c}\text{Vector}\\\text{}\end{array}}=4\cdot1+3\cdot-2$$
	+ 图示： 
		+ ![[Pasted image 20240629190435.png]]