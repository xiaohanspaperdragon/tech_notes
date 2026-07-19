## 17.1 基本概念 
##### **定义**： #两个方程组的公共解
> <font color="#ccc1d9">描述：</font>齐次线性方程组 $A_{m\times n}x=0$ 和 $B_{m\times n}x=0$ 的公共解是满足方程组 $\begin{bmatrix}A\\B\end{bmatrix}x=0$，即联立求解；
> 由此同理，可以求 $Ax=\alpha$ 与 $Bx=\beta$ 的公共解；

**分析**：考察公共解的两种方法
+ 方法一：给出 $Ax=0$ 的基础解系 $\xi_1,\xi_2,\cdots,\xi_s$ 和 $B$ 的具体表达式时；
	+ 步骤一：先求 $Ax=0$ 的通解 $k_1\xi_1,k_2\xi_2,\cdots,k_s\xi_s$
	+ 步骤二：将求得的通解代入 $Bx=0$ 当中，求出：$k_i\quad(i=1,2,3...)$ 之间的关系
	+ 步骤三：将求得的 $k_i$ 的关系代入 $Ax=0$ 的通解当中，得到公共解；
+ 方法二：给出 $Ax=0$ 和 $Bx=0$ 它们两个分别的基础解系 $\xi_1,\xi_2,\cdots,\xi_s$ 与 $\eta_1,\eta_2,\cdots,\eta_1$；
	+ 步骤一：求公共解，$\gamma=k_{1}\xi_{1}+k_{2}\xi_{2}+\cdots+k_{s}\xi_{s}=l_{1}\eta_{1}+l_{2}\eta_{2}+\cdots+l_{1}\eta_{t}$
	+ 步骤二：将解系相减、移到左边，得到 $k_{1}\xi_{1}+k_{2}\xi_{2}+\cdots+k_{s}\xi_{s}-l_{1}\eta_{1}-l_{2}\eta_{2}-\cdots-l_{t}\eta_{t}=0$
	+ 步骤三：求出 $\text{}k_{i}\text{或}l_{j}, i=1,2,\cdots, s; j=1,2,\cdots, t,\text{即可求出}\gamma$