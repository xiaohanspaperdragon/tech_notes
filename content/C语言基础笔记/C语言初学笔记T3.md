---
title: C语言初学笔记T3
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - C语言
created: 2025-04-30
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
>2025.04.30

# 数组 字符串 指针
## 题目
### 字符串复制问题

>[!question]
>功能：用函数实现字符串的复制,把第一个字符串str1的内容复制给第二个字符串str2 
不允许用strcpy()函数

```c
#include <stdio.h>
void wwjt(); 
void copy(char str1[], char str2[])
{
    /**********Program**********/
    int i = 0;
    // 循环遍历str1直到遇到字符串结束符'\0'
    while(str1[i] != '\0')
    {
        // 将str1的每个字符复制到str2
        str2[i] = str1[i];
        i++;
    }
    // 在str2末尾添加字符串结束符
    str2[i] = '\0';
    /**********  End  **********/
}

void main()
{
    char c1[40], c2[40];
    gets(c1);
    copy(c1, c2);
    puts(c2);
    wwjt();
}

void wwjt()
{
    FILE *IN, *OUT;
    char i[100];
    char o[100];
    IN = fopen("in.dat", "r");
    if(IN == NULL)
    {
        printf("Read FILE Error");
    }
    OUT = fopen("out.dat", "w");
    if(OUT == NULL)
    {
        printf("Write FILE Error");
    }
    fscanf(IN, "%s", i);
    copy(i, o);
    fprintf(OUT, "%s\n", o);
    fclose(IN);
    fclose(OUT);
}
```

>[!note]
>代码说明：
> 在`copy`函数中，使用`while`循环逐个字符复制 
>循环条件是检查源字符串`str1`是否到达结束符`'\0'`
>复制完成后，手动在目标字符串`str2`末尾添加结束符'`\0'` 
>主程序通过`gets`获取输入字符串，调用`copy`函数复制，然后`puts`输出结果 
>`wwjt`函数用于文件测试，保持原样未作修改    
>注意：`gets()`函数在新标准中已不推荐使用，因为它不安全（可能导致缓冲区溢出），但在本题中为保持题目要求仍使用。在实际开发中建议使用`fgets()`替代


----------

### 统计字符串次数问题
>[!question]
>题目：分别统计字符串中字母、数字、空格和其他字符出现的 次数（字符长度小于80,不包含字符串的结束符）

```c
#include <stdio.h>
void  wwjt(); 

/*-全局变量，a用于保存字母个数、num用于保存数字个数
b用于保存空格个数、other用于保存其他字符字数*/
int a=0,num=0,b=0,other=0;

void count(char c[])
{
   /**********Program**********/
	int i = 0;
   while(c[i] != '\0' && i < 80)  // 遍历字符串直到结束符或达到最大长度
   {
       if((c[i] >= 'a' && c[i] <= 'z') || (c[i] >= 'A' && c[i] <= 'Z'))
           a++;  // 统计字母
       else if(c[i] >= '0' && c[i] <= '9')
           num++;  // 统计数字
       else if(c[i] == ' ')
           b++;  // 统计空格
       else
           other++;  // 统计其他字符
       i++;
   }
  /**********  End  **********/

}

void main()
{
                                
 char ch[80];  
 
 printf ("input string:"); 
 gets(ch);                                             

 count(ch); 

 printf ("a=%d num=%d b=%d other=%d\n",a,num,b,other);  

 wwjt();
}





void wwjt()
{
  FILE *IN,*OUT;
  int i;
  char sin[80];
  IN=fopen("in.dat","r");
  if(IN==NULL)
  {
    printf("Please Verify The Currernt Dir..it May Be Changed");
  }
  OUT=fopen("out.dat","w");
  if(OUT==NULL)
  {
    printf("Please Verify The Current Dir.. it May Be Changed");
  }
  for(i=0;i<5;i++)
  { 
    a=0;
    num=0;
    b=0;
    other=0;       
    fscanf(IN,"%s",&sin);
    count(sin);
    fprintf(OUT,"%d\n",a);
    fprintf(OUT,"%d\n",num);
    fprintf(OUT,"%d\n",b);
    fprintf(OUT,"%d\n",other);  
  }
  
  fclose(IN);
  fclose(OUT);
}
```

----------

### 字符串内容逆置
>[!question]
>题目： 请编一个函数`fun(char s[])`，函数的功能是把`s`所指字符串
中的内容逆置。例如：字符串中原有的字符串为：`abcdefg`，则调
用该函数后, 串中的内容为：`gfedcba`

```c
#include <string.h>
#include <stdio.h>
#define   N   81
void fun ( char  s[ ] )
{
/**********Program**********/          
int length = strlen(s);
    int i, j;
    char temp;
    
    for(i = 0, j = length - 1; i < j; i++, j--)
    {
        temp = s[i];
        s[i] = s[j];
        s[j] = temp;
    }
/**********  End  **********/
}
main( )
{
   char   a[N];
   printf ( "Enter  a  string :  " ); gets ( a );
   printf ( "The original string is :  " ); puts( a );
   fun ( a );
   printf("\n");
   printf ( "The string after modified :  ");
   puts ( a );
}


```


>[!question]
>输入一串字符s，把s所指字符串中的内容逆置。例如：字符串中原有的字符串为：abcdefg，则执行后, 串s中的内容为：gfedcba

```c
#include <stdio.h>
#include <string.h>
void Inverse(char a[]);
#define N 80
main()
{
	char s[N];
	printf("请输入字符串:\n");
	scanf("%s", s);
	Inverse(s);
}
void Inverse(char a[])
{
	int i,n=strlen(a);
	char t;
	for(i=0;i<n/2;i++)
	{
		t=a[i];
		a[i]=a[n-1-i];
		a[n-1-i]=t;
	}
	printf("\n字符串逆置后:\n%s\n", a);
}

```



----------

### 统计问题
>[!question]
>功能：统计出若干个学生的平均成绩，最高分以及得最高
>      分的人数。（最高分可能不止一个）
>例如：输入10名学生的成绩分别为92，87，68，56，92，
>      84，67，75，92，66，则输出平均成绩为77.9，
>      最高分为92，得最高分的人数为3人

```c
#include <stdio.h>
   
float Max=0;/*Max为最高分变量，注意最高分不止一个*/
int J=0; /*J为最高分的人数*/

float fun(float array[],int n)
{
  
  /**********Program**********/
  float sum = 0;
    int i;
    
    // 计算总分并找出最高分
    Max = array[0];
    for(i = 0; i < n; i++)
    {
        sum += array[i];  // 累加计算总分
        if(array[i] > Max)  // 找出最高分
        {
            Max = array[i];
        }
    }
    
    // 统计最高分人数
    for(i = 0; i < n; i++)
    {
        if(array[i] == Max)  // 统计等于最高分的人数
        {
            J++;
        }
    }
    
    return sum / n;  // 返回平均分
  /**********  End  **********/
  
}

main(  )
{
  float  a[10],ave;
  int i=0;
  for(i=0;i<10;i++)
    scanf("%f",&a[i]);
  ave=fun(a,10);
  printf("ave=%f\n",ave);
  printf("max=%f\n",Max);
  printf("Total:%d\n",J);
  return 0;
}

```

```c
#include <stdio.h>
void wwjt();
   
float Max=0;/*Max为最高分变量，注意最高分不止一个*/
int J=0; /*J为最高分的人数*/

float fun(float array[],int n)
{
  
  /**********Program**********/
  float sum = 0;
  int i;
  
  // 计算总分并找出最高分
  Max = array[0];
  for (i = 0; i < n; i++) {
      sum += array[i];
      if (array[i] > Max) {
          Max = array[i];
      }
  }
  
  // 统计最高分人数
  J = 0;
  for (i = 0; i < n; i++) {
      if (array[i] == Max) {
          J++;
      }
  }
  
  // 返回平均分
  return sum / n;
  /**********  End  **********/
  
}

void main(  )
{
  float  a[10],ave;
  int i=0;
  for(i=0;i<10;i++)
    scanf("%f",&a[i]);
  ave=fun(a,10);
  printf("ave=%f\n",ave);
  printf("max=%f\n",Max);
  printf("Total:%d\n",J);
  wwjt();
  return 0;
}

void wwjt()
{
  FILE *IN,*OUT;
  float iIN[10],iOUT;
  int iCOUNT;
  IN=fopen("in.dat","r");
  if(IN==NULL)
  {
    printf("Please Verify The Currernt Dir..it May Be Changed");
  }
  OUT=fopen("out.dat","w");
  if(OUT==NULL)
  {
    printf("Please Verify The Current Dir.. it May Be Changed");
  }
  for(iCOUNT=0;iCOUNT<10;iCOUNT++)
    fscanf(IN,"%f",&iIN[iCOUNT]);
  iOUT=fun(iIN,10);
  fprintf(OUT,"%f\n%f\n",iOUT,Max);
  fclose(IN);
  fclose(OUT);
}
```
----------

### 素数问题
>[!question]
>题目： 编写函数，要求计算并输出不超过n的最大的k个素数以及它们的和。注意找到
>的k个素数先要保存在数组a中。
>
>输入格式:  输入在一行中给出n(10≤n≤10000)和k(1≤k≤10)的值。
>输出格式:  在一行中按下列格式输出:
>           素数1+素数2+…+素数k=总和值
> 
>  其中素数按递减顺序输出。若n以内不够k个素数，则按实际个数输出。
>
>输入样例1:  1000 10
>输出样例1: 997+991+983+977+971+967+953+947+941+937=9664
>
>输入样例2:   12 6
>输出样例2: 11+7+5+3+2=28


```c
#include <stdio.h>
int a[11];
int count=0,sum=0;/*count数组中存放素数的个数，sum数组中素数求和*/
void fun(int n,int k)
{   
    int i,j;
/**********Program**********/  
    count = 0;
    sum = 0;
    for (i = n; i >= 2; i--) {
        int isPrime = 1;
        if (i < 2) {
            isPrime = 0;
        } else if (i == 2) {
            isPrime = 1;
        } else if (i % 2 == 0) {
            isPrime = 0;
        } else {
            for (j = 3; j * j <= i; j += 2) {
                if (i % j == 0) {
                    isPrime = 0;
                    break;
                }
            }
        }
        if (isPrime) {
            a[count] = i;
            sum += i;
            count++;
            if (count == k) break;
        }
    }
    for (j = 0; j < count; j++) {
        printf("%d", a[j]);
        if (j < count - 1) printf("+");
    }
    printf("=%d\n", sum);
/**********  End  **********/
}

int main()
{
    int n,k;
    printf("\nInput n and k:  ");
    scanf("%d %d",&n,&k);
    fun(n,k);
    return 0;
}
```

----------

### 字符串删除问题
>[!question]
>假定输入的字符串中只包含字母和*号。请编写函数fun，它的功能是：
>     删除字符串中所有的*号。
>     在编写函数时，不得使用C语言提供的字符串函数。
>     例如，字符串中的内容为：`****A*BC*DEF*G*******`
>     删除后，字符串中的内容应当是：ABCDEFG。
>     
>  注意：请勿改动主函数main和其它函数中的任何内容，仅在函数fun的花括号中填入你编写的若干语句

```c
#include <stdio.h>
void  fun( char a[])
{
  /**********Program**********/
	int i, j;
  for (i = 0, j = 0; a[i] != '\0'; i++) {
      if (a[i] != '*') {
          a[j++] = a[i];
      }
  }
  a[j] = '\0';
  /**********  End  **********/

}

void main()
{
   char  s[81];
   printf("Enter a string:\n");gets(s);
   fun( s );
   printf("The string after deleted:\n");puts(s);
}
```


>[!question]
>将字符串S中下标为偶数的字符删除，串中剩余字符形成的新串放在数组t中。例如，当字符串s中的内容为："ABCDEFGHIJK"，在数组t中的内容应是："BDFHJ"

```c
#include <stdio.h>
#include <string.h>
void Delete(char b[]);
#define N 80
main()
{
	char s[N];
	printf("请输入字符串:\n");
	scanf("%s", s);
          Delete(s);
}
void Delete(char b[])
{
	char t[N/2];
	int i, j,n=strlen(b);
	for(i=0,j=0;i<n;i++)
	{  
		if(i%2==1)  
		{
			t[j]=b[i];
			j++;
		}
	}
	t[j] = '\0';
	printf("\n去掉下标为偶数的字符（即去掉第奇数个字符）后:\n%s\n", t);
}

```

----------

### 排序问题
>[!question]
>编写函数用排序法对数组中的数据进行从小到大的排序

```c
#include <stdlib.h>
#include<stdio.h>

void sort(int a[],int n)
{
  /**********Program**********/
   int i, j, temp;
  for (i = 0; i < n - 1; i++) {
      for (j = 0; j < n - i - 1; j++) {
          if (a[j] > a[j + 1]) {
              temp = a[j];
              a[j] = a[j + 1];
              a[j + 1] = temp;
          }
      }
  }
  /**********  End  **********/
}

main()
{
  int a[16],i;
  for(i=0;i<16;i++)
    a[i]=rand()%100;
  for(i=0;i<16;i++)
    printf("%4d",a[i]);
  printf("\n-------------------\n");
  sort(a,16);
  for(i=0;i<16;i++)
    printf("%4d",a[i]);
}
```

----------

### 二维数组问题
>[!question]
>题目： 请编一个函数void fun(int tt[M][N ], int pp[N])，tt指向
>一个M行N列的二维数组，求出二维数组每列中最小元素，并依次放入
>pp所指一维数组中。二维数组中的数已在主函数中赋予。
>   示例结果可以见样图

<img src="data:image/png;base64,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"/>

```c
#include <stdio.h>
#define  M  3
#define  N  4
void  fun ( int tt[M][N], int pp[N] )
{
/**********Program**********/          
	int i, j;  // 将变量声明移到函数开头
    for (j = 0; j < N; j++) {
        pp[j] = tt[0][j];  // 初始化为每列第一个元素
        for (i = 1; i < M; i++) {
            if (tt[i][j] < pp[j]) {
                pp[j] = tt[i][j];  // 更新为更小的值
            }
        }
    }
/**********  End  **********/
}

main( )
{
   int t [ M ][ N ]={{22,45, 56,30},
                     {19,33, 45,38},
                     {20,22, 66,40}};
   int  p [ N ],  i,  j,  k;
   printf ( "The original data is : \n" );
   for( i=0; i<M; i++ ){
     for( j=0; j<N; j++ )
       printf ( "%6d", t[i][j] );
     printf("\n");
   }
   fun ( t, p );
   printf( "\nThe result  is:\n" );
   for ( k = 0; k < N; k++ ) printf ( " %4d ", p[ k ] );
   printf("\n");
}


```

----------

>[!question]
>题目：程序定义了N×N的二维数组，并在主函数中赋值。
>请编写函数fun,函数的功能是：求出数组周边元素的平均值
>并作为函数值返给主函数中的s

```c
#include <stdio.h>
#include <stdlib.h>
#define  N  5
double fun ( int w[][N] )
{
/**********Program**********/  
int i, j;
    double sum = 0.0;
    int count = 0;
    
    // 计算第一行和最后一行
    for(j = 0; j < N; j++) {
        sum += w[0][j];    // 第一行
        sum += w[N-1][j];  // 最后一行
        count += 2;
    }
    
    // 计算中间行的第一列和最后一列(跳过已计算的第一行和最后一行)
    for(i = 1; i < N-1; i++) {
        sum += w[i][0];    // 第一列
        sum += w[i][N-1];  // 最后一列
        count += 2;
    }
    
    // 计算平均值
    return sum / count;
/**********  End  **********/        
}

main ( )
{ 
   int a[N][N]={0,1,2,7,9,1,9,7,4,5,2,3,8,3,1,4,5,6,8,2,5,9,1,4,1};
   int i, j;
   double s ;
   printf("***** The array *****\n");
   for ( i =0;  i<N; i++ )
   {  for ( j =0; j<N; j++ )
     {  printf( "%4d", a[i][j] ); }
        printf("\n");
   }
   s = fun ( a );
   printf ("***** THE  RESULT *****\n");
   printf( "The sum is :  %lf\n",s );
}
```

----------

## 其他问题

>[!question]
>题目：编程序按如图片所示公式计算s的值（其中x1、x2、、…、x10由键盘输入）。
>其中x0是x1、x2、、…、x10的平均值）

<img src="data:image/png;base64,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"/>

```c
/*-------------------------------------------------------
【程序设计】
---------------------------------------------------------

  题目：编程序按如图片所示公式计算s的值（其中x1、x2、、…、x10由键盘输入）。
         （其中x0是x1、x2、、…、x10的平均值）

  
-------------------------------------------------------*/
#include <stdio.h>
void wwjt();
#define N 10

float fun(float x0,float x[N])
{
        int i;
        float s=0;

/**********Program**********/
		// 计算平均值x0
    x0 = 0;
    for (i = 0; i < N; i++) {
        x0 += x[i];
    }
    x0 /= N;

    // 计算s的值
    for (i = 0; i < N; i++) {
        s += (x[i] - x0) * (x[i] - x0);  // 计算平方和
    }
    // 根据题目描述，s是平方和，不需要再除以N
    // 如果题目要求的是方差，则应该除以N
/**********  End  **********/

        return s;
}


void main( )
{  
        float  x[N], x0=0, s=0;
        int i;
        for (i=0 ; i<N; i++)   
        {
           scanf( "%f", &x[i]); 
        }

        s=fun(x0,x);

        printf( "s=%f\n", s);

        wwjt();
}

void wwjt()
{
        
        FILE *IN,*OUT;
        int j;
        float x[N];
        IN=fopen("in.dat","r");
        if(IN==NULL)
        {
                printf("Please Verify The Currernt Dir..It May Be Changed");
        }
        OUT=fopen("out.dat","w");
        if(OUT==NULL)
        {
                printf("Please Verify The Current Dir.. It May Be Changed");
        }
        for(j=0;j<10;j++)
        {
                fscanf(IN,"%f",&x[j]);
        } 
        fprintf(OUT,"%f\n",fun(0,x));
        
        fclose(IN);
        fclose(OUT);
}

```

----------

>[!question]
>功能：求一批数中最大值和最小值的积。

```c
/*------------------------------------------------
【程序设计】
--------------------------------------------------

功能：求一批数中最大值和最小值的积。

------------------------------------------------*/

#define N 30
#include "stdlib.h"
#include <stdio.h>
void  wwjt(); 

int max_min(int a[],int n)
{
  /**********Program**********/
  
	int i, max = a[0], min = a[0];
  
  for(i = 1; i < n; i++) {
      if(a[i] > max) {
          max = a[i];
      }
      if(a[i] < min) {
          min = a[i];
      }
  }
  
  return max * min;
  
  
  
  
  
  /**********  End  **********/
}

void main()
{
  int a[N],i,k;
  for(i=0;i<N;i++)
    a[i]=rand()%51+10;
  for(i=0;i<N;i++)
  {
    printf("%5d",a[i]);
    if((i+1)%5==0) printf("\n");
  }
  k=max_min(a,N);
  printf("the result is:%d\n",k);
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
  for(n=0;n<10;n++)
  {    
    fscanf(IN,"%d",&i[n]);
  }
  o=max_min(i,10);
  fprintf(OUT,"%d\n",o);
  fclose(IN);
  fclose(OUT);
}
```