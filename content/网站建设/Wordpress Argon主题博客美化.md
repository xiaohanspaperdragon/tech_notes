---
title: Wordpress Argon主题博客美化
created: 2026-08-17
tags:
  - wordpress
  - 网站建设
  - argon
  - 主题
author:
  - 潇寒子
  - 潇寒paper龙
---

本文参考 [Argon主题博客美化 - Echo](https://liveout.cn/archives/2.html/comment-page-2#comments)
## 年度倒计时显示(左侧栏)

**在左侧栏里添加工具——简码，复制一下代码粘贴进去**

```php
<div class="progress-wrapper" style="padding: 0">
<div class="progress-info">
<div class="progress-label">
<span id="yearprogress_yearname"></span>
</div>
<div id="yearprogress_text_container" class="progress-percentage">
<span id="yearprogress_progresstext"></span>
<span id="yearprogress_progresstext_full"></span>
</div>
</div>
<div class="progress">
<div id="yearprogress_progressbar" class="progress-bar bg-primary"></div>
</div>
</div>
<script no-pjax="">
function yearprogress_refresh() {
let year = new Date().getFullYear();
$("#yearprogress_yearname").text(year);
let from = new Date(year, 0, 1, 0, 0, 0);
let to = new Date(year, 11, 31, 23, 59, 59);
let now = new Date();
let progress = (((now - from) / (to - from + 1)) * 100).toFixed(7);
let progressshort = (((now - from) / (to - from + 1)) * 100).toFixed(2);
$("#yearprogress_progresstext").text(progressshort + "%");
$("#yearprogress_progresstext_full").text(progress + "%");
$("#yearprogress_progressbar").css("width", progress + "%");
}
yearprogress_refresh();
if (typeof yearProgressIntervalHasSet == "undefined") {
var yearProgressIntervalHasSet = true;
setInterval(function () {
yearprogress_refresh();
}, 500);
}
</script>
<style>
#yearprogress_text_container {
width: 100%;
height: 22px;
overflow: hidden;
user-select: none;
}
#yearprogress_text_container > span {
transition: all 0.3s ease;
display: block;
}
#yearprogress_text_container:hover > span {
transform: translateY(-45px);
}
</style>
```

## 底部音乐播放

[如何在博客中添加Aplayer音乐播放器 - echeverra](https://echeverra.cn/aplayer)

> 下面的调用链接可能会突然失效，如有需要可参考官方文档
> [Home - APlayer](https://aplayer.js.org/#/home)
> [GitHub - DIYgod/APlayer: :lollipop: Wow, such a beautiful HTML5 music player · GitHub](https://github.com/DIYgod/APlayer)
> [APlayer HTML5音乐播放器 | ACE-BLOG](https://ace520.github.io/blog/post/2020/05/26/aplayer/)

 `server="netease` 指定音乐平台为网易云， `type="song"`  
指单曲类型， `id=""` 为音乐的 id（这里的id为打开音乐歌单,是自己创建的歌单，网址显示的id）

**开启吸底模式 `fixed="true"`
**开启迷你模式** `mini="true"`
**随机播放**`order="random"`
**关闭底部歌词** `lrc-type="0"`

**注意** ：id需要为自己创建的歌单，不能为我喜欢的音乐；server可以改自己用的音乐平台，如netease(网易云)、tencent(QQ音乐)

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.css">
<script src="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/meting@2.0.1/dist/Meting.min.js"></script>
 
<meting-js 
    server="netease" 
    type="playlist" 
    id="7360465359"
    fixed="true" 
    mini="true"
    order="random"
    loop="all"
    preload="auto"
    list-folded="false">
</meting-js>
```


## 虚拟人物(看板娘)

以下代码选择一项复制即可，效果不同，自行选择

具体文章：
[把萌萌哒的看板娘抱回家 (ノ≧∇≦)ノ | Live2D widget for web platform](https://github.com/stevenjoezhang/live2d-widget)


```html
<script src="https://fastly.jsdelivr.net/gh/stevenjoezhang/live2d-widget@latest/autoload.js"></script>
```

2. **其中 jsonpath: 后面的链接可按自己爱好更改，选择别的虚拟人物**

```html
<script src="https://eqcn.ajz.miesnfu.com/wp-content/plugins/wp-3d-pony/live2dw/lib/L2Dwidget.min.js"></script>
<script>
    L2Dwidget.init({
        "model": {
　　　　　　　//jsonpath控制显示那个小萝莉模型，
            //(切换模型需要改动)
//              "https://unpkg.com/(live2d-widget-model-koharu)@1.0.5/assets/(koharu).model.json"
            jsonPath: "https://unpkg.com/live2d-widget-model-koharu@1.0.5/assets/koharu.model.json",
            "scale": 1
        },
        "display": {
            "position": "right", //看板娘的表现位置
            "width": 75,  //小萝莉的宽度
            "height": 150, //小萝莉的高度
            "hOffset": 0,
            "vOffset": -20
        },
        "mobile": {
            "show": true,
            "scale": 0.5
        },
        "react": {
            "opacityDefault": 0.7,
            "opacityOnHover": 0.2
        }
    });
</script>

   /*   小帅哥： https://unpkg.com/live2d-widget-model-chitose@1.0.5/assets/chitose.model.json
      萌娘：https://unpkg.com/live2d-widget-model-shizuku@1.0.5/assets/shizuku.model.json
      白猫：https://unpkg.com/live2d-widget-model-tororo@1.0.5/assets/tororo.model.json
      黑猫： https://unpkg.com/live2d-widget-model-hijiki@1.0.5/assets/hijiki.model.json
      小可爱（女）：https://unpkg.com/live2d-widget-model-koharu@1.0.5/assets/koharu.model.json
      小可爱（男）：https://unpkg.com/live2d-widget-model-haruto@1.0.5/assets/haruto.model.json
      初音：https://unpkg.com/live2d-widget-model-miku@1.0.5/assets/miku.model.json
      圣职者妹妹：https://unpkg.com/live2d-widget-model-z16@1.0.5/assets/z16.model.json
      茶杯犬：https://cdn.jsdelivr.net/npm/live2d-widget-model-wanko@1.0.5/assets/wanko.model.json
      绿毛妹妹：https://unpkg.com/live2d-widget-model-tsumiki@1.0.5/assets/tsumiki.model.json
      金龟子妹妹：https://unpkg.com/live2d-widget-model-unitychan@1.0.5/assets/unitychan.model.json
      https://unpkg.com/live2d-widget-model-nito@1.0.5/assets/nito.model.json
      https://unpkg.com/live2d-widget-model-ni-j@1.0.5/assets/ni-j.model.json
      小阿狸： https://unpkg.com/live2d-widget-model-nico@1.0.5/assets/nico.model.json
      https://unpkg.com/live2d-widget-model-nietzche@1.0.5/assets/nietzche.model.json
      https://unpkg.com/live2d-widget-model-nipsilon@1.0.5/assets/nipsilon.model.json
      女学生： https://unpkg.com/live2d-widget-model-hibiki@1.0.5/assets/hibiki.model.json */
```

## 网站底部信息

### CSS(样式表)

```markup
<style>
/* 核心样式 */
.github-badge {
display: inline-block;
border-radius: 4px;
text-shadow: none;
font-size: 13.1px;
color: #fff;
line-height: 15px;
margin-bottom: 5px;
font-family: "Open Sans", sans-serif;
}
.github-badge .badge-subject {
display: inline-block;
background-color: #4d4d4d;
padding: 4px 4px 4px 6px;
border-top-left-radius: 4px;
border-bottom-left-radius: 4px;
font-family: "Open Sans", sans-serif;
}
.github-badge .badge-value {
display: inline-block;
padding: 4px 6px 4px 4px;
border-top-right-radius: 4px;
border-bottom-right-radius: 4px;
font-family: "Open Sans", sans-serif;
}
.github-badge-big {
display: inline-block;
border-radius: 6px;
text-shadow: none;
font-size: 14.1px;
color: #fff;
line-height: 18px;
margin-bottom: 7px;
}
.github-badge-big .badge-subject {
display: inline-block;
background-color: #4d4d4d;
padding: 4px 4px 4px 6px;
border-top-left-radius: 4px;
border-bottom-left-radius: 4px;
}
.github-badge-big .badge-value {
display: inline-block;
padding: 4px 6px 4px 4px;
border-top-right-radius: 4px;
border-bottom-right-radius: 4px;
}
.bg-orange {
background-color: #ec8a64 !important;
}
.bg-red {
background-color: #cb7574 !important;
}
.bg-apricots {
background-color: #f7c280 !important;
}
.bg-casein {
background-color: #dfe291 !important;
}
.bg-shallots {
background-color: #97c3c6 !important;
}
.bg-ogling {
background-color: #95c7e0 !important;
}
.bg-haze {
background-color: #9aaec7 !important;
}
.bg-mountain-terrier {
background-color: #99a5cd !important;
}
</style>
```

### HTML(底部信息)

```php
<div class="github-badge-big">
      <span class="badge-subject"><i class="fa fa-id-card"></i> 备案号 </span>
      <span class="badge-value bg-orange">
          <!-- 备案链接 -->
          <a href="https://beian.miit.gov.cn/" target="_blank" one-link-mark="yes">某ICP备xxxxxxxxxx号</a>|
          <a href="https://www.beian.gov.cn/portal/index?token=e547b70c-fbe1-4c80-a4a2-857b17389a71" target="_blank"
              one-link-mark="yes">
              某公网安备 xxxxxxxxxxxxxx号</a>
      </span>
  </div>

<div class="github-badge-big">
      <span class="badge-subject"><i class="fa fa-cloud" aria-hidden="true"></i> CDN</span>
      <span class="badge-value bg-shallots">
          <!-- 又拍云链接 -->
          <a href="https://www.upyun.com/" target="_blank" one-link-mark="yes">Upyun</a>
      </span>

      <span class="badge-subject"><i class="fa fa-wordpress"></i> Powered</span>
      <span class="badge-value bg-green">
          <!-- wordpress链接 -->
          <a href="https://cn.wordpress.org/" target="_blank" one-link-mark="yes">
              WordPress</a></span>
  </div>

  <div class="github-badge-big">
      <span class="badge-subject"><i class="fa fa-copyright" aria-hidden="true"></i>Copyright </span>
      <span class="badge-value bg-red">2022-2023</i>
          <a href="https://www.liveout.cn/" target="_blank" one-link-mark="yes">@ Echo
      </span>
      </script>
  </div>

  <!-- 运行时间 -->
  <div class="github-badge-big">
      <span class="badge-subject"><i class="fa fa-clock-o"></i> Running Time</span><span
          class="badge-value bg-apricots"><span id="blog_running_days" class="odometer odometer-auto-theme"></span>
          days
          <span id="blog_running_hours" class="odometer odometer-auto-theme"></span> H
          <span id="blog_running_mins" class="odometer odometer-auto-theme"></span> M
          <span id="blog_running_secs" class="odometer odometer-auto-theme"></span>S
      </span>
```

### JavaScript（网站运行时间脚本）

**注意** ：new Date( year, month, date, hrs, min, sec) 按给定的参数创建 日期对象

**其中month的值域为0～11，0代表1月，11表代表12月；所以你输入的月份需要为自己真正月份的前一个月**

```php
<script no-pjax="">
var blog_running_days = document.getElementById("blog_running_days");
var blog_running_hours = document.getElementById("blog_running_hours");
var blog_running_mins = document.getElementById("blog_running_mins");
var blog_running_secs = document.getElementById("blog_running_secs");
function refresh_blog_running_time() {
var time = new Date() - new Date(2022, 5, 31, 0, 0, 0); /*此处日期的月份改为自己真正月份的前一个月*/
var d = parseInt(time / 24 / 60 / 60 / 1000);
var h = parseInt((time % (24 * 60 * 60 * 1000)) / 60 / 60 / 1000);
var m = parseInt((time % (60 * 60 * 1000)) / 60 / 1000);
var s = parseInt((time % (60 * 1000)) / 1000);
blog_running_days.innerHTML = d;
blog_running_hours.innerHTML = h;
blog_running_mins.innerHTML = m;
blog_running_secs.innerHTML = s;
}
refresh_blog_running_time();
if (typeof bottomTimeIntervalHasSet == "undefined") {
var bottomTimeIntervalHasSet = true;
setInterval(function () {
refresh_blog_running_time();
}, 500);
}
</script>
```

## 字体、鼠标等特效

[Docker系列 WordPress系列 特效 - Bensz](https://blognas.hwb0307.com/linux/docker/744#comment-918)


## 自定义CSS样式

### 额外CSS

> 参考上面链接, 额外CSS，涉及字体、透明等博客样式

在 `外观` --- `自定义` --- `额外CSS` 中

ps: 字体链接需要上传到云端调用才能生效（下面字体链接已失效）

```php
/*网站字体*/
/*原则上你可以设置多个字体，然后在不同的部位使用不同的字体。*/
@font-face{
    font-family:echo;
src:url(https://fastly.jsdelivr.net/gh/huangwb8/bloghelper@latest/fonts/13.woff2) format('woff2')
}

body{
        font-family: 'echo', Georgia, -apple-system, 'Nimbus Roman No9 L', 'PingFang SC', 'Hiragino Sans GB', 'Noto Serif SC', 'Microsoft Yahei', 'WenQuanYi Micro Hei', 'ST Heiti', sans-serif
}
 
/*横幅字体大小*/
.banner-title {
  font-size: 2.5em;
}
.banner-subtitle{
  font-size: 28px;
    
    -webkit-text-fill-color: transparent;        
background: linear-gradient(94.75deg,rgb(60, 172, 247) 0%,rgb(131, 101, 253) 43.66%,                rgb(255, 141, 112) 64.23%,rgb(247, 201, 102) 83.76%,rgb(172, 143, 100) 100%);        
-webkit-background-clip: text;
}
 
/*文章标题字体大小*/
.post-title {
    font-size: 25px
}
 
/*正文字体大小（不包含代码）*/
.post-content p{
    font-size: 1.25rem;
}
li{
    font-size: 1.2rem;
    
}
 
/*评论区字体大小*/
p {
    font-size: 1.2rem
            
}
 
/*评论发送区字体大小*/
.form-control{
    font-size: 1.2rem
}
 
/*评论勾选项目字体大小*/
.custom-checkbox .custom-control-input~.custom-control-label{
    font-size: 1.2rem
}
/*评论区代码的强调色*/
code {
  color: rgba(var(--themecolor-rgbstr));
}
 
/*说说字体大小和颜色设置*/
.shuoshuo-title {
    font-size: 25px;
/*  color: rgba(var(--themecolor-rgbstr)); */
}
 
/*尾注字体大小*/
.additional-content-after-post{
    font-size: 1.2rem
}
 
/* 公告居中 */
.leftbar-announcement-title {
    font-size: 20px;
/*     text-align: center; */
                 color: #00FFFF
}

.leftbar-announcement-content {
    font-size: 15px;
    line-height: 1.8;
    padding-top: 8px;
    opacity: 0.8;
/*     text-align: center; */
            color:#00FFFF;
}

/* 一言居中 */
.leftbar-banner-title {
    font-size: 20px;
    display: block;
    text-align: center;
        opacity: 0.8;
}

/* 个性签名居中 */
.leftbar-banner-subtitle {
    margin-top: 15px;
    margin-bottom: 8px;
    font-size: 13px;
    opacity: 0.8;
    display: block;
    text-align: center;
}

/*========颜色设置===========*/
 
/*文章或页面的正文颜色*/
body{
    color:#364863
}
 
/*引文属性设置*/
blockquote {
    /*添加弱主题色为背景色*/
    background: rgba(var(--themecolor-rgbstr), 0.1) !important;
    width: 100%
}
 
/*引文颜色 建议用主题色*/
:root {
    /*也可以用类似于--color-border-on-foreground-deeper: #009688;这样的命令*/
    --color-border-on-foreground-deeper: rgba(var(--themecolor-rgbstr));
}
 
/*左侧菜单栏突出颜色修改*/
.leftbar-menu-item > a:hover, .leftbar-menu-item.current > a{
    background-color: #f9f9f980;
}
 
/*站点概览分隔线颜色修改*/
.site-state-item{
    border-left: 1px solid #aaa;
}
.site-friend-links-title {
    border-top: 1px dotted #aaa;
}
#leftbar_tab_tools ul li {
    padding-top: 3px;
    padding-bottom: 3px;
    border-bottom:none;
}
html.darkmode #leftbar_tab_tools ul li {
    border-bottom:none;
}
 
/*左侧栏搜索框的颜色*/
button#leftbar_search_container {
    background-color: transparent;
}
 
/*========透明设置===========*/
 
/*白天卡片背景透明*/
.card{
    background-color:rgba(255, 255, 255, 0.8) !important;
    /*backdrop-filter:blur(6px);*//*毛玻璃效果主要属性*/
    -webkit-backdrop-filter:blur(6px);
}
 
/*小工具栏背景完全透明*/
/*小工具栏是card的子元素，如果用同一个透明度会叠加变色，故改为完全透明*/
.card .widget,.darkmode .card .widget,#post_content > div > div > div.argon-timeline-card.card.bg-gradient-secondary.archive-timeline-title{
    background-color:#ffffff00 !important;
    backdrop-filter:none;
    -webkit-backdrop-filter:none;
}
.emotion-keyboard,#fabtn_blog_settings_popup{
    background-color:rgba(255, 255, 255, 0.95) !important;
}
 
/*分类卡片透明*/
.bg-gradient-secondary{
    background:rgba(255, 255, 255, 0.1) !important;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter:blur(10px);
}
 
/*夜间透明*/
html.darkmode.bg-white,html.darkmode .card,html.darkmode #footer{
    background:rgba(66, 66, 66, 0.9) !important;
}
html.darkmode #fabtn_blog_settings_popup{
    background:rgba(66, 66, 66, 0.95) !important;
}
 
/*标签背景
.post-meta-detail-tag {
    background:rgba(255, 255, 255, 0.5)!important;
}*/
 
 
/*========排版设置===========*/
 
/*左侧栏层级置于上层*/
#leftbar_part1 {
    z-index: 1;
}
 
/*分类卡片文本居中*/
#content > div.page-information-card-container > div > div{
    text-align:center;
}
 
/*子菜单对齐及样式调整*/
.dropdown-menu .dropdown-item>i{
    width: 10px;
}
.dropdown-menu>a {
    color:var(--themecolor);
}
.dropdown-menu{
    min-width:max-content;
}
.dropdown-menu .dropdown-item {
    padding: .5rem 1.5rem 0.5rem 1rem;
}
.leftbar-menu-subitem{
    min-width:max-content;
}
.leftbar-menu-subitem .leftbar-menu-item>a{
    padding: 0rem 1.5rem 0rem 1rem;
}
 
/*左侧栏边距修改*/
.tab-content{
    padding:10px 0px 0px 0px !important;
}
.site-author-links{
    padding:0px 0px 0px 10px ;
}
/*目录位置偏移修改*/
#leftbar_catalog{
    margin-left: 0px;
}
/*目录条目边距修改*/
#leftbar_catalog .index-link{
    padding: 4px 4px 4px 4px;
}
/*左侧栏小工具栏字体缩小*/
#leftbar_tab_tools{
    font-size: 14px;
}
 
/*正文图片边距修改*/
article figure {margin:0;}
/*正文图片居中显示*/
.fancybox-wrapper {
    margin: auto;
}
/*正文表格样式修改*/
article table > tbody > tr > td,
article table > tbody > tr > th,
article table > tfoot > tr > td,
article table > tfoot > tr > th,
article table > thead > tr > td,
article table > thead > tr > th{
    padding: 8px 10px;
    border: 1px solid;
}
/*表格居中样式*/
.wp-block-table.aligncenter{margin:10px auto;}
 
/*回顶图标放大*/
button#fabtn_back_to_top, button#fabtn_go_to_comment, button#fabtn_toggle_blog_settings_popup, button#fabtn_toggle_sides, button#fabtn_open_sidebar{
    font-size: 1.2rem;
}
 
/*顶栏菜单放大*/
/*这里也可以设置刚刚我们设置的btfFont字体。试试看！*/

.navbar-nav .nav-link {
    font-size: 1rem;
    font-family: 'echo';
            
}
.navbar-brand {
    font-family: 'echo';
    font-size: 1.2rem;
    margin-right: 1.0 rem;
    padding-bottom: 0.2 rem;
    
    -webkit-text-fill-color: transparent;        
background: linear-gradient(94.75deg,rgb(60, 172, 247) 0%,rgb(131, 101, 253) 43.66%,                rgb(255, 141, 112) 64.23%,rgb(247, 201, 102) 83.76%,rgb(172, 143, 100) 100%);        
-webkit-background-clip: text;
}

/*菜单大小*/
.nav-link-inner--text {
    font-size: 1.25em;
}
.navbar-nav .nav-item {
    margin-right:0;
}
.mr-lg-5, .mx-lg-5 {
    margin-right:1rem !important;
}
.navbar-toggler-icon {
    width: 1.8rem;
    height: 1.8rem;
}
/*菜单间距*/
.navbar-expand-lg .navbar-nav .nav-link {
    padding-right: 1.4em;
    padding-left: 1.4em;
}
 
/*隐藏wp-SEO插件带来的线条阴影（不一定要装）*/
*[style='position: relative; z-index: 99998;'] {
    display: none;
}

/* Github卡片样式*/
.github-info-card-header a {
    /*Github卡片抬头颜色*/
    color: black !important;
    font-size: 1.5rem;
}
.github-info-card {
    /*Github卡片文字（非链接）*/
    font-size: 1rem;
    color: black !important;
}
.github-info-card.github-info-card-full.card.shadow-sm {
    /*Github卡片背景色*/
    background-color: rgba(var(--themecolor-rgbstr), 0.1) !important;
}

/*      左侧栏外观CSS     */

/* 头像 */
#leftbar_overview_author_image {
    width: 100px;
    height: 100px;
    margin: auto;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-color: rgba(127, 127, 127, 0.1);
    overflow: hidden;
    transition: transform 0.3s ease;
}

/*  头像亮暗  */
#leftbar_overview_author_image:hover {
    transform: scale(1.23);
    filter: brightness(150%);
}

/* 名称 */
#leftbar_overview_author_name {
      margin-top: 15px;
    font-size: 18px;align-content;
    color:#00FFFF;
}

/* 简介 */
#leftbar_overview_author_description {
    font-size: 14px;
    margin-top: -4px;
    opacity: 0.8;
    color:#c21f30;
}

/* 标题，链接等 */
a, .btn-neutral {
    color:#AF7AC5 ;
    
}

/* 页脚透明 */
#footer {
    background: var(--themecolor-gradient);
    color: #fff;
    width: 100%;
    float: right;
    margin-bottom: 25px;
    text-align: center;
    padding: 25px 20px;
    line-height: 1.8;
    transition: none;
    opacity: 0.6;
}
```


## 头像缩放或亮暗

鼠标经过头像时自动缩放、高亮/暗

在 `外观` --- `自定义` --- `额外CSS` 中

```text
#leftbar_overview_author_image {
    width: 100px;
    height: 100px;
    margin: auto;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-color: rgba(127, 127, 127, 0.1);
    overflow: hidden;
    box-shadow: 0 0 5px rgba(116, 8, 204, 0.3);
    transition: transform 0.3s ease; /*变化速度*/
}

#leftbar_overview_author_image:hover {
    transform: scale(1.2); /*缩放大小*/
    filter: brightness(150%); /*调节亮度*/
}
```

## 头像/姓名跳转相关页

在 `外观` --- `主题文件编辑器` 中, 选择 `边栏文件(sidebar.php)`

点击 `头像` 跳转大概在第 `126` 行左右,

添加 `<a>` 标签,即 `<a href="https://www.liveout.cn/about/">`, 其中链接改为想要跳转的地方

```php
<div class="tab-pane fade text-center<?php if ($nowActiveTab == 1) { echo ' active show'; }?>" id="leftbar_tab_overview" role="tabpanel" aria-labelledby="leftbar_tab_overview_btn">
<a href="https://www.example.com/">
<div id="leftbar_overview_author_image" style="background-image: ........ 
<a/>
```

点击 `姓名` 跳转则是 `130` 行左右

添加 `<a href="https://www.liveout.cn/about/">.... <a/>`

```php
<a href="https://www.example.com">
<h6 id="leftbar_overview_author_name"><?php echo get_option('argon_sidebar_auther_name') == '' ? bloginfo('name') : get_option('argon_sidebar_auther_name'); ?> </h6>
<a/>
```

---

## 评论头像显示

在 `外观` --- `主题文件编辑器` 中的 `function` 模板函数添加此代码

```php
if ( ! function_exists( 'get_cravatar_url' ) ) {
    /**
    *  把Gravatar头像服务替换为Cravatar
    * @param string $url
    * @return string
    */
    function get_cravatar_url( $url ) {
        $sources = array(
            'www.gravatar.com',
            '0.gravatar.com',
            '1.gravatar.com',
            '2.gravatar.com',
            'secure.gravatar.com',
            'cn.gravatar.com'
        );
        return str_replace( $sources, 'cravatar.cn', $url );
    }
    add_filter( 'um_user_avatar_url_filter', 'get_cravatar_url', 1 );
    add_filter( 'bp_gravatar_url', 'get_cravatar_url', 1 );
    add_filter( 'get_avatar_url', 'get_cravatar_url', 1 );
}
```

来源：网络

## wp插件合集

### 网站访问数据(左侧栏)

1. **进入Wordpress，点击插件，搜索并且下载 Wp Statistics**
2. **外观——小工具——站点额外内容——旧版小工具——统计**

### 评论IP地址

参考文章
[WP-UserAgent | kyleabaker.com](https://www.kyleabaker.com/goodies/coding/wp-useragent/)

[obaby 𝐢‍𝐧⃝ void](https://h4ck.org.cn/)

[[WordPress 展示评论者地理位置插件 Easy Location | 歲月留聲 (0xo.net)](https://0xo.net/1947)](https://0xo.net/1947)

### 评论管理

**Akismet Anti-Spam: Spam Protection**

### 邮件发送

**WP Mail SMTP**

### 文章字数统计

**WP Word Count**

### WP用户个人头像

**Simple Local Avatars**

## 相关链接

**Argon主题 GitHub地址** ：[GitHub - solstice23/argon-theme: 📖 Argon - 一个轻盈、简洁的 WordPress 主题 · GitHub](https://github.com/solstice23/argon-theme)
**Argon主题作者博客** ：[solstice23 – Blog](https://archive-blog.s23.moe/)
**Argon主题使用文档** ： [Argon Theme Docs](https://argon-docs.solstice23.top/#/)


**Argon主题美化** ：[Argon主题博客美化 - Echo](https://liveout.cn/archives/2.html/comment-page-2#comments)



