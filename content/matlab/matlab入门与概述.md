### 例4
已知某个控制系统的传递函数为：
$$H(s) = \frac{-11s}{s^3 - 12s^2 + s - 1}$$
试判断它的单位阶跃响应特性、幅频特性和相频特性。

```matlab
num=[-11,0]; den=[1, -12, 1, -1]; %获得控制系统传函分子和分母的多项式
step(num,den); %命令step()用于获得控制系统的 %单位阶跃响应特性曲线
```

![[untitled.svg]]

---

### 例5
需要分别绘制四幅图，例如 y1 = sin(t)，y2 = -sin(t)，y3 = cos(t)，y4 = -cos(t)，并标注横、纵坐标为：t(deg)，sin(t)，-sin(t)，cos(t)，-cos(t)

```matlab
% 图形分割命令的使用方法举例

clear; clc; close;

t = [0:pi/20:5*pi];

subplot(2,2,1);

% 图形分割1

plot(t, sin(t), 'r', 'linewidth', 3)

% 绘制正弦函数 sin(t) 的曲线图

axis([0 16 -1.5 1.5]); xlabel('t(deg)'); ylabel('magnitude'); title('sin(t)'); grid on;

subplot(2,2,2);

% 图形分割2

plot(t, -sin(t), 'b', 'linewidth', 3)

% 绘制正弦函数 -sin(t) 的曲线图

axis([0 16 -1.5 1.5]); xlabel('t(deg)'); ylabel('magnitude'); title('-sin(t)'); grid on;

subplot(2,2,3);

% 图形分割3

plot(t, cos(t), 'y', 'linewidth', 3)

% 绘制余弦函数 cos(t) 的曲线图

axis([0 16 -1.5 1.5]); xlabel('t(deg)'); ylabel('magnitude'); title('cos(t)'); grid on;

subplot(2,2,4);

% 图形分割4

plot(t, -cos(t), 'c', 'linewidth', 3)

% 绘制余弦函数 -cos(t) 的曲线图

axis([0 16 -1.5 1.5]); xlabel('t(deg)'); ylabel('magnitude'); title('-cos(t)'); grid on;
```

![[untitled15.svg]]

---

### 例16
在 MATLAB 的编辑器中键入下列命令语句

```matlab
t = 0:pi/50:2*pi;
x = sin(t); y = cos(t); z = t;

subplot(2,1,1);
grid on
stem3(x, y, z);
view([-37, 24]);

subplot(2,1,2);
grid on
fill3(x, y, z, 'g');
view([-42, 36]);
```

![[untitled16.svg]]

---

### 例19
已知某个传感器的传递函数为：
$$
H_s(s) = -K_s \frac{s\omega_n^2}{s^2 + 2\xi\omega_n s + \omega_n^2}
$$

式中 $\omega_n^2$、$K_s$、$\xi$ 分别为：

$$
\omega_n^2 = \frac{R_0 + R_s}{L_0 C_0 R_s}, \quad 
K_s = \frac{M R_s}{R_s + R_0}, \quad 
\xi = \frac{R_s + R_0 + L_0}{2\sqrt{R_s + R_0}\sqrt{R_s L_0 C_0}}
$$

需要研究该传感器的以下特性：  
(1) 单位阶跃响应；  
(2) 幅频特性和相频特性。

假设式（1-1）中各个参数的取值分别为：

$$
R_0 = 0.5\Omega, \quad M = 100\mu H, \quad R_s = 0.05\Omega, \quad L_0 = nM, \quad n = 50, \quad C_0 = 100pF
$$

现用 MATLAB 的编辑器创建 M 文件，并保存为 `exm_20_Step.m`：

```matlab
% 研究传感器的单位阶跃响应
% 参数赋值

R0 = 0.5; 
M = 100e-6; 
Rs = 0.05; 
n = 50; 
L0 = n * M; 
C0 = 100e-12; 
k = -M * Rs / (R0 + Rs);

pusine = (L0 + R0) / 2 / sqrt(Rs * L0 * C0 * (Rs + R0));
womga = sqrt((Rs + R0) / (Rs * L0 * C0));

% 定义传感器的传递函数的分子与分母
num = [k * womga * womga, 0];
den = [1, 2 * womga * pusine, womga * womga];

sys = step(num, den);

plot(sys, 'r', 'linewidth', 3), grid on;

% 获取传感器传递函数的单位阶跃响应曲线，并添加网格线
title('传感器的单位阶跃响应');
xlabel('Second');
```

执行本程序，即可获得传感器的单位阶跃响应曲线，如图所示

![[untitled19.svg]]


---

```matlab
% 研究传感器的幅频特性和相频特性

R0 = 0.5; 
M = 100e-6; 
Rs = 0.05; 
n = 50; 
L0 = n * M; 
C0 = 100e-12; 
k = -M * Rs / (R0 + Rs);

pusine = (L0 + R0) / 2 / sqrt(Rs * L0 * C0 * (Rs + R0));
womga = sqrt((Rs + L0 * C0) / (Rs + L0 * C0));   % 注：原文此处公式疑似有误，通常应为 sqrt((Rs+R0)/(Rs*L0*C0))

num = [k * womga * womga, 0];
den = [1, 2 * womga * pusine, womga * womga];

bode(num, den), grid on;

% 获取传感器传递函数的幅频和相频特性，并绘制网络线
```

![[untitled20.svg]]

---

### 例27
#### 整流波形描述方法举例
**【举例27】** 逐段解析函数的计算和表达。如果要绘制图1-47所示图形，可以在MATLAB的编辑器窗口中键入以下命令并保存为 `exm_28.m`：

```matlab
% 逐段解析函数的计算和表达

t = linspace(0, 3*pi, 500); % 从0到3*pi均匀产生500个数据，赋值给t

y = 10 * sin(t); % 产生正弦波

z = (y >= 0) .* y; % 正弦波叠加半波（正半波保留，负半波置零）

a = 10 * sin(pi/3); % 设定阈值

z = (y >= a) * a + (y < a) .* z; % 前项的正弦波叠加半波（幅值限制）

plot(t, y, 'r--', 'linewidth', 3); hold on; % 红色虚线

plot(t, z, 'b', 'linewidth', 3); % 蓝色实线

% 绘图形添加横、纵坐标和标题

xlabel('时间 t');

ylabel('幅值');

title('逐段解析函数示例');

legend('y = 10sin(t)', '整流后波形');

grid on;
```

本例的执行结果如图所示。
![[untitled27.svg]]


---

**补充说明**：用于获得半波整流的其他编程方法。

假设在 `[0, 3π]` 区间，表达式为 `y = sin(x)`，可以在MATLAB命令窗口中键入：

```matlab
x = 0:pi/200:3*pi; y = sin(x);
y1 = (x < pi | x > 2*pi) .* y; plot(x, y1, 'r', 'linewidth', 3);
% 语句中 "x < pi | x > 2*pi" 表示 x 小于 pi 或者 x 大于 2*pi，即消去负半波波形

title('半波整流')
```

本例的执行结果如图所示（半波整流输出曲线）

![[untitled28.svg]]

---





