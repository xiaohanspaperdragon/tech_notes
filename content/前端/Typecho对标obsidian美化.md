## 启用数学公式渲染

>笔者使用的笔记是Obsidian,所以被渲染的数学公式要以`$ $` 或`$$ $$` 包含

**手动添加 MathJax 脚本**
**如果找不到合适的插件，可直接在主题模板中插入 MathJax 代码。**

### 步骤 1：修改主题文件
打开当前主题的 footer.php 文件（路径：/usr/themes/your-theme/）。

在 </body> 标签前插入以下代码：

```html
<script>
MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']],
    displayMath: [['$$', '$$'], ['\\[', '\\]']]
  }
};
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
```

### 步骤 2：测试公式
在文章中插入公式并检查渲染效果。

这个错误表明你的电脑浏览器无法从 `cdn.jsdelivr.net` 加载 MathJax 资源，通常是由于网络连接问题导致的。以下是解决方案：

## **使用本地托管**（最稳定）
1. 1. 下载 MathJax 3.2.2 的 [tex-mml-chtml.js](https://github.com/mathjax/MathJax/archive/refs/tags/3.2.2.zip)
2. 2. 上传到你的服务器（如 `/usr/themes/你的主题/js/mathjax/`）
3. 3. 修改引用路径：
   ```html
   <script src="/usr/themes/你的主题/js/mathjax/tex-mml-chtml.js"></script>
   ```


- - -

## 代码高亮
### 使用 Prism.js 实现复杂高亮**

Prism.js 支持插件扩展，可添加行号、高亮指定行、语言扩展等功能。

#### **1. 引入 Prism.js 核心 + 插件**

在主题的 `header.php` 或自定义模板中，添加以下资源（根据需求选择插件）：

```html

<!-- Prism.js 核心 -->
<link href="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/themes/prism.min.css" rel="stylesheet">
<script src="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/prism.min.js"></script>

<!-- 扩展：行号插件 -->
<link href="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/plugins/line-numbers/prism-line-numbers.min.css" rel="stylesheet">
<script src="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/plugins/line-numbers/prism-line-numbers.min.js"></script>

<!-- 扩展：高亮指定行插件 -->
<script src="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/plugins/line-highlight/prism-line-highlight.min.js"></script>
<link href="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/plugins/line-highlight/prism-line-highlight.min.css" rel="stylesheet">

<!-- 扩展：语言支持（如Python、Java、C++） -->
<script src="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/components/prism-python.min.js"></script>
<script src="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/components/prism-java.min.js"></script>
<script src="https://cdn.bootcdn.net/ajax/libs/prism/1.25.0/components/prism-cpp.min.js"></script>
```
#### **2. 配置代码块样式**

在主题的 CSS 文件中添加以下规则，启用行号和高亮行功能：

```css
/* 强制代码块换行 */
pre[class*="language-"] {
  white-space: pre-wrap !important;
  word-break: break-word !important;
}

/* 行号样式 */
pre.line-numbers {
  position: relative;
  padding-left: 3.8em;
  counter-reset: linenumber;
}

.line-numbers-rows {
  position: absolute;
  pointer-events: none;
  top: 0;
  left: -3.8em;
  width: 3em;
  letter-spacing: -1px;
  border-right: 1px solid #999;
  user-select: none;
}

/* 高亮指定行（例如第2-4行） */
pre[data-line] {
  position: relative;
}

.line-highlight {
  background: rgba(255, 255, 0, 0.2);
  left: -3.8em !important; /* 与行号对齐 */
}
```

#### **3. 编写带高级功能的代码块**

在文章中使用 Markdown 语法，并通过 `data-line` 属性指定高亮行：

```markdown
```python {data-line="2-4"}
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b
        
```

- - - 

## 用`==`来强调内容

在 Typecho 中，默认的 Markdown 语法并不直接支持通过 `==` 符号来强调内容（类似于某些 Markdown 扩展中的「高亮」功能）。但可以通过以下两种方法实现类似效果：

---

### **方法一：修改 Markdown 解析器（进阶）**
#### 1. **修改 Parsed.php 文件**
Typecho 的 Markdown 解析器位于 `/var/Typecho/Common/Markdown/Parsed.php`。  
在文件中添加对 `==` 符号的解析规则，将其转换为 `<mark>` 标签：

1. 找到 `_doItalicsAndBold` 方法，添加以下正则表达式规则：
   ```php
   // 匹配 ==高亮== 语法
   $text = preg_replace('/==(.+?)==/s', '<mark>\1</mark>', $text);
   ```

2. **注意**：修改核心文件后，Typecho 升级时可能被覆盖，建议备份或通过插件实现。

---

### **方法二：通过 CSS/JavaScript 实现（推荐）**
#### 1. **使用 CSS 直接渲染 == 符号**
在主题的 CSS 文件中添加样式，将 `==内容==` 转换为带背景色的高亮效果：

```css
/* 自定义 ==高亮== 样式 */
article .markdown-body del del { 
  /* 通过删除线嵌套实现（需配合JS替换） */
  background-color: #ffeb3b; 
  color: inherit; 
  text-decoration: none; 
  padding: 0 0.2em; 
}
```

#### 2. **通过 JavaScript 动态替换**
在主题的 `footer.php` 中添加 JavaScript 代码，自动将 `==内容==` 转换为 `<mark>` 标签：

```javascript
<script>
document.addEventListener('DOMContentLoaded', function() {
  // 匹配 ==内容== 并替换为 <mark>
  document.querySelectorAll('.post-content').forEach(el => {
    el.innerHTML = el.innerHTML.replace(/==(.*?)==/g, '<mark>$1</mark>');
  });
});
</script>
```

---

### **使用示例**
在文章中直接书写：
```markdown
这是一段 ==需要高亮== 的文字。
```
**效果**：  
这是一段 <mark style="background: #ffeb3b; padding: 0 0.2em;">需要高亮</mark> 的文字。

---

### **注意事项**
1. **正则表达式限制**：  
   JavaScript 的简单替换可能无法处理嵌套 Markdown 语法（如 `==**加粗高亮**==`），需根据需求调整正则表达式。

2. **代码块冲突**：  
   如果要在代码块中使用 `==` 符号，需禁用替换规则，或在正则表达式中排除代码块。

3. **主题兼容性**：  
   确保 CSS 选择器（如 `.post-content`）与你的主题文章容器类名匹配。

---

### **替代方案：使用现有 Markdown 标签**
如果不想修改解析器或添加脚本，可用原生 Markdown 语法配合 CSS 实现类似效果：
```markdown
用 <mark>自定义高亮</mark> 或 <span class="highlight">文本</span>。
```
然后在 CSS 中定义 `.highlight` 样式。

---

选择适合你需求的方法即可。推荐 **方法二**（CSS/JS 替换），无需修改核心文件且兼容性较好。

- - - 

要在 Typecho 中将引用块（`>` 语法生成的 `<blockquote>` 标签）的左边框样式改为类似 Obsidian 的紫色效果，只需通过 **自定义 CSS** 修改边框颜色和样式即可。以下是具体实现步骤：

---

##  引用块的对标
>[!important]
```c
/* 引用块样式：紫色左边框 + 圆角 */
blockquote {
  border-left: 4px solid #9a6fc4 !important; /* Obsidian 风格紫色 */
  margin: 1.5em 0;
  padding: 0.8em 1.2em;
  background-color: #f9f9f9; /* 浅灰色背景 */
  color: #333; /* 文字颜色 */
  border-radius: 15px; /* 统一四个角的圆角（或单独控制左右） */
  /* 如果只想右侧有圆角，可以这样写： */
  /* border-radius: 0 8px 8px 0; */ /* 左上、右上、右下、左下 */
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}
```

### **步骤 1：找到并编辑主题的 CSS 文件**
1. 进入 Typecho 后台的 **「控制台」→「外观」**，确认你当前使用的主题。
2. 通过 FTP 或服务器文件管理器，找到主题目录：`/usr/themes/你的主题名称/`。
3. 编辑主题的 CSS 文件（通常是 `style.css` 或 `screen.css`）。

---

### **步骤 2：添加自定义 CSS 样式**
在 CSS 文件末尾添加以下代码（模仿 Obsidian 的紫色风格）：

```css
/* 引用块样式：紫色左边框 */
blockquote {
  border-left: 4px solid #9a6fc4 !important; /* Obsidian 风格紫色 */
  margin: 1.5em 0;
  padding: 0.8em 1.2em;
  background-color: #f9f9f9; /* 浅灰色背景（可选） */
  color: #333; /* 文字颜色 */
  border-radius: 0 4px 4px 0; /* 右侧圆角 */
}
```

---

### **效果对比**
| 默认样式                                                                     | 修改后的 Obsidian 风格                                                             |
| ------------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| ![默认引用块](https://dummyimage.com/400x100/eee/aaa&text=Default+Blockquote) | ![紫色边框引用块](https://dummyimage.com/400x100/f9f9f9/9a6fc4&text=Obsidian+Style) |

---

### **高级定制（可选）**
1. **动态渐变边框**：  
   如果希望更接近 Obsidian 的现代风格，可以使用渐变色边框：
   ```css
   blockquote {
     padding: 1em;
     margin: 1em 0;
     background: linear-gradient(to right, #f9f9f9, #fff);
     border-left: 4px solid;
     border-image: linear-gradient(to bottom, #9a6fc4, #7d4d9a) 1 100%;
   }
   ```

2. **添加阴影**：  
   模仿 Obsidian 的柔和阴影效果：
   ```css
   blockquote {
     box-shadow: 2px 0 8px rgba(154, 111, 196, 0.1);
   }
   ```

3. **自定义图标**：  
   在左侧添加小图标（需引入图标库如 Font Awesome）：
   ```css
   blockquote::before {
     content: "\f10d"; /* Font Awesome 的引用图标 */
     font-family: "Font Awesome 5 Free";
     color: #9a6fc4;
     margin-right: 10px;
   }
   ```

---

### **注意事项**
1. **选择器优先级**：  
   如果主题原有样式未生效，可通过 `!important` 强制覆盖（如示例代码所示）。  
   **优化方案**：使用更具体的选择器（如 `.post-content blockquote`）。

2. **清除缓存**：  
   修改 CSS 后，按 `Ctrl + F5` 强制刷新浏览器缓存查看效果。

3. **Obsidian 主题适配**：  
   若需完全复刻 Obsidian 的暗色模式，可调整颜色值：
   ```css
   /* 暗色模式适配 */
   blockquote {
     border-left-color: #7d4d9a;
     background-color: #2a2a2a;
     color: #e0e0e0;
   }
   ```

---

完成上述修改后，Typecho 的引用块便会呈现与 Obsidian 相似的紫色边框效果。如果遇到样式冲突，可通过浏览器的 **开发者工具（F12）** 检查元素并调试。

- - - 
