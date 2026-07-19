---
title: C语言初学笔记T2
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - C语言
created: 2025-04-15
modified: 2025-08-05
draft: false
description: C语言初学笔记
---


>[!important]
>文章作者：**潇寒paper龙**
>版权声明：
>本文采用知识共享署名-非商业性使用-禁止演绎 4.0 
>国际许可协议（<a href="https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh"> CC BY-NC-ND 4.0 </a>）
>转载请注明来自 <a href="https://xiaohans.xyz">潇寒的雪屋</a> 或<a href="https://log.xiaohans.xyz">潇寒的日志</a>
>作者邮箱：**xiaohans@xiaohans.xyz**
>2025.04.15
>2024.04.16


# C 函数
# 函数的定义
C 语言中的函数定义的一般形式如下：
```c
return_type function_name( parameter list )
{
   body of the function
}

```

>[!note]
>在C中，函数由一个函数头和一个函数主体组成
>**返回类型（Return Type）**：指定函数返回值的数据类型，若无返回值则用 `void`。  
>**函数名（Function Name）**：函数的唯一标识符，用于调用该函数。  
>**参数列表（Parameter List）**：定义函数接受的输入参数及其类型，若无参数可写 `void` 或留空。 
>**函数体（Function Body）**：包含函数的具体执行代码，必须用 `{}` 包裹，非 `void` 函数需返回对应类型的数据。

>[!question]
>已知五边形的各条边a、b、c、d、e、f、g的长度，计算其面积
><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAbUAAAFuCAMAAAFGikaVAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAHyUExURf///9vb29u2tra2kGZmZmY6Ojo6AGa2/v//tmYBADo6OgAAAAAAZrb+////25A6AQBmtv7///+2ZgEAALZmATqQ2gAAOpDa///bkDoBAAA6kNr//9uQOtu2kGY6AAA6OmaQttv//5BmOpDa25BmAGa22//btpA6ADo6kLZmAGYAAGa2/7b//zoAADpmttuQZgA6ZpC22//b27ZmOrbb/7aQZjpmkP7+/gEBAZCQZjo6ZmaQkLa2tma2ttu2ZpDb/5BmZjqQ2zoAOmY6kDpmZtv/2zqQtmaQ2zpmOv39/dvb/2ZmtgICAtvbtraQkLbb25Db/tuQO5C127X+/7ZnOwEBADsBAABmtdu2Z2YBAWa1/v+2ZwEBOpC12rZmOzsBOpDa/pA7Zrb+/rZnAf7+/2Y7kNv+/7X+/tr+/ztmtpA7AWa12mcBAQE6kAEAZgEAOgFmtme2/js6Zma122Y6ATpmtWdnZma1/QE6OgAAZbX9/gBltf3+/7ZnAjqP2mcCAY/a/v/bkTsBAQA6j9r+/tuRO5E7AWW1/du2kWc7OzpltQA6ZbXa2tvbkWc7AQE6ZbW1ZmW12mZmkLa227aQOjs6OgE6j49mAWW1/o/a2v7bkbXa/pFnOzs7kLX+2pA7O2WP2raRZzplj5BmtpC2tgAAAGgXgPAAAACmdFJOU////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////wBGa60oAAAACXBIWXMAABcRAAAXEQHKJvM/AAAcZElEQVR4Xu2dW68kt3GAW3G0GCyFgTAPg4Exu+uzgM74jDQr7Z6VAcvJ2pYTI7Ah6yFvfsuPyOvCxoH9FiBIAjhGhFw2+aEByb6QxSJZTVZ3s2f5PZwLWawLqy/sbja7ad4/xPDX8GccMcjfwLoAnYlRtkwnZVN6WyhJbIpJ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" width="300"/>
><img src="data:image/png;base64,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" width="200"/>
>计算多边形面积，可将多边形分解成若干个三角形
>根据海伦公式计算三角形面积的海伦公式如下
>$p = (x + y + z) / 2$
>$s = \sqrt{p(p - x)(p - y)(p - z)}$

```c
#include <math.h>
#include <stdio.h>
/* 定义求三角形面积函数 */
double area(double x, double y, double z) {
    double p, s;
    p = (x + y + z) / 2.0;
    s = sqrt(p * (p - x) * (p - y) * (p - z));
    return s;
}
/* 主函数 */
int main() {
    double a, b, c, d, e, f, g, s;
    /* 输入七条边长 */
    scanf("%lf%lf%lf%lf%lf%lf%lf", &a, &b, &c, &d, &e, &f, &g);
    /* 计算三个三角形面积之和 */
    s = area(a, b, c) + area(c, d, e) + area(e, f, g);
    /* 输出结果 */
    printf("%f\n", s);
    return 0;
}
```

# 函数调用及参数传递
```c
#include<stdio.h>   
double fun(int m)
{
	int i=1; double s=1;
	for(;i<=m;i++)
		s*=i;
	return s;
}
int main( )
{
	int j,n;
	double sum=0;
	printf("input the n:\n");
	scanf("%d",&n);
	for(j=1;j<=n;j++)
		sum += fun(j);
	printf("1!+2!+...+%d!=%.1f\n",n,sum);
    return 0;
}

```

>[!success]

```c
input the n:
3
1!+2!+...+3!=9.0
请按任意键继续. . .
```

>[!warning]
>### 函数调用可以嵌套，但函数的定义不能嵌套

# 函数的递归调用和递归函数

>[!note]
>如果一个对象部分地由它自己组成或按它自己定义，则我们称它是递归（Recursive）的

>[!question]
>**计算n！**
>$n! = \begin{cases} 1 & \text{若 } n=0 \text{ 或 } 1 \\ n \times (n-1)! & \text{若 } n>1 \end{cases}$
>
>**求阶乘的递归函数fact ( )，递归条件为：**
>$fact(n) = \begin{cases} 1 & \text{若 } n=0 \text{ 或 } 1 \\ n \times fact(n-1) & \text{若 } n>1 \end{cases}$

>[!note]
>递归函数必须由这两部分条件构成：
>
>if(递归终止条件成立）
>return 递归公式的初值；
>else
>return 递归函数调用返回的结果值；

>[!question]
>求Fibonacci数列前40个数。这个数列有如下特点：第1，2两个数为1，1。从第3个数开始，该数是其前面两个数之和
>**即：**
>- $F(1) = 1$ （当 $n = 1$ 时）
>- $F(2) = 1$ （当 $n = 2$ 时）
>- $F(n) = F(n-1) + F(n-2)$ （当 $n \geq 3$ 时）

## 递归与迭代的比较

>[!question]
>求Fibonacci数列前40个数。这个数列有如下特点：第1，2两个数为1，1。从第3个数开始，该数是其前面两个数之和
>**即：**
>- $F(1) = 1$ （当 $n = 1$ 时）
>- $F(2) = 1$ （当 $n = 2$ 时）
>- $F(n) = F(n-1) + F(n-2)$ （当 $n \geq 3$ 时）


```c
#include<stdio.h>
main()
{
    int f1,f2,f3;
    int i;
    f1=1;  f2=1;
    printf("%12d%12d",f1,f2);
    for(i=3;i<=40;i++)
       {  
            f3=f1+f2;
            f1=f2;
            f2=f3;
            printf("%12d",f3);
            if(i%4==0)  printf("\n");
       }
}
```

```c
#include<stdio.h>
int Fib(int n);
int main()
{
    int i,x;
    for(i=1;i<=40;i++)
   {    x=Fib(i);
        printf("%12d",x);
        if(i%4==0)  printf("\n");
    }
	return 0;
}
int Fib(int n)
{    int result=0;
      if(0==n) result=0;
      else if(1==n) result=1;
      else result=(Fib(n-1)+Fib(n-2));
      return result;
}
```

>[!note]
>## 递归的优缺点
>### 优点：
>- 从编程角度来看，比较直观、精炼，逻辑清楚
>- 符合人的思维习惯，逼近数学公式的表示
>- 尤其适合非数值计算领域
  >- **hanoi塔**（加粗下划线）、骑士游历、八皇后问题（回溯法）
>### 缺点：
>- 增加了函数调用的开销（参数传递、现场保护等）
>- 耗费更多的时间和栈空间
>- 应尽量用迭代形式

- - -
# 练习
## 数字反转问题
>[!question]
>题目：用循环实现输入一个五位正整数，将它倒序后返回给主函数输出。
>例如输入12345，输出应为54321。（不采用指针、数组）

```c
#include <stdio.h>
int fun(int  n)
{ 
int reversed = 0;
    while (n > 0) {
        reversed = reversed * 10 + n % 10;
        n /= 10;
    }
    return reversed;
}
int main()
{ 
   int n,r;
   scanf("%d",&n);
   r=fun(n);
   printf("%d\n", r);
   return 0;
}
```

- - - 

## 大小写转化问题

>[!question]
>题目：若形参ch中是小写字母就转换成大写字母；若是大写字母就
>转换成小写字母，若是数字字符就转换成阿拉伯数字，其他字符不变。
>最终以ASCII值形式返回主函数输出。
>(不采用isupper函数和isdigit函数判断)

```c
#include <stdio.h>
int fun(char ch)
{ 
   if (ch >= 'a' && ch <= 'z') {
        return ch - 32;  // 小写转大写
    } else if (ch >= 'A' && ch <= 'Z') {
        return ch + 32;  // 大写转小写
    } else if (ch >= '0' && ch <= '9') {
        return ch - '0'; // 数字字符转阿拉伯数字
    } else {
        return ch;       // 其他字符不变
    }
}
int main()
{ 
    char ch;
    ch=getchar();
    printf("%d\n",fun(ch));
    return 0;
}
```

- - - 
## 找素数问题

>[!question]
>题目：将大于形参m且紧靠m的k个素数求和并返回到主函数输出。例如，若
>输入17, 5，可以找出五个素数分别是19, 23, 29, 31, 37。和为139
>
>**完整的ANSI C解决方案，不使用辅助函数，也不使用`math.h`库**

```c
#include<stdio.h>
int fun(int m,int k)
{
int sum = 0;
    int count = 0;
    int current = m + 1;  // 从m+1开始查找素数
    int i;  // 循环变量在函数开头声明
    while (count < k)
    {
        int is_prime = 1;  // 假设当前数是素数
        // 处理小于2的数
        if (current < 2)
        {
            is_prime = 0;
        }
        // 处理2
        else if (current == 2)
        {
            is_prime = 1;
        }
        // 处理偶数
        else if (current % 2 == 0)
        {
            is_prime = 0;
        }
        // 处理奇数
        else
        {
            // 检查从3到current/2的所有奇数因子
            for (i = 3; i <= current / 2; i += 2)
            {
                if (current % i == 0)
                {
                    is_prime = 0;
                    break;
                }
            }
        }
        // 如果是素数，则累加
        if (is_prime)
        {
            sum += current;
            count++;
        }
        current++;  // 检查下一个数
    }
    return sum;
}
int main()
{
     printf("%d\n",fun(17,5));
     return 0;
}
```

>[!info]
>### 紧凑版如下

```c
#include<stdio.h>
int fun(int m,int k)
{
int sum=0, count=0, current=m+1, i, is_prime;
    while(count<k) {
        is_prime = current>1;
        for(i=2; is_prime && i*i<=current; i++) 
            if(current%i==0) is_prime=0;
        if(is_prime) sum+=current, count++;
        current++;
    }
    return sum;
}

int main()
{
     printf("%d\n",fun(17,5));
     return 0;
}
```

- - - 
## 素数平方和问题

>[!question]
>题目：请编写函数，其功能是计算3到n之间所有素数的平方根之和。
>例如, 在主函数中从键盘给n输入100后,输出为: sum=148.874270。
>（注意: 要求n的值大于2且不超过100。）

```c
#include <math.h>
#include <stdio.h>
double fun(int  n)
{
/**********Program**********/
double sum = 0.0;
    int i, j, is_prime;
    
    for(i = 3; i <= n; i++) {
        is_prime = 1;
        for(j = 2; j <= sqrt(i); j++) {
            if(i % j == 0) {
                is_prime = 0;
                break;
            }
        }
        if(is_prime) {
            sum += sqrt(i);
        }
    }
    return sum;
}
int main()
{
        int  n; 
        double  sum;
        printf("\n\nInput n:  "); scanf("%d",&n);
        sum=fun(n);
        printf("\n\nsum=%lf\n\n",sum);
        return 0;
}

```

- - - 
## 样图公式求π
>[!queston]
>题目：请编写一个函数fun，它的功能是：根据以下样图公式求π的值
>(比如要求满足精度0.0005, 即某项小于0.0005 时停止迭代)

>[!caution]
>$$\frac{\pi}{2} = 1 + \frac{1}{3} + \frac{1 \times 2}{3 \times 5} + \frac{1 \times 2 \times 3}{3 \times 5 \times 7} + \cdots + \frac{1 \times 2 \times \cdots \times n}{3 \times 5 \times \cdots \times (2n+1)}.$$

```c
#include <stdio.h>
#include <math.h>

double  fun ( double  eps)
{
	double pi_over_2 = 1.0;  // 初始化 π/2 的值
    double term = 1.0;       // 初始化当前项的值
    int n = 1;               // 初始化 n 的值

    while (1) {
        term *= (double)n / (2 * n + 1);  // 计算下一项的值
        if (term < eps) {                 // 如果某项小于 eps，停止迭代
            break;
        }
        pi_over_2 += term;               // 累加到 π/2 的值中
        n++;
    }

    return 2 * pi_over_2;  // 返回 π 的近似值
}

int main( )
{ 
        double  x;
        printf("Input eps:") ;
        scanf("%lf",&x);
        printf("\neps = %lf, PI=%lf\n", x, fun(x));
        return 0;
}
```

- - -
## Fibonacci数列问题

>[!question]
>编写函数fun，它的功能是：求Fibonacci数列中大于t的最小的
>一个数，结果由函数返回。其中Fibonacci数列F(n)的定义为：
>F(0)＝0，F(1)＝1 ，F(n)＝F(n－1)＋F(n－2)

```c
#include <math.h>
#include <stdio.h>
int  fun( int  t)
{
    int a = 0, b = 1, c;
    if (t < 0) return 1; // 处理t为负数的情况，因为F(1)=1是最小的正整数解
    
    while (1) {
        c = a + b;
        if (c > t) {
            return c;
        }
        a = b;
        b = c;
    }
}
main()   /* 主函数 */
{ 
        int  n;  
        n=1000;   
        printf("n = %d, f = %d\n",n, fun(n));
        return 0;
}
```

- - - 
## 多项式求和问题

>[!question]
>题目：计算如样图所示的多项式求和，输入一个x就可以得到求和
>要求x<0.97。
>$S_x = 1 + 0.5x + \frac{0.5(0.5-1)}{2!} x^2 + \frac{0.5(0.5-1)(0.5-2)}{3!} x^3 + \ldots + \frac{0.5(0.5-1)(0.5-2)\cdots(0.5-n+1)}{n!} x^n$


$$S_x = 1 + 0.5x + \frac{0.5(0.5-1)}{2!} x^2 + \frac{0.5(0.5-1)(0.5-2)}{3!} x^3 + \ldots + \frac{0.5(0.5-1)(0.5-2)\cdots(0.5-n+1)}{n!} x^n$$


```c
#include<stdio.h>
#include<math.h>

double fun(double x)
{
/**********Program**********/
	double sum = 1.0;      // First term is always 1
    double term = 1.0;      // Current term value
    int n = 1;              // Term counter
    
    // Continue adding terms until they become insignificant
    while (fabs(term) > 1e-10) {  // Stop when terms are very small
        term *= (0.5 - (n - 1)) * x / n;
        sum += term;
        n++;
        
        // Prevent infinite loop for x values too close to 1
        if (n > 1000) break;
    }
    
    return sum;
/**********  End  **********/
}

int main()
{
        double x;
        scanf("%lf",&x);                                  
        printf("%lf\n",fun(x));
        return 0;
}
```

- - - 
## 自然数倒数之和问题

>[!question]
>题目： 请编写函数fun, 它的功能是:计算并输出n(包括n)以内能
>被5或9整除的所有自然数的倒数之和。例如,在主函数中从键盘给
>n输入20后, 输出为: s=0.583333。注意: 要求n的值不大于100。

```c
#include <stdio.h>
double fun(int  n)
{
/**********Program**********/     
	double sum = 0.0;
    int i;
    
    if (n > 100) {  // 检查 n 是否超过 100
        printf("Error: n should not exceed 100.\n");
        return 0.0;  // 返回 0 或其他错误标识
    }
    
    for (i = 1; i <= n; i++) {
        if (i % 5 == 0 || i % 9 == 0) {
            sum += 1.0 / i;
        }
    }
    
    return sum;
/**********  End  **********/
}
int main()
{
        int  n;
        double  s;
        printf("\nInput n:  ");scanf("%d",&n);
        s=fun(n);
        printf("s=%f\n",s);
        return 0;
}
```






  










