---
title: Windows 下 Node.js PATH 配置
tags:
  - windows
  - path
  - node_js
date: 2026-08-25
author:
  - 潇寒paper龙
---

## 问题现象

终端执行 `node --version` 显示 `v6.14.0`（旧版），而 `C:\Program Files\nodejs\` 下实际安装的是 `v22.18.0`。导致 Hexo 等需要 Node 18+ 的工具无法运行，报 `Cannot find module 'node:path'` 错误。

## 原因分析

Windows 有两套 PATH 环境变量：
- **用户变量** PATH（仅当前用户）
- **系统变量** PATH（所有用户）

终端按**从上到下**的顺序搜索 PATH 中的路径，先找到的先执行。旧版 Node 的路径排在了新版前面，或者新版路径根本不在 PATH 中。

## 解决步骤

### 1. 打开环境变量编辑器

以下任一方式：
```powershell
# 方法一：PowerShell 命令直接打开
rundll32 sysdm.cpl,EditEnvironmentVariables

# 方法二：Win + R 输入
sysdm.cpl
# 然后点"高级" → "环境变量"
```
![[Pasted image 20260817221718.webp]]
![[Pasted image 20260817221744.webp]]
### 2. 添加新版 Node.js 路径

在 **用户变量**或者**系统变量** 的 `Path` 中：
1. 点"新建"，输入 `C:\Program Files\nodejs\`
2. 选中该条，点"上移"移至**最顶部**
![[Pasted image 20260817221845.webp]]
![[Pasted image 20260817221929.webp]]
### 3. 清理系统变量中的旧版路径

在 **系统变量** 的 `Path` 中：
- 检查是否有指向旧版 Node.js 的路径
- 如有，删除或移至新版路径之后

### 4. 验证

**关闭并重新打开**终端（环境变量修改需要新窗口生效）：

```powershell
node --version
# 期望输出：v22.18.0
```

## 注意事项

- 修改 PATH 后必须**重新打开**终端窗口，已打开的窗口不会自动刷新环境变量
- 如果安装了 nvm/fnm 等版本管理工具，它们会自动管理 PATH 中的 Node 路径，无需手动配置
- `C:\Users\<用户名>\AppData\Roaming\npm` 是全局 npm 包的路径，应保留在 PATH 中

---
