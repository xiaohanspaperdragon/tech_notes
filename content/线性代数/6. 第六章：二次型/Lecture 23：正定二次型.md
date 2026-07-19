## 23.1 正定二次型
### 23.1.1 基本概念 
##### **定义**： #正定二次型
> <font color="#ccc1d9">描述：</font> $$n\text{元二次型}f(x_1,x_2,\cdots,x_n)=x^TAx.\text{若对任意的}x=[x_1,x_2,\cdots,x_n]^T\neq0,\text{均有}x^TAx>0,\text{则称}f为正定二次型$$
> 称二次型的对应矩阵 $A$ 为正定矩阵；

**解释**
+ 解释：几何理解 
	+ 比如在二元情况下，在二维坐标系下，正定就是抛面；

##### **定理**： #正定二次型的充要条件 
> <font color="#ccc1d9">描述：</font> 
> $n$ 元二次型 $f=x^\mathrm{T}Ax$ 正定 
> $\Leftrightarrow$ 对任意 $x\neq0$,有 $x^\mathrm{T}Ax>0(定义)$  
> $\Leftrightarrow f$ 的正惯性指数 $p=n$
> $\Leftrightarrow$ 存在可逆矩阵 $D$,使 $A=D^TD$
> $\Leftrightarrow A=E$
> $\Leftrightarrow A$ 的特征值 $\lambda_i>0\left(i=1,2,\cdots,n\right)$
> $\Leftrightarrow A$ 的全部顺序主子式均大于 $0$

**解释**
+ 顺序主子式： 
	+ 一定是主子式，是主子式的一种；
	+ 开头一定是 $a_{11}$，结尾一定是 $a_{kk}$
	+ $$\begin{vmatrix}A_{k}\end{vmatrix}=\begin{vmatrix}a_{11}&a_{12}&\cdots&a_{1k}\\a_{21}&a_{22}&\cdots&a_{2k}\\\vdots&\vdots&&\vdots\\a_{k1}&a_{k2}&\cdots&a_{kk}\end{vmatrix}$$

##### **定理**： #二次型正定的必要条件 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $$\begin{aligned}&\left(1\right)a_{ii}>0\left(i=1,2,\cdots,n\right).\\&\left(2\right)\left|A\right|>0 .\end{aligned}$$

## 23.2 判断正定
**总结**：判断正定的方法
+ 方法一：利用充分条件 - $A$ 的全部顺序主子式均大于 $0$
	+ 如果满足都大于 $0$，则矩阵正定；
+ 方法二：利用特征值，特征值全正、则矩阵正定
+ 方法三：配方法 - 函数配成二次型标准型的格式，看起系数是否都是正的；
+ 方法四：定义法 
	+ 首先进行配方，对函数 $f=(x_1+x_2)^2+(x_1+x_3)^2+(x_2+x_3)^2$ ，这不是配方法；如果配成了这样，往往就是一个不可逆的变换；
	+ 判读：因为是平方和，所以 $f=0$ 的充要条件就是 $\begin{cases}x_{1}+x_{2}=0\\x_{1}+x_{3}=0\\x_{2}+x_{3}=0.\end{cases}$
	+ 其行列式为 $\left|\begin{matrix}1&1&0\\1&0&1\\0&1&1\end{matrix}\right|$
	+ 所以：$x_1=X_2=x_3=0$  
	+ 所以根据定义：$f>0\Leftrightarrow\left(\begin{matrix}x_{1}\\x_{2}\\x_{3}\end{matrix}\right)\neq0$ 

**总结**：证明正定二次型充要条件的步骤
+ （1）先说明 $A^T=A$
+ （2）再用充分条件；
	+ 注意：`q=0` 无法推出来 `p=n` 