**分类**：按照考题的角度
+ 1. 有规律的行列式：
	+ `n` 阶，`n` 可能很大，因为有规律、所以可以解决，都可以使用公式解决；
+ 2. 无规律的行列式：
	+ 都是以三阶为主，偶尔有四阶；
	+ 使用性质、将其化成 `12+1` 种类型；

## 3.1 具体性行列式的计算 
**方法**：三种方法
+ 几何：几乎不行
+ 性质：性质 1-7
+ 逆序数法：一般是用于研究某一项用的
+ 展开公式：
	+ 准备工作：
		+ `->` 使用性质、将行列式尽可能多的展开多的 0；
		+ `->` 使用性质、使得行列式能够**化成基本型**，此时就可以直接写答案了 
			+ 找基本型的思路：1. 找差别不大的行来换 2. 找规律；
	+ 展开
+ 归纳法/递推法；

### 3.1.1 化为基本型 
#### 3.1.1.1 爪形与行和相等
**思路**：把行列式化成基本型
+ 方法：
	+ 如果符合形式，则直接使用方法（比如爪形行列式的形式）
	+ 如果不符合形式，则找差别不大的行来换；

**概念**：爪形行列式 
+ 化型 `->` 类似于三角行列式；
+ 思路：用斜的爪子，去消掉平的爪子；
+ 解释：
	+ 适用性质七：倍加的性质，将主或者副对角线上的元素，通过倍加的方式，消掉竖（横）的爪子上的数，进而化成三角行列式；

##### **定义**： #行和相等的行列式
> <font color="#ccc1d9">描述：</font> $$D_n=\begin{vmatrix}a&b&b&\cdots&b\\b&a&b&\cdots&b\\b&b&a&\cdots&b\\\vdots&\vdots&\vdots&&\vdots\\b&b&b&\cdots&a\end{vmatrix}\quad\quad\quad\quad D_{n}=(a+(n-1)b)\begin{vmatrix}1&b&b\cdots b\\1&a&b\cdots b\\\vdots&\vdots&\vdots\\1&b&b\cdots a\end{vmatrix}=[a+(n-b)b](a-b)^{n-1}$$

**解释**
+ 证明过程：
	+ 第一步：因为行和相等，所以把所有列都加到第一列；
	+ 第二步：提出公因式部分 `[a+(n-1)b]`
	+ 第三步：将每列加 `-1` 倍至每列；
	+ 第四步：计算结果，得到 $D_n=[a+(n-1)b](a-b)^{n-1}$

**补充一**
+ 行列式：
	+ $$当a=0,b=1时,\begin{vmatrix}0&1&1&\cdots&1\\1&0&1&\cdots&1\\1&1&0&\cdots&1\\\vdots&\vdots&\vdots&&\vdots\\1&1&1&\cdots&0\end{vmatrix}_{n\times n}=(n-1)(-1)^{n-1}$$
+ 解释：
	+ 主对角线都是 0，其他都是 1 `<-` 把 `行和相等的行列式` 中的 `a` 取为 0，`b` 取为 1 ，代入 $[a+(n-b)b](a-b)^{n-1}$ 即可算出；

**补充二**
+ 行列式： 
	+ $$当a=2,b=1时,\begin{vmatrix}2&1&1&\cdots&1\\1&2&1&\cdots&1\\1&1&2&\cdots&1\\\vdots&\vdots&\vdots&&\vdots\\1&1&1&\cdots&2\end{vmatrix}=n+1.$$

**补充三**：当 a 在副对角线时
+ 行列式： 
	+ $$G_n=\begin{vmatrix}b&b&\cdots&b&a\\b&b&\cdots&a&b\\\vdots&\vdots&&\vdots&\vdots\\b&a&\cdots&b&b\\a&b&\cdots&b&b\end{vmatrix}=(-1)^{\frac{n(n-1)}2}\begin{vmatrix}a&b&\cdots&b&b\\b&a&\cdots&b&b\\\vdots&\vdots&&\vdots&\vdots\\b&b&\cdots&a&b\\b&b&\cdots&b&a\end{vmatrix}=\left(-1\right)^{\frac{n\left(n-1\right)}{2}}\left[a+\left(n-1\right)b\right]\left(a-b\right)^{n-1}$$

#### 3.1.1.2 X 型
**举例**
+ 行列式： 
	+ $$D_4=\begin{vmatrix}a_1&0&0&b_1\\0&a_2&b_2&0\\0&b_3&a_3&0\\b_4&0&0&a_4\end{vmatrix}=(a_{1}a_{4}-b_{1}b_{4})(a_{2}a_{3}-b_{2}b_{3}).$$
+ 分析：
	+ 先换行、列，将所有的 `0` 凑在一起，然后使用拉普拉斯展开式

#### 3.1.1.3 范德蒙德型
**举例**
+ $$\begin{vmatrix}a&b&c\\a^{2}&b^{2}&c^{2}\\b+c&a+c&a+b\end{vmatrix}=\left(a+b+c\right)\left|\begin{matrix}1&1&1\\a&b&c\\a^{2}&b^{2}&c^{2}\end{matrix}\right|=\left(a+b+c\right)\left(c-a\right)\left(c-b\right)\left(b-a\right)$$
+ 使用性质，将其化成范德蒙德型

### 3.1.2 递推法 
**概念**：递推法和归纳法
+ 关系：
	+ 递推法和归纳法是两种不同的方向；
	+ 递推法是从 n 阶开始往下推，推到 `n-1`、`n-2`
	+ 归纳法是从 `1` 阶开始找到规律、往上推，推到 `n-1`、`n`
+ 基本思路：
	+ 1. 元素的分布规律相同；
	+ 2. $D_{n-1}$ 比 $D_n$ 少一阶； 

**举例**：宽对角行列式
+ 行列式：递推
	+ $$D_4=\begin{vmatrix}1-a&a&0&0\\-1&1-a&a&0\\0&-1&1-a&a\\0&0&-1&1-a\end{vmatrix}=(-1)^{4+1}\cdot(-a)\cdot a^{3}+D_{3}=a^{4}+\left(-a^{3}\right)+D_{2}=a^{4}+(-a^{3})+a^{2}+D_{1}=a^{4}-a^{3}+a^{2}-a+1$$
+ 分析：
	+ 其中上述 $D_4$ 是计算余子式；
	+ 上面也可以使用归纳法

### 3.1.3 行列式表示的函数和方程
**补充**：这类问题的行列式元素 $a_{ij}$ 往往不是具体数值，而是含 $x$ 或 $\lambda$ 等的函数，可能会在计算之外给考生带来新的困难和麻烦，自然也会给命题人带来新的角度，需要重视对此类问题的研究；

**举例**
+ 题目：$设f\left(x\right)=\begin{vmatrix}1&0&x\\1&2&x^{2}\\1&3&x^{3}\end{vmatrix},求f\left(x+1\right)-f\left(x\right)$ 
+ 分析：$f(x+1)-f(x)=\left|\begin{matrix}1&0&x+1\\1&2&(x+1)^{2}\\1&3&(x+1)^{3}\end{matrix}\right|-\left|\begin{matrix}1&0&x\\1&2&x^{4}\\1&3&x^{3}\end{matrix}\right|=\left.\left|\begin{matrix}1&0&1\\1&2&2x+1\\1&3&3x^{2}+3x+1\end{matrix}\right.\right|=\left|\begin{matrix}1&0&0\\1&2&0\\1&3&3x^{2}\end{matrix}\right|=6x^2$

**举例**
+ 题目：$设方程\begin{vmatrix}\lambda-1&-2&3\\1&\lambda-4&3\\-1&a&\lambda-5\end{vmatrix}=0有二重根，求参数a的值$
+ 分析：这是一个关于 $f(\lambda)$ 的表达式，且因为主对角线上有 $\lambda$，所以肯定有一个关于 $\lambda$ 的三次方
+ 解析：
	+ 求行列式： $f\left(\lambda\right)=\left|\begin{matrix}\lambda-2&-\lambda+2&0\\1&\lambda-4&3\\-1&a&\lambda-5\end{matrix}\right|=\begin{vmatrix}\lambda-2&0&0\\1&\lambda-3&3\\-1&a-1&\lambda-5\end{vmatrix}=\left(\lambda-2\right)\left|\begin{matrix}\lambda-3&3\\a-1&\lambda-5\end{matrix}\right|=(\lambda-2)(\lambda^{2}-8\lambda+18-3a)=0$
	+ 讨论二重根：在 $(\lambda-2)(\lambda^{2}-8\lambda+18-3a)=0$ 种
		+ 1. 如果 $\lambda =2$ 是二重根：$(\lambda^{2}-8\lambda+18-3a)|_{\lambda=2}=0$ `->` $4-16+18-39=0$，所以 `a=2`
		+ 2. 如果 $\lambda =2$ 不是二重根：讨论 $\Delta=0$ ，求出 $a=\frac{2}{3}$ 所以 $\lambda =4$

## 3.2 抽象型行列式的计算 
**核心**：方法 
+ 1. 用性质；
+ 2. 用公式 $|AB|=|A||B|$ 
	+ 先用 `B` 对 `C` 做一个变换，然后再用 `A` 对 `BC` 做一个变换：`ABC`
	+ 其结果等于分别的两个测度变化的结果

### 3.2.1 抽象型：一般方法 - 利用性质凑
**例题**：$\text{已知4阶行列式}|\alpha_{1},\alpha_{2},\alpha_{3},\beta|=a,|\beta+\gamma,\alpha_{2},\alpha_{3},\alpha_{1}|=b,则|\alpha_{2}+\alpha_{3},\alpha_{1},\alpha_{3},\gamma|=$ 
+ 分析：什么是抽象型：其中的元素是抽象的符号，不知道其具体的值；
+ 解析：如何求
	+ 从抽象的行求抽象的行；
	+ 利用行列式计算的性质，凑出来目标；

### 3.2.2 抽象性：点积法
**核心**：凑出来两个方的矩阵相乘，行列式就等于 $|AB|=|A||B|$ 

**例题**：$设\alpha_1,\alpha_2,\alpha_3均为3维列向量,已知$：$A=[\alpha_{1},\alpha_{2},\alpha_{3}],B=[\alpha_{1}-\alpha_{2}+2\alpha_{3},2\alpha_{1}+3\alpha_{2}-5\alpha_{3},\alpha_{1}+2\alpha_{2}-\alpha_{3}],\text{且}|A|=2,\text{则}|B-A|=$
+ 知识点
	+ 虽然其中的 $\alpha_1$ 是一个三维向量，但是只要是用一个符号 $\alpha_1$ 来表示它，此时它就作为一个整体而存在 `->` 本质上它是一个分块阵，只要一个矩阵分成一个分块阵，此时这个分块阵就把其当成元素来看待；
	+ 结论：分块阵当作元素进行计算；
+ 解析
	+ $B-A=(-\alpha_{2}+2\alpha_{3},2\alpha_{1}+2\alpha_{2}-5\alpha_{3},\alpha_{1}+2\alpha_{2}-2\alpha_{3})$
		+ $(\alpha_{1},\alpha_{2},\alpha_{3})\left(\begin{matrix}0&2&1\\-1&2&2\\2&5&-2\end{matrix}\right) \leftarrow (\alpha_{1},\alpha_{2},\alpha_{3})\left(\begin{matrix}0\\-1\\2\end{matrix}\right)\left(\begin{matrix}2\\2\\-5\end{matrix}\right)\left(\begin{matrix}1\\2\\-2\end{matrix}\right)$ 
	+ 其中的 $(\alpha_{1},\alpha_{2},\alpha_{3})$ 为基准，因此计算其基于基准的表示：
		+ $0\alpha_{1}-\alpha_{2}+2\alpha_{3}=[\alpha_{1},\alpha_{2},\alpha_{3}]\begin{bmatrix}0\\-1\\2\end{bmatrix},2\alpha_{1}+2\alpha_{2}-5\alpha_{3}=[\alpha_{1},\alpha_{2},\alpha_{3}]\begin{bmatrix}2\\2\\-5\end{bmatrix},a_{1}+2a_{2}-2a_{3}=\left[a_{1},a_{2},a_{3}\right]\left[\begin{matrix}1\\2\\-2\end{matrix}\right]$
	+ 得到： $B-A=(-\alpha_{2}+2\alpha_{3},2\alpha_{1}+2\alpha_{2}-5\alpha_{3},\alpha_{1}+2\alpha_{2}-2\alpha_{3})$ d 的计算结果就是：$(\alpha_{1},\alpha_{2},\alpha_{3})\left(\begin{matrix}0&2&1\\-1&2&2\\2&5&-2\end{matrix}\right)$ 
		+ 所以 $|B-A|=|A|\left|\begin{matrix}0&2&1\\-1&2&2\\2&5&-2\end{matrix}\right|$
	+ 计算结果： $|B-A|=|A|\left|\begin{matrix}0&2&1\\-1&2&2\\2&5&-2\end{matrix}\right|=2*5=10$

### 3.2.3 余子式和代数余子式的线性组合计算
##### **定理**： #余子式和代数余子式的线性组合计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 由 $a_{i1}A_{i1}+a_{i2}A_{i2}+\cdots+a_{in}A_{in}=\begin{vmatrix}*\\a_{i1}&a_{i2}&\cdots&a_{in}\\*&\end{vmatrix}$
> 则 $k_{1}A_{i1}+k_{2}A_{i2}+\cdots+k_{n}A_{in}=\begin{vmatrix}&&*&&\\k_{1}&&k_{2}&\cdots&k_{n}\\&&*&&\end{vmatrix}$

**解释**
+ 解释： 
	+ 展开式法：  
		+ 本质上是一种降阶的运算；
		+ 任何一个行列式的计算，可以为其某一行（列）的展开：$|a_{i_{1}}\cdots a_{i_{n}}|=a_{i_{1}}A_{i_{1}}+\cdots+a_{i_{n}}A_{i_{n}}$
	+ 代数余子式的线性组合：
		+ 本质上就是展开式法的逆过程；
		+ 举例：$A_{{11}}-2A_{{12}}+A_{{13}}=M_{11}+2M_{12}+M_{13}$
			+ 因为 $M_{ij}=(-1)^{i+j}A_{j}$
+ 方法：
	+ 核心：
		+ 大 `A` 配小 `a`，逆用展开式； 
		+ 大 `A` 配小 `k`，`k` 把小 `a` 吃；
	+ 举例：已知 $|A|=\begin{vmatrix}1&-2&1\\1&0&0\\0&1&0\end{vmatrix}$，则求 $A_{11}-2A_{12}+A_{13}$ 
		+ 由 `A` 知道：按第一行展开：$|A|=1\cdot A_{11}+(-2)A_{12}+1A_{13}=1$

## 3.3 克拉默法则 
##### **定理**： #克拉默法则 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>对个方程 `n` 个未知数 (这是前提)的非齐次线性方程组：$$\begin{cases}a_{11}x_{1}+a_{12}x_{2}+\cdots+a_{1n}x_{n}=b_{1},\\a_{21}x_{1}+a_{22}x_{2}+\cdots+a_{2n}x_{n}=b_{2},\\\cdots\cdots\\a_{n1}x_{1}+a_{n2}x_{2}+\cdots+a_{nn}x_{n}=b_{n},\end{cases}$$
> 若系数行列式 $$D=\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn}\end{vmatrix}\neq0$$ 则方程组右唯一解，且解为：$x_{i}=\frac{D_{i}}{D},i=1,2,\cdots,n$，其中 $D_i\text{是由常数项}b_1,b_2,\cdots,b_n\text{替换}D\text{ 中第 }i\text{列元素得到的行列式}$
> 

**解释**
+ 要求：
	+ 必须得是方形的矩阵，而且对系数有要求，所以难用；
+ 举例：
	+ $\begin{cases}x_{1}-2x_{2}+x_{3}=1\\x_{1}+0x_{2}+0x_{3}=2\\0x_{1}+x_{2}+0x_{3}=5\end{cases}$
	+ 若行列式：$|A|=|\begin{smallmatrix}1&-2&1\\0&0&0\\1&0\end{smallmatrix}|\neq0$ 不等于 `0`，则其解为 $x_{i}=\frac{D_{i}}{D},i=1,2,\cdots,n$  
	+ 则 $x_{1}=\frac{D_{1}}{D}=\frac{\left|\begin{matrix}1&-2&1\\2&0&0\\5&1&0\end{matrix}\right|}{1}$ （第一列换成自由项，第二列第三列不变）
	+ 算 $x_2$ 也类似，把第二列换成自由项；同理第三列；
	+ 所以 $x_1x_2x_3$ 分别为 2、5、9
+ 作用：
	+ 克拉默法则提供了一个流程化的解法；

##### **定理**： #齐次时克拉默法则
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>齐次时：$$\begin{cases}a_{11}x_{1}+a_{12}x_{2}+\cdots+a_{1n}x_{n}=0,\\a_{21}x_{1}+a_{22}x_{2}+\cdots+a_{2n}x_{n}=0,\\\cdots\cdots\\a_{n1}x_{1}+a_{n2}x_{2}+\cdots+a_{nn}x_{n}=0,\end{cases}$$
> $若D\neq0,则齐次方程组只有零解;若D=0,则齐次方程组有非零解$ 

**解释**
