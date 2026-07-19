---
title: Node.js���ڿصƲ���
---
## 硬件

```c
#include <reg51.h>   // AT89C55头文�?
sbit LED = P1^0;     // LED接P1.0

// ====== 串口初始�?(9600bps @ 11.0592MHz) ======
void UART_Init() {
    TMOD = 0x20;      // 定时�?，模�? (8位自动重�?
    TH1 = 0xFD;       // 9600波特�?    TL1 = 0xFD;
    SCON = 0x50;      // 模式1 (8位UART)，允许接�?    TR1 = 1;          // 启动定时�?
    ES = 1;           // 使能串口中断
    EA = 1;           // 使能总中�?}

// ====== 串口中断服务 ======
void UART_ISR() interrupt 4 {
    unsigned char cmd;
    
    if (RI) {                     // 接收到数�?        cmd = SBUF;               // 读取指令
        RI = 0;                   // 清除接收标志
        
        if (cmd == 0x01) {
            LED = 0;              // 开�?        } else if (cmd == 0x00) {
            LED = 1;              // 关灯
        }
        
        // 可选：回传确认（调试用�?        SBUF = cmd;               // 回显
        while(!TI);               // 等待发送完�?        TI = 0;
    }
}

// ====== 主函�?======
void main() {
    LED = 1;          // 初始关灯
    UART_Init();
    
    while(1) {
        // 无限循环，所有工作都在中断里完成
    }
}
```


---

## 后端

```javascript
const express = require('express');

const { SerialPort } = require('serialport');

const app = express();

const PORT = 3000;

  

app.use(express.json());

app.use(express.static('public'));

  

// ====== 配置虚拟串口 ======

// VSPD创建了一对：COM3 �?COM4

// Node.js用COM3，Proteus用COM4

const serialPort = new SerialPort({

    path: 'COM3',        // 改成你VSPD创建的那个端�?
    baudRate: 9600,

    dataBits: 8,

    stopBits: 1,

    parity: 'none'

});

  

serialPort.on('open', () => {

    console.log('�?串口COM3已打开');

});

  

serialPort.on('error', (err) => {

    console.log('�?串口错误:', err.message);

});

  

// ====== 接收网页控制指令 ======

app.post('/led', (req, res) => {

    const state = req.body.state;  // 0=�? 1=开

    // 协议：单字节指令

    // 0x01 = 开�? 0x00 = 关灯

    const cmd = Buffer.from([state]);

    serialPort.write(cmd, (err) => {

        if (err) {

            console.log('�?串口写入失败:', err.message);

            res.status(500).send('控制失败');

        } else {

            console.log(`💡 发送指�? ${state === 1 ? '开�? : '关灯'}`);

            res.send('成功');

        }

    });

});

  

app.listen(PORT, () => {

    console.log(`🌐 服务启动: http://localhost:${PORT}`);

});
```


---

## 前端

```html
<!DOCTYPE html>

<html>

<head>

    <meta charset="UTF-8">

    <title>LED控制面板</title>

    <style>

        body { font-family: Arial; text-align: center; padding: 50px; }

        .btn {

            padding: 30px 60px;

            font-size: 28px;

            border: none;

            border-radius: 15px;

            cursor: pointer;

            margin: 20px;

            transition: 0.3s;

        }

        .btn-on { background: #4CAF50; color: white; }

        .btn-on:hover { background: #45a049; }

        .btn-off { background: #f44336; color: white; }

        .btn-off:hover { background: #da190b; }

        #status { font-size: 24px; margin-top: 30px; }

    </style>

</head>

<body>

    <h1>💡 LED智能控制</h1>

    <button class="btn btn-on" onclick="sendCmd(1)">🔛 开�?/button>

    <button class="btn btn-off" onclick="sendCmd(0)">🔛 关灯</button>

    <div id="status">等待操作...</div>

  

    <script>

        function sendCmd(state) {

            fetch('/led', {

                method: 'POST',

                headers: { 'Content-Type': 'application/json' },

                body: JSON.stringify({ state: state })

            })

            .then(res => res.text())

            .then(data => {

                document.getElementById('status').innerHTML =

                    state === 1 ? '�?灯已开�? : '�?灯已关闭';

            })

            .catch(err => {

                document.getElementById('status').innerHTML = '�?发送失�?;

            });

        }

    </script>

</body>

</html>
```
