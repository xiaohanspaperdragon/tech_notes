## 20.1 矩阵相似 
### 20.1.1 相似矩阵的定义
##### **定义**： #矩阵相似 
> <font color="#ccc1d9">描述：</font>设 A, B 是两个 `n` 阶方阵，若存在 `n` 阶可逆矩阵 `P`，使得 $P^{-1}AP=B$，则称 `A` 相似于 `B`，记成 `A~B`

**解释**
+ 概念： 
	+ 如果假设都是方阵；
		+ 等价矩阵： `PAQ=B` ``<-`` 同型矩阵：P 和 Q 两个矩阵没有关系；
		+ 相似矩阵：$P^{-1}AP=B$ `<-` 等价矩阵：P 和 P 逆，两者夹击产生的效果得到 `B` ；
	+ `->` 所以相似的矩阵肯定也是等价的矩阵
+ 公式： 
	+ `A~A`：反身性
	+ 若 `A~A`，则 `B~A`：对称性
	+ 若 `A~B,B~C`，则 `A~C`：传递性 `->` 证明 `A~C`，可以先求 A 到 B、再求 B 到 C，也就得到了 A 到 C； 
+ 补充： 
	+ 所有的矩阵，都有一个最理想的矩阵和其相似 `<->` 传递性；

**补充**：相似矩阵与 $A^{-1}MA$
+ 意义： 
	+ $A^{-1}MA$ 表达式暗示着数学上的转移作用；
	+ 中间的矩阵代表了一种你见过的变换，外侧的两个矩阵代表转移作用，也就是视角的上的变换；
	+ 矩阵乘积仍然代表着**同一个变换**，只不过是从其他人的角度来看的 `->` 矩阵 `A` 和 `B` 相似，但基向量不同；
+ 图示： 
	+ ![[Pasted image 20240629194927.png]]

### 20.1.2 相似矩阵的性质
**概念**：相似矩阵的六大性质
+  $$\begin{aligned}
&{1}.\quad\left|A\right|=\left|B\right| \\
&{2}.\quad r\left(A\right)=r\left(B\right). \\
&{3}.\quad tr\left(A\right)=tr\left(B\right). \\
&{4}.\quad\lambda_{A}=\lambda_{B}\left(或\left|\lambda E-A\right|=\left|\lambda E-B\right|\right). \\
&{5}.\quad r\left(\lambda E-A\right)=r\left(\lambda E-B\right). \\
&{6}.\quad A,B的各阶主子式之和分别相等。
\end{aligned}$$
+ 注意： 
	+ 以上六条条件是矩阵相似的必要条件，只要其中一个不满足，则两个矩阵不相似；
	+ 但是，即使 `1~6` 全成立，也不能说 `A` 相似于 `B`；
+ 补充： 
	+ 概念： 
		+ 在进行相似变换时，其不变量是"各阶主子式之和"；
	+ 举例： 
		+ $A=\begin{bmatrix}1&1&0\\0&1&1\\1&0&1\end{bmatrix}$，其二阶主子式之和为 $A_{11}+A_{22}+A_{33}=1+1+1=3$
		+ $B=\begin{bmatrix}1&1&-1\\0&1&0\\1&0&1\end{bmatrix}$，其二阶主子式之和为 $\widetilde{A}_{11}+\widetilde{A}_{22}+\widetilde{A}_{33}=1+2+1=4$
		+ 故 A 和 B 不相似；

### 20.1.3 相似矩阵的重要结论 
**概念**：结论一
+ $$若A\sim B,则A^{k}\sim B^{k},f\left(A\right)\sim f\left(B\right)\left(\text{其中}f\left(x\right)\text{是多项式}\right)$$

**概念**：结论二
+ $$若A\sim B,且A可逆,则A^{-1}\sim B^{-1},f\left(A^{-1}\right)\sim f\left(B^{-1}\right)\left(\text{其中}f\left(x\right)\text{是多项式}\right)$$

**概念**：结论三
+ $$若A\sim B,且A可逆,则A^*\sim B^*$$

**概念**：结论四
+ $$若A\sim B,且A可逆,则A^T\sim B^T$$

**概念**：结论五
+  $$若A\sim C,B\sim D,则\begin{bmatrix}A&O\\O&B\end{bmatrix}\sim\begin{bmatrix}C&O\\O&D\end{bmatrix}$$

**分析**：结论 `1~3`
+ 因为从 A `->` B 的手段，在 `1~3` 当中是一致的，所以它们的组合：$aA^{*}+bA^{-1}+cf\left(A\right)$ 加上 $P^{-1}$ 和 $P$ 后：
+ $$P^{-1}(aA^{*}+bA^{-1}+cf\left(A\right))P=aB^{*}+bB^{-1}+cf\left(B\right)$$

**分析**：结论 `4`
+ $A\sim B,则存在可逆矩阵P,使得P^{-1}AP=B,两边取转置,有P^TA^T(P^{-1})^T=B^T$
+ $P^{T}A^{T}\left(P^{T}\right)^{-1}=B^{T},故A^{T}\sim B^{T}.由此可知，$ $A^{\mathrm{T}}与B^{T}相似的手段与(1)\sim(3)不同.$

### 20.1.4 两个矩阵相似的判别与证明
**方法**：定义法 
+ $\text{若存在可逆矩阵}P,\text{使得}P^{-1}AP=B,\text{则}A\sim B.$

**方法**：利用传递性
+ 若 `A~V`，`V~B`，则 `A~B`

**方法**：使用性质 
+ 使用性质只能否定 A、B 的相似性，不能证明其相似；
+ 补充： 
	+ 可在 A~B 的条件下, 用性质反求参数, 但如前所述, 所有的性质都只是 A~B 的必要条件

## 20.2 矩阵的相似对角化
### 20.2.1 基础概念 
##### **定义**： #矩阵的相似对角化
> <font color="#ccc1d9">描述：</font> 设 `n` 阶矩阵 `A`，若存在 `n` 阶可逆矩阵 `P`，使得 $P^{-1}AP=\Lambda$，则其中的 $\Lambda$ 是对角矩阵，并且称 `A` 可相似对角化，记作 $A\sim\Lambda$，并称 $\Lambda$ 为 `A` 的相似标准型；
> `A` 可以相似对角化、最本质的定义是：`A` 有 `n` 个线性无关的特征向量； 

**概念**：图形解释
+ ![[Pasted image 20240701202326.png]]

**概念**：相似对角化的条件 - 结论一
+ `->` 假设：A 可以相似对角化
+ `->` 存在可逆矩阵 P ，使得 $P^{-1}AP=\Lambda$
+ `->` 存在可逆矩阵 $P=(\xi_1,\xi_2)$，使得 $AP=P\Lambda$
+ `->` 存在可逆矩阵 $P=(\xi_1,\xi_2)$，使得 $A(\xi_1,\xi_2)=(\xi_1,\xi_2)\Lambda$
+ `->` 存在可逆矩阵 $P=(\xi_1,\xi_2)$，使得 $(A\xi_1,A\xi_2)=(\lambda\xi_1,\lambda\xi_2)$
+ `->` 存在可逆矩阵 $P=(\xi_1,\xi_2)$，使得 $A\xi_i=\lambda\xi_i$
+ `->` 所以得到特征值和特征向量：$A\xi_i=\lambda\xi_i$ 
+ `->` 组成 P 的列向量就是特征向量
+ `->` 结论：
	+ 1. `A` 有 `n` 个线性无关的特征向量；
	+ 2. $P=[\xi_1, \xi_2, \cdots, \xi_n]$
	+ 3. $\Lambda=\begin{bmatrix}\lambda_1&&&&\\&\lambda_2&&&\\&&\ddots&&\\&&&\lambda_n\end{bmatrix}$
	+ 4. $$P^{-1}AP=\Lambda \quad\quad\rightarrow\quad\quad [\xi_1, \xi_2, \cdots, \xi_n]^{-1}A[\xi_1, \xi_2, \cdots, \xi_n]=\begin{bmatrix}\lambda_1&&&&\\&\lambda_2&&&\\&&\ddots&&\\&&&\lambda_n\end{bmatrix}$$
+ 这是充要条件；

**概念**：相似对角化的条件 - 结论二
+ 结论：如果 `n` 阶矩阵 `A` 可以相似对角化 $\rightarrow$ $A$ 对应于每个 $k_i$ 重特征值都有 $k_i$ 个线性无关的特征向量；
+ 这是充要条件；

**概念**：相似对角化的条件 - 结论三
+ 结论：如果 `n` 阶矩阵 `A` 有 n 个不同特征值 $\rightarrow$ A 可以相似对角化； 
+ `->` 全都是单根，自带线性无关，所以可以相似对角化；
+ 这是充分条件

**概念**：相似对角化的条件 - 结论四
+ 结论：如果 `n` 阶矩阵 `A` 为实对称矩阵 $\rightarrow$ A 可以相似对角化； 
+ 这是充分条件

**概念**：其他相似的重要结论
+ 结论 - 如果 $A\sim\Lambda$，则 $P$ 中的每一列、都是 `A` 矩阵的特征向量，并且这些特征向量必然是线性无关的；
+ 结论 - 如果 $A\xi_i=\lambda_i\xi_i$，$\xi_i(i=1,2,3)$ 构成 $\Lambda$，则 $A\sim\Lambda$
+ 结论：自产自销 
	+ 只要给出一个矩阵 A，其满足有 $\lambda$ 以及 $\xi$，并且其有 n 个线性无关的特征向量，则 $P^{-1}AP=\Lambda$，$P=(\xi_1,\xi_2...\xi_n)$

### 20.2.2 相似对角化的求解
**方法**：基于 $P^{-1}AP=\Lambda$，求 `P` 步骤
+ 步骤： 
	+ 1. 因为 $|\lambda E-A|=0$ ，写出行列式 $|\lambda E-A|$，求出 $A$ 的 $\lambda_1,\lambda_2,\lambda_3,...\lambda_i$
	+ 2. 求：对应的 $\lambda_1,\lambda_2,\lambda_3,...\lambda_i$ 下时，`A` 的阶梯型矩阵，并由此求出 `A` 的特征向量 $\xi_1,\xi_2...\xi_i$
	+ 3. 根据特征向量与特征值的性质，判断当前特征向量是否是 `n` 个线性无关的向量，如果是的话，把解出的 $\xi_i$ 拼在一起得到 $P$：
		+ $P^{-1}AP=\Lambda=\begin{bmatrix}\lambda_1&&&&\\&\lambda_2&&&\\&&\ddots&&\\&&&\lambda_n\end{bmatrix}$
+ 注意： 
	+ $\text{需要注意的是,}P\text{中特征向量}\boldsymbol{\xi}_i\text{与}A\text{中特征值}\lambda_i\text{对应,且}P\text{没有唯一性 }.$

**方法**：由特征值、特征向量反求 $A$ 
+ 方法： 
	+ $\text{若有可逆矩阵}P\text{,使得}P^{-1}AP=A\text{,则}A=PAP^{-1}\text{,这是反求}A\text{ 的一个基本思路 }.$
+ 举例： 
	+ `->` $(\xi_{1},\xi_{2})^{-1}A(\xi_{1},\xi_{2})=(\begin{matrix}\lambda_{1}&0\\0&\lambda_{2}\end{matrix})$
	+ `->` $A=(\xi_{1},\xi_{2})(\begin{matrix}\lambda_{1}&0\\0&\lambda_{2}\end{matrix})(\xi_{1},\xi_{2})^{-1}$

**方法**：求 $A^k$ 和 $f(A)$
+ `->` $$P^{-1}A^kP=A^k, A^k=PA^kP^{-1}=P\begin{bmatrix}\lambda_1^k&&&&\\&\lambda_2^k&&&\\&&\ddots&&\\&&&\lambda_n^k\end{bmatrix}P^{-1}$$
+ `->` $$P^{-1}f(A)P=f(A), f(A)=Pf(A)P^{-1}=P\begin{bmatrix}f(\lambda_1)&&&\\&f(\lambda_2)&&\\&&\ddots&\\&&&f(\lambda_n)\end{bmatrix}P^{-1}.$$

**补充**：在可逆矩阵中使用不可逆矩阵的性质
+ 若 $|A|=0\rightarrow|0·E+A=0|\rightarrow\lambda_1=0\quad(至少一个)\rightarrow A不可逆$
	+ $|A^{*}|\rightarrow |A|^{n-1}$ 这个是由 $A^{-1}$ 存在而推出来的；
+ 其他： 
	+ $|A^{*}|=|A|^{n-1}$ 的前提是 `A` 可逆；
	+  的前提是 A 可逆；$\left(AB\right)^{*}=B^{*}A^{*}$ 的前提是 `A,B` 可逆； 
+ 不可逆时： 
	+ 假设 A 有三重根，一个特征值 `1`；
	+ 如果现在在 A 前面加上 E：`+E+A`；
	+ 所以：$|(tE+A)^{*}|=|tE+A|^{n-1}.$
	+ 当 $t\rightarrow 0^+$，原来的 t 特征值一定不 `0`，都是关于 t 的连续函数 `->` $|A^{*}|=|A|^{n-1}$；
+ 即：$|A^{*}|=|A|^{n-1}$ 对于可逆、不可逆都是成立的；
### 20.2.3 举例
**例题**：一下选项中哪些不能相似于对角矩阵：
+ 题目： 
	+ $$\begin{aligned}\left(A\right)A=&\begin{bmatrix}0&0&1\\0&1&0\\1&0&0\end{bmatrix}&(\mathbf{B}) \boldsymbol{B}=&\begin{bmatrix}1&1&1\\0&2&2\\0&0&3\end{bmatrix}\\(\mathbf{C})\boldsymbol{C}=&\begin{bmatrix}1&-2&1\\2&-4&2\\1&-2&1\end{bmatrix}&(\mathbf{D})\boldsymbol{D}=&\begin{bmatrix}2&-1&2\\5&-3&3\\-1&0&-2\end{bmatrix}\end{aligned}$$
+ 分析
	+ A 很明显对称，所以 A 相似于对角矩阵；
	+ B 有明显的台阶，并且刚好是三个互不相同的特征值，所以如果三个单根分别对应特征值，所以一定相似对角化；
	+ C 是一个秩一矩阵，所以一个两重跟，一个单根，需要分别判断他们对应的特征向量个数。而 C 选项的重根数等于其线性无关特征向量个数，所以 C 相似于对角矩阵； 
+ 解析



## 20.3 实对称矩阵的相似对角化 
### 20.3.1 实对称矩阵 
##### **定义**： #实对称矩阵
> <font color="#ccc1d9">描述：</font>若 $A^T=A$ ，则 A 为对称矩阵。如果组成 A 的元素都是实数，则 A 为实对称矩阵；
> （1）`A` 是实对称矩阵，则 A 的特征值是实数，特征向量是实向量 (不用证明)；
> （2）实对称矩阵 `A` 的属于不同特征值的特征向量相互正交，即：$A\begin{cases}\lambda_{1}\neq\lambda_{2}\Rightarrow\xi_{1}\perp\xi_{2},\\\lambda_{1}=\lambda_{2}\xrightarrow{可能}\begin{cases}\xi_{1}\perp\xi_{2},\\\xi_{1}与\xi_{2}无关\end{cases}\end{cases}$
> （3）对于任意的 n 阶实对称矩阵 A，存在 n 阶正交矩阵 Q，使得：$Q^{\mathrm{T}}AQ=Q^{-1}AQ=\begin{bmatrix}\lambda_1&&&\\&\lambda_2&&\\&&\ddots&\\&&&\lambda_n\end{bmatrix}$ ，这里 $\lambda_i$ 是 A 的全部特征值； 

**解释**
+ 解释（2）：
	+ 对于实对称矩阵，无论其特征值是否相等，$\xi$ 都是线性无关 `->` **因此实对称矩阵，一定可以相似对角化**；
+ 解释（3）： 
	+ 回顾：A 有 n 个线性无关 `->` A~$\Lambda$ `->`  $[\xi_1, \xi_2, \cdots, \xi_n]^{-1}A[\xi_1, \xi_2, \cdots, \xi_n]=\begin{bmatrix}\lambda_1&&&&\\&\lambda_2&&&\\&&\ddots&&\\&&&\lambda_n\end{bmatrix}$
	+ 对称矩阵因为无条件就可以得到 $A\sim\Lambda$，因此就一定可以得到 $[\xi_1, \xi_2, \cdots, \xi_n]^{-1}A[\xi_1, \xi_2, \cdots, \xi_n]=\begin{bmatrix}\lambda_1&&&&\\&\lambda_2&&&\\&&\ddots&&\\&&&\lambda_n\end{bmatrix}$ 这种局面；
	+ 并且对称矩阵还能得到 $[\xi_1, \xi_2, \cdots, \xi_n]^{T}A[\xi_1, \xi_2, \cdots, \xi_n]=\begin{bmatrix}\lambda_1&&&&\\&\lambda_2&&&\\&&\ddots&&\\&&&\lambda_n\end{bmatrix}$ 这种局面；
+ 补充：正交矩阵 
	+ $Q^T=Q^{-1}$
	+ $Q^TQ=E$
	+ `Q` 由标准正交基组成 `<-` 可以通过正交化、单位化，来得到正交矩阵；
	+ 不存在正交阵使得 $Q^TAQ=\Lambda$ 

### 20.3.2 实对称矩阵相似对角化基本步骤 
**方法**：若 A 为 n 阶实对称矩阵，则其用正交矩阵 Q 相似对角化的基本步骤如下：
+ $$\begin{aligned}&\left(1\right)\text{求}A\text{的特征值}\lambda_1,\lambda_2,\cdots,\lambda_n.\\&\left(2\right)\text{求}A\text{的对应于特征值}\lambda_1,\lambda_2,\cdots,\lambda_n\text{的特征向量}\xi_1,\xi_2,\cdots,\xi_n.\\&\left(3\right)\text{将}\xi_{1},\xi_{2},\cdots,\xi_{n}\text{正交化(若需要的话)、单位化为}\eta_{1},\eta_{2},\cdots,\eta_{n}.\\&\left(4\right)\text{令}Q=\left[\eta_{1},\eta_{2},\cdots,\eta_{n}\right],\text{则}Q\text{为正交矩阵,且}Q^{-1}AQ=Q^{\mathrm{T}}AQ=A\end{aligned}$$