## 13.1 基本概念
**概念一**：向量组等价和矩阵等价是两个不同的概念；
+ 矩阵等价要同型，当然行数、列数都要相等； 
+ 向量组等价要同维，但向量个数可以不等；

**概念二**：$A,B\text{同型时},A\cong B\Leftrightarrow r(A)=r(B)\Leftrightarrow PAQ=B(P,Q\text{是可逆矩阵 }).$ 
+ 把一个秩相同的矩阵，化成最简形中的所有矩阵、都是等价的；

**概念三**：向量组同维，则：
+ $\{\alpha_{1},\alpha_{2},\cdots,\alpha_{s}\}\cong\{\beta_{1},\beta_{2},\cdots,\beta_{t}\}$
+ $\Leftrightarrow\left\{\alpha_{1},\alpha_{2},\cdots,\alpha_{s}\right\}\text{与}\left\{\beta_{1},\beta_{2},\cdots,\beta_{t}\right\}\text{可以相互表示}$
+ $\Leftrightarrow r(\alpha_1,\alpha_2,\cdots,\alpha_s)=r(\beta_1,\beta_2,\cdots,\beta_i),\text{且可单方向表示,即只需知}\alpha_1,\alpha_2,\cdots,\alpha_s\text{与}\beta_1,\beta_2,\cdots,\beta_l$ 这两个向量组中的某一个向量组可由另一个向量组线性表示；
+ $\Leftrightarrow r\left(\alpha_{1},\alpha_{2},\cdots,\alpha_{s}\right)=r\left(\beta_{1},\beta_{2},\cdots,\beta_{t}\right)=r\left(\alpha_{1},\alpha_{2},\cdots,\alpha_{s},\beta_{1},\beta_{2},\cdots,\beta_{t}\right)\left(\text{三秩相同 }\right).$