## 7.1 初等变换 
### 7.1.1 定义 
##### **定义**： #初等变换 
> <font color="#ccc1d9">描述：</font>
>(1)倍乘：一个非零常数乘矩阵的某一行 (列);
  (2)互换：互换矩阵中某两行 (列)的位置;
  (3)倍加：将矩阵的某一行 (列)的 k 倍加到另一行 (列).
  以上三种变换称为矩阵的初等行 (列)变换，且分别称为倍乘、互换、倍加初等行 (列) 变换；

**解释**
+ 这三种变换都被称之为 **同解变换** `<-` 无论怎么变换，必须要保证是同解的；

**本质**：矩阵的秩不变，但行列式发生变化；

### 7.1.2 补充：线性变换的本质 
**概念**：什么是变换
+ 解释： 
	+ 变换本质上是“函数”的一种花哨说法，接受一个向量，并输出一个向量变换的结果；
+ 变换：
	+ 使用变换一词，是在暗示你基于“运动”的视角去思考；

**概念**：什么是线性的变换
+ 线性的变换需要具有以下两个性质： 
	+ 1. 直线再变换后依然维持为直线，不能有弯曲；
	+ 2. 原点必须保持固定； 
+ 什么是线性变换： 
	+ 线性变换是操作空间的一种手段，它它保持网格线平行且等距分布，并且保持原点不动，并且可以通过矩阵来描述清楚；

**概念**：如何描述变换后的向量空间
+ 只需要对基变量进行变换即可；
+ 因为：假设当前向量被两个基向量表示：
	+ $$\vec{\mathbf{v}}=-1\hat{i}+2\hat{j}$$
	+ 此时即使对基向量进行变换，以上的线性关系依然不会发生变换；
	+ 因此可以只根据变换后的 `i` 帽和 `j` 帽就推断出变换后的 `v`；
	+ 其中 i 是两个坐标的数值构成的二维向量，j 是另一个两个坐标的数值构成的二维向量；
+ 引入矩阵： 
	+ 把基向量 `i` 和基向量 `j` 合在一起，就构成了一个 `2*2` 矩阵：

**概念**：矩阵的意义
+ 意义： 
	+ 给定了一个任意的初始向量，可以通过两个基，进行线性变换、得到其线性变换后的结果；
	+ $$\begin{aligned}\begin{bmatrix}3&2\\-2&1\end{bmatrix}&\underbrace{{\left[\begin{array}{c}5\\7\end{array}\right]}}\\&\text{Any ol' vector}\\&\text{任意初始向量}\end{aligned}$$
+ 举例： 
	+ $$\begin{aligned}\begin{bmatrix}3&2\\-2&1\end{bmatrix}{{\left[\begin{array}{c}5\\7\end{array}\right]}}\end{aligned}=5\bigg[\begin{array}{c}3\\-2\end{array}\bigg]+7\bigg[\begin{array}{c}2\\1\end{array}\bigg]\leftarrow等同于缩放基向量再相加$$
+ 公式：二维
	+ $$\left.\left[\begin{array}{cc}a&b\\c&d\end{array}\right.\right]\left[\begin{array}{c}x\\y\end{array}\right]=x\left[\begin{array}{c}a\\c\end{array}\right]+y\left[\begin{array}{c}b\\d\end{array}\right]=\left[\begin{array}{c}ax+by\\cx+dy\end{array}\right]$$

## 7.2 初等矩阵
### 7.2.1 初等矩阵的定义 
##### **定义**： #初等矩阵的定义
> <font color="#ccc1d9">描述：</font>由单位矩阵经过一次初等变换得到的矩阵称为**初等矩阵**. 以 3 阶矩阵为例：$E_{2}\left(k\right)=\left[\begin{matrix}1&0&0\\0&k&0\\0&0&1\end{matrix}\right]$
> E 的第 `2` 行 (或第 2 列)乘 `k` 倍，称为倍乘初等矩阵；
> 
> 定义：$E_i(k)(k\neq 0)$ 表示单位矩阵正的第 $i$ 行 (或者第 $j$ 列)乘以非零常数 $k$ 所得的初等矩阵

**解释**
+ 补充：单位矩阵的作用
	+ 单位矩阵的特点，是作用在任何矩阵上时、其没有任何实质的作用；
	+ 即： `EA=A`
+ 注意：
	+ 变换一定是行列都可以变换的；
+ 概念：
	+ 左乘：在向量的左边进行变换 `->` 左读行变换；
	+ 右乘：在向量的右边进行变换 `->` 右读列变换；
		+ 对研究对象相对在其右边；`(x)g`
+ 作用：
	+ 用一个初等矩阵变化一个向量组时， 

##### **定理**： #左行右列定理 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>对 `n` 阶矩阵 `A` 进行初等行变换，相当于在矩阵 A 的左边乘相应的初等矩阵；
> 同样，对 `A` 进行初等变换，相当于在矩阵 `A` 的右边乘以相对应的初等矩阵；

**解释**

### 7.2.2 互换初等矩阵 
##### **定义**： #互换初等矩阵
> <font color="#ccc1d9">描述：</font> $E_{12}=\begin{bmatrix}0&1&0\\1&0&0\\0&0&1\end{bmatrix}$，E 的第 1、2 行（或 1、2 列）互换，称为互换初等矩阵；
> 定义：$$E_{ij}\text{表示单位矩阵}E\text{交换第}i\text{ 行与第}j\text{行}(\text{或交换第}i\text{列与第}j\text{列})\text{所得的初等矩阵}$$

**解释**
+ 概念：
	+ 做行变换：放到左边去
		+ $\left.\left(\begin{matrix}0&1\\1&0\end{matrix}\right.\right)\left(\begin{matrix}1&2\\3&4\end{matrix}\right)=\left(\begin{matrix}3&4\\1&2\end{matrix}\right)$
	+ 做列变换：放到右边去
		+ $\left.\left(\begin{matrix}1&2\\3&4\end{matrix}\right.\right)\left(\begin{matrix}0&1\\1&0\end{matrix}\right)=\left(\begin{matrix}2&1\\4&3\end{matrix}\right)$
+ 举例：
	+ $$\begin{pmatrix}1&2&-4\\2&3&2\\-1&-2&0\end{pmatrix}\begin{pmatrix}1&0&0\\0&0&1\\0&1&0\end{pmatrix}=\begin{pmatrix}1&-4&2\\2&3&3\\-1&0&-2\end{pmatrix}$$
	+ 因为初等矩阵在右边，所以是进行列变换；
	+ 因为初等矩阵的第二列和第三列互换，所以 $\begin{pmatrix}1&2&-4\\2&3&2\\-1&-2&0\end{pmatrix}$ 的第二列、第三列互换；

### 7.2.3 倍加初等矩阵 
##### **定义**： #倍加初等矩阵
> <font color="#ccc1d9">描述：</font> $E_{31}\left(k\right)=\left[\begin{matrix}1&0&0\\0&1&0\\k&0&1\end{matrix}\right]$，E 的第 1 行的 k 倍加到第 3 行 (或第 3 列的 k 倍加到第 1 列)，称为倍加初等矩阵；
> 定义：$E_{ij}(k)$ 表示单位矩阵 $E$ 的第 $j$ 行的 $k$ 倍加到第 $i$ 行 (或第 $i$ 列的 $k$ 倍加到第 $j$ 列)所得的初等矩阵；

**解释**

## 7.3 初等矩阵的性质 
**性质一**：初等矩阵的转置依然是初等矩阵
+ $E_{ij}^{T}=E_{ij}$
+ $E_{i}^{T}\left(k\right)=E_{i}\left(k\right)$
+ $E_{ij}^{T}\left(k\right)=E_{ji}\left(k\right)$

**性质二**：行列式、逆矩阵与初等矩阵 
+ 因为 $\left|E_{i}\left(k\right)\right|=k\neq0,\left|E_{ij}\right|=-1\neq0,\left|E_{ij}\left(k\right)\right|=1\neq0$
+ 故初等矩阵都是可逆矩阵，且 $\left[E_{i}\left(k\right)\right]^{-1}=E_{i}\left(\frac{1}{k}\right),E_{ij}^{-1}=E_{ij},\left[E_{ij}\left(k\right)\right]^{-1}=E_{ij}\left(-k\right)$ 其逆矩阵仍是同一类型的初等矩阵；

**性质三**：若 `A` 是可逆矩阵，则 `A` 可以表示成有限个初等矩阵的乘积，即 $A=P_{1}P_{2}\cdots P_{s},\text{其中}P_{1},P_{2},\cdots,$ $P_s$ 是初等矩阵；
+ 若 A 是可逆矩阵，则 A 矩阵肯定可以分解成若干个初等矩阵的乘积；
+ 所以说：初等矩阵其实就是多个矩阵的复合，比如 $A\alpha=p_{1}p_{2}\cdots p_{s}\alpha$ ；
+ 若 $A=P_{1}P_{2}\cdots P_{s}$ ，两边都是乘以 P 的逆矩阵，则右边就是 `E`；
	+ 得到：$P_{S}^{-1}\cdots P_{2}^{-1}P_{1}^{-1}A=P_{S}^{-1}\cdots P_{2}^{-1}P_{1}^{-1}P_{1}P_{2}\cdots P_{S}$ 
	+ 得到：$\theta_{5}\cdots\theta_{2}\theta_{1}E=A^{-1}$
+ 公式：
	+ $\begin{aligned}Q_{5}\cdots Q_{2}Q_{1}\cdot A=E\\Q_{5}\cdots Q_{2}Q_{1}E=A^{-1}\end{aligned}$
+ 结论：
	+ $(A|E)\xrightarrow{行}(E|A^{-1})$
	+ 给 A 拼上一个 E，进行行变换，得到的就是 A 逆矩阵；

**性质四**：对 `n` 阶矩阵 `A` 进行初等行变换，相当于在矩阵 `A` 的左边乘相应的初等矩阵；同样，对 `A` 进行初等列变换，相当于在矩阵 `A` 的右边乘相应的初等矩阵； 


## 7.4 行阶梯形矩阵与行最简阶梯形矩阵
### 7.4.1 行阶梯形矩阵
##### **定义**： #行阶梯形矩阵 
> <font color="#ccc1d9">描述：</font>具有如下特征的矩阵称为行阶梯形矩阵：
> ① 若有零行 (即元素全为零的行)，则零行全都位于非零行的下方；
> ② 各非零行左起第一个非零元素的列指标由上至下是严格增大的 `->` 解；

**解释**
+ 目标：
+ 概念：
	+ 将方程组进行变换，但进行的都是同解变换；
	+ 因为下面一行比上面一行的零的数量肯定更多 `->` 下面一行的自变量的数量更小；
+ 举例：
	+ $$\rightarrow\begin{bmatrix}1&1&0&-3&-1\\0&-2&2&2&1\\0&0&0&3&-1\\0&0&0&0&0\end{bmatrix}=B$$
+ 台脚：
	+ 每个台阶的最左边的元素称之为台脚 `->` 将其化成最简形式；

**举例**：求齐次线性方程组的通解：$\begin{cases}x_{1}+x_{2}-3x_{4}-x_{5}=0,\\x_{1}-x_{2}+2x_{3}-x_{4}=0,\\4x_{1}-2x_{2}+6x_{3}+3x_{4}-4x_{5}=0,\\2x_{1}+4x_{2}-2x_{3}+4x_{4}-7x_{5}=0\end{cases}$

### 7.4.2 行最简阶梯型梯形矩阵
##### **定义**： #行最简阶梯型梯形矩阵
> <font color="#ccc1d9">描述：</font>一个行阶梯形矩阵称为行最简阶梯形矩阵，如果其非零行的第一个非零元素为 `1`，并且这些非零元素所在列的其他元素均为 `0`；

**解释**
+ 和行列式的区别：$其非零行的第一个非零元素为1$
+ 特征：
	+ 1. 若有零行，全在下方；
	+ 2. 各非零行左起第一个非零元素的列指标由上至下是严格增大的
	+ 3. 台脚处的元素必须是 `1`；
	+ 4. 台脚正上方的元素必须都是 `0`；
+ 作用：
	+ 服务于解方程组；
	+ 一般化成行阶梯形矩阵就可以了；

**补充**：对于任何非零矩阵 `A`，总可以经过有限次初等行变换把它化为行阶梯形矩阵和行最简阶梯形矩阵；
+ 单位矩阵是最标准的行阶梯形矩阵；
+ 线性方程组总是可以进行消元代入；
+ 一般化为行阶梯形矩阵就可以了；

## 7 .5 用初等变换求逆矩阵 
##### **定理**： #用初等变换求逆矩阵
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\begin{bmatrix}A\vdots E\end{bmatrix}\xrightarrow{\text{初等行变换}}\begin{bmatrix}E\vdots A^{-1}\end{bmatrix},\\\begin{bmatrix}A\\E\end{bmatrix}\xrightarrow{\text{初等列变换}}\begin{bmatrix}E\\A^{-1}\end{bmatrix}.$$

**例题**：当 $A=\begin{bmatrix}0&2&-1\\1&1&2\\-1&-1&-1\end{bmatrix}$，求 $A^{-1}$ 
+ 分析
	+ $\left.\left(A|E\right)=\left(\begin{matrix}0&2&-1&1&0&0\\1&1&2&0&1&0\\-1&-1&-1&-1&0&0&1\end{matrix}\right.\right)$
	+ 然后 A、E 矩阵各自都第一行、第二行互换位置
	+ 然后第一行加到第三行：$\left.\left(\begin{matrix}1&1&2&1&0\\0&2&-1&1&1&0&0\\0&0&1&0&1&1\end{matrix}\right.\right)->\begin{bmatrix}1&1&0&-3&-1\\0&1&-1&-1&-\frac{1}{2}\\0&0&0&1&-\frac{1}{3}\\0&0&0&0&0\end{bmatrix}$
	+ 最后拼成 $(E|A^{-1})$ 的形式
+ 解析

## 7.6 简单分块矩阵的逆
##### **定义**： #简单分块矩阵的逆
> <font color="#ccc1d9">描述：</font> $$\begin{bmatrix}A&O\\O&B\end{bmatrix}^{-1}=\begin{bmatrix}A^{-1}&O\\O&B^{-1}\end{bmatrix},\begin{bmatrix}O&A\\B&O\end{bmatrix}^{-1}=\begin{bmatrix}O&B^{-1}\\A^{-1}&O\end{bmatrix}$$

**解释**
+ 注意： 
	+ $\begin{bmatrix}O&A\\B&O\end{bmatrix}^{-1}$ 求逆矩阵后，要对调； 
+ 证明：       
	+ $\left.\left(\begin{matrix}0&A\\B&0\end{matrix}\right.\right)\left(\begin{matrix}0&B^{-1}\\A^{-1}&0.\end{matrix}\right)=E$

**补充**：求副对角线上分块矩阵的，可推广如下
+ 主对角线时，不用反过来写，副对角线的需要反过来写：
+ $$A=\begin{bmatrix}&&&A_{1}\\&&A_{2}\\&&\cdots\\A_{s}\end{bmatrix}\xrightarrow{\text{ }}A_{i}(i=1,2,\cdots,s)可逆，则A可逆，且\rightarrow A^{-1}=\begin{bmatrix}&&&&A_s^{-1}\\&&&\ddots\\&&A_2^{-1}&&\\A_1^{-1}&&&&\end{bmatrix}$$

**补充**：分块三角阵
+ 举例：$\text{已知}A=\begin{bmatrix}B&O\\D&C\end{bmatrix},\text{ 其中 }B\text{ 是}r\times r\text{ 可逆矩阵, }C\text{是}s\times s\text{ 可逆矩阵,证明}A\text{ 可逆,并求}A^{-1}$
	+ $|A|=|\begin{matrix}B&0\\D&C\end{matrix}|=|B||C|\neq0$
	+ 定义法：$\begin{pmatrix}B&0\\D&C\end{pmatrix}\begin{pmatrix}X&Y\\Z&W\end{pmatrix}=\begin{pmatrix}E&0\\0&E\end{pmatrix}$
+ 结论：
	+ 得到 A 的逆矩阵： $\begin{pmatrix}B&0\\D&C\end{pmatrix}$ 的逆矩阵：$\left(\begin{matrix}B^{-1}&0\\-C^{-1}DB^{-1}&C^{-1}\end{matrix}\right)$
+ 补充： 
	+ 右上三角也类似，右上角是 $B^{-1}DC^{-1}$ 
	+ 右下三角也类似，其 `B` 和 `C` 要换位置后取逆，然后左上角是 $C^{-1}DB^{-1}$ 
	+ 左下三角也类似，其 `B` 和 `C` 要换位置后取逆，然后右下角是 $B^{-1}DC^{-1}$ 