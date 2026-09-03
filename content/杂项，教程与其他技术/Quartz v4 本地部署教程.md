---
title: Quartz v4 本地部署教程
author:
  - 潇寒paper龙
  - 潇寒子
tags:
  - quartz
  - 静态blog
  - obsidian
created: 2025-08-01
modified: 2025-08-05
draft: false
description: Quartz v4 本地部署的完整步骤总结
---


>[!check]
>以下是 **Quartz v4 本地部署的完整步骤总结**，适用于你已经下载好 `quartz-4` 源码，并希望从 `content` 构建，最终通过浏览器本地访问 `index.html` 来查看完整站点：
>
>项目源码：[jackyzha0/quartz: 🌱 a fast, batteries-included static-site generator that transforms Markdown content into fully functional websites](https://github.com/jackyzha0/quartz)

---

# ✅ Quartz v4 本地部署完整步骤


>[!note]
>大体流程如下

```bash
npm install         # 安装依赖
npm run dev         # 本地开发调试
npm run build       # 生成 public 文件夹
npm run preview     # 本地预览构建结果
```

---

## 🧱 第一步：准备环境

### 1. 安装 Node.js（推荐版本 ≥ 22）

>[!note]
>去官网下载并安装：
>
>🔗 [https://nodejs.org](https://nodejs.org/)
>



---

### 2. 启用 PowerShell 脚本权限（Windows 用户）

>[!tip]
>如果你看到 `npm.ps1 无法执行` 错误：

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

>[!note]
>输入 `Y` 确认。

---

## 📦 第二步：安装依赖

>进入项目文件夹（以你下载的 quartz 文件夹为例）：

```bash
cd C:\Users\ASUS\Downloads\quartz-4
```

>安装依赖：

```bash
npm install --legacy-peer-deps
```

>安装完成后重新打开终端：
>检查版本是否更新成功：

```bash
node -v
npm -v
```


---


## ✏️ 第三步：配置构建来源文件夹（可选）

###  `quartz.config.ts` 文件
编辑 `quartz.config.ts` 文件：

```ts
ignorePatterns: ["private", "templates", ".obsidian"],
```

⚠️ 如果你想用 `content/` 而不是 `docs/` 文件夹：

你需要把 `content/` 改名为 `docs/`，或者在代码中自定义构建入口（Quartz v4 默认是 `docs/` 文件夹作为输入目录）。

>修改配置以构建 `content` 文件夹
>在你的 `configuration` 对象中，添加一行：

```ts
contentDir: "content",
```

>改后示例：

```ts
const config: QuartzConfig = {
  configuration: {
    pageTitle: "Quartz 4",
    pageTitleSuffix: "",
    enableSPA: true,
    enablePopovers: true,
    analytics: {
      provider: "plausible",
    },
    locale: "en-US",
    baseUrl: "https://xiaohanspapergradon.github.io/quartz",
    ignorePatterns: ["private", "templates", ".obsidian"],
    defaultDateType: "modified",
    theme: {
      fontOrigin: "googleFonts",
      cdnCaching: true,
      typography: {
        header: "Schibsted Grotesk",
        body: "Source Sans Pro",
        code: "IBM Plex Mono",
      },
      colors: {
        lightMode: {
          light: "#faf8f8",
          lightgray: "#e5e5e5",
          gray: "#b8b8b8",
          darkgray: "#4e4e4e",
          dark: "#2b2b2b",
          secondary: "#284b63",
          tertiary: "#84a59d",
          highlight: "rgba(143, 159, 169, 0.15)",
          textHighlight: "#fff23688",
        },
        darkMode: {
          light: "#161618",
          lightgray: "#393639",
          gray: "#646464",
          darkgray: "#d4d4d4",
          dark: "#ebebec",
          secondary: "#7b97aa",
          tertiary: "#84a59d",
          highlight: "rgba(143, 159, 169, 0.15)",
          textHighlight: "#b3aa0288",
        },
      },
    },

    contentDir: "content",  // <== 添加这行

  },
  plugins: {
    transformers: [
      Plugin.FrontMatter(),
      Plugin.CreatedModifiedDate({
        priority: ["frontmatter", "git", "filesystem"],
      }),
      Plugin.SyntaxHighlighting({
        theme: {
          light: "github-light",
          dark: "github-dark",
        },
        keepBackground: false,
      }),
      Plugin.ObsidianFlavoredMarkdown({ enableInHtmlEmbed: false }),
      Plugin.GitHubFlavoredMarkdown(),
      Plugin.TableOfContents(),
      Plugin.CrawlLinks({ markdownLinkResolution: "shortest" }),
      Plugin.Description(),
      Plugin.Latex({ renderEngine: "katex" }),
    ],
    filters: [Plugin.RemoveDrafts()],
    emitters: [
      Plugin.AliasRedirects(),
      Plugin.ComponentResources(),
      Plugin.ContentPage(),
      Plugin.FolderPage(),
      Plugin.TagPage(),
      Plugin.ContentIndex({
        enableSiteMap: true,
        enableRSS: true,
      }),
      Plugin.Assets(),
      Plugin.Static(),
      Plugin.Favicon(),
      Plugin.NotFoundPage(),
      // Comment out CustomOgImages to speed up build time
      Plugin.CustomOgImages(),
    ],
  },
}

```

### `package.json` 文件

>[!important]
 >如果`package.json` 里没有 `dev`、`build`、`preview` 这些脚本
>
>目前你的 `"scripts"` 部分是：

```json
"scripts": {
  "quartz": "./quartz/bootstrap-cli.mjs",
  "docs": "npx quartz build --serve -d docs",
  "check": "tsc --noEmit && npx prettier . --check",
  "format": "npx prettier . --write",
  "test": "tsx --test",
  "profile": "0x -D prof ./quartz/bootstrap-cli.mjs build --concurrency=1"
}
```

>[!warning]
>这说明：
>
>- Quartz 的源码是用自己的 CLI（`./quartz/bootstrap-cli.mjs`）来驱动的，不是用传统的 `npm run dev` 或 `npm run build`
>    
>- 你需要用自定义命令或者 CLI 来启动和构建
    

---

### Quartz 的正确本地运行步骤（基于你当前 `package.json`）

#### 1. 先运行 quartz CLI

```bash
npm run quartz
```

但是这个命令看起来只是启动 CLI，具体构建你要传参数。

---

#### 2. 运行构建命令

根据 `docs` 脚本的定义：

```bash
npx quartz build --serve -d docs
```

这里用的是 `quartz` CLI 的 `build` 命令。

你可以试试：

```bash
npx quartz build
```

它会生成默认的 `public` 文件夹。

---

#### 3. 预览本地网站

你可以运行：

```bash
npx quartz build --serve
```

或者

```bash
npx quartz docs
```

看它是不是会启动本地服务器。

---


- 构建：`npx quartz build`
    
- 构建并启动预览服务器：`npx quartz build --serve`
    
- 查看文档目录预览：`npm run docs` (执行 `npx quartz build --serve -d docs`)
    

---

 如果你想直接用这些命令，总结一个快捷脚本

你可以在 `package.json` `"scripts"` 里添加：

```json
"scripts": {
  "dev": "npx quartz build --serve",
  "build": "npx quartz build",
  "quartz": "./quartz/bootstrap-cli.mjs",
  "docs": "npx quartz build --serve -d docs",
  "check": "tsc --noEmit && npx prettier . --check",
  "format": "npx prettier . --write",
  "test": "tsx --test",
  "profile": "0x -D prof ./quartz/bootstrap-cli.mjs build --concurrency=1"
}
```

然后你就可以用

```bash
npm run dev
npm run build
```

来启动和构建。

---

## 🛠️ 第四步：构建站点

运行以下命令，生成静态站点：

```bash
npx quartz build
```

构建结果会输出到 `public/` 文件夹。

如果你想每次都指定目录，也可以用命令行参数覆盖：

```bash
npx quartz build --serve -d content
```

---

## 🌐 第五步：本地预览（推荐）

在本地启动 HTTP 服务器查看效果：

```bash
npx quartz build --serve
```

访问：[http://localhost:8080](http://localhost:8080/)

---

## 📁 第六步：部署到宝塔等 Web 服务器（可选）

1. 构建后的站点都在 `public/` 文件夹里。
    
2. 把 `public/` 里的所有文件上传到宝塔的站点根目录即可。
    
3. 确保宝塔设置了正确的访问地址，例如绑定了你的域名。
    

---

## 🚫 不推荐的方式：直接双击 `index.html`

- 浏览器的 `file://` 协议不能正确加载资源。
    
- 会出现空白页、CSS 丢失、JS 失效等问题。
    

🟡 **必须通过 HTTP 服务器访问，才能看到完整效果。**

---

## ✅ 推荐的快速本地预览命令（备选）

如果你不想用 Quartz 自带的服务器，也可以使用：

```bash
npx serve public
```

或者：

```bash
cd public
python -m http.server 8080
```

访问：[http://localhost:8080](http://localhost:8080/)

---

