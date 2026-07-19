---
title: typecho 美化v0.1
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - typecho
  - css
  - blog
created: 2025-01-24
modified: 2025-08-05
draft: false
description: typecho 美化v0.1
---

```css
/* ------------------------------------
 * Typecho Default Theme
 *
 * @author  Typecho Team
 * @link  http: //typecho.org/
 * @update  2013-10-28
 * --------------------------------- */

/* ------------------
 * Global style
 * --------------- */

:root {
  --primary: #6a5acd;       /* 主紫色 */
  --secondary: #9370db;     /* 次紫色 */
  --dark: #2d2d3d;         /* 深灰 */
  --light: #f8f9fa;        /* 浅灰 */
  --accent: #ff7e5d;       /* 强调色 */
}

body {
  background-color: var(--light);
  color: #444;
  font-family: "Noto Sans SC", "Droid Serif", "PingFang SC", sans-serif;
  font-size: 100%;
  line-height: 1.8;
}

/* ------------------
 * 内容区域宽度扩展
 * --------------- */
.container {
  max-width: 1200px !important; /* 原952px → 1200px */
  padding: 0 30px;
}


a {
  color: var(--primary);
  text-decoration: none;
  transition: all 0.2s;
}
a:hover, a:active {
  color: var(--accent);
  text-decoration: underline;
}

pre, code { 
  background: #f5e9ff;
  font-family: 'Fira Code', Menlo, Monaco, Consolas, monospace;
  border-radius: 4px;
}
code { 
  padding: 2px 4px; 
  color: #b94a48; 
}
pre {
 white-space: pre-wrap;       /* 保留空格但允许换行 */
  word-wrap: break-word;       /* 允许单词内断行 */
  overflow: visible !important; /* 强制禁用滚动条 */
  max-height: none !important; /* 移除高度限制 */
  overflow-x: visible !important; /* 禁用横向滚动 */
  
  /* 增强可读性 */
  padding: 1.2em;
  border-radius: 4px;
  font-family: 'Fira Code', Consolas, Monaco, 'Andale Mono', monospace;
  line-height: 1.6;
}

blockquote {
  border-left: 4px solid var(--primary) !important;
  margin: 1.5em 0;
  padding: 1.2em;
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-radius: 0 12px 12px 0;
  box-shadow: 0 4px 15px rgba(106, 90, 205, 0.1);
  position: relative;
  overflow: hidden;
}

blockquote:hover {
  background: rgba(255, 255, 255, 0.9);
  transition: all 0.3s ease;
}

table {
  border: 1px solid #ddd;
  width: 100%;
}
table th,
table td {
  padding: 5px 10px;
  border: 1px solid #eee;
}
table th {
  background: #f3f3f3;
}

h1, h2, h3, h4, h5, h6 {
  font-family: "Helvetica Neue", Helvetica, Arial, "PingFang SC", "Hiragino Sans GB", "WenQuanYi Micro Hei","Microsoft Yahei", sans-serif;
}

input[type="text"],
input[type="email"],
input[type="url"],
input[type="password"],
textarea {
  padding: 5px;
  border: 1px solid #E9E9E9;
  width: 100%;

  border-radius: 2px;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
textarea {
  resize: vertical;
}


/* Special link style */
.post-meta a,
.post-content a,
.widget a,
.comment-content a {
  border-bottom: 1px solid #EEE;
}

.post-meta a:hover,
.post-content a:hover,
.widget a:hover,
.comment-content a:hover {
  border-bottom-color: transparent;
}

/* ------------------
 * Header
 * --------------- */

#header {
  padding-top: 35px;
  border-bottom: 1px solid #EEE;
  background: linear-gradient(
    135deg, 
    var(--primary) 0%, 
    color-mix(in srgb, var(--primary), white 20%) 30%, 
    color-mix(in srgb, var(--secondary), black 20%) 70%, 
    var(--secondary) 100%
  );
  color: white;
  margin-bottom: 2rem;
}

/* Logo和标题容器：强制同行显示并垂直居中 */
.logo-title-wrap {
    display: flex;
    align-items: center; /* 垂直居中对齐 */
    gap: 15px; /* Logo和标题间距（可调整） */
}

/* Logo图片样式优化（继承原CSS并补充） */
#logo.logo-img {
    display: inline-block; /* 确保不独占一行 */
}
#logo img {
    max-height: 64px; /* 保持原高度 */
    width: auto; /* 防止图片拉伸 */
    vertical-align: middle; /* 对齐文字基线 */
}

/* 文字标题样式（原#logo样式迁移至此） */
#text-logo {
    color: white;
    text-shadow: 1px 1px 3px rgba(0,0,0,0.2);
    font-family: 'Roboto Condensed', sans-serif;
    font-size: 2em; /* 保持原字体大小 */
    text-decoration: none; /* 去除下划线 */
    white-space: nowrap; /* 防止标题换行 */
}

/* 描述文字样式（保持原样式，确保在标题下方） */
.description {
    margin: .5em 0 0;
    color: rgba(255,255,255,0.8);
    font-style: italic;
    text-align: left !important; /* 强制左对齐（核心修复） */
    padding-left: 0 !important; /* 移除可能的左内边距 */
    clear: both; /* 清除浮动影响（若存在） */
}

/* Navigation menu */
#nav-menu {
  margin: 25px 0 0;
  padding: 0;
}
#nav-menu a {
  display: block;
  margin-right: -1px;
  padding: 0 20px;
  border: 1px solid #EEE;
  border-bottom: none;
  height: 32px;
  line-height: 32px;
  color: #444;
  float: left;
}
#nav-menu a:hover,
#nav-menu .current {
  background: #F6F6F6;
}

/* Search */
#search {
  position: relative;
  margin-top: 15px;
}
#search input {
  padding-right: 30px;
}
#search button {
  position: absolute;
  right: 4px;
  top: 2px;
  border: none;
  padding: 0;
  width: 24px;
  height: 24px;
  background: transparent url(img/icon-search.png) no-repeat center center;
  direction: ltr; /* fix RTL language */
  text-indent: -9999em;
}

@media 
(-webkit-min-device-pixel-ratio: 2), 
(min-resolution: 192dpi) {
  #search button {
    background-image: url(img/icon-search@2x.png);
    -webkit-background-size: 24px 24px;
    -moz-background-size: 24px 24px;
    -o-background-size: 24px 24px;
    background-size: 24px 24px;
  }
}


/* ------------------
 * Main
 * --------------- */

.post {
  background: white;
  border-radius: 8px;
  padding: 1.8rem;
  margin: 2rem 0;
  box-shadow: 0 3px 10px rgba(0,0,0,0.05);
  transition: transform 0.3s ease;
  border-top: 3px solid var(--primary);
  max-width: none; /* 移除宽度限制 */
  padding: 2rem 3rem; /* 增加水平内边距 */
}

/* ------------------
 * 标题字体层级放大
 * --------------- */
h1 { font-size: 2.5rem; } /* 原约2rem */
h2 { font-size: 2rem; }
h3 { font-size: 1.75rem; }

.post:hover {
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(106, 90, 205, 0.15);
}

.post-title a { 
  font-size: 2.3rem !important;
  color: var(--primary) !important;
  font-family: 'Roboto Condensed', sans-serif;
}

.post-title a:hover { 
  color: var(--accent) !important; 
}

.post-meta {
  margin-top: -0.5em;
  padding: 0;
  color: #999;
  font-size: .92857em;
}
.post-meta li {
  display: inline-block;
  margin: 0 8px 0 0;
  padding-left: 12px;
  border-left: 1px solid #EEE;
}
.post-meta li:first-child {
  margin-left: 0;
  padding-left: 0;
  border: none;
}
.post-content {
  font-size: 1.1rem; /* 约17.6px */
  line-height: 1.5;
}
.post .tags {
  clear: both;
}

.post-near {
  list-style: none;
  margin: 30px 0;
  padding: 0;
  color: #999;
}
.post-near li {
  margin: 10px 0;
}

.archive-title {
  margin: 1em 0 -1em;
  padding-top: 20px;
  color: #999;
  font-size: 1em;
}
.more {
  text-align: center;
}
.more a {
  border: none;
}
.protected .text {
  width: 50%;
}

/* Page nav */

.page-navigator {
  list-style: none;
  margin: 25px 0;
  padding: 0;
  text-align: center;
}
.page-navigator li {
  display: inline-block;
  margin: 0 4px;
}
.page-navigator a {
  display: inline-block;
  padding: 0 10px;
  height: 30px;
  line-height: 30px;
}
.page-navigator a:hover {
  background: #EEE;
  text-decoration: none;
}

.page-navigator .current a {
  color: #444;
  background: #EEE;
}

/* ------------------
 * Comment list
 * --------------- */
#comments {
  padding-top: 15px;
}
.comment-list, .comment-list ol {
  list-style: none;
  margin: 0;
  padding: 0;
}
.comment-list li {
  padding: 14px;
  margin-top: 10px;
  border: 1px solid #EEE;
}
.comment-list li.comment-level-odd {
  background: #F6F6F3;
}
.comment-list li.comment-level-even {
  background: #FFF;
}
.comment-list li.comment-by-author {
  background: #FFF9E8;
}
.comment-list li .comment-reply {
  text-align: right;
  font-size: .92857em;
}
.comment-meta a {
  color: #999;
  font-size: .92857em;
}
.comment-author {
  display: block;
  margin-bottom: 3px;
  color: #444;
}
.comment-author .avatar {
  float: left;
  margin-right: 10px;
}
.comment-author cite {
  font-weight: bold;
  font-style: normal;
}

/* Comment reply */
.comment-list .respond {
  margin-top: 15px;
  border-top: 1px solid #EEE;
}
.respond .cancel-comment-reply {
  float: right;
  margin-top: 15px;
  font-size: .92857em;
}
#comment-form label {
  display: block;
  margin-bottom: .5em;
  font-weight: bold;
}
#comment-form .required:after {
  content: " *";
  color: #C00;
}

/* ------------------
 * secondary
 * --------------- */
#secondary {
  width: 300px; 
  flex-shrink: 0; /* 禁止侧边栏收缩 */
  order: 2; /* 视觉顺序保持在右侧 */
  padding-top: 15px;
  word-wrap: break-word;
  width: 200px; 
  flex-shrink: 0; /* 禁止侧边栏收缩 */
  order: 2; /* 视觉顺序保持在右侧 */

}
.widget {
  margin-bottom: 30px;
}
.widget-list {
  list-style: none;
  padding: 0;
}
.widget-list li {
  margin: 5px 0;
  line-height: 1.6;
}

.widget-list li ul {
  margin-left: 15px;
}


/* ------------------
 * Footer 
 * --------------- */
#footer {
  padding: 3em 0;
  line-height: 1.5;
  text-align: center;
  color: #999;
}


/* -----------------
 * Error page
 * -------------- */
.error-page {
  margin-top: 100px;
  margin-bottom: 100px;
}


/* -----------------
 * Content format
 *--------------- */
.post-content, .comment-content {
  line-height: 1.5;
  word-wrap: break-word;
}
.post-content h2, .comment-content h2 {
  font-size: 1.28571em;
}
.post-content img, .comment-content img,
.post-content video, .comment-content video {
  max-width: 100%;
}
.post-content a img,
.comment-content a img {
  background: #FFF;
  position: relative;
  bottom: -4px;  /* hidden img parent link border  */
}
.post-content hr, .comment-content hr {
  margin: 2em auto;
  width: 100px;
  border: 1px solid #E9E9E9;
  border-width: 2px 0 0 0;
}


/* -----------------
 * Misc
 *--------------- */
.aligncenter, div.aligncenter {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.alignleft {
  float: left;
}
.alignright {
  float: right;
}
img.alignleft {
  margin: 0 15px 0 0;
}
img.alignright {
  margin: 0 0 0 15px;
}


/* -----------------
 * Responsive
 *--------------- */

@media (max-width: 768px) {
  h1 {
    font-size: 1.8rem !important; /* 约28.8px */
    line-height: 1.3;
  }
  h2 {
    font-size: 1.5rem !important; /* 约24px */
  }
  h3 {
    font-size: 1.3rem !important; /* 约20.8px */
  }
  .post-title a {
    font-size: 1.6rem !important; /* 约25.6px */
    line-height: 1.4;
  }
  /* 容器边距缩小 */
  .container {
    padding: 0 15px !important; /* 水平间距减半 */
  }
  
  /* 文章卡片内边距调整 */
  .post {
    padding: 1.2rem 1.5rem !important; /* 四周间距缩小 */
    margin: 1rem 0 !important; /* 文章间距减小 */
  }

  
}

@media (max-width: 767px) {
  body {
    font-size: 82.25%;
  }
  .post-content {
    font-size: 1rem; /* 正文回归默认大小 */
    line-height: 1.7; /* 增加行高提升可读性 */
  }
  #nav-menu a {
    float: none;
    display: inline-block;
    margin: 0 -2px;
  }
}

@media (max-width: 768px) {
  #header,
  .post-title,
  .post-meta {
    text-align: center;
  }
}

@media (min-width: 992px) {

}

@media (min-width: 1200px) {
  .container {
    max-width: 952px;
  }
}


/*
* Hide from both screenreaders and browsers: h5bp.com/u
*/
.hidden {
  display: none !important;
  visibility: hidden; }

/*
* Hide only visually, but have it available for screenreaders: h5bp.com/v
*/
.sr-only {
  border: 0;
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px; }

/*
* Extends the .sr-only class to allow the element to be focusable
* when navigated to via the keyboard: h5bp.com/p
*/
.sr-only.focusable:active,
.sr-only.focusable:focus {
  clip: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  position: static;
  width: auto; }

/*
* Hide visually and from screenreaders, but maintain layout
*/
.invisible {
  visibility: hidden; }



```