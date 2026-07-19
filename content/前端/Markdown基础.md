---
title: Markdown基础
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - markdown
  - blog
  - obsidian
created: 2025-01-24
modified: 2025-08-05
draft: false
description: Markdown基础
---


## Markdown简介
>Markdown是一种轻量级标记语言，纯文本格式编写，被广泛用于在各大论坛上撰写帮助文档和发表消息  
>市面上有很多编辑器支持markdown语法，笔者使用vs code和odsidian协同编写
>在 VSCode 下安装 **Markdown Preview Enhanced** 插件来实现更强大的功能

## Markdown标题
>使用#可以表示标题，有1至6级标题
>一级标题一个#，二级标题两个#
>以此类推

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
## Markdown字体
>常见的有三种字体

- 斜体文本
- 粗体文本
- 斜粗体文本
```
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```

## Markdown分割线

>常见在一行中使用三个以上的星号、减号、底线来创建一个分割线
>以下的几种都阔以的
```
***

* * *

*****

- - -

----------
```

## Markdown删除线

>~~这是一个删除线~~
```
~~删除线在这里~~
```

## Markdown下划线
>可以使用html的`<u>` 标签来实现
><u>我下面有下划线</u>
```
<u>我下面会有下划线</u>
```

## Markdown脚注
>脚注的格式是这样的：
>`[^要加脚注的文本]`
>我后面有一个脚注[^我是脚注]

## Markdown列表
>支持两种列表，有序列表和无序列表
>无序列表使用星号`*` 、加号`+` 或者减号`-` 作为列表标记，后面再加上一个空格
>有序列表使用数字加上一个`.` 
### 列表嵌套
>列表嵌套只需在子列表中的选项前面添加两个或四个空格即可

## Markdown区块
>符号`>` 加上一个<kbd>空格</kbd>
>区块可嵌套

```
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
```

>在列表中使用区块

```
* 第一项
    > 我是第一行
    > 我是第一行的下一行，第二行
* 第二项
```

## Markdown代码

- 用反引号包起来
- 一整段代码可以用三个反引号包起来

## Markdown链接
>链接构成：`[链接名称](链接地址)` 
>或者直接使用地址：`<https://xiaohans.xyz>`

## Markdown图片
>构成如下
```
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```
>要想设定图片的高度和宽度，可以使用H5标签
```
<img src="https://www.xiaohans.xyz/images/logo.png" width="50%">
```

## Markdown表格
>用制表符`|` 来分隔单元格
>用`-` 来分隔表头和其他行
```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```
>我们还可以设置表格的对齐方式
```
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```


---

## Obisian的callout block

- note
- abstract, summary, tldr
- info, todo
- tip, hint, important
- success, check, done
- question, help, faq
- warning, caution, attention
- failure, fail, missing
- danger, error
- bug
- example
- quote, cite


- note（注释）  
- abstract（摘要）、summary（概要）、tldr（简洁版）  
- info（信息）、todo（待办事项）  
- tip（提示）、hint（提示）、important（重要的）  
- success（成功）、check（检查）、done（完成）  
- question（问题）、help（帮助）、faq（常见问题解答）  
- warning（警告）、caution（注意）、attention（注意）  
- failure（失败）、fail（失败）、missing（缺失）  
- danger（危险）、error（错误）  
- bug（漏洞）  
- example（示例）  
- quote（引述）、cite（引用）
