## 2.1 行列式基础概念
### 2.1.1 行列式的由来
**行列式的由来**
+ 概念：
	+ 矩阵：
		+ $$\left(\begin{matrix}a_{1}&a_{2}\\b_{1}&b_{2}\end{matrix}\right)=A$$
	+ 行列式：
		+ $$\begin{vmatrix}\mathrm{a}&\mathrm{b}\\\mathrm{c}&\mathrm{d}\end{vmatrix}=|A|$$
+ 关系：
	+ 行列式的概念由矩阵而来，矩阵是变换的一种**性质**；
	+ 矩阵是在**表达信息**，只有作用在一个向量上时，才会产生对另一个向量的作用；
	+ 行列式是把矩阵 `A` 放进来后，计算其某种性质、特点的测度；

**补充**：行列式的意义 - 二维时
+ 概念： 
	+ 行列式用于描述：一个矩阵在进行线性变换之后，这个线性变换对图像的面积改变的比例，称之为这个变换的行列式；
+ 举例： 
	+ 假设有一个二维的矩阵 A，如果矩阵 A 的行列式为 0，则表示将整个平面压缩到一条线、甚至是一个点上；
	+ 此时如果有一个图形在接受矩阵 A 的线性变换，此图形在进行线性变换后、其面积变为 0；
+ 意义：
	+ 这也就意味着：只需要检验一个矩阵的行列式是否为 `0`，我们就能了解这个矩阵所代表的变换是否将空间压缩到更小的维度上 `->` 当前矩阵中有线性相关的列向量；
+ 补充：定向
	+ 当行列式的值为负数时，则其表示定向发生改变；
+ 补充：三维 
	+ 如果是在三维时，此时行列式的值、就代表了线性变换后体积的改变比例；
	+ 因此：如果三维矩阵的行列式等于 0，则此时矩阵的列必然线性相关；

**概念**：二阶行列式的计算
+ 公式：
	+ $$|A|=|\begin{matrix}a&b\\c&d\end{matrix}|=ad-bc$$
+ 主对角线：
	+ 从 `a->d` 是主对角线；
+ 副对角线：
	+ 从 `d->c` 是副对角线；
+ 行列式的值：
	+ 就是主对角线减去副对角线；
	+ 其值的意义 `->` 行列式的值，实际上就是对行列式对应的面积的改变的度量；

### 2.1.2 行列式的知识结构
**知识结构**
+ 行列式的基础概念：
	+ 本质定义
	+ 性质
	+ 逆序数法定义
	+ 展开定理
+ 几个重要的行列式：`12+1`
	+ 主对角线行列式
	+ 副对角线行列式
	+ 拉普拉斯展开式
	+ 范德蒙德行列式
+ 行列式的计算
	+ 具体型
		+ 化成基本型
		+ 递推法
		+ 行列式表示的函数和方程
	+ 抽象型
		+ 用性质
		+ 用公式 $|AB|=|A||B|$
			+ 补充：`AB不等于BA`
			+ 但 `|AB|` 面积的结果，等于 A 和 B 的行列式的面积值得相乘
			+ 所以：`|AB|=|A||B|=|B||A|=|BA|`
+ 余子式与代数余子式的计算
+ 克拉默法则
	+ 不重要

## 2.2 行列式的第一种定义
### 2.2.1 二阶行列式
**概念**：二阶行列式的概念
+ 概念：
	+ $$2 阶行列式D_2=\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}$$
+ 解释：
	+ 其中 $a_{ij}$ 的第一个下标 $i$ 表示此元素所在的行数，第二个下标 $j$ 表示此元素所在的列数 `->` 定位置；
		+ $i=1,2,j=1,2$；
	+ 于是此行列式中有四个元素；
+ 计算：
	+ $\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}=a_{11}a_{22}-a_{12}a_{21}$
+ 几何意义：
	+ 计算：
		+ $S_D=l*m*\sin(\beta-\alpha)=a_{11}a_{22}-a_{12}a_{21}$
	+ 意义：
		+ 二阶行列式是一个平行四边形的面积值 `->` 体现测度；
		+ `2` 阶行列式是由**两个 `2` 维向量组成**的，其 (运算规则的) 结果为以这两个向量为邻边的平行四边形的面积, 这不仅得出了 2 阶行列式的计算规则，也能够清楚地看到其几何意义；

### 2.2.2 三阶行列式
**概念**：三阶行列式
+ 概念：
	+ $$\text{3阶行列式}D_{3}=\begin{vmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{vmatrix}$$
+ 解释：
	+ `3` 阶行列式是由三个 `3` 维向量 $a_1=[a_{11}, a_{12}, a_{13}]$, $a_2=[a_{21}, a_{22}, a_{23}]$, $a_3=[a_{31}, a_{32}, a_{33}]$ 组成；
	+ 其 (运算规则的) 结果为**以这三个向量为邻边的平行六面体的体积**；
+ 计算：
	+ 公式 $$\begin{vmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{vmatrix}=(a_{11}a_{22}a_{33}+a_{13}a_{21}a_{32}+a_{12}a_{23}a_{31})-(a_{13}a_{22}a_{31}+a_{12}a_{21}a_{33}+a_{11}a_{23}a_{32})$$
	+ 手算方法：
		+ 画线法 `->` 画两条线。第一条是从 `a11->a22->a33`，然后基于此线画两个叉子 `a13->a21->a32` 与 `a12->a23->a31`；同理是第二条线，以 `a13->a22->a31` 然后画两个叉子；

### 2.2.3 n 阶行列式的本质定义
##### **定义**： #n阶行列式
> <font color="#ccc1d9">描述：</font> $$\begin{aligned}&n\text{ 阶行列式 }D_n=\begin{vmatrix}a_{11}&\cdots&a_{1n}\\\vdots&&\vdots\\a_{n1}&\cdots&a_{nn}\end{vmatrix}\text{是由 }n\text{ 个 }n\text{ 维向量 }a_1=\begin{bmatrix}a_{11}&a_{12}&\cdots,a_{1n}\end{bmatrix},\cdots,a_{n}=[a_{n1},a_{n2},\cdots,a_{nn}]\text{组成的,其(运算规则的)结果是以这 }n\text{个向量为邻边的 }n\text{维图形的(有}\\&\text{向)体积.}\end{aligned}$$

**解释**
+ 行列式为 `0`，向量组线性相关行列式不为 `0`，向量组线性无关；

## 2.3 行列式的第二种定义
### 2.3.1 排列和逆序
**概念**：排列
+ 排列由 `n` 个数 `1,2,…, n` 组成的一个有序数组称为一个 `n` 级排列；
+ 如 `23145` 是一个 `5` 级排列，`41352` 也是一个 `5` 级排列，`n` 级排列共有 `n!` 个；

**概念**：逆序
+ $\text{在一个}n\text{ 级排列 }i_1i_2\cdots i_s\cdots i_t\cdots i_n\text{中,若}i_s>i_t\text{,且}i_s\text{排在}i_t\text{前面,则称这两个数构成一个逆序 }.$

**概念**：逆序数
+ 逆序数一个排列中，逆序的总数称为该排列的逆序数，记作 $\tau\left(i_{1}i_{2}\cdots i_{n}\right)$，如 $\tau(231546)=3$
+ 由小到大顺排的排列称为自然排序，如 `12345`，显然，自然排序的逆序数为 `0`；

**概念**：奇排列和偶排列
+ 该排列排列的逆序数为奇数时，该排列称为奇排列；
+ 排列的逆序数为偶数时，称为偶排列；

### 2.3.2 n 阶行列式的第二种定义
##### **定义**： #n阶行列式：第二种定义
> <font color="#ccc1d9">描述：</font> $$\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn}\end{vmatrix}=\sum_{j_{1}j_{2}\cdots j_{n}}(-1)^{r(j_{1}j_{2}\cdots j_{n})}a_{1j_{1}}a_{2j_{2}}\cdots a_{nj_{n}}.$$

**解释**
+ 解释：
	+  $\sum_{h_1,h_2,...h_n}$：
		+ 表示对所有 $n$ 个列下标排列求和，故为 $n!$ 项之和；
		+ 注意 `->` 行下标已经顺排，而列下标是任一个 $n$ 级排列； 
	+ $(-1)^{\tau(j_1j_2\cdots j_n)}.$：
		+ 每项的正、负号取决于 $(-1)^{\tau(j_1j_2\cdots j_n)}.$ 
		+ 即：正负取决于 $\tau(j_1j_2\cdots j_n)$ 的结果，对列的下标的排列计算其逆序数；
		+ 当列下标为奇排列时，应附加负号；当列下标为偶排列时，应附加正号； 
	+  $a_{1j_{1}}a_{2j_{2}}\cdots a_{nj_{n}}$：
		+ 每项由取自不同行、不同列的 $n$ 个元素的乘积组成
+ 意义：
	+ 把 `n` 阶行列式，展开成 `n` 的阶乘个项 `->` 即表示 n 阶排列式，通用的计算规则；
+ 举例：
	+ 题目：
		+ $请确定a_{12}a_{31}a_{54}a_{43}a_{25}这一展开项前的正、负号$
	+ 分析：
		+ 先把行排好 `->` $a_{12}a_{25}a_{31}a_{43}a_{54}$
		+ 然后再看 $\tau(25134)=4$ 

## 2.4 行列式的第三种定义
**核心思想**：降阶

### 2.4.1 余子式 
##### **定义**： #余子式
> <font color="#ccc1d9">描述：</font>在 $n$ 阶行列式中，去掉元素 $a_{ij}$ 所在的第 $i$ 行、第 $j$ 列元素，由剩下的元素按原来的位置与顺序成的 $n-1$ 阶行列式称为元素 $a_{ij}$ 的余子式，记作 $M_{ij}$
> 即：$$M_{ij}=\begin{vmatrix}a_{11}&\cdots&a_{1,j-1}&a_{1,j+1}&\cdots&a_{1n}\\\vdots&&\vdots&\vdots&&\vdots\\a_{i-1,1}&\cdots&a_{i-1,j-1}&a_{i-1,j+1}&\cdots&a_{i-1,n}\\a_{i+1,1}&\cdots&a_{i+1,j-1}&a_{i+1,j+1}&\cdots&a_{i+1,n}\\\vdots&&\vdots&\vdots&&\vdots\\a_{n1}&\cdots&a_{n,j-1}&a_{n,j+1}&\cdots&a_{mn}\end{vmatrix}.$$

**解释**
+ 补充：
	+ 子式：
		+ 提到的所有子式，都是指的行列式；
		+ 子式是原本的行列式的一部分；
	+ 子矩阵：
		+ 子矩阵就是就是矩阵；
+ 解释：
	+ 把 $a_{ij}$ 所在的第 $i$ 行、第 $j$ 列元素的所有元素都去掉，得到的行列式就是 $(n-1)*(n-1)$ ，将其剩下的部分称之为子式，即**余子式**；
+ 举例： 
	+ 矩阵为 $\begin{vmatrix}1&2&1\\2&5&7\\-6&4&9\end{vmatrix}$ ，其 $A_{23}$ 的余子式 $M_{23}$ 为 $\left|\begin{matrix}1&2\\-6&4\end{matrix}\right|$ 

### 2.4.2 代数余子式
##### **定义**： #代数余子式
> <font color="#ccc1d9">描述：</font> $\text{余子式 }M_{ij}\text{乘(}-1\text{)}^{i+j}\text{后称为}a_{ij}\text{ 的代数余子式,记作 }A_{ij}\text{,即}$：
> $$A_{ij}=(-1)^{i+j}M_{ij}\quad\quad 且显然还有 M_{ij}=(-1)^{i+j}A_{ij} $$

**解释**
+ 概念：  
	+ 在余子式的基础上，给它添上一个 $(-1)^{i+j}$ 的正负号； 
+ 举例： 
	+ $A_{23}=(-1)^{2+3}M_{23}$

### 2.4.3 行列式的展开公式
##### **定理**： #行列式的展开定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>行列式的**值**等于行列式的**某行 (列) 元素分别乘其相应的代数余子式**后再求和，即：$$\left|A\right|=\begin{cases}a_{i1}A_{i1}+a_{i2}A_{i2}+\cdots+a_{in}A_{in}=\sum_{j=1}^{n}a_{ij}A_{ij}\left(i=1,2,\cdots,n\right),\\\\a_{1j}A_{1j}+a_{2j}A_{2j}+\cdots+a_{nj}A_{nj}=\sum_{i=1}^{n}a_{ij}A_{ij}\left(j=1,2,\cdots,n\right).\end{cases}$$

**解释**
+ 举例： 
	+ 展开：
		+ 对 $|A|_{3\times3}$ 按照第一行展开，得到 $|A|_{3\times3}=a_{11}A_{11}+a_{12}A_{12}+a_{13}A_{13}$
	+ 分析：
		+ 在上述例子中，将一个三阶的式子展开成了二阶，但代价是式子变成了三个；
		+ 如果四阶时就是 $|A|_{4\times4}=a_{21}A_{21}+a_{22}A_{22}+a_{23}A_{3}+a_{24}A_{24}$
+ 目的：
	+ 核心思想 `->` 降阶后求行列式的值；
	+ 将 `n` 阶降成 `n` 个 `n-1` 阶
+ 展开原则：
	+ 某一行（列）的为 `0` 的元素越多越好；

## 2.5 行列式的性质 
### 2.5.1 性质一
**性质一**：行列互换，其值不变，即 $|A|=|A^{\mathrm{T}}|$
+ 概念补充：
	+ 转置矩阵：
		+ 若 $|A|=|A^{\mathrm{T}}|$，则称 $A^{\mathrm{T}}$ 是 `A` 的**转置矩阵**；
	+ 对称矩阵：
		+ 在 $A^{\mathrm{T}}$ 是 `A` 的**转置矩阵**的基础上，如果 $A=A^{\mathrm{T}}$ ，则称其为对称矩阵；
+ 性质解释：
	+ $|A|=|A^{\mathrm{T}}|$ `->` 即使如果当前 $A^{\mathrm{T}}$ 和 `A` 不是对称矩阵时，它们的值（二阶行列式的几何上的面积）也是相同的；
+ 结论：
	+ 对于行列式来讲，行和列地位等价 `->` **能用在行上的性质，在列上都能用**；

### 2.5.2 性质二
**性质二**：行列式中某行（列）元素全为零，则行列式为零
+ 如果在行列式当中，有一行为 `0` `->` 意味着这个行列式已经被降了一维 `->` 因为测不到，所以测度为 `0`；
+ 同理，如果有某一列全为 0，则行列式为零；

### 2.5.3 性质三：倍乘
**性质三**：行列式中某行（列）元素有公因子 `k(k≠0)`，则 `k` 可提到行列式外面，即：
+ 公式：
	+ $$\begin{vmatrix}a_{11}&a_{12}&\ldots&a_{1n}\\\vdots&\vdots&&\vdots\\ka_{i1}&ka_{i2}&\ldots&ka_{in}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\ldots&a_{nn}\end{vmatrix}=k\begin{vmatrix}a_{11}&a_{12}&\ldots&a_{1n}\\\vdots&\vdots&&\vdots\\a_{i1}&a_{i2}&\ldots&a_{in}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\ldots&a_{nn}\end{vmatrix}.$$
+ 解释：
	+ 如果从几何上理解：如果是一个二阶行列式，乘以 `K` 代表其在**某一个**方向上乘以 `k`，而不是所有（这里的所有，其实就是两个方向）方向，只能延长某一个边 `->` 如果是对所有方向都乘以 `K`，则得到的结果将是平方；
	+ 上述乘以提取 K 的过程中，等式从右到左的运算都称之为“**倍乘**”的性质；
+ 举例：
	+ 可以把数乘到（提取）到**某一行**上
	+ $$\begin{vmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{vmatrix}=k\begin{vmatrix}a_{11}&a_{12}\\\frac{a_{21}}{k}&\frac{a_{22}}{k}\end{vmatrix}$$
+ 作用：
	+ 将行列式中的分母去掉；

### 2.5.4 性质四
**性质四**：行列式中某行（列）元素均是两个元素之和，则可拆成两个行列式之和，即：
+ 公式：
	+ $$\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\\vdots&\vdots&&\vdots\\a_{i1}+b_{i1}&a_{i2}+b_{i2}&\cdots&a_{in}+b_{in}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn}\end{vmatrix}=\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\\vdots&\vdots&&\vdots\\a_{i1}&a_{i2}&\cdots&a_{m}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn}\end{vmatrix}+\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\\vdots&\vdots&&\vdots\\b_{i1}&b_{i2}&\cdots&b_{in}\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn}\end{vmatrix}$$
+ 解释：
	+ 单行可拆 (加) 性；  
	+ 等式从右到左是两个行列式的相加的运算。如果**两个行列式的其他元素对应相等，只有一行（列）不同**时，可以相加，相加时其他元素不变，不同元素的行（列）对应相加即可；
+ 补充：
	+ 单行可加性 `->` 行列式中对应的行不一样、其他的每一行都完全一样 `->` 此时才可以加；
+ 举例：二阶行列式时
	+ $$\begin{vmatrix}a_1&a_2\\b_1&b_2\end{vmatrix}+\begin{vmatrix}a_1&a_2\\c_1&c_2\end{vmatrix}=\begin{vmatrix}a_1&a_2\\c_1+b_1&c_2+b_2\end{vmatrix}$$
+ 注意：
	+ 显然，由此性质可知：$|A|+|B|\neq|A+B|$

### 2.5.5 性质五：互换
**性质五**：行列式中，两行（列）互换，行列式变号
+ 几何意义：
	+ 比如在二阶行列式中，所画的平行四边形、两边顺序互换，得到的面积因此相反；
+ 注意：
	+ 此性质被称之为“**互换**”性质；
	+ 互换时，如果互换偶数次 `->` 值不变；换奇数次 `->` 值变号；

### 2.5.6 性质六
**性质六**：行列式中的两行 (列) 元素相等或对应成比例，则行列式为零
+ 举例：  
	+ $$\vert\begin{matrix}1&2\\2&4\end{matrix}\vert=0$$
+ 解释：
	+ 如果有两行元素完全相同或者成比例，则此行列式为零；
+ 几何含义：
	+ 二阶行列式中，两向量平行；
+ 注意：
	+ 负方向也可以平行；

### 2.5.7 性质七：倍加
**性质七**：行列式中某行 (列)的 k 倍加到另一行 (列)，行列式不变
+ 举例： 
	+ 把 $\left|\begin{matrix}1&2\\2&3\end{matrix}\right|$ 中的 $|1\quad 2|$ 的 `-2` 倍加到 $|2\quad 3|$ 中
	+ 即：`(1,2)*-2=(-2,-4)` 加到 $|2\quad 3|$ 中 `->` `|0，-1|` `->` 即得到 $\left|\begin{matrix}1&2\\0&-1\end{matrix}\right|$
	+ 且 $\left|\begin{matrix}1&2\\0&-1\end{matrix}\right|$ =  $\left|\begin{matrix}1&2\\2&3\end{matrix}\right|$ 
+ 解释： 
	+ 此性质称之为“**倍加**”性质 `->` 讲某一行倍乘之后，加到另一行上；
+ 作用：
	+ 把行列式中的 `0` 化出来 `->` 即是为了化简；

## 2.6 几个重要的行列式 
### 2.6.1 主对角线行列式 
##### **定义**： #主对角线行列式 
> <font color="#ccc1d9">描述：</font> $$\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\0&a_{22}&\cdots&a_{2n}\\\vdots&\vdots&&\vdots\\0&0&\cdots&a_{nn}\end{vmatrix}=\begin{vmatrix}a_{11}&0&\cdots&0\\a_{21}&a_{22}&\cdots&0\\\vdots&\vdots&&\vdots\\a_{n1}&a_{n2}&\cdots&a_{nn}\end{vmatrix}=\begin{vmatrix}a_{11}&0&\cdots&0\\0&a_{22}&\cdots&0\\\vdots&\vdots&&\vdots\\0&0&\cdots&a_{nn}\end{vmatrix}=\prod_{i=1}^na_{ii}.$$

**解释**：上 (下)三角形行列式
+ 结果等于主对角线元素连乘；

### 2.6.2 副对角线行列式
##### **定义**： #副对角线行列式 
> <font color="#ccc1d9">描述：</font> $$\begin{aligned}\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1,n-1}&a_{1n}\\a_{21}&a_{22}&\cdots&a_{2,n-1}&0\\\vdots&\vdots&&\vdots&\vdots\\a_{n1}&0&\cdots&0&0\end{vmatrix}&=\begin{vmatrix}0&\cdots&0&a_{1n}\\0&\cdots&a_{2,n-1}&a_{2n}\\\vdots&&\vdots&\vdots\\a_{n1}&\cdots&a_{n,n-1}&a_{nn}\end{vmatrix}=\begin{vmatrix}0&\cdots&0&a_{1n}\\0&\cdots&a_{2,n-1}&0\\\vdots&&\vdots&\vdots\\a_{n1}&\cdots&0&0\end{vmatrix}\\&=(-1)^{\frac{n(n-1)}{2}}a_{1n}a_{2,n-1}\cdots a_{n1}.\end{aligned}$$

**解释**
+ 结果等于副对角线元素连乘再乘上逆序数；

### 2.6.3 拉普拉斯展开式
##### **定义**： #拉普拉斯展开式 
> <font color="#ccc1d9">描述：</font> $$\begin{gathered}
设A为m阶矩阵,B为n阶矩阵,则 \\
\begin{vmatrix}A&O\\O&B\end{vmatrix}=\begin{vmatrix}A&C\\O&B\end{vmatrix}=\begin{vmatrix}A&O\\C&B\end{vmatrix}=|A||B|, \\
 \\
\begin{vmatrix}\boldsymbol{O}&\boldsymbol{A}\\\boldsymbol{B}&\boldsymbol{O}\end{vmatrix}=\begin{vmatrix}\boldsymbol{C}&\boldsymbol{A}\\\boldsymbol{B}&\boldsymbol{O}\end{vmatrix}=\begin{vmatrix}\boldsymbol{O}&\boldsymbol{A}\\\boldsymbol{B}&\boldsymbol{C}\end{vmatrix}=(-1)^{mn}|\boldsymbol{A}||\boldsymbol{B}|. 
\end{gathered}$$

**解释**
+ 分块阵的行列式：$\begin{vmatrix}A&O\\O&B\end{vmatrix}$ 
	+ 这里面的 `A、B、0` 都是矩阵；
	+ 用若干条横线和若干条竖线，把一个矩阵分成若干个子矩阵，分出来的子矩阵就是原矩阵的分块，我们称这样的矩阵表达的方法叫做分块儿矩阵；
	+ 比如：A 可以是一个三阶矩阵 $A_{3*3}$，B 可以是一个二阶矩阵 $B_{2*2}$ ，因此 $\begin{vmatrix}A&O\\O&B\end{vmatrix}$ 是一个五阶矩阵；
+ 分块阵的含义：
	+ 把矩阵、从数的角度广义化；
+ 分析：
	+ $\begin{vmatrix}A&O\\O&B\end{vmatrix}=\begin{vmatrix}A&C\\O&B\end{vmatrix}=\begin{vmatrix}A&O\\C&B\end{vmatrix}=|A||B|$ `<-` 它的结论可以理解成主对角线的结论；
	+ $\begin{vmatrix}\boldsymbol{O}&\boldsymbol{A}\\\boldsymbol{B}&\boldsymbol{O}\end{vmatrix}=\begin{vmatrix}\boldsymbol{C}&\boldsymbol{A}\\\boldsymbol{B}&\boldsymbol{O}\end{vmatrix}=\begin{vmatrix}\boldsymbol{O}&\boldsymbol{A}\\\boldsymbol{B}&\boldsymbol{C}\end{vmatrix}=(-1)^{mn}|\boldsymbol{A}||\boldsymbol{B}|$ `<-` 它的结论可以理解成副对角线的形式的结论，`mn` 就是换了多少次；

### 2.6.4 范德蒙德行列式 
##### **定义**： #范德蒙德行列式
> <font color="#ccc1d9">描述：</font> $$\begin{vmatrix}1&1&\cdots&1\\x_1&x_2&\cdots&x_n\\x_1^2&x_2^2&\cdots&x_n^2\\\vdots&\vdots&&\vdots\\x_1^{n-1}&x_2^{n-1}&\cdots&x_n^{n-1}\end{vmatrix}=\prod_{1\leq i<j\leq n}(x_j-x_i),n\geq2.$$

**解释**
+ 分析：三阶范德蒙德行列式 `->` $V_{3}=\begin{vmatrix}1&1&1\\x_{1}&x_{2}&x_{3}\\x_{1}^{2}&x_{2}^{2}&x_{3}^{2}\end{vmatrix}$
+ 计算方法：三阶时
	+ 不管是几行，总是往当中第二行看；
	+ 计算：${(x_{3}-x_{2})(x_{3}-x_{1}).}{(x_{2}-x_{1})}$  *//"高年级欺负低年级"*
+ 注意：
	+ 最后一行的次数是阶数减一，因为次数是从 0 开始数的；
+ 举例：  
	+ $\begin{vmatrix}1&a&a^{2}\\1&b&b^{2}\\1&c&c^{2}\end{vmatrix}=\begin{vmatrix}1&1&1\\a&b&c^{2}\\a^{2}&b^{2}&c^{2}\end{vmatrix}=$


