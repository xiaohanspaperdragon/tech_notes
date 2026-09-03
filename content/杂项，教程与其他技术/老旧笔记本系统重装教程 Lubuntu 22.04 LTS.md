---
title: 老旧笔记本系统重装教程 Lubuntu 22.04 LTS
tags:
  - linux
  - 操作系统
  - 重装系统
  - Lubuntu
  - Ubuntu
date: 2026-09-02
author:
  - 潇寒paper龙
---

> [!info] 元信息
> - **设备型号**：Dell Inspiron 1122 (或同类老旧笔记本)
> - **原系统**：Microsoft Windows XP Professional
> - **目标版本**：Lubuntu 22.04.5 LTS (amd64)
> - **硬件配置参考**：AMD E-350 (1.6GHz) / 1.6GB RAM / 320GB HDD
> - 具体请看[[Dell Inspiron 1122 电脑硬件配置清单]]

> [!note] 适用硬件范围
> 本教程专门针对：**CPU 主频 < 2.0GHz、内存 RAM ≤ 4GB、使用传统机械硬盘 (HDD)** 的入门级老旧笔记本电脑。对于非此类配置的机器，步骤可能略有不同。

## 📝 快速检查清单
在开始安装前，请核对以下事项：
- [x] 备份笔记本内所有重要数据（安装会抹除全盘）。
- [ ] 准备一个容量 ≥ 8GB 的空白 U 盘。
- [ ] 已下载 Lubuntu 22.04.5 LTS 的 `.iso` 镜像文件。
- [ ] 已下载 Rufus 启动盘制作工具。
- [ ] 确保笔记本电源连接稳定（防止安装中途没电）。

---

## 一、 安装前准备

### 1.硬件检查与备份

> [!warning] 
> 选择“抹除磁盘”安装将彻底删除硬盘上的所有数据。请务必使用移动硬盘提前备份 `C:\Users` 下的个人文件及重要资料。

### 2.下载镜像

- **镜像下载地址**：访问 [Lubuntu 官网](https://lubuntu.me) (`lubuntu.me`)，
- ![[Pasted image 20260903182146.png]]
- 进入[Lubuntu 22.04.5 LTS (Jammy Jellyfish)](https://cdimage.ubuntu.com/lubuntu/releases/22.04/release/)
- ![[Pasted image 20260903182638.webp]]
- 👉 **点击下载这个文件：`lubuntu-22.04.5-desktop-amd64.iso`** （文件大小是 **2.9G** 的那个）

### 3.下载Rufus启动盘制作工具

- 进入[Rufus官网](https://rufus.ie/zh/)
- ![[Pasted image 20260903182828.webp]]
- 下载对应版本即可，针对老旧笔记本电脑的情况），**请下载第一个文件：**👉 **`rufus-4.15.exe`**
- ![[Pasted image 20260903183140.webp]]


### 4.制作启动盘

- 打开**Rufus**
- ![[rufus pasted.webp]]
- **设备：** 设备选择你的 U 盘
- **镜像：** 引导类型选择下载好的 `.iso` 文件`lubuntu-22.04.5-desktop-amd64.iso`
- **分区类型：** 对于老旧电脑（传统 BIOS），强制选择 **`MBR`**
- **目标系统：** 选择 **`BIOS 或 UEFI`**
-  点击“开始”。遇到“UEFI 吊销警告”和“ISOHybrid 镜像”提示时，**均直接点击【OK】** 并选择 **【以 ISO 镜像模式写入】**
- ![[Pasted image 20260903184324.webp]]
- ![[Pasted image 20260903184348.webp]]
- ![[Pasted image 20260903184407.webp]]

### BIOS/UEFI 设置差异
> [!tip] 老旧机型 (BIOS)
> 开机狂按 `F2` 进入 BIOS。在 `Advanced` 菜单中，将 `SATA Operation` 从 `AHCI` 修改为 `ATA`（或 `IDE`）模式，以提升老硬件兼容性。保存后重启。

> [!tip] 较新机型 (UEFI)
> 开机狂按 `F2` 进入 BIOS。在 `Boot` 选项卡中，关闭 `Secure Boot` (安全启动)，并将 U 盘设为第一启动项（Boot Priority ）。

---

## 二、 详细安装步骤

### 1. 启动 U 盘
插入 U 盘，开机狂按 `F12`，在 `Boot Option Menu` 中选择 **`USB Storage Device`** 或 **`Removable Device`** 进入。

>[!note]
>有时老旧电脑会检测不到我们的U盘可以尝试以下这些办法，笔者一开始U盘也是识别不出来，不过一番瞎折腾之后就突然好使了
>包括但不限于拔下u盘换个位置，彻底断电放静电，开机并启用 USB 支持（F2 键再次进 BIOS 设置界面 进去之后，看看能不能看到USB字样的菜单项或者叫Legacy USB Suppor，USB Configuration。如果有，确保它状态是Enabled）， 多次热拔插几次，暴力拍拍大法等

### 2.进入图形桌面

启动U盘后等待一段时间会出现这个界面
![[Pasted image 20260903190659.webp]]
进入黑底白字的菜单后，**强烈建议用键盘的上下方向键选择 `Lubuntu (safe graphics)` (安全图形模式)**，以防因显卡驱动问题导致黑屏。
![[Pasted image 20260903190816.webp]]
这样就算成功进入了

### 直接开始安装

1. 用鼠标双击桌面上的第二个图标：**`Install Lubuntu 22.04 LTS`**（带绿色向下箭头的那个）。
2. 启动安装程序。
3. 一路按照常识正常点继续

![[Pasted image 20260903191403.webp]]

![[Pasted image 20260903191422.webp]]

![[Pasted image 20260903191433.webp]]

![[Pasted image 20260903191440.webp]]

![[Pasted image 20260903191451.webp]]

### 网路连接

#### 方法1：插有线网线
找一根网线，一头插在你家路由器上，另一头直接插在这台戴尔电脑侧面的网口上。只要插上去，通常 3 秒钟内，屏幕右下角任务栏的网络图标就会发生改变，自动连上有线网络，你什么都不用设置。

#### 方法2：手机USB共享网络
笔者是荣耀手机，先进入设置里的关于手机，点击五下版本号进入开发者模式，再进入开发者选项，选择USB配置，RNDIS（USB以太网）。再找一根数据线，type-c连手机，usb那端连到电脑上。跟有线网线一样，通常只需要几秒钟就能连上网络。

### 方法3：WLAN
即使是老旧的笔记本，有的也可以连接wifi（路由器的wifi信号或者手机热点都可以），和windows一样，右下角任务栏里会有网络连接相关图标。
用手机热点的话，为了wifi信号可以兼容，安全性选WPA2-Personal，AP频段选2.4GHz频段（更好兼容性），WLAN协议版本用Wi-Fi 5(11ac)

>[!caution]
>如果半天连不上wifi，记得看看键盘上有没有类似信号塔的标志，一般在F1~F5的某个键位。
>笔者搞了半天才知道这个老笔记本键盘上有个控制网络的物理按键，气煞我也

## 三、 安装后必要设置

### 1. 语言与输入法
- 打开“首选项” -> “Language Support”，安装简体中文语言包。
- 打开“Muon 软件包管理器”，搜索并安装 `fcitx` 和 `fcitx-googlepinyin`。
- 在“首选项” -> “输入法” (Fcitx Configuration) 中添加 `Google Pinyin`。
- 注销并重新登录，按 `Ctrl+Space` 切换中英文，按 `Shift` 临时切换英文。

### 2. 软件源更新
打开终端 `QTerminal`，输入以下命令更新系统：

```bash
sudo apt update && sudo apt upgrade -y
```

### 3. 轻量级软件推荐
- **浏览器**：使用系统自带的 `Falkon`，或者安装 `Palemoon`，远离吃内存的 Firefox。
- **媒体播放**：安装 `VLC` (`sudo apt install vlc`)，用于播放本地视频及 m3u8 链接。
- **广告拦截**：务必在浏览器安装 `uBlock Origin` 插件，可极大提升网页浏览速度。

### 4. 无线网卡驱动处理
> [!warning] 常见问题
> 老旧无线网卡（如博通系列）在 Linux 下经常出现 `Hard blocked` 或被禁用的现象。

- 确保通过手机 USB 数据线共享网络（打开手机“USB 网络共享”）。
- 在终端输入 `sudo rfkill list` 检查状态。若显示 `Hard blocked: yes`，输入 `sudo rfkill unblock all` 强制解锁。
- 如果驱动缺失，通过 Muon 搜索并安装 `bcmwl-kernel-source`。安装后重启。

---

## 四、 常见问题及解决方案

> [!tip] 按优先级从高到低排列

1. **U盘插上就黑屏/死机 (优先级高)**
   - **现象**：一插 U 盘开机就黑屏，按什么键都没用。
   - **原因**：老电脑主板对 USB 3.0 接口或特定 U 盘芯片兼容性差。
   - **解决**：拔下 U 盘，换到黑色的 USB 2.0 接口。长按电源键 15 秒彻底放电，再插上 U 盘开机。

2. **BIOS 里键盘无法操作 (优先级高)**
   - **现象**：进入 BIOS 后按方向键和回车均无反应。
   - **原因**：BIOS 假死或 USB 键盘驱动未加载。
   - **解决**：强制关机断电，长按电源键 30 秒重置主板；检查是否是内置键盘问题。若是外接 USB 键盘，请务必插在黑色 USB 2.0 接口。

3. **BIOS 启动菜单里找不到 U 盘 (优先级高)**
   - **现象**：`Boot Option Menu` 只有 `Hard Drive` 和 `Network`。
   - **原因**：BIOS 未开启 USB 启动或模式不匹配。
   - **解决**：按 F2 进 BIOS，在 `Boot` 项内确认 `USB Boot` 为 `Enabled`；或在 `Advanced` 中修改 `SATA Operation` 为 `ATA` 后保存重启。

4. **安装时出现“正在等待其他软件管理器退出” (优先级高)**
   - **现象**：使用 Muon 时卡在等待界面。
   - **原因**：后台有 `apt` 进程锁冲突。
   - **解决**：打开 `QTerminal`，输入 `sudo killall apt apt-get` 强制清理锁，再输入 `sudo dpkg --configure -a` 修复。

5. **安装过程黑屏无反应 (优先级高)**
   - **现象**：进入引导菜单后屏幕变黑，光标闪烁但不进入桌面。
   - **原因**：老旧显卡无法正常硬件加速。
   - **解决**：重启，按 `F12` 重新进入菜单，**务必选择第二项 `Lubuntu (safe graphics)`**。

6. **安装系统后无法连 Wi-Fi (优先级中)**
   - **现象**：`Enable Wi-Fi` 选项点不开，或搜不到网络。
   - **原因**：网卡被硬件开关或系统驱动锁定。
   - **解决**：检查笔记本侧面/键盘上的物理 Wi-Fi 开关；在终端执行 `sudo rfkill unblock all` 强制解锁。

7. **找不到安装的输入法 (优先级中)**
   - **现象**：按 `Ctrl+Space` 无任何反应。
   - **原因**：未在 `Fcitx Configuration` 中添加输入法。
   - **解决**：打开“首选项” -> “输入法”，点击底部的 `+` 号，取消勾选 `Only Show Current Language`，手动搜索添加 `Google Pinyin`。

8. **火狐浏览器异常卡顿 (优先级中)**
   - **现象**：打开网页长时间无法响应。
   - **原因**：火狐在现代网页面前对老旧内存消耗极大。
   - **解决**：卸载火狐，使用轻量级的 `Falkon` 浏览器，并安装 `uBlock Origin`。

9. **系统桌面特效卡顿严重 (优先级低)**
   - **现象**：拖动窗口像放幻灯片。
   - **原因**：老旧核显处理 3D 合成特效吃力。
   - **解决**：在“LXQt 配置中心” -> “窗口特效”中，关闭所有的合成器效果。

10. **机械硬盘读写声音大且速度慢 (优先级低)**
    - **现象**：安装或打开程序时硬盘嘎吱作响。
    - **原因**：机械硬盘寿命长但性能瓶颈明显。
    - **解决**：通过 `Muon` 安装 `zram-tools`（内存压缩交换），以缓解磁盘 I/O 压力。

---

