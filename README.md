# Grove Kit for Win10 IoT Core & Azure Platform

This guide book specailly design for `Grove Kit for Win10 IoT Core & Azure Platform` which is created by [Seeed Studio](http://seeed.cc)'s Grove module and [Microsoft Azure](http://azure.microsoft.com) services.

Grove Kit for Win10 IoT Core & Azure Platform是一款为Microsoft Azure设计的物联网开发套件。

与传统的Grove Gettting Started不同的是，这款套件不关心具体的硬件开发，而是帮助你快速的了解和学习使用Windows IoT Core和Microsoft Auzre，以及其他的相关的服务。并且我们为此套件撰写一本Guide Book，其中包括了五个在不同Scenario下的项目。

**Architecture diagram:**

![](/assets/diagram.png)

**Scenarios and features:**

`Scenario 1: Don't catch cold`

检测温湿度传感器的值。然后通知你不要着凉了。

`Scenario 2: Sound&Light and relay`

Sound 或 Light 有一个触发条件，大于某个数值会触发 Relay Function。

然后Function会连接到IFTTT的 Maker 通道。

`Scenario 3: GAS monitor`

Gas 发送数据到 Azure，如果 CO 超标，触发异常 function，发送 eamil 给用户，同时打开 mini i2c motor driver（或者 mini fan？）1x Grove - 4 Digit Display $5.90 实时显示 Gas （CO）含量。问题：驱动电机做什么？抽风？还是？

`Scenario 4: One-Click SOS`

Button 触发 SOS 事件，Function 发送 Email 或者电话给家人。

`Scenario 5: Human detector`

PIR 发送人体运动事件到 iot hub，半个小时内 PIR 触发 &gt; 三次，记录这半小时为有人时段。发一份统计报告到 PowerBI

**What's included?**

1 xGrvoePi+

`Sensor:`

1 xGrove - Temp&Humi Sensor

1 xGrove - PIR Motion Sensor

1 xGrove - Sound Sensor

1 xGrove - Light Sensor v1.2

1 xGrove - Gas Sensor\(MQ2\)

1 xGrove - Button

`Actutor:`

1 x Grove - Relay

1 xGrove - LCD RGB Backlight

1 xGrove - 4 Digit Display

1 xGrove - Mini I2C Motor Driver v1.0

1 xDC Motor

1 xMini Fan

**Specification**

 - Connect map between Grove and GrovePi:

| Grove | GrovePi Port |
| :--- | :--- |
| D2 | Grove - Temp&Humi Sensor |
| D3 | Grove - PIR Motion Sensor |
| D4 | Grove – Button |
| D5 | Grove - Relay |
| A0 | Grove - Sound Sensor |
| A1 | Grove - Light Sensor |
| A2 | Grove - Gas Sensor |
| I2C1 | Grove - OLED Display 0.96" |
| I2C2 | Grove - Mini I2C Motor Driver |

**Resources:**

[Buy the kit](http://seeedstuido.com)

[Source code at Gtihub](https://github.com/Seeed-Studio/AzureGroveKit)

[UWP code](https://github.com/Seeed-Studio/AzureGroveKit/tree/master/UWP)

