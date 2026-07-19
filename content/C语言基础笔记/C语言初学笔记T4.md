---
title: C语言初学笔记T4
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - C语言
created: 2025-05-19
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
>2025.05.19

## 输出字符串长度
>[!question]
>功能：编写函数fun求一个字符串的长度,在main函数中
>输入字符串,并输出其长度。
>注意不能用strlen函数

```c
/*------------------------------------------------
【程序设计】
--------------------------------------------------

功能：编写函数fun求一个字符串的长度,在main函数中
      输入字符串,并输出其长度。
      注意不能用strlen函数
------------------------------------------------*/

#include <stdio.h>
void  wwjt(); 

int fun(char *p1)
{
  
  /**********Program**********/
  int length = 0;
  while (*p1 != '\0') {
    length++;
    p1++;
  }
  return length;
  /**********  End  **********/
  
  
}

void main()
{
  char *p,a[20];
  int len;
  p=a;
  printf("please input a string:\n");
  gets(p);
  len=fun(p);
  printf("The string's length is:%d\n",len);
  wwjt();
}

void wwjt()
{
  FILE *IN,*OUT;
  char *pIN,sin[20];
  int iOUT,i;
  pIN=sin;
  IN=fopen("3.in","r");
  if(IN==NULL)
  {
    printf("Please Verify The Currernt Dir..it May Be Changed");
  }
  OUT=fopen("3.out","w");
  if(OUT==NULL)
  {
    printf("Please Verify The Current Dir.. it May Be Changed");
  }
  for(i=0;i<10;i++)
  {        
    fscanf(IN,"%s",pIN);
    iOUT=fun(pIN);
    fprintf(OUT,"%d\n",iOUT);
  }
  fclose(IN);
  fclose(OUT);
}
```

----------

## 字符串统计
>[!question]
>功能：求统计一个给定字符串中英文字母的个数。
>如“12abc5FGkjh78”,k=8

```c
/*------------------------------------------------
【程序设计】
--------------------------------------------------

功能：求统计一个给定字符串中英文字母的个数。
      如“12abc5FGkjh78”,k=8
------------------------------------------------*/

#include <stdio.h>
void wwjt();
    
int fun(char s[])
{
  
  /**********Program**********/
  int count = 0;  // 字母计数器
  int i = 0;      // 数组索引
  
  // 遍历字符串直到结束符
  while(s[i] != '\0') {
    // 判断是否为大写字母
    if(s[i] >= 'A' && s[i] <= 'Z') {
      count++;
    }
    // 判断是否为小写字母
    else if(s[i] >= 'a' && s[i] <= 'z') {
      count++;
    }
    i++;  // 移动到下一个字符
  }
  return count;  // 返回字母总数
  /**********  End  **********/
  
}

void main()
{
  char str[]="Best wishes for you!";
  int k;
  k=fun(str);
  printf("k=%d\n",k);
  wwjt();
  
}

void wwjt()
{
  FILE *IN,*OUT;
  char sin[80];
  int iOUT,i;
  IN=fopen("in.dat","r");
  if(IN==NULL)
  {
    printf("Please Verify The Currernt Dir..it May Be Changed");
  }
  OUT=fopen("out.dat","w");
  if(OUT==NULL)
  {
    printf("Please Verify The Current Dir.. It May Be Changed");
  }
  for(i=0;i<10;i++)
  {    
    fscanf(IN,"%s",sin);
    iOUT=fun(sin);
  }
  fprintf(OUT,"%d\n",iOUT);
  fclose(IN);
  fclose(OUT);
}
```

----------

## 比较字符串长度
>[!question]
>题目：请编写一个函数fun，它的功能是：比较两个字符串的长度,
>(不得调用C语言提供的求字符串长度的函数)，函数返回较长的字符
串。若两个字符串长度相同，则返回第一个字符串。
>例如，输入beijing回车shanghai ,  函数将返回shanghai

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------
题目：请编写一个函数fun，它的功能是：比较两个字符串的长度,
(不得调用C语言提供的求字符串长度的函数)，函数返回较长的字符
串。若两个字符串长度相同，则返回第一个字符串。
    例如，输入beijing <CR> shanghai <CR>（<CR>为回车键）,  
函数将返回shanghai。
-------------------------------------------------------*/

#include <stdio.h>
char  *fun ( char *s,  char *t)
{
/**********Program**********/  
	int len_s = 0, len_t = 0;
    char *p1 = s, *p2 = t;
    
    // 计算第一个字符串的长度
    while (*p1 != '\0') {
        len_s++;
        p1++;
    }
    
    // 计算第二个字符串的长度
    while (*p2 != '\0') {
        len_t++;
        p2++;
    }
    
    // 比较长度并返回结果
    if (len_t > len_s) {
        return t;
    } else {
        return s;
    }
/**********  End  **********/
}

int main( )
{
        char a[20],b[20];
        printf("Input 1th string:") ;
        gets( a);
        printf("Input 2th string:") ;
        gets( b);
        printf("%s\n",fun (a, b ));
        return 0;
}
```

----------
## 整数交换
>[!question]
>题目：请编写一个交换函数void swap(int *p , int *q)，该函数
>实现两个整数的交换。在main函数中构造两个整型变量，通过调
>用swap函数实现这两个整型变量的数值交换，并显示交换前和交
>换后的数据

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------
题目：请编写一个交换函数void swap(int *p , int *q)，该函数
实现两个整数的交换。在main函数中构造两个整型变量，通过调
用swap函数实现这两个整型变量的数值交换，并显示交换前和交
换后的数据。
-------------------------------------------------------*/
#include <stdio.h>
void  swap( int  *p, int *q)
{
/**********Program**********/  
int temp = *p;  // 临时保存第一个变量的值
    *p = *q;        // 将第二个变量的值赋给第一个变量
    *q = temp;      // 将临时保存的值赋给第二个变量
/**********  End  **********/   
}

int main()
{ 
   int a=10,b=20;
   printf("交换前a和b的值\n");printf("a=%d,b=%d\n",a,b);
   swap(&a,&b);
   printf("交换后a和b的值\n");printf("a=%d,b=%d\n",a,b);
   return 0;
}
```

----------
## 数组移动问题
>[!question]
>题目：请编写函数fun, 函数的功能是: 移动一维数组中的内容; 
>若数组中有n个整数, 要求把下标从0到p(含p,p小于等于n-1)的
>数组元素平移到数组的最后。例如, 一维数组中的原始内容为:
 >1,2,3,4,5,6,7,8,9,10 
>p的值为3。移动后, 一维数组中的内容应为:
 >5,6,7,8,9,10,1,2,3,4 

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------
题目：请编写函数fun, 函数的功能是: 移动一维数组中的内容; 
若数组中有n个整数, 要求把下标从0到p(含p,p小于等于n-1)的
数组元素平移到数组的最后。例如, 一维数组中的原始内容为:
 1,2,3,4,5,6,7,8,9,10 
p的值为3。移动后, 一维数组中的内容应为:
 5,6,7,8,9,10,1,2,3,4 

-------------------------------------------------------*/
#include <stdio.h>
#define    N    80
void  fun(int  *w, int  p, int  n)
{
/**********Program**********/  
 int temp[N];  // 临时数组存储要移动的元素
    int i, j = 0;
    
    // 1. 将下标0到p的元素暂存到临时数组
    for (i = 0; i <= p; i++) {
        temp[i] = w[i];
    }
    
    // 2. 将p+1到n-1的元素前移
    for (i = 0; i < n - p - 1; i++) {
        w[i] = w[p + 1 + i];
    }
    
    // 3. 将临时数组中的元素放到数组末尾
    for (i = n - p - 1; i < n; i++) {
        w[i] = temp[j++];
    }
/**********  End  **********/ 
}
int main()
{ 
   int  a[N]={1,2,3,4,5,6,7,8,9,10,11,12,13,14,15};
   int  i,p,n=15;
   printf("The original data:\n");
   for(i=0; i<n; i++)printf("%3d",a[i]);
   printf("\n\nEnter  p:  ");scanf("%d",&p);
   fun(a,p,n);
   printf("\nThe data after moving:\n");
   for(i=0; i<n; i++)printf("%3d",a[i]);
   printf("\n\n");
   return 0;
}
```

----------
## 字符串删除问题
>[!question]
>题目： 请编写一个函数，函数的功能是删除字符串中的所有
>空格。例如, 主函数中输入"asd af aa z67", 
>则输出为 "asdafaaz67"

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------
题目： 请编写一个函数，函数的功能是删除字符串中的所有
空格。例如, 主函数中输入"asd af aa z67", 
则输出为 "asdafaaz67"。
-------------------------------------------------------*/
#include <stdio.h>


void fun(char *str)
{
/**********Program**********/  
	char *p = str;  // 用于遍历字符串的指针
    char *q = str;  // 用于存储非空格字符的指针
    
    while (*p != '\0') {  // 遍历字符串直到结束符
        if (*p != ' ') {  // 如果当前字符不是空格
            *q = *p;      // 保存到q指向的位置
            q++;          // q指针前移
        }
        p++;              // 无论是否空格，p都前移
    }
    *q = '\0';            // 在新字符串末尾添加结束符
/**********  End  **********/   
}

int main()
{
  char str[81];
  printf("Input a string:") ;
  gets(str);
  puts(str);
  fun(str);
  printf("*** str: %s\n",str);
  return 0;
}
```

----------

## 年龄统计问题
>[!question]
>题目：请编写函数fun,函数的功能是:统计各年龄段的人数。N个年龄通过
>调用随机函数获得,并放在主函数的age数组中；要求函数把0至9岁年龄段
>的人数放在d[0]中,把10至19岁年龄段的人数放在d[1]中,把20至29岁年龄
>段的人数放在d[2]中, 其余依此类推, 把100岁 (含100)以上年龄的人数
>都放在d[10]中。结果在主函数中输出

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------

题目：请编写函数fun,函数的功能是:统计各年龄段的人数。N个年龄通过
调用随机函数获得,并放在主函数的age数组中；要求函数把0至9岁年龄段
的人数放在d[0]中,把10至19岁年龄段的人数放在d[1]中,把20至29岁年龄
段的人数放在d[2]中, 其余依此类推, 把100岁 (含100)以上年龄的人数
都放在d[10]中。结果在主函数中输出。

-------------------------------------------------------*/

#include <stdio.h>
#define   N   50
#define   M   11
void  fun(int *a, int *b)
{
/**********Program**********/
	int i;
    for (i = 0; i < N; i++) {
        if (a[i] < 10) {
            b[0]++;
        } else if (a[i] < 20) {
            b[1]++;
        } else if (a[i] < 30) {
            b[2]++;
        } else if (a[i] < 40) {
            b[3]++;
        } else if (a[i] < 50) {
            b[4]++;
        } else if (a[i] < 60) {
            b[5]++;
        } else if (a[i] < 70) {
            b[6]++;
        } else if (a[i] < 80) {
            b[7]++;
        } else if (a[i] < 90) {
            b[8]++;
        } else if (a[i] < 100) {
            b[9]++;
        } else {
            b[10]++;
        }
    }
/**********  End  **********/

}
double  rnd()  //产生一个随机小数
{  static int t=29,c=217,m=1024,r=0;
   r=(r*t+c)%m;  return((double)r/m);
}
main()
{  int  age[N], i, d[M]={0};//d数组用于存放各年龄段人数
   for(i=0; i<N;i++)age[i]=(int)(115*rnd());//调用rnd()函数产生的一个随机小数，用来将age数组中每个元素都赋值为115以内的整数
   printf("The original data :\n");
   for(i=0;i<N;i++) printf((i+1)%10==0?"%4d\n":"%4d",age[i]);
   printf("\n\n");
   fun( age, d);
   for(i=0;i<10;i++)printf("%4d---%4d:%4d\n",i*10,i*10+9,d[i]); //按格式输出年龄段人数统计
   printf("  Over  100:%4d\n",d[10]);
   
}

```

>[!info]
>==标准答案==

```c
#include <stdio.h>
#define   N   50
#define   M   11
void  fun(int *a, int *b)
{
/**********Program**********/
	int i,j;
	for(i=0;i<M;i++)
		b[i]=0;
	for(i=0;i<N;i++)
	{
	j=a[i]/10;
	if(j>10)
	b[M-1]++;
	else b[j]++;
	}
/**********  End  **********/

}
double  rnd()  //产生一个随机小数
{  static int t=29,c=217,m=1024,r=0;
   r=(r*t+c)%m;  return((double)r/m);
}
main()
{  int  age[N], i, d[M]={0};//d数组用于存放各年龄段人数
   for(i=0; i<N;i++)age[i]=(int)(115*rnd());//调用rnd()函数产生的一个随机小数，用来将age数组中每个元素都赋值为115以内的整数
   printf("The original data :\n");
   for(i=0;i<N;i++) printf((i+1)%10==0?"%4d\n":"%4d",age[i]);
   printf("\n\n");
   fun( age, d);
   for(i=0;i<10;i++)printf("%4d---%4d:%4d\n",i*10,i*10+9,d[i]); //按格式输出年龄段人数统计
   printf("  Over  100:%4d\n",d[10]);
   
}
```
----------

## 数组删除问题

>[!question]
>题目：请编写函数fun, 函数的功能是: 删去一维数组中所有相
>同的数, 使之只剩一个。数组中的数已按由小到大的顺序排列,
>函数返回删除后数组中数据的个数。
>例如, 一维数组中的数据是:
> 2 2 2 3 4 4 5 6 6 6 6 7 7 8 9 9 10 10 10 
>删除后,数组中的内容应该是: 
>2 3 4 5 6 7 8 9 10
>

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------
题目：请编写函数fun, 函数的功能是: 删去一维数组中所有相
同的数, 使之只剩一个。数组中的数已按由小到大的顺序排列,
函数返回删除后数组中数据的个数。
例如, 一维数组中的数据是:
      2 2 2 3 4 4 5 6 6 6 6 7 7 8 9 9 10 10 10 
删除后,数组中的内容应该是: 
      2 3 4 5 6 7 8 9 10 
-------------------------------------------------------*/

#include <stdio.h>
#define    N    80
int  fun(int  *a, int  n)
{
/**********Program**********/  
int i, j;  /* ANSI C 要求变量声明在块开头 */
    
    if (n <= 1) return n;  /* 处理边界情况 */
    
    for (i = 1, j = 0; i < n; i++) {
        if (a[j] != a[i]) {
            j++;
            a[j] = a[i];  /* 发现新元素时前移 */
        }
    }
    return j + 1;  /* 返回新长度 */
/**********  End  **********/   
}
int main()
{  
   int  a[N]={2,2,2,3,4,4,5,6,6,6,6,7,7,8,9,9,10,10,10,10},i,n=20;
   printf("The original data :\n");
   for(i=0; i<n; i++)printf("%3d",a[i]);
   n=fun(a,n);
   printf("\n\nThe data after deleted :\n");
   for(i=0;i<n;i++)printf("%3d",a[i]); printf("\n\n");
   return 0;
}
```

----------
## 数组最小值问题

>[!question]
>功能：把VSIZE个随机数存入一个数组，然后输出该数组中的
>最小值。其中最小值的下标i由fun函数返回（return i;），
>请完善fun中的代码书写


```c
/*------------------------------------------------
【程序设计】
--------------------------------------------------

功能：把VSIZE个随机数存入一个数组，然后输出该数组中的
      最小值。其中最小值的下标i由fun函数返回（return i;），
      请完善fun中的代码书写。
     
------------------------------------------------*/

#include <stdio.h>
#include <stdlib.h>
#define VSIZE 20     
void  wwjt(); 
  
int vector[VSIZE] ;     

int fun(int list[],int size)     
{
  /**********Program**********/
  
  int i, min_index = 0;
  for (i = 1; i < size; i++) {
    if (list[i] < list[min_index]) {
      min_index = i;
    }
  }
  return min_index;
  /**********  End  **********/     
  
} 

void main()     
{     
  int i;     
  for (i=0;i<VSIZE;i++)
  {
    vector[i]=rand();  /*随机产生一个整数*/   
    printf("Vector[%d]=%6d\n",i,vector[i]);     
  }     
  i=fun(vector,VSIZE);     
  printf("\nMininum: Vector[%d]=%6d\n",i,vector[i]);
  
  wwjt();
}     

void wwjt()     
{     
  int i,t;
  FILE *fp ;     
  fp = fopen("out.dat", "w") ;
  for (i=0;i<VSIZE;i++)
  {
    fprintf(fp,"Vector[%d]=%6d\n",i,vector[i]);
  }     
  t=fun(vector,VSIZE);
  fprintf(fp,"\nMininum: Vector[%d]=%6d\n",t,vector[t]);
  fclose(fp) ;     
}
```

----------

## 数组最大值问题

>[!question]
>功能：把20个随机数存入一个数组，fun函数返回该数组中最大值的下标i


```c
/*------------------------------------------------
【程序设计】
--------------------------------------------------

功能：把20个随机数存入一个数组，fun函数返回该数组中最大值的下标i。   

------------------------------------------------*/

#include <stdio.h>
#include <stdlib.h>
#define VSIZE 20     
void  wwjt(); 

int vector[VSIZE] ;     
int fun(int list[],int size)     
{
  /**********Program**********/
  
  int i, max_index = 0;  // 初始化max_index为0，假设第一个元素最大
  
  for (i = 1; i < size; i++) {
    if (list[i] > list[max_index]) {  // 如果找到更大的元素
      max_index = i;                  // 更新最大值下标
    }
  }
  return max_index;  // 返回最大值下标
  /**********  End  **********/     
  
}     
void main()     
{     
  int i;     
  for (i=0;i<VSIZE;i++)
  {
    vector[i]=rand();     
    printf("Vector[%d]=%6d\n",i,vector[i]);     
  }     
  i=fun(vector,VSIZE);     
  printf("\nMaxnum: Vector[%d]=%6d\n",i,vector[i]);
  
  wwjt();
}     
void wwjt()     

{     
  int i,t;
  FILE *fp ;     
  fp = fopen("out.dat", "w") ;
  for (i=0;i<VSIZE;i++)
  {
    fprintf(fp,"Vector[%d]=%6d\n",i,vector[i]);
  }     
  t=fun(vector,VSIZE);
  fprintf(fp,"\nMaxnum: Vector[%d]=%6d\n",t,vector[t]);
  fclose(fp) ;     
}
```


--------

## 小于平均值的数的个数

>[!question]
>功能：求一批数中小于平均值的数的个数。
>程序运行后，输入数据的个数，以及数据的值进行结果测试


```c
/*------------------------------------------------
【程序设计】
--------------------------------------------------

功能：求一批数中小于平均值的数的个数。
程序运行后，输入数据的个数，以及数据的值进行结果测试

------------------------------------------------*/

#include<stdio.h>
void  wwjt(); 

int average_num(int a[],int n)
{
  /**********Program**********/
  int i, sum = 0, count = 0;
  float average;
  
  // 计算总和
  for (i = 0; i < n; i++) {
    sum += a[i];
  }
  
  // 计算平均值
  average = (float)sum / n;
  
  // 统计小于平均值的数的个数
  for (i = 0; i < n; i++) {
    if (a[i] < average) {
      count++;
    }
  }
  
  return count;
  /**********  End  **********/
}

void main()
{
  int n,a[100],i,num;
  scanf("%d",&n);
  for(i=0;i<n;i++)
    scanf("%d",&a[i]);
  num=average_num(a,n);
  printf("the num is:%d\n",num);
  wwjt();
}

void wwjt()
{
  FILE *IN,*OUT;
  int n;
  int i[10];
  int o;
  IN=fopen("in.dat","r");
  if(IN==NULL)
  {
    printf("Read FILE Error");
  }
  OUT=fopen("out.dat","w");
  if(OUT==NULL)
  {
    printf("Write FILE Error");
  }
  for(n=0;n<5;n++)
  {    
    fscanf(IN,"%d",&i[n]);
  }
  o=average_num(i,5);
  fprintf(OUT,"%d\n",o);
  fclose(IN);
  fclose(OUT);
}
```

--------

# 杨辉三角

>[!question]
>功能：以下程序输出前六行杨辉三角形,既


```c
/*------------------------------------------------------        
【程序改错】
--------------------------------------------------------

功能：以下程序输出前六行杨辉三角形,既
             1
          1     1
       1     2     1
    1     3     3     1 
 1     4     6     4     1
         …………
         …………

------------------------------------------------------*/
#include <stdio.h>
void main( )
{
  static int a[6][6];
  int i,j,k;
  /***********FOUND***********/
  for(i=0;i<=6;i++)  
  {
    for(k=0;k<10-2*i;k++)  
      printf(" ");
    for(j=0;j<=i;j++)
    {
      /***********FOUND***********/ 
      if(j==0||j==i)  
        a[i][j]=1; 
      else 
        /***********FOUND***********/
        a[i][j]=a[i-1][j]+a[i-1][j-1];
      printf(" ");
      printf("%-3d",a[i][j]);
    }
    /***********FOUND***********/
    printf("\n");    
  }
}
```

--------

