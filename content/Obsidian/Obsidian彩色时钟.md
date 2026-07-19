---
tags:
  - obsidian/plugins/dataview
aliases:
  - Obsidian彩色时钟
---

#### 原理：
[[Obsidian的可编程性#插件如何“劫持”代码块]]

#### 样例代码

```dataviewjs
// --- 1. 定义时钟的 HTML 结构 ---
const clockHTML = `
<div id="clock" class="progress-clock">
    <button class="progress-clock__time-date" data-group="d" type="button">
        <small data-unit="w">星期四</small><br>
        <span data-unit="mo">六月</span>
        <span data-unit="d">20</span>
    </button>
    <button class="progress-clock__time-digit" data-unit="h" data-group="h" type="button">12</button>
    <span class="progress-clock__time-colon">:</span>
    <button class="progress-clock__time-digit" data-unit="m" data-group="m" type="button">30</button>
    <span class="progress-clock__time-colon">:</span>
    <button class="progress-clock__time-digit" data-unit="s" data-group="s" type="button">55</button>
    <span class="progress-clock__time-ampm" data-unit="ap">pm</span>
    <svg class="progress-clock__rings" width="256" height="256" viewBox="0 0 256 256">
        <g data-units="d">
            <circle class="progress-clock__ring" cx="128" cy="128" r="74" fill="none" opacity="0.1" stroke="#e13e78" stroke-width="12"></circle>
            <circle class="progress-clock__ring-fill" data-ring="mo" cx="128" cy="128" r="74" fill="none" stroke="#e13e78" stroke-width="12" stroke-dasharray="465 465" stroke-dashoffset="0" stroke-linecap="round" transform="rotate(-90,128,128)"></circle>
        </g>
        <g data-units="h">
            <circle class="progress-clock__ring" cx="128" cy="128" r="90" fill="none" opacity="0.1" stroke="#e79742" stroke-width="12"></circle>
            <circle class="progress-clock__ring-fill" data-ring="d" cx="128" cy="128" r="90" fill="none" stroke="#e79742" stroke-width="12" stroke-dasharray="565.5 565.5" stroke-dashoffset="0" stroke-linecap="round" transform="rotate(-90,128,128)"></circle>
        </g>
        <g data-units="m">
            <circle class="progress-clock__ring" cx="128" cy="128" r="106" fill="none" opacity="0.1" stroke="#4483ec" stroke-width="12"></circle>
            <circle class="progress-clock__ring-fill" data-ring="h" cx="128" cy="128" r="106" fill="none" stroke="#4483ec" stroke-width="12" stroke-dasharray="666 666" stroke-dashoffset="0" stroke-linecap="round" transform="rotate(-90,128,128)"></circle>
        </g>
        <g data-units="s">
            <circle class="progress-clock__ring" cx="128" cy="128" r="122" fill="none" opacity="0.1" stroke="#8f30eb" stroke-width="12"></circle>
            <circle class="progress-clock__ring-fill" data-ring="m" cx="128" cy="128" r="122" fill="none" stroke="#8f30eb" stroke-width="12" stroke-dasharray="766.5 766.5" stroke-dashoffset="0" stroke-linecap="round" transform="rotate(-90,128,128)"></circle>
        </g>
    </svg>
</div>
`;

// 将 HTML 渲染到 Dataview 容器中
dv.container.innerHTML = clockHTML;

// --- 2. JavaScript 逻辑 ---
// DataviewJS 内置了 moment.js
const dateElements = {
    week: dv.container.querySelector('[data-unit="w"]'),
    month: dv.container.querySelector('[data-unit="mo"]'),
    day: dv.container.querySelector('[data-unit="d"]'),
};
const timeElements = {
    hour: dv.container.querySelector('[data-unit="h"]'),
    minute: dv.container.querySelector('[data-unit="m"]'),
    second: dv.container.querySelector('[data-unit="s"]'),
    ampm: dv.container.querySelector('[data-unit="ap"]'),
};
const ringFills = {
    day: dv.container.querySelector('[data-ring="mo"]'),
    hour: dv.container.querySelector('[data-ring="d"]'),
    minute: dv.container.querySelector('[data-ring="h"]'),
    second: dv.container.querySelector('[data-ring="m"]'),
};

// 主更新函数
function updateClock() {
    moment.locale('zh-cn');
    const now = moment();
    const formatDate = now.format("dddd-MMMM-D-H-mm-ss-a").split("-");
    const [week, month, day, hour, minute, second, ampm] = formatDate;

    if (dateElements.week) dateElements.week.textContent = week;
    if (dateElements.month) dateElements.month.textContent = month;
    if (dateElements.day) dateElements.day.textContent = day;
    
    if (timeElements.hour) timeElements.hour.textContent = hour;
    if (timeElements.minute) timeElements.minute.textContent = minute;
    if (timeElements.second) timeElements.second.textContent = second;
    if (timeElements.ampm) timeElements.ampm.textContent = ampm;

    const daysInMonth = now.daysInMonth(); 
    const secProgress = second / 60;
    const minProgress = (parseInt(minute) + secProgress) / 60;
    const hourProgress = (parseInt(hour) + minProgress) / 24;
    const dayProgress = (parseInt(day) - 1 + hourProgress) / daysInMonth;

    const circumferences = { day: 465, hour: 565.5, minute: 666, second: 766.5 };

    if (ringFills.second) ringFills.second.setAttribute('stroke-dashoffset', (1 - secProgress) * circumferences.second);
    if (ringFills.minute) ringFills.minute.setAttribute('stroke-dashoffset', (1 - minProgress) * circumferences.minute);
    if (ringFills.hour) ringFills.hour.setAttribute('stroke-dashoffset', (1 - hourProgress) * circumferences.hour);
    if (ringFills.day) ringFills.day.setAttribute('stroke-dashoffset', (1 - dayProgress) * circumferences.day);
}

// 首次加载时立即执行一次
updateClock();

// **--- 以下是修正部分 ---**

// 设置定时器，每秒更新一次，并保存其 ID
const intervalId = window.setInterval(updateClock, 1000);

// 使用 dv.container.onunload 注册一个清理函数。
// 当这个 Dataview 块从 DOM 中卸载时 (例如切换笔记或关闭此文件)，
// 这个函数会被自动调用，从而清除我们的定时器。
dv.container.onunload = () => {
    window.clearInterval(intervalId);
}
```

#### CSS代码（添加到.obsidian/snippets文件夹下）：
```css
/*

  Colorful Clock CSS Snippet for Obsidian

  Version 9 - The Minimal Fix

*/

  

/* 基础容器的 Grid 布局是正确的，保持不变 */

.progress-clock {

  display: grid;

  justify-content: center;

  align-content: center;

  position: relative;

  text-align: center;

  height: 15em;

  width: 15em;

  margin: 2em auto;

}

  

.progress-clock button {

  padding: 0; border: none; box-shadow: none;

  background-color: transparent; display: block;

  color: var(--text-normal);

}

.progress-clock button:hover { background-color: transparent; }

  

/*

  --- 关键修改 #1：让所有文本元素成为可堆叠的图层 ---

  我们给所有文本元素加上 position: relative 和一个较高的 z-index，

  把它们从默认层“拉”到上层。

*/

.progress-clock__time-date,

.progress-clock__time-digit,

.progress-clock__time-colon,

.progress-clock__time-ampm {

  position: relative; /* z-index 生效的前提 */

  z-index: 2;         /* 确保在最上层 */

  

  /* 以下是原有的样式，保持不变 */

  font: 1em/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;

  transition: color 0.2s linear;

  -webkit-user-select: none;

  -moz-user-select: none;

  user-select: none;

}

  

.progress-clock__time-date,

.progress-clock__time-digit {

  background: transparent;

}

  

/* 以下所有的 Grid 布局规则都是正确的，保持不变 */

.progress-clock__time-date,

.progress-clock__time-ampm {

  grid-column: 1 / 6;

}

.progress-clock__time-date {

  font-size: 0.75em;

  line-height: 1.33;

}

.progress-clock__time-digit,

.progress-clock__time-colon {

  font-size: 1.6em;

  font-weight: 400;

  grid-row: 2;

  margin: 0;

}

.progress-clock__time-colon { line-height: 1.5em; }

.progress-clock__time-ampm { cursor: default; grid-row: 3; }

  
  

/*

  --- 关键修改 #2：让圆环也成为一个图层，但层级较低 ---

  我们不再使用 z-index: -1，而是给它一个正数，但比文本的要低。

*/

.progress-clock__rings {

  display: block;

  position: absolute;

  top: 0;

  left: 0;

  width: 100%;

  height: 100%;

  z-index: 1; /* 比文本的 z-index: 2 要低，所以会在文本下面 */

  opacity: 0.6;

}

  
  

/* 其他样式保持不变 */

.progress-clock__ring { opacity: 0.1; }

.progress-clock__ring-fill { transition: opacity 0s 0.3s linear, stroke-dashoffset 0.3s ease-in-out; }

[data-group]:focus { outline: transparent; }

[data-units] { transition: opacity 0.2s linear; }

[data-group="d"]:focus, [data-group="d"]:hover { color: hsl(333,90%,55%); }

[data-group="h"]:focus, [data-group="h"]:hover { color: hsl(33,90%,55%); }

[data-group="m"]:focus, [data-group="m"]:hover { color: hsl(213,90%,55%); }

[data-group="s"]:focus, [data-group="s"]:hover { color: hsl(273,90%,55%); }

[data-group]:focus ~ .progress-clock__rings [data-units],

[data-group]:hover ~ .progress-clock__rings [data-units] { opacity: 0.2; }

[data-group="d"]:focus ~ .progress-clock__rings [data-units="d"],

[data-group="d"]:hover ~ .progress-clock__rings [data-units="d"],

[data-group="h"]:focus ~ .progress-clock__rings [data-units="h"],

[data-group="h"]:hover ~ .progress-clock__rings [data-units="h"],

[data-group="m"]:focus ~ .progress-clock__rings [data-units="m"],

[data-group="m"]:hover ~ .progress-clock__rings [data-units="m"],

[data-group="s"]:focus ~ .progress-clock__rings [data-units="s"],

[data-group="s"]:hover ~ .progress-clock__rings [data-units="s"] { opacity: 1; }
```