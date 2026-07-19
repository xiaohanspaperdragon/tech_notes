## 11.1 向量
### 11.1.1 向量的定义
**概念**：线性相关性 
+ `->` 研究向量组内部之间的关系：$(\alpha_1,\alpha_2,\alpha_3...\alpha_n)$ -> 
+ `->` 最简形式：一般都是表示新的向量和之前的向量系数相同 `<-` 行变换； 
+ `->` 向量组之间的关系：$(\beta_1,\beta_2...\beta_n)$ 和 $(\alpha_1,\alpha_2,\alpha_3...\alpha_n)$

##### **定义**： #向量 
> <font color="#ccc1d9">描述：</font>
> 矩阵中的若干个行 (列) 都是向量，它们之间存在着某种联系，这种联系说到底就是线性无关的向量个数 (独立信息的个数)的问题，也就是在若干个向量组成的向量组中，其中某几个就足够代表这个向量组了，其他的向量都可以由这几个向量线性表示出来；
> 比如，向量组 $[1,2,3]$, $[6,7,9]$ 与 $[2,4,6]$, 有三个成员，可是 $[2,4,6]$ 这个向量可以由 $[1,2,3]$ 这个向量的 2 倍来表示，于是 $[2,4,6]$ 这个向量就是“多余”的，不是独立的信息
> 极大线性无关组是向量组的“代表”，而矩阵就是由向量组拼成的，所以**矩阵的秩、向量组的秩都反映了“代表”中向量的个数，本质完全相同**；

**解释**
+ 向量组： $\begin{pmatrix}1&6&2\\2&7&4\\3&9&6\end{pmatrix}$
	+ 向量组合在一起就是矩阵；
+ 列向量： $[1,2,3]$, $[6,7,9]$ 与 $[2,4,6]$；
+ 计算：比如 $2\alpha_1=\alpha_3$
	+ 比如：`[1,2,3]` 和 `[2,4,6]`
	+ 因为它们可以进行线性运算，所以说具有线性相关性；
+ 目标： 
	+ 在当前向量组当中，找到某几个可以足够代表整个向量组的向量；
	+ 比如 $2\alpha_1=\alpha_3$ 时，$\alpha_3$ 就可以被抹去了，而 $\alpha_2$ 不行；
	+ 此时 $\alpha_1$ 和 $\alpha_2$ 就可以表达所有向量组 `->` 空间的维度（秩）；
+ 目标： 
	+ 搞清楚向量与向量之间的关系：**线性无关、线性独立**；

##### **定义**： #n维向量
> <font color="#ccc1d9">描述：</font> $n\text{ 个数构成的一个有序数组}\left[a_1,a_2,\cdots,a_n\right]\text{称为一个}n\text{ 维向量},\text{记成}\alpha=\left[a_1,a_2,\cdots,a_n\right]$；
> 并称 $\alpha\text{为}n\text{维行向量},\alpha^{\mathrm{T}}=[a_1,a_2,\cdots,a_n]^{\mathrm{T}}\text{称为}n\text{维列向量,其中}a_i\text{称为向量}\alpha(\text{或}\alpha^{\mathrm{T}})\text{的第}i\text{个分量}$

**解释**
+ `n` 维：
+ 对应矩阵的行数或者列数；
+ 并且 `n` 在小于三时、是完全可以理解的；
+ 当 n 大于 `3` 之后，此时就需要现在空间当中先定义距离、面积等内容，比如利用点积来计算；

##### **定义**： #向量的基本运算 
> <font color="#ccc1d9">描述：</font>
> 1. 相等：向量的相等就是矩阵的相等，对应元素全部相同；
> 2. 加法：$a+\beta=\left[a_1+b_1,a_2+b_2,\cdots,a_n+b_n\right]$
> 3. 数乘：$ka=\begin{bmatrix}ka_1,ka_2,\cdots,ka_n\end{bmatrix}$

### 11.1.2 补充：什么是向量
**概念**：向量的基
+ 每当我们使用数字来描述向量时，它都依赖于我们正在使用的基；

**概念**：给定向量张成的空间
+ 解释： 
	+ 所有可以表示为给定向量线性组合的向量的集合，表示给定向量张成的空间；
	+ 因为线性代数中只有向量加法和向量乘法运算 `->` 给定向量张成的空间：意味着在当前 `向量的基` 的基础上，你能得到的所有可能向量的集合是什么；
+ 举例： 
	+ 三维空间中，两个线性无关的向量张成的空间：就是这两个向量缩放（乘法）再相加（加法）得到的所有可能的向量；
		+ 图示： ![[Pasted image 20240625184520.png]]
	+ 三维空间中，三个线性无关的向量张成的空间：三个自由的标量可以被随意乘到这三个向量上，因此可以得到整个空间；


**概念**：线性相关 
+ 一个向量可以表示为其它向量的线性组合。因为这个向量已经落在其它向量张成的空间之中；

## 11.2 向量的内积与正交 
### 11.2.1 向量的内积 
##### **定义**： #向量的内积 
> <font color="#ccc1d9">描述：</font> $$\alpha^{\mathrm{T}}\beta=\sum_{i=1}^{n}a_{i}b_{i}=a_{1}b_{1}+a_{2}b_{2}+\cdots+a_{n}b_{n}=||\alpha||||\beta||cos_{角度}$$
> $\text{为向量}\alpha,\beta\text{的内积, 记作}\left (\alpha,\beta\right),\text{即}\left (\alpha,\beta\right)=\alpha^{\mathrm{T}}\beta$

**解释**
+ 配对相乘再相加：
	+ 向量的配对相乘再相加，得到向量的内积；
	+ 等于： $\alpha^{\mathrm{T}}\beta=\sum_{i=1}^{n}a_{i}b_{i}=||\alpha||||\beta||cos_{角度}$
	+ 虽然不能在图形上看到它，但是可以求出它的 $cosx$
+ 举例： 
	+ $\left.A^{T}A=\left(\begin{matrix}\alpha^{T}\\\beta^{T}\end{matrix}\right.\right)({\alpha}{\beta})=\left(\begin{matrix}{\alpha^{T}\cdot\alpha}&{\alpha^{T}\beta}\\{\beta^{T}\alpha}&{\beta^{T}\beta}\\\end{matrix}\right)=\begin{pmatrix}||\alpha||^{2}&||\alpha||||\beta||\cdot\cos\theta&\\||\alpha||||&||\beta||^{2}\end{pmatrix}$

### 11.2.2 向量的正交 
##### **定义**： #正交
> <font color="#ccc1d9">描述：</font>位置关系里面的特殊关系：当 $\alpha^T\beta=0$ 时，称向量 $\alpha,\beta$ 是正交向量；

**解释**
+ 为什么叫正交而不是垂直：因为垂直是三维或者二维中的概念；

**概念**：模
+ $\parallel\alpha\parallel=\sqrt{\sum_{i=1}^{n}a_{i}^{2}}$ 称之为向量的长度（模）
+ $\parallel\alpha\parallel=1$ 的向量是单位向量 `->` $A^{T}A=(\begin{matrix}1&0\\0&1\end{matrix})=E$

**概念**：`n` 阶正交矩阵
+ $$A^{T}A=(\begin{matrix}1&0\\0&1\end{matrix})=E$$

##### **定义**： #标准正交向量组
> <font color="#ccc1d9">描述：</font>若列向量组 $a_1,a_2,\cdots,a_s$ 满足：$$\alpha_i^\mathrm{T}\alpha_j=\begin{cases}0,&i\neq j,\\1,&i=j,\end{cases}$$
> 则称 $a_1,a_2,\cdots,a_s$ 为标准或单位正交向量组，也叫规范正交基；

##### **定义**： #正交矩阵 
> <font color="#ccc1d9">描述：</font> $设A是n阶方阵，满足A^TA=E，则称A是正交矩阵$；
> $A\text{ 是正交矩阵}\Leftrightarrow A^\top A=E\Leftrightarrow A^\top=A^-\Leftrightarrow A\text{ 的行 }(\text{列 })\text{ 向量组是规范正交基}$

**解释**
+ 解释：
	+ 正交矩阵当中都是单位向量，并且这些向量之间都垂直；
	+ 其他无数的正交阵，都是由标准正交阵旋转移动而来 `->` 组成的矩阵是无数个的；
+ 作用：
	+ 用来把数据进行正交旋转、变换；
	+ 通过变换，可以更好的求得其最大值、最小值；
	+ 举例：把一个椭圆进行旋转，然后可以得到其在 y 轴上的顶点；
+ 举例： $\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$
	+ 它乘上任何一个角度，都是将其旋转 `sin` 的角度 $\theta$；
	+ $\left(\begin{matrix}\frac{\sqrt{2}}{2}-\frac{\sqrt{2}}{2}\\\frac{\sqrt{2}}{2}\frac{\sqrt{2}}{2}\end{matrix}\right)\left(i\right)=\left(\begin{matrix}0\\\sqrt{2}\end{matrix}\right)$
+ 概念： 
	+ 正交矩阵进行操作时，不会变换矩阵的性质，只是将其相对位置进行变换，而不会使得其形状发生变化；

**补充**：三维时的情况
+ $A=\begin{bmatrix}a_{1}&a_{2}&a_{3}\\b_{1}&b_{2}&b_{3}\\c_{1}&c_{2}&c_{3}\end{bmatrix}$
+ $\alpha=[a_1,a_2,a_3]^\mathrm{T},\beta=[b_1,b_2,b_3]^\mathrm{T},\gamma=[c_1,c_2,c_3]^\mathrm{T}$ 
+ 得到：${AA^\mathrm{T}=\begin{bmatrix}a_1&a_2&a_3\\b_1&b_2&b_3\\c_1&c_2&c_3\end{bmatrix}\begin{bmatrix}a_1&b_1&c_1\\a_2&b_2&c_2\\a_3&b_3&c_3\end{bmatrix}=E=\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}}$
+ 得到：$\begin{aligned}&a_{1}^{2}+a_{2}^{2}+a_{3}^{2}=1\Rightarrow\left\|\alpha\right\|=1,\\&b_{1}^{2}+b_{2}^{2}+b_{3}^{2}=1\Rightarrow\left\|\beta\right\|=1,\\&c_{1}^{2}+c_{2}^{2}+c_{3}^{2}=1\Rightarrow\left\|\gamma\right\|=1,\\&a_{1}b_{1}+a_{2}b_{2}+a_{3}b_{3}=0\Rightarrow\left(\alpha,\beta\right)=0,即\alpha 与\beta 正交,\\&a_{1}c_{1}+a_{2}c_{2}+a_{3}c_{3}=0\Rightarrow\left(\alpha,\gamma\right)=0,即\alpha 与\gamma 正交,\\&b_{1}c_{1}+b_{2}c_{2}+b_{3}c_{3}=0\Rightarrow\left(\beta,\gamma\right)=0,即\beta 与\gamma 正交,\end{aligned}$

## 11.3 线性相关与线性无关 
### 11.3.1 线性组合 
##### **定义**： #线性组合 
> <font color="#ccc1d9">描述：</font>对 `m` 个 `n` 维向量和 `m` 个数，线性组合：$$k_1\alpha_1+k_2\alpha_2+\cdots+k_m\alpha_m$$

**解释**
+ 作用： 
	+ 当只有两个向量时，假设一个是 $(0,1)$ 一个是 $(1,0)^T$
	+ 若 `k` 任意取值，则可以用 $k_1\alpha_1+k_2\alpha_2$ 来表示空间中的所有点；

### 11.3.2 线性表示 
##### **定义**： #线性表示 
> <font color="#ccc1d9">描述：</font> $\text{向量}\beta\text{能表示成向量组}\alpha_1,\alpha_2,\cdots,\alpha_m\text{的线性组合,即存在}m\text{ 个数}k_1,k_2,\cdots,k_m\text{,使得}：$
> $$\beta=k_1\alpha_1+k_2\alpha_2+\cdotp\cdotp\cdotp+k_m\alpha_m$$
> 则称向量 $\beta$ 可被向量组线性表示；

**解释**
+ 如果 $\beta$ 可以被 `m` 个空间中数表示，也表示 $\beta$ 是存在于这个空间当中；

### 11.3.3 线性相关与线性无关 
##### **定义**： #线性相关 
> <font color="#ccc1d9">描述：</font> $对于m个n维向量a_1,a_2,\cdots,a_m,若存在一组不全为零的数k_1,k_2,\cdots,k_m,使得$：
> $$k_1\alpha_1+k_2\alpha_2+\cdotp\cdotp\cdotp+k_m\alpha_m=0$$
> 则称向量线性相关；
> 含有零向量或有成比例的向量的向量组必线性相关；

**解释**
+ 解释：
	+ 即意味着 $\alpha_i$ 这一项是可以被其他向量线性表示的；
+ 概念： 
	+ 一组向量线性相关：它是指**这组向量中至少有一个向量、可以被其他向量组成的空间所表示**； 
	+ 再换句话说：一个线性相关的向量组，至少在这个小组里，**至少有一个向量可以被其它向量表示**；
	+ 那也就是说，**至少有一个向量是多的信息**。我们就称这组向量线性相关；
+ 注意： 
	+ 第一个：零向量 
		+ 零向量一定可以被其他向量表示： 
		+ 这个空间里的，零向量只要在里头，一定这个小组是线性相关的；因为零一定可以被其他的表示；
	+ 第二个：成比例的向量；
		+ 如果一个向量组里面有成比例的向量 `->` 多余的向量；

##### **定义**： #线性无关 
> <font color="#ccc1d9">描述：</font>不存在任何一个向量可以被其他向量表示；
> $\text{只有当 }k_1=k_2=\cdots=k_m=0\text{时,才有 }k_1a_1+k_2a_2+\cdots+k_ma_m=0成立，则称向量线性无关；$

**解释**
+ 概念： 
	+ 把线性相关当成线性无关的反面来理解；
	+ 向量组或线性相关或线性无关，二者必居其一且仅居其一；
+ 解释： 
	+ 它实际上就是**没有一个向量是多余的**；
	+ 它对装成它们所在的这样一个 `N` 维空间，每个人都有贡献；
	+ 我们称其为叫做线性无关；
	+ 比如现在有三个向量，它们之间谁也表示不了谁，则此时是三维向量；
+ 注意： 
	+ 单个非零向量、两个不成比例的向量均线性无关；

## 11.4 判别线性相关性的定理
##### **定理**： #线性相关定理一
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>向量组 $\alpha_{1},\alpha_{2},\cdots,\alpha_{n}(n\geqslant2)$ 线性相关的**充要条件**是：向量组中至少有一个向量可由其余的 `n-1` 个向量线性表示；

**解释**
+ 三个三维向量，组成的是三维空间；
+ 一个三维的非零的向量，它组成的是三维空间里的一维子空间；
+ 两个线性无关的非零三维向量，组成的是三维空间中的二维平面；

##### **定理**： #线性相关定理二 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若 $\alpha_{1},\alpha_{2},\cdots,\alpha_{n}$ 线性无关，而 $\alpha_{1},\alpha_{2},\cdots,\alpha_{n},\beta$ 线性相关，则称 $\beta$ 可以被线性表示，且表示法唯一；

**解释**
+ 举例：$\beta=\left(\begin{matrix}2\\3\end{matrix}\right)=2\left(\begin{matrix}1\\0\end{matrix}\right)+3\left(\begin{matrix}0\\1\end{matrix}\right)$

##### **定理**： #线性相关定理三 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若向量组 $\beta_1,\beta_2...\beta_t$ 可以被 $\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$ 线性表示，且 $t>s$，则 $\beta_1,\beta_2...\beta_t$ 线性相关；

**解释**
+ 核心：**以少表多，多的相关**
+ 不管 $\alpha$ 是线性相关还是线性无关，$\beta$ 都是线性相关的；

**概念**：$\text{如果向量组}\beta_1,\beta_2,\cdots,\beta_t\text{可由向量组}\alpha_1,\alpha_2,\cdots,\alpha_s\text{线性表示,且}\beta_1,\beta_2,\cdots,\beta_t\text{线性无关}，则：t<=s$ 

##### **定理**： #线性相关定理四 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设 `m` 个向量 $\alpha_{1},\alpha_{2},\cdots,\alpha_{m}$，其中：$$\begin{aligned}&\alpha_{1}=[a_{11},a_{21},\cdots,a_{n1}]^{\mathrm{T}},\\&\alpha_{2}=[a_{12},a_{22},\cdots,a_{n2}]^{\mathrm{T}},\\&\cdots\cdots\\&\alpha_{m}=[a_{1m},a_{2m},\cdots,a_{nm}]^{\mathrm{T}}.\end{aligned}$$
> 方程组的形式为：$$\begin{cases}a_{11}x_{1}+a_{12}x_{2}+\cdots+a_{1m}x_{m}=0,\\a_{21}x_{1}+a_{22}x_{2}+\cdots+a_{2m}x_{m}=0,\\\cdots\cdots\\a_{n1}x_{1}+a_{n2}x_{2}+\cdots+a_{nm}x_{m}=0.\end{cases}$$
> 则：$\text{向量组 }\alpha_1,\alpha_2,\cdots,\alpha_m\text{线性相关}\Leftrightarrow\text{齐次线性方程组}$
> 即：$$\begin{bmatrix}\alpha_1,\alpha_2,\cdots,\alpha_m\end{bmatrix}\begin{bmatrix}x_1\\x_2\\\vdots\\x_m\end{bmatrix}=x_1\alpha_1+x_2\alpha_2+\cdots+x_m\alpha_m=0$$
> 结论：$\text{其有非零解}\Leftrightarrow r(\boldsymbol{\alpha}_1,\boldsymbol{\alpha}_2,\cdots,\boldsymbol{\alpha}_m)<m$

**解释**
+ 意义： 
	+ 通过此定理将以下三个概念联系在了一起：
	+ 1. 线性相关或线性无关；
	+ 2. 齐次方程组；
	+ 3. 秩；
+ $x_i$
	+ $\left.x_{1}\left(\begin{matrix}a_{11}\\a_{21}\\...\\a_{n1}\end{matrix}\right.\right)+x_{2}\left(\begin{matrix}a_{12}\\a_{22}\\...\\a_{n2}\end{matrix}\right)+\cdots+x_{nn}\left(\begin{matrix}a_{1m_{1}}\\a_{2m_{1}}\\...\\a_{nm}\end{matrix}\right)=0$
	+ $x_i$ 在这里是作为系数存在的；
+ $\begin{bmatrix}\alpha_1,\alpha_2,\cdots,\alpha_m\end{bmatrix}\begin{bmatrix}x_1\\x_2\\\vdots\\x_m\end{bmatrix}=x_1\alpha_1+x_2\alpha_2+\cdots+x_m\alpha_m=0$
	+ 作用： 
		+ 通过这个式子，可以将线性相关、线性无关和方程组的解联系在了一起；
	+ 即：
		+ 1. **线性相关有非零解**；
		+ 2. 当线性相关时，这些向量拼不成 `n` 维空间，即空间维度小于 `m` 的，即 $r(\boldsymbol{\alpha}_1,\boldsymbol{\alpha}_2,\cdots,\boldsymbol{\alpha}_m)<m$
+ 补充： 
	+ $r(\boldsymbol{\alpha}_1,\boldsymbol{\alpha}_2,\cdots,\boldsymbol{\alpha}_m)<m$ 中的数使其真实的约束个数；
	+ 两个约束也就意味着两个自由度；

**补充**：方程组的未知数个数问题 
+ （1）如果 `n<m`：即方程个数小于未知数个数, 则齐次线性方程组 `(*)` 求解时必有**自由未知量**；
+ （2）$n\text{个}n\text{维列向量}a_1,a_2,\cdots,a_n\text{线性相关}\Leftrightarrow\left|a_1,a_2,\cdots,a_n\right|=0$
	+ $\text{线性无关}\Leftrightarrow\left|\alpha_{1},\alpha_{2},\cdots,\alpha_{n}\right|\neq0$ 
	+ 前提：个数和维数相同的情况下；
+ 补充：“瘦瘦高高方程组”和“方方正正方程组”
	+ “瘦瘦高高方程组”：方程组的行数比列数多，但方程组的秩是由列数最大值确定了，因此肯定有多余的方程；
	+ 此时可以将其化成“方方正正的方程组”；
	+ 也有可能变成“胖乎乎方程组”；

##### **定理**： #线性相关定理五
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{向量}\beta\text{可由向量组}a_1,a_2,\cdots,a_s\text{线性表示}$ 
> $\Leftrightarrow$ 非齐次线性方程组：$\left[a_1,a_2,\cdots,a_s\right]\begin{bmatrix}x_1\\x_2\\...s\\x_s\end{bmatrix}=x_1\alpha_1+x_2\alpha_2+\cdots+x_s\alpha_s=\beta$ 有解 
> $\Leftrightarrow r([\alpha_{1},\alpha_{2},\cdots,\alpha_{s}])=r([\alpha_{1},\alpha_{2},\cdots,\alpha_{s},\beta])$；
> 反之：$\text{向量}\beta\text{不能由向量组}a_1,a_2,\cdots,a_s\text{线性表示},则\left[a_1,a_2,\cdots,a_s\right]\begin{bmatrix}x_1\\x_2\\...s\\x_s\end{bmatrix}=x_1\alpha_1+x_2\alpha_2+\cdots+x_s\alpha_s=\beta无解$

**解释**
+ $x_1\alpha_1+x_2\alpha_2+\cdots+x_s\alpha_s=\beta$ 
	+ 存在一组数使得其有解；
+ 补充： 
	+ 系数阵：$r([\alpha_{1},\alpha_{2},\cdots,\alpha_{s}])$
	+ 增广阵：$r([\alpha_{1},\alpha_{2},\cdots,\alpha_{s},\beta])$

##### **定理**： #线性相关定理六 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若向量组 $a_1,a_2,\cdots,a_n$ 中有一部分向量线性相关，则整个向量组也线性相关；
> 其逆否命题：$\text{如果}a_1,a_2,\cdots,a_m\text{线性无关},\text{则其任一部分向量组都线性无关}$

**解释**
+ 部分相关，整体必相关；

##### **定理**： #线性相关定理七 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若一组 n 维向量 $a_1,a_2,\cdots,a_s$ 线性无关，那么把这些向量各任意添加 m 各分量所得到的新向量 `(n+m)维` 组 $a_{1}^{*},a_{2}^{*},\cdots,a_{s}^{*}$ 也是线性无关的； 
> 逆否命题：若一组 n 维向量 $a_1,a_2,\cdots,a_s$ 线性相关，那么把这些向量各任意去掉相同的若干个分量所得到的新向量组是线性相关的； 

**解释**
+ **只要不成比例，就还是线性无关的**；
+ 二维空间中的两个线性无关的二维向量 `->` 三维中的二维平面 `<-` 三维空间中某个方向上的平面 `->` 三维空间中的一个二维子空间；
+ 二维空间中的两个线性无关的二维向量 `->` 二维中的二维平面 `->` 可以组成二维平面中的所有向量；

**补充**：定理总结
+ 部分相关，整体相关；
+ 整体无关，部分无关；
+ 原来无关，延长无关；
+ 原来相关，缩短相关；