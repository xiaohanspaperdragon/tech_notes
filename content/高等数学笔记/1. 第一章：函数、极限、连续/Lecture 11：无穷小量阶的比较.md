---
title: Lecture 11：无穷小量阶的比较
tags:
  - 数学
  - 无穷小
categories: 
date: 2024-03-11
---
---
## 11.1 无穷小量阶比较例题
**例题**：$\text{当 }x\to0\text{ 时},\alpha(x)=kx^2\text{与}\beta(x)=\sqrt{1+x\arcsin x}-\sqrt{\cos x}\text{ 是等价无穷小,则 }k=\_\_\_\_\_\_.$
+ 分析
	+ 因为是等价无穷小，所以之比是 1；
	+ **碰到根式差，所以可以考虑用分子有理化、等价代换方法**；
	+ $=\frac1k\lim_{x\to0}\frac{1+x\arcsin x-\cos x}{x^2[\sqrt{1+x\arcsin x}+\sqrt{\cos x}]}$（有理化）
	+ $=\frac1{2k}\lim_{x\to0}\frac{1+x\arcsin x-\cos x}{x^2}$
	+ 然后拆分，提出；
+ 解析
+ 题型： #无穷小 

**两个等价无穷小的更通用形式**
+ $\log^{a}(1+2x)\sim(2x)^{a}=2^{a}x^{a}$
+ $(1-ax)^{\frac{1}{\alpha}}\sim(\frac{1}{2}x^{2})^{\frac{1}{\alpha}}$

**无穷小阶数排序问题**
+ 方法一：两两比较；
+ 方法二：对每一个进行定阶数；
	+ 比如：$\alpha_1=x(\cos\sqrt{x}-1),\alpha_2=\sqrt{x}\ln(1+\sqrt[3]{x}),\alpha_3=\sqrt[3]{x+1}-1.$ 当 $x\to0^+$ 时，以上 3 个无穷小量从低阶到高阶的排序是；
	+ 可以对 a 1 a 2 a 3 分别定阶数，然后排序；
