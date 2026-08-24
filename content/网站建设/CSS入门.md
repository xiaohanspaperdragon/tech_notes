---
title: CSS入门
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - css
  - blog
  - 前端
created: 2025-01-27
modified: 2025-08-05
draft: false
description: CSS入门
---


# CSS入门：让你的网页“美”起来

嘿，大家好，我是潇寒！今天咱们来聊聊CSS，这个能让网页变美的神奇魔法。CSS，也就是层叠样式表（Cascading Style Sheets），它就像给网页穿上了五彩斑斓的衣服，让原本枯燥的网页内容瞬间鲜活起来。别急，接下来我就带你一步步走进CSS的世界。

## 一、CSS的基本概念

CSS主要是用来设置HTML页面中的文本内容（字体、颜色、间距等）、图片的外形（宽高、边框样式、边距等）以及版面的布局等外观显示样式。简单来说，HTML是网页的骨架，而CSS就是给骨架穿上漂亮的衣服，化上精致的妆容。

## 二、CSS的引入方式

### （一）行内样式

这种方式就是直接在HTML标签中使用`style`属性来添加样式。比如：

HTML复制

```html
<p style="color: red; font-size: 20px;">这是一段红色的、字号为20px的文本</p>
```

这种方式简单直接，但缺点也很明显，就是样式和结构混在一起，不利于维护。想象一下，如果一个页面有几百个这样的标签，你得一个个去改样式，岂不是要累死？

### （二）内部样式

在HTML文档的`<head>`部分使用`<style>`标签来定义样式。例如：

HTML复制

```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <p>这是一段蓝色的、字号为16px的文本</p>
</body>
```

这种方式比行内样式好一些，至少把样式集中管理了。但当多个页面需要使用相同的样式时，就显得有些力不从心了。

### （三）外部样式

这是最常用也是最推荐的方式。把样式写在一个单独的`.css`文件中，然后在HTML页面中通过`<link>`标签引入。比如：

HTML复制

```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

在`styles.css`文件中：

css复制

```css
p {
    color: green;
    font-size: 14px;
}
```

这样一来，多个页面都可以共享这个样式文件，大大提高了代码的复用性，维护起来也方便多了。

## 三、CSS选择器

要想给特定的元素添加样式，就得先选中它们，这就需要用到选择器了。

### （一）元素选择器

直接用HTML标签名作为选择器。比如：

css复制

```css
p {
    /* 选中所有的p标签 */
    color: purple;
}
```

### （二）类选择器

在HTML元素中使用`class`属性来定义类，然后在CSS中用点（.）加上类名来选择。例如：

HTML复制

```html
<div class="box">这是一个盒子</div>
```

css复制

```css
.box {
    /* 选中所有class为box的元素 */
    width: 100px;
    height: 100px;
    background-color: yellow;
}
```

### （三）ID选择器

在HTML元素中使用`id`属性来定义ID，然后在CSS中用井号（#）加上ID名来选择。注意，ID在页面中是唯一的。比如：

HTML复制

```html
<div id="unique-box">这是一个独一无二的盒子</div>
```

css复制

```css
#unique-box {
    /* 选中id为unique-box的元素 */
    width: 200px;
    height: 200px;
    background-color: pink;
}
```

## 四、CSS的基本属性

### （一）文本样式

- `color`：设置文本颜色。比如`color: red;`，文本就变成红色的啦。
    
- `font-size`：设置字体大小。像`font-size: 24px;`，字体大小就变成了24px。
    
- `font-family`：设置字体类型。例如`font-family: 'Arial', sans-serif;`，优先使用Arial字体，如果没有就使用系统默认的无衬线字体。
    

### （二）盒子模型相关

- `width`和`height`：设置元素的宽度和高度。比如`width: 300px; height: 200px;`，元素的大小就固定啦。
    
- `border`：设置边框。例如`border: 2px solid black;`，就会有一个2px宽的黑色实线边框。
    
- `padding`：设置内边距。比如`padding: 10px;`，元素内容和边框之间就有了10px的间距。
    
- `margin`：设置外边距。像`margin: 20px;`，元素和其他元素之间就有了20px的间距。
    

## 五、CSS的继承和层叠性

### （一）继承

有些CSS属性是可以继承的，比如`font-size`、`color`等。当父元素设置了这些属性，子元素就会自动继承。比如：

HTML复制

```html
<div style="color: orange;">
    我是父元素
    <p>我是子元素</p>
</div>
```

在这个例子中，`<p>`标签就会继承`<div>`的橙色字体。

### （二）层叠性

当多个CSS规则同时作用于同一个元素时，就会涉及到层叠性。简单来说，就是后面的规则会覆盖前面的规则。比如：

css复制

```css
p {
    color: blue;
}

p {
    color: red;
}
```

最终，`<p>`标签的字体颜色会是红色，因为后面的规则覆盖了前面的。

## 六、常用布局方式

### （一）块级布局

块级元素（如`div`）默认会独占一行，可以通过设置`width`、`height`、`margin`等属性来控制布局。比如：

css复制

```css
.box {
    width: 300px;
    height: 200px;
    margin: 20px auto; /* 水平居中 */
    background-color: lightblue;
}
```

### （二）行内布局

行内元素（如`span`）不会独占一行，多个行内元素会在一行内排列。可以通过设置`display: inline;`来让块级元素变为行内元素。

### （三）弹性布局（Flexbox）

这是一种更强大的布局方式，可以轻松实现复杂布局。比如：

css复制

```css
.container {
    display: flex; /* 开启弹性布局 */
    justify-content: center; /* 水平居中 */
    align-items: center; /* 垂直居中 */
}

.item {
    width: 100px;
    height: 100px;
    background-color: coral;
}
```

HTML复制

```html
<div class="container">
    <div class="item"></div>
</div>
```

这样，`.item`就会在`.container`中水平和垂直居中显示啦。

## 七、总结

CSS就像是网页的魔法师，通过选择器选中元素，然后用各种属性给它们打扮。引入方式有行内、内部和外部三种，外部引入最常用。文本样式、盒子模型相关属性是基础中的基础，继承和层叠性让CSS更加灵活。常用的布局方式有块级、行内和弹性布局，弹性布局尤其强大。

好啦，今天关于CSS基础的分享就到这里。希望你能掌握这些知识，让你的网页变得美美哒！如果你还有啥不懂的，欢迎随时来问我哦。