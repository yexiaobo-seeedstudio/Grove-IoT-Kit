# Grove Kit for Win10 IoT Core & Azure Platform

**Note:** This guide book specailly design for `Grove Kit for Win10 IoT Core & Azure Platform` which is created by [Seeed Studio](http://seeed.cc)'s Grove module and [Microsoft Azure](http://azure.microsoft.com) services.

---

Grove Kit for Win10 IoT Core & Azure Platform is an IoT development kit which contains some Grove hardware module and  designed for Microsoft Azure services.

Unlike traditional Grove Getting Started kit, this kit does not concerned with how to write hardware driver or embedded development, but helps you quickly understand and learn how to use Windows 10 IoT Core and Microsoft Azure services. And We wrote a guide book for this Grove kit which included five projects with separate scenario.

**Overview:**![](https://raw.githubusercontent.com/Seeed-Studio/AzureGroveKit/master/physical.jpg)

**Architecture diagram:**

![](/assets/diagram.png)

**Scenarios and features:**

`Scenario 1: Don't catch cold`

Check the value of the temperature and humidity sensor. And then tell you not to catch cold when it low.

`Scenario 2: Sound&Light and relay`

When the Sound or Light sensor is greater than a value triggers the Microsoft Azure Function for relay sensor, then Function connects to the Maker channel of the IFTTT.

`Scenario 3: GAS monitor`

Gas send data to Azure, if CO‘s value exceeded, triggering exception Microsoft Azure Function, send eamil to the user, as well as opening mini fan.

`Scenario 4: One-Click SOS`

Button triggers an SOS event, Microsoft Azure Function sends an email or a call to a family.

`Scenario 5: Human detector`

PIR sensor sends human motion events to Microsoft Azure IoT Hub, within half an hour PIR triggers more than three times, recording this and then send a statistical report to PowerBI.

**What's included?**

1 x GrvoePi+

`Sensor:`

1 x Grove - Temp&Humi Sensor

1 x Grove - PIR Motion Sensor

1 x Grove - Sound Sensor

1 x Grove - Light Sensor v1.2

1 x Grove - Gas Sensor\(MQ2\)

1 x Grove - Button

`Actutor:`

1 x Grove - Relay

1 x Grove - OLED Display 0.96"

1 x Grove - 4 Digit Display

1 x Grove - Mini I2C Motor Driver v1.0

1 x DC Motor

1 x Mini Fan

**Specification**

* Connect map between Grove and GrovePi:

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

