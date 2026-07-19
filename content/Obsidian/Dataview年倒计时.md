---
tags:
  - obsidian/plugins/dataview
aliases:
  - Dataview年倒计时
---

#### 原理：
[[Obsidian的可编程性#插件如何“劫持”代码块]]

#### 样例代码：

```dataviewjs

const year = dv.current().year || new Date().getFullYear();

let rawCssClasses = dv.current().cssclasses;

let classesArray = [];

if (rawCssClasses) {

    if (Array.isArray(rawCssClasses)) {

        classesArray = rawCssClasses; // 如果本身就是数组，直接使用

    } else {

        classesArray = [String(rawCssClasses)]; // 如果是单个值（字符串），将其放入一个新数组中

    }

}

// --- End of Enhanced Code ---

  

const titleAlignClass = classesArray.find(c => c.startsWith("align-")) ?? "align-left";

  

// 使用 div 显示为块级元素，字体大小和颜色由配套CSS控制

dv.el("div", `${year} 年倒计时`, { cls: `year-title ${titleAlignClass}` });

  

const startDate = moment(`${year}-01-01`);

const endDate = moment(`${year}-12-31`);

const today = moment();

  

const container = dv.el("div", "", { cls: "year-calendar" });

  

for (let d = startDate.clone(); d.isSameOrBefore(endDate); d.add(1, "day")) {

  const dayBox = document.createElement("div");

  dayBox.classList.add("day-box");

  dayBox.setAttribute("title", d.format("YYYY-MM-DD"));

  

  if (d.isBefore(today, 'day')) {

    dayBox.classList.add("past");

  } else if (d.isSame(today, 'day')) {

    dayBox.classList.add("today");

  } else {

    dayBox.classList.add("future");

  }

  

  container.appendChild(dayBox);

}

```

#### CSS代码（添加到.obsidian/snippets文件夹下）：

```css
.year-title {

  margin-bottom: 0.5em;

  font-size: 1.2em;

  color: var(--text-muted);

}

  

.align-left .year-title {

  text-align: left;

}

  

.align-center .year-title {

  text-align: center;

}

  

.align-right .year-title {

  text-align: right;

}

  

.year-calendar {

  display: flex;

  flex-wrap: wrap;

  justify-content: start;

  gap: 0.5px;

}

  

.day-box {

  width: 10px;

  height: 10px;

  border-radius: 1px;

  margin: 1px;

  background-color: white;

  transition: transform 0.2s;

}

  

.day-box.past {

  background-color: #3A353F;

}

  

.day-box.today {

  background-color: #A6D676;

}

  

.day-box.future {

  background-color: #EEE7DF;

  border: 0.5px solid #ddd;

}

  

.day-box:hover {

  transform: scale(1.4);

  cursor: pointer;

}

  

@media (max-width: 600px) {

  .year-calendar {

    justify-content: center;

    gap: 1px;

  }

  

  .day-box {

    width: 8px;

    height: 8px;

    margin: 0.5px;

  }

}
```