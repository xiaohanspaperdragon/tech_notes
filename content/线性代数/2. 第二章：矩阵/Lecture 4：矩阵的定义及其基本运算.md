## 4.1 矩阵的本质
### 4.1.1 矩阵概念
**引入**：矩阵的作用 `->` 表达系统信息；
+ 核心：任何一个矩阵，最后都可以用基向量来表示，矩阵中的信息都是可以用基向量表达出来的；

**概念**：什么是矩阵
+ 概念： 
	+ 列：
		+ 代表变换的基向量的个数；
	+ 行： 
		+ 代表变换后空间的维数；
+ 意义： 
	+ 从线性变换的角度，假设现在有一个三维方阵矩阵 $A_{3*3}$，此时 A 矩阵的三个列就代表了：在进行线性变换 `Ax=b` 当中，对三个基向量的变换；
+ 举例：如果当前是 `3*2` 的矩阵，即当前矩阵有三行、两列；
	+ 两列：也就是有两个基向量，也就是一个二维的平面；
	+ 三行：代表这两个基向量有 `[x,y,z]` 这三个维度；
	+ 乘以三行两列，也就代表：
		+ 将两个基向量映射到三维的空间中，因此变换构成了三维空间中的二维平面；
		+ 当出现 `3*2` 的矩阵 $A_{3*2}$ 时，其表示将一个二维的图形映射到三维的空间中；因为 A 有两个基向量，并且这两个基向量现在是三维的 `[x,y,z]`；
+ 举例： 如果当前是 `2*3` 的矩阵，即当前矩阵有两行、三列
	+ 当出现 `2*3` 的矩阵 $A_{3*2}$ 时，其表示将一个三维的图形映射到二维的空间中；因为 A 有三个基向量，并且这三个基向量现在是二维的 `[x,y]` 基向量；

**概念**：矩阵和行列式分别的乘积
+ 矩阵：表示系统信息的乘积，作用在每一个系统信息上
	+ $$\left.k\cdot A=\left(\begin{matrix}ka_{11}&ka_{12}\\ka_{21}&ka_{22}\end{matrix}\right.\right)$$
+ 行列式：表示对一个测度（比如一个平行四边形的某个维度）进行乘积
	+ $$k|A|=\left|\begin{matrix}ka_{11}&ka_{12}\\a_{21}&a_{22}\end{matrix}\right|$$
+ 公式：
	+ $$|kA|=k^{n}\cdot|A|$$

**概念**：矩阵信息表达中、数据和数据之间的关系
+ 引入：
	+ 矩阵不一定是方形的，可能是 `1000*2` 或者 `2*1000`；
+ `Gram` 矩阵
	+ 对于 $A=(\begin{matrix}a\\b\end{matrix})$ ，$A^T=(a\quad b)$ $A^{T}A=(ab)(\begin{matrix}a\\b\end{matrix})=\alpha^{T}\cdot\alpha=||\alpha||^{2}=||\alpha||^{2}*\cos 0$
+ 作用：
	+ 如果只是给了你一个 $A=(\alpha_1\quad \alpha_2)$ 的矩阵，其实并不知道其中 $\alpha_1\quad \alpha_2$ 之间的关系；但是可以通过将 $A$ 乘以其转置矩阵的方式，得到其中更多的信息：
	+ $$A^{T}A=\left(\begin{matrix}\alpha_{1}^{T}\\\alpha_{2}^{T}\end{matrix}\right)\left(\alpha_{1}\alpha_{2}\right)=\left.k\cdot A=\left(\begin{matrix}||\alpha_1||||\alpha_1||*\cos \theta_{11}&||\alpha_1||||\alpha_2||*\cos \theta_{12}\\||\alpha_2||||\alpha_1||*\cos \theta_{21}&||\alpha_2||||\alpha_2||*\cos \theta_{22}\end{matrix}\right.\right)$$
	+ 在这里面可以得到数据之间的相似度；
+ 概念：
	+ 矩阵不能运算，但是其若干**行 (列) 向量之间**可能存在着某种关系

**重要观点 1**：矩阵也是由若干行 (列) 向量拼成的 
+ 上面那个矩阵可以看作由三个行向量：$[1,2,3],[4,6,9],[2,4,6]$ 组成，也可以看作是三个列向量组成：$[1,6,2]^{\mathrm{T}},[2,7,4]^{\mathrm{T}}与[3,9,6]^{\mathrm{T}}$

##### **定义**： #矩阵的秩
> <font color="#ccc1d9">描述：</font>设 $A$ 是 $m*n$ 矩阵，$A$ 中**最高阶非零子式的阶数**称为**矩阵的秩**，记为 $r(A)$ 
> 也可以这样定义：若存在 $k$ 阶子式不为零，而任意 $k+1$ 阶子式 (如果有的话) 全为零，则 $r(A)=k$，且：
> $$r\left(A_{n\times n}\right)=n\Leftrightarrow\left|A\right|\neq0\Leftrightarrow A\text{可逆}$$
> 即：矩阵秩的本质，就是组成该矩阵的线性无关的向量的个数

**概念**
+ 解释：
	+ 如果一个向量，可以找到其基准向量、其所有内容可以使用基准向量表示出来；
	+ 基准向量当中成员的个数，就是矩阵的秩；
+ 意义：
	+ 比如秩为 1：
	+ 这个矩阵所形成的一个世界是一维的；
	+ 一维不仅是一个 `x` 轴；

### 4.1.2 矩阵和行列式区别 
1、行列式的本质是线性变换的放大率，而矩阵的本质就是个数表。
2、行列式行数=列数，矩阵不一定（行数列数都等于n的叫n阶方阵），二者的表示方式亦有区别。
3、行列式与矩阵的运算明显不同
（1） 相等：只有两个同型的矩阵才有可能相等，并且要求对应元素都相等；而两个行列式相等不要求其对应元素都相等，甚至阶数还可以不一样，只要两个行列式作为两个数的值是相等即可。
（2）加（减）法：两个矩阵相加（减）是将其对应元素相加（减），因此只有同型的矩阵才可以相加（减）；而两行列式作为两个数总是可以相加（减）的。
（3）  数乘运算：一个数乘以矩阵是指该数乘以矩阵的每一个元素；而数乘行列式，只能用此数乘行列式的某一行或列，提取公因数也是如此。
（4）  乘法：矩阵的乘法不满足交换律，所以，一般地，   AB≠BA。但是，如果 A与 B 都是 n 阶方阵，则有 |AB|=|A| |B|=|B| |A|=|BA|。

## 4.2 矩阵的定义
##### **定义**： #矩阵 
> <font color="#ccc1d9">描述：</font> $\text{由}m\times n\text{ 个数}a_{ij}(i=1,2,\cdots,m;j=1,2,\cdots,n)\text{排成的}m\text{行}n\text{列的矩形表格}$：
> $$\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\a_{m1}&a_{m2}&\cdots&a_{mn}\end{bmatrix}$$
> 其称为一个 $m\times n$ 矩阵，简记为 $A$ 或 $\left(a_{ij}\right)_{m\times n}\left(i=1,2,\cdotp\cdotp\cdotp,m;\: j=1,2,\cdotp\cdotp\cdotp,n\right).$ 
> 当 $m=n$ 时，称 $A$ 为 $n$ 阶方阵；
> 两个矩阵 $A=\left(a_ij\right)_{mxn},\boldsymbol{B}=\left(b_{ij}\right)_{sxk}$，若 $m=s,n=k$,则称 $A$ 与 $\boldsymbol B$ 为同型矩阵.

**解释**
+ 补充：为什么要研究方阵
	+ 实际情况中，使用矩阵时经常需要使用到非方阵，经常不是方形；
	+ 但如果要使用逆矩阵等性质时，又必须要基于方阵来求；
	+ 所以就需要经常使用 $AA^T$ 来得到非方阵矩阵的方阵形式；
+ 同型矩阵：
	+ `A` 和 `B` 的行和列数量相等；

## 4.3 矩阵运算 
**分析**：如何计算矩阵
+ 1. 先看其是不是 `秩 1 矩阵` 
+ 2. 如果不是 `秩 1 矩阵` ，此时可以考虑试算一下其平方或三次方；
	+ 举例：$\left(\begin{matrix}0&-1\\1&0\end{matrix}\right)^4=\left(\begin{matrix}1&0\\0&1\end{matrix}\right)$ 即单位阵 `<-` 经过四次运作，变成了单位阵；
+ 3. 如果按照矩阵可以分成合的分解，可以将矩阵进行分解

### 4.3.1 矩阵基本运算
**运算**：相等
+ $$A=(a_ij)_{m\times n}=B=(b_i)_{s\times k}\Leftrightarrow m=_S,n=k$$
+ 且 $a_{ij}=b_j(i=1,2,\cdots,m;j=1,2,\cdots,n)$,即 $A,B$ 是同型矩阵，且对应元素相等.

**运算**：加法
+ 两个矩阵是**同型矩阵**时，可以相加，即：
+ $$C=A+B=\left(a_{ij}\right)_{m\times n}+\left(b_{ij}\right)_{m\times n}=\left(c_{ij}\right)_{m\times n}$$
+ $\text{其中,}c_{ij}=a_{ij}+b_{ij}(i=1,2,\cdots,m;j=1,2,\cdots,n),\text{ 即对应元素相加}$

**运算**：数乘
+ 每一个元素都需要乘；
+ $$\begin{aligned}kA=Ak=&k\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\a_{m1}&a_{m2}&\cdots&a_{mn}\end{bmatrix}=\begin{bmatrix}ka_{11}&ka_{12}&\cdots&ka_{1n}\\ka_{21}&ka_{22}&\cdots&ka_{2n}\\\vdots&\vdots&&\vdots\\ka_{m1}&ka_{m2}&\cdots&ka_{mn}\end{bmatrix}\\&=\left(ka_{ij}\right)_{m\times n}\end{aligned}$$

**运算**：运算律 - 数乘/加具有交换律、结合律、分配律
1. $交换律：A+B=B+A;$
2. $结合律：\left(A+B\right)+C=A+\left(B+C\right);$
3. $分配律：k\left(A+B\right)=kA+kB,\left(k+l\right)A=kA+lA$
4. $数和矩阵相乘的结合律：k\left(lA\right)=\left(kl\right)A=l\left(kA\right).$
其中，`A，B，C` 是同型矩阵，k, l 是任意常数

### 4.3.2 矩阵乘法运算
##### **定理**： #矩阵乘法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>矩阵的乘法设 $A$ 是 $m\times s$ 矩阵，$B$ 是 $s\times n$ 矩阵 (矩阵 $A$ 的列数必须与矩阵 $B$ 的行数相等 ), 则 $A$ , $B$ 可以相乘，乘积 $AB$ 是 $m\times n$ 矩阵，记 $C=AB=(c_ij)_{m\times n}$
> $C$ 的第 $i$ 行第 $j$ 列元素 $c_{ij}$ 是 $A$ 的第 $i$ 行的 `s` 个元素与 $B$ 的第 $j$ 列的 $s$ 个对应元素两两乘积之和，即：
> $$c_{ij}=\sum_{k=1}^{s}a_{ik}b_{kj}=a_{i1}b_{1j}+a_{i2}b_{2j}+\cdots+a_{is}b_{sj}(i=1,2,\cdots,m;j=1,2,\cdots,n)$$

**解释**
+ 本质：
	+ 两个矩阵相乘，实际上体现了一种运算：**左边矩阵的每一行，乘以右边矩阵的每一列**，而且**每一行乘以每一列都是向量的内积**（点积运算）
	+ 内积的结果，可以体现两个向量的大小，还可以体现两个向量的夹角的余弦；
+ 计算：
	+ 核心：**左边的决定行，右边的决定列**；
	+ 是一种多行乘多列的类型，需要将 A 矩阵中的每一列乘以 B 中的每一行；
	+ 因为是以 `A` 的列中每个乘以 `B` 中行的每个，因此 `A` 的列数需要和 `B` 的行数相等；
+ 即：矩阵的乘法得到的结果中的每个元素，都是内积的结果；
	+ $$\left(\alpha_{1}\alpha_{2}\right)^{T}\left(\alpha_{1}\alpha_{2}\right)=\left(\begin{matrix}\alpha_{1}^{T}\\\alpha_{2}^{T}\end{matrix}\right)\left(\alpha_{1}\alpha_{2}\right)=\left.\left(\begin{matrix}(\alpha_{1},\alpha_{1})&(\alpha_{1},\alpha_{2})\\(\alpha_{2},\alpha_{1})&(\alpha_{2},\alpha_{2})\end{matrix}\right.\right)$$
+ 举例：
	+ 1. 多行乘多列：$\begin{pmatrix}a_{1}\\a_{2}\\a_{3}\end{pmatrix}(b_{1}b_{2}b_{3})=\begin{pmatrix}a_{1}b_{1}&a_{1}b_{2}&a_{1}b_{3}\\a_{2}b_{1}&a_{2}b_{2}&a_{2}b_{3}\\a_{3}b_{1}&a_{3}b_{2}&a_{3}b_{3}\end{pmatrix}$


**运算**：乘法运算的运算律
+ 运算律：
	+ 1. 结合律：满足
	+ 2. 分配律：满足
	+ 3. 数乘与矩阵乘积的结合律 `->` $(kA_{m\times s})B_{s\times n}=A_{m\times s}(kB_{s\times n})=k(A_{m\times s}B_{s\times n})$
+ 不能用的：**不满足交换律**、**不能使用消去律**
	+ 1. 矩阵的乘法一般情况下不满足交换律，即 `AB≠BA`
		+ 比如：`AB*C` 和 `BA*C` 是不一定相等的；
	+ 2. $存在A\neq O,B\neq O,而AB=O的情况,故AB=O\nRightarrow A=O或B=O$
	+ 3. $AB=AC\Rightarrow A(B-C)=O,此时即使有A\neq O,一般也得不出B=C$

**运算**：乘法运算的其他规律
+ （1）$\begin{aligned}&(A+B)^2=(A+B)(A+B)=A^2+AB+BA+B^2\neq A^2+2AB+B^2,\\&(A-B)^2=A^2-AB-BA+B^2\neq A^2-2AB+B^2,\end{aligned}$
+ （2）$\begin{aligned}&(A+B)(A-B)=A^{2}+BA-AB-B^{2}\neq A^{2}-B^{2},\\&(AB)^{m}=\overbrace{(AB)(AB)\cdots(AB)}^{m\uparrow}\neq A^{m}B^{m}.\end{aligned}$
+ （3）重要：`A` 的多项式
	+  $若f\left(x\right)=a_{0}+a_{1}x+\cdotp\cdotp\cdotp+a_{m}x^{m},\text{则}：f(A)=a_0E+a_1A+\cdots+a_mA^m$

### 4.3.3 转置矩阵 
##### **定义**： #转置矩阵
> <font color="#ccc1d9">描述：</font> $\text{将 }m\times n\text{ 矩阵 }A=\left(a_{ij}\right)_{m\times n}\text{的行与列互换得到的}n\times m\text{矩阵,称为矩阵 }A\text{ 的转置矩阵}，记为A^T，即：$ 
> $$A^{T}=\begin{bmatrix}a_{11}&a_{21}&\cdots&a_{m1}\\a_{12}&a_{22}&\cdots&a_{m2}\\\vdots&\vdots&&\vdots\\a_{1n}&a_{2n}&\cdots&a_{mn}\end{bmatrix}$$

**解释**
+ 第 `n` 行写到第 `n` 列；
+ $A^{T}A$：
	+ $$\left.A^{T}A=\left(\begin{matrix}a_{11}&a_{21}\\a_{12}&a_{22}\\a_{13}&a_{23}\end{matrix}\right.\right)_{3*{2}}\left(\begin{matrix}a_{11}&a_{12}&a_{13}\\a_{22}&a_{12}&a_{23}\end{matrix}\right)_{{2}*{3}}$$
+ 假设 $\alpha_1=({a_{11},a_{21}})$ ，其他其次类推，则得到：
	+ $$\left.\left(\begin{matrix}(\alpha_{1},\alpha_{1})&(\alpha_{1},\alpha_{2})&(\alpha_{1},\alpha_{3})\\(\alpha_{2},\alpha_{1})&(\alpha_{2},\alpha_{2})&(\alpha_{2},\alpha_{3})\\(\alpha_{3},\alpha_{1})&(\alpha_{3},\alpha_{2})&(\alpha_{3},\alpha_{3})\end{matrix}\right.\right)$$
+ 这是一个格拉姆矩阵 `->` $A^{T}A$

**运算**：转置矩阵的运算律
+ $${(1)}\left(A^{\mathrm{T}}\right)^{\mathrm{T}}=A;\quad{(2)}\left(kA\right)^{\mathrm{T}}=kA^{\mathrm{T}};\quad{(3)}\left(A+B\right)^{\mathrm{T}}=A^{\mathrm{T}}+B^{\mathrm{T}};\quad{(4)}\left(AB\right)^{\mathrm{T}}=B^{\mathrm{T}}A^{\mathrm{T}}$$
+ 重要：穿脱原则
	+ $(AB)^{\mathrm{T}}=B^{\mathrm{T}}A^{\mathrm{T}}$
	+ 从左到右乘，等于从右到左写：$\left(ABC\right)^{T}=C^{T}B^{T}A^{T}$

### 4.3.4 方阵的行列式 
##### **定义**： #方阵的行列式
> <font color="#ccc1d9">描述：</font> $\text{当用}n\text{ 阶方阵}A\text{ 计算行列式时,记成}|A|$；
> 1. $|kA|=k^{n}|A|\neq k|A|(n\geqslant2,k\neq0,1)$
> 2. $\text{一般地,}\left|A+B\right|\neq\left|A\right|+\left|B\right|$
> 3. 注意：$A\neq0\Rightarrow|A|\neq0$
> 4. $A\neq B\Rightarrow\left|A\right|\neq\left|B\right|$ 
> 5. $\left|A^{\mathrm{T}}\right|=\left|A\right|$
> 6. $\text{设}A,B\text{是同阶方阵,则}|AB|=|A||B|$

## 4.4 几种重要矩阵 
### 4.4.1 基本矩阵形式
**矩阵一**：零矩阵 
+ 定义：每个元素均为零的矩阵，记为 $O$

**矩阵二**：单位矩阵
+ 定义：
	+ 主对角线元素均为 `1`, 其余元素全为零的 `n` 阶方阵, 称为 `n` 阶单位矩阵，记成 $E$ 或 $I$
+ 注意：`E` 的写法
	+ 如果是 $A_{3*2}$ 与 $B_{2*3}$
	+ 此时：若要计算 `E-AB`
	+ 则 $E$ 要写成 $E_{3}$
	+ 此时：若要计算 `E-BA`
	+ 则 $E$ 要写成 $E_{2}$

**矩阵三**：数量矩阵
+ 定义： 
	+ 数 `k` 和单位矩阵的乘积称为数量矩阵
+ 公式：
	+ $k\cdot E_{n}=\left.\left(\begin{matrix}k&\\&k&\\&&k\end{matrix}\right.\right)$
+ 特征：
	+ 数量矩阵和任何的矩阵相乘都是可以交换的：$k\cdot E\cdot A=A\cdot kE$

**矩阵四**：(重点) 对角矩阵 
+ 定义：  
	+ 非主对角线元素均为零的矩阵称为对角矩阵；
	+ 即：主对角线之外的元素皆为 `0` 的矩阵  
	+ 这是矩阵的最简形式，大量的矩阵不能化成这个矩阵；
+ 公式：
	+ $A=\begin{pmatrix}\lambda_1&&&\\&\lambda_2&&\\&&\ddots&\\&&&\lambda_n\end{pmatrix}$

**矩阵五**：上(下)三角矩阵
+ 定义： 
	+ 当 $i>j$ 或 $i<j$ 是，$a_{ij}=0$ 的矩阵称之为**上三角矩阵**或者**下三角矩阵**；

**矩阵六**：(重要) 对称矩阵 
+ 定义： 
	+ $$\text{满足条件}A^\mathrm{T}=A\text{ 的矩阵}A\text{称为对称矩阵,}A^\mathrm{T}=A\Leftrightarrow a_{ij}=a_{ji}$$
+ 概念：
	+ 如果一个矩阵转置之后还是它自己，则称其为对称矩阵；
	+ 对称阵天生性质很多，适合进行数学上的分析； 
+ 举例：
	+ $$\left(\begin{matrix}1&-2&1\\-2&0&3\\1&3&-1\end{matrix}\right)$$
+ 结论：
	+ $\left(A^{T}A\right)^{T}=A^{T}\left(A^{T}\right)^{T}=A^{T}A$
	+ 所以：$A^{T}A$ 必定是一个对称矩阵。可以使用对称矩阵的形式；

**矩阵七**：反对称矩阵
+ 定义：  
	+ 满足 $A^T=-A$ 的矩阵 $A$ 称之为反对称矩阵；
+ 公式：
	+ $A^{\mathrm{T}}=-A\Leftrightarrow\begin{cases}a_{ij}=-a_{ji},i\neq j,\\a_{ii}=0.\end{cases}$
+ 概念：
	+ 反对称阵的主对角线一定都是零；
+ 举例： 
	+ $\begin{pmatrix}0&-2&1\\2&0&3\\-1&-3&0\end{pmatrix}$

**矩阵八**：行矩阵
+ 只有一行元素的矩阵，也称行向量；
+ 实际上就是一行多列；

**矩阵九**：列矩阵
+ 只有一列元素的矩阵，也称列向量；
+ 实际上就是多行一列；
+ 补充： 
	+ 一般写向量，一般都是写成列向量；
	+ 需要把向量写成转置，才能使行向量；
+ 补充：$\alpha^T\alpha$ 和 $\alpha\alpha^T$
	+ $\alpha^T\alpha$ ：`1*n` 和 `n*1` 相乘 `->` 得到 `1*1`
	+ $\alpha\alpha^T$：`n*1` 和 `1*n` 相乘 `->` 得到 `n*n`

**补充**：秩 1 方阵
+ 举例：
	+ 已知 $\left(\begin{matrix}-1&-1&2\\2&2&-4\\1&1&-2\end{matrix}\right)$ 要找回到 $\left(\begin{matrix}-1\\2\\1\end{matrix}\right)\left(1\quad 1\quad -2\right)$，此时必须要其数值成比例；
	+ 这种矩阵就是秩 `1` 矩阵；
	+ 这个矩阵当中，另外两个向量都可以由 `(1.1,-2)` 这个向量乘以 `2` 和 `-1` 表示出来 `->` 即：其基准向量是一个； 
	+ 所以其是三维向量当中的一个子空间；
+ 注意：  
	+ 并不是秩为 1 的矩阵就是秩 1 矩阵；
+ 性质： 
	+ 对于秩 1 方阵 A，其 $A^n=[tr(A)]^{n-1}$ 
	+ 比如： $A^3B=AAAB=[tr(A)]^2AB$

**补充**：矩阵的迹
+ 概念： 
	+ 矩阵的主对角线之和，称之为矩阵的迹；
+ 符号：
	+ `tr`

### 4.4.2 分块矩阵 
**概念**：矩阵的分块 
+ 概念： 
	+ 用几条纵线和横线把一个矩阵分成若干小块，每一小块称为原矩阵的子块；
	+ 把子块看作原矩阵的一个元素，就得到了分块矩阵；
	+ 分块可以体现矩阵里面的一些规律，此时就可以利用这些分块、简化计算；
		+ 比如：$C=\left(\begin{matrix}A&O\\O&B\end{matrix}\right)$
+ 按 `A` 进行按行分块： 
	+ $$A=\begin{bmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\\hline a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\\hline a_{m1}&a_{m2}&\cdots&a_{mn}\end{bmatrix}=\begin{bmatrix}A_1\\A_2\\\vdots\\A_m\end{bmatrix}$$
+ 按 `B` 进行按列分块：
	+ $$B=\begin{bmatrix}b_{11}&b_{12}&\cdots&b_{1n}\\b_{21}&b_{22}&\cdots&b_{2n}\\\vdots&\vdots&&\vdots\\b_{m1}&b_{m2}&\cdots&b_{mn}\end{bmatrix}=\begin{bmatrix}B_1,B_2,\cdots,B_n\end{bmatrix}$$

**运算**：分块矩阵的基本运算（以 `2*2` 举例）
+ 加法：$\text{同型,且分法一致,则}\begin{bmatrix}A_1&A_2\\A_3&A_4\end{bmatrix}+\begin{bmatrix}B_1&B_2\\B_3&B_4\end{bmatrix}=\begin{bmatrix}A_1+B_1&A_2+B_2\\A_3+B_3&A_4+B_4\end{bmatrix}$
	+ 注意：两个矩阵的切法必须一致，此时就等于每个元素对应相加；
+ 数乘：$k\begin{bmatrix}A&B\\C&D\end{bmatrix}=\begin{bmatrix}kA&kB\\kC&kD\end{bmatrix}$
+ 乘法：$\begin{bmatrix}A&B\\C&D\end{bmatrix}\begin{bmatrix}X&Y\\Z&W\end{bmatrix}=\begin{bmatrix}AX+BZ&AY+BW\\CX+DZ&CY+DW\end{bmatrix},\text{要可乘、可加}$
	+ 概念：
		+ 分块之后，将其当元素看，相当于两个 `2*2` 的矩阵相乘；
	+ 注意：
		+ 因为是矩阵运算，没有交换律，因此得到的结果，比如 $AX+BZ$，其顺序不能变化，不能写成 $XA+BZ$
	+ 注意：
		+ 对于乘法的运算要注意，分块相乘后，左边的矩阵仍在左边，右边的矩阵仍在右边；
		+ 若 A, B 分别为 `m, n` 阶方阵，则分块对角矩阵的幂为；
	+ 补充：
		+ $\begin{bmatrix}A&O\\O&B\end{bmatrix}^n=\begin{bmatrix}A^n&O\\O&B^n\end{bmatrix}$

## 4.5 矩阵的复合变换
**举例**：矩阵的复合变换
+ 概念： 
	+ 矩阵需要从右往左读，因为函数写在变量左侧：`f(g(x))` 
+ 举例： 
	+ ![[Pasted image 20240626192119.png]]