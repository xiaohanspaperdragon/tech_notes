---
title: HTML基础
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - HTML
  - blog
  - 前端
created: 2025-01-26
modified: 2025-08-05
draft: false
description: HTML基础
---


# HTML简介
>超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言
>
>HTML不是编程语言，而是一种标记语言，它使用标签来描述网页
>web浏览器可以读取HTML文件并将内容显示给用户

>完整的html通常包含以下几个元素

- `<!DOCTYPE html>`  声明为 HTML5 文档
- `<html>` 元素是 HTML 页面的根元素
- `<head>` 元素包含了文档的元数据(meta)
- `title` 文档的标题
- `<body>` 是html页面的可见内容
## 编辑器
>笔者主要使用占IDE半边天的Visual Studio Code,它是一款由微软推出的免费、开源、跨平台的代码编辑器，功能十分强大
>也可以使用Brakets等专门针对前端三件套的编辑器，它原生支持实时预览，当然vs code装上插件也可以实现

# HTML头部
## head元素
| 标签             | 描述                |
| -------------- | ----------------- |
| ==`<head>`==   | 定义文档信息            |
| ==`<title>`==  | 定义文档标题            |
| ==`<base>`==   | 定义了页面链接标签的默认链接地址  |
| ==`<link>`==   | 定义了一个文档和外部资源之间的关系 |
| ==`<meta>`==   | 定义了html文档中的元数据    |
| ==`<script>`== | 定义了客户端的脚本文件       |
| ==`<style>`==  | 定义了html文档的样式文件    |

>一个简单的html文档
```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>标题</title>
</head>
 
<body>
可视内容...
</body>
 
</html>
```
>==`<link>`== 元素实例
```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```
>==`<style>`== 元素实例
```html
<head>
<style type="text/css">
body {
    background-color:yellow;
}
p {
    color:blue
}
</style>
</head>
```
## `<meta>` 元素
>meta标签描述了基本的元数据
>元数据不会显示在可视的页面上，但会被浏览器解析
>==`<meta>`== 元素通常用于网页的描述，关键词，文件的最后修改时间，作者等其他元数据

>通过meta标签的 charset属性来规定HTML文档应该使用哪种字符编码
>==`<meta charset="utf-8">`==

### 示例
>为搜索引擎定义关键词
>==`<meta name="keywords" content="HTML, CSS, XML JavaScript">`== 
>
>为网页定义描述内容
>==`<meta name="description" content="前端笔记教程">`== 
>
>定义网页作者
>==`<meta name="author" content="Xiaohans">`== 
>
>每30秒钟刷新当前页面
>==`<meta http-equiv="refresh" content="30">`== 

# HTML文本

| ==标签==          | ==描述==         |
| --------------- | -------------- |
| `<html>`        | 定义html文档       |
| `<body>`        | 定义文档的主体        |
| ==`<h1>`==      | 最大的标题          |
| `<h2>`          |                |
| `<h3>`          |                |
| `<h4>`          |                |
| `<h5>`          |                |
| ==`<h6>`==      | 最小的标题          |
| `<hr>`          | ==水平线==，用于分隔内容 |
| `<!-- 我是注释 -->` | 注释             |
| `<p>`           | 定义段落(块级元素)     |
| `<br>`          | ==换行==         |
### 文本格式化

>不建议刻意使用格式化标签来达到粗体等字体的效果，因为这会影响到SEO，推荐使用css

| 标签             | 描述     | "计算机输出"标签    | 描述        | 引用、引文及标签定义      | 描述        |
| -------------- | ------ | ------------ | --------- | --------------- | --------- |
| ==`<b>`==      | 定义粗体文字 | ==`<code>`== | 定义计算机代码   | `<abbr>`        | 定义缩写      |
| ==`<em>`==     | 定义着重文字 | ==`<kbd>`==  | 定义键盘码     | ==`<address>`== | 定义地址      |
| ==`<i>`==      | 定义斜体字  | `<samp>`     | 定义计算机代码样本 | `<bdo>`         | 定义文字方向    |
| ==`<small>`==  | 定义小号子  | `<var>`      | 定义变量      | `<blockquote`   | 定义长的引用    |
| ==`<strong>`== | 定义加重语气 | `<pre>`      | 定义预格式文本   | `<q>`           | 定义短语的而引用语 |
| ==`<sub>`==    | 定义下标字  |              |           | `<cite>`        | 定义引用、引证   |
| ==`<sup>`==    | 定义上标字  |              |           | `<dfn>`         | 定义一个定义项目  |
| `<ins>`        | 定义插入字  |              |           |                 |           |
| ==`<del>`==    | 定义删除字  |              |           |                 |           |

# HTML链接
## 简介
>使用链接Anchor可以实现网页之间的跳转
>语法：`<a href="URL">链接文本</a>`
>默认样式：未访问为蓝色字体加下划线，访问过的为紫色带下划线，点击时为红色带下划线

## 特殊属性

| 标签    | 属性         | 值            | 描述                                |
| ----- | ---------- | ------------ | --------------------------------- |
| `<a>` | ==target== | ==`_blank`== | 新窗口或新标签打开                         |
|       |            | `_self`      | 当前窗口或标签页打开                        |
|       |            | `_parent`    | 在父框架中打开链接                         |
|       |            | `_top`       | 在整个窗口中打开链接。取消任何框架                 |
|       | ==href==   |              | 链接目标，可以是网页、文件、邮件、电话号码或者javascript |
|       | download   | 文件名          | 提示浏览器下载链接目标，若指定文件名会下载并保存为指定文件名    |
|       | title      | 额外信息的文本      | 鼠标悬停的提示                           |
|       | hreflang   |              | 指定链接目标的URL语言                      |
## 常见示例

>文本链接
>`<a href="https://www.xiaohans.xyz">访问潇寒主页</a>`

>图片链接
```html
<a href="https://www.xiaohans.xyz">
  <img src="example.png" alt="潇寒的示例图片">
</a>
```

>锚点链接
```html
<a href="#section2">跳转到第二个部分</a>
<!-- 在页面中的某个位置 -->
<a name="section2"></a>
```

>下载链接
```html
<a href="document.pdf" download>下载文档</a>
```

>==复杂的电子邮件链接==
```html
<p>
这是另一个电子邮件链接：
<a href="mailto:xiaohans@xiaohans.xyz?cc=xiaohans002@xiaohans.xyz&bcc=xiaohans003@xiaohans.xyz&subject=Hello%20Xiaohan&body=You%20are%20invited%20to%20a%20big%20party!" target="_top">发送邮件!</a>
</p>
```
>mailto:收件人
>cc:抄送
>bcc:密件抄送
>subject:主题
>body:正文
>&:链接各个部分
>%20:单词之间的空格

# HTML媒体
## HTML图像
>语法
>`<img src="url" alt="text">`
### 设置高度和宽度
>示例
>`<img src="ex.jpg" alt="ex" width="300" height="200">`

### 图像标签

| 标签       | 描述           |
| -------- | ------------ |
| `<img>`  | 图像           |
| `<map>`  | 图像地图         |
| `<area>` | 定义图像地图的可点击区域 |
## HTML5 Video视频
```html
<video width="300" height="200" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
您的浏览器不支持Video标签。
</video>
```
### 视频格式

| 格式   | MIME-type  |
| ---- | ---------- |
| MP4  | video/mp4  |
| WebM | video/webm |
| Ogg  | video/ogg  |
### track标签
>定义在媒体播放器的文本轨迹
>下面是一个带上字幕的示例
```html
<video width="300" height="200" controls>
<video controls
       src="/video/xiaohans.mp4">
    <track default
           kind="captions"
           srclang="en"
           src="/video/xiaohans.vtt" />
    抱歉，您的浏览器不支持嵌入视频！
</video>
</video>
```

## HTML5 Audio音频
```html
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
您的浏览器不支持 audio 元素。
</audio>
```
### 格式

| Format | MIME-type  |
| :----- | :--------- |
| MP3    | audio/mpeg |
| Ogg    | audio/ogg  |
| Wav    | audio/wav  |

# HTML表格

| 标签           | 描述   |
| ------------ | ---- |
| `<table>`    | 定义表格 |
| `<th>`       | 表头   |
| `<tr>`       | 行    |
| `<td>`       | 单元   |
| `<caption>`  | 标题   |
| `<colgroup>` | 列的组  |
| `<col>`      | 列的属性 |
| `<thead>`    | 页眉   |
| `<tbody>`    | 主题   |
| `<tfoot>`    | 页脚   |
>示例如下
```html
<table border="1">
    <tr>
        <td>row 1, cell 1</td>
        <td>row 1, cell 2</td>
    </tr>
    <tr>
        <td>row 2, cell 1</td>
        <td>row 2, cell 2</td>
    </tr>
</table>
```

# HTML列表
## HTML无序列表
```html
<ul>  
<li>Coffee</li>  
<li>Milk</li>  
</ul>
```
>圆点列表
```html
<ul style="list-style-type:disc">
 <li>ex</li>
</ul>  
```
>圆圈列表
```html
<ul style="list-style-type:circle">
 <li>ex</li>
</ul>  
```
>正方形列表
```html
<ul style="list-style-type:square">
 <li>ex</li>
</ul>
```

## HTML有序列表
```html
<ol>  
<li>Coffee</li>  
<li>Milk</li>  
</ol>
```

| 属性   | 值   | 描述       |
| ---- | --- | -------- |
| type | A   | 大写字母列表   |
|      | a   | 小写字母列表   |
|      | I   | 罗马数字列表   |
|      | i   | 小写罗马数字列表 |

## HTML自定义列表
```html
<dl>  
<dt>Coffee</dt>  
<dd>- black hot drink</dd>  
<dt>Milk</dt>  
<dd>- white cold drink</dd>  
</dl>
```

# HTML表单
## 文本
```html
<form>
First name: <input type="text" name="firstname"><br>
Last name: <input type="text" name="lastname">
</form>
```

## 密码
```html
<form>
Password: <input type="password" name="pwd">
</form>
```

## 单选按钮
```html
<form action="">
<input type="radio" name="sex" value="male">男<br>
<input type="radio" name="sex" value="female">女
</form>
```

## 复选框
```html
<form>
	<input type="checkbox" id="agree" name="agree" value="agree" required>

	<lable for="agree">我已阅读并同意《用户协议》</lable>
</form>
```

## 提交按钮
```html
<form name="input" action="html_form_action.php" method="get">
Username: 
	<input type="text" name="user">
	<input type="submit" value="Submit">
</form>
```

## 下拉菜单
```html
<form>
	<lable for="country">国家</lable>

		<select id="country" name="country">

			<!-- 东区选项组 -->

			<optgroup label="east">

				<!-- 中国选项 -->

				<option value="CN">CN</option>

				<!-- 日本选项 -->

				<option value="JP">JP</option>

			</optgroup>

			<!-- 西区选项组 -->

			<optgroup label="west">

				<!-- 美国选项 -->

				<option value="US">US</option>

				<!-- 英国选项 -->

				<option value="UK">UK</option>

			</optgroup>

		</select>
</form>
```

## 邮件输入框
```html
<form>
<!-- 邮箱标签 -->

<lable for="email">邮箱：</lable>

<!-- 邮箱输入框，必须填写 -->

<input type="email" id="email" name="email" required>
</form>
```

## 留言文本框
```html
<form>
<!-- 留言标签 -->

<lable for="message">留言：</lable>

<!-- 留言文本框，必须填写 -->

<textarea id="message" name="message" rows="5" cols="30" required></textarea>
</form>
```

>下面是一些额外的实例
>带边框的表单
```html
<fieldset>
<legend>Personal information:</legend>
Name: <input type="text" size="30"><br>
E-mail: <input type="text" size="30"><br>
Date of birth: <input type="text" size="10">
</fieldset>
</form>
```
>从表单发送电子邮件
```html
<form action="MAILTO:someone@example.com" method="post" enctype="text/plain">
Name:<br>
<input type="text" name="name" value="your name"><br>
E-mail:<br>
<input type="text" name="mail" value="your email"><br>
Comment:<br>
<input type="text" name="comment" value="your comment" size="50"><br><br>
<input type="submit" value="发送">
<input type="reset" value="重置">
</form>
```

# HTML区块
## 块级元素
>以标签`<div>` 为典型代表
>块级元素独占一行，可以设置宽高和边距等样式
>适用于页面的大块结构，创建结构和布局

## 行内元素
>以`<span>` 为代表
>不会独占一行，宽度由内容决定
>可以包裹文本和其他内行元素

# 其他
>三个常用的字符实体

| 符号      | 描述   | 实体名称      | 实体编号      |
| ------- | ---- | --------- | --------- |
| &copy;  | 版权   | `&copy;`  | `&#169;`  |
| &reg;   | 注册商标 | `&reg;`   | `&#174;`  |
| &trade; | 商标   | `&trade;` | `&#8482;` |
