# Sun2UsbAdapter
Adapter for using Sun Keyboards (4/5/6) as USB devices, with macro support, using the excellent [Alexander Vollschwitz's suniversal adapter](https://codeberg.org/xelalexv/suniversal). This repo includes the specific pinout for the OEM 8pin
connector, and how to wire it to the arduino pro micro (clone).

## Parts

[Cheap Ebay 8Pin MiniDin](https://es.aliexpress.com/item/1005004227811305.html?spm=a2g0o.order_detail.order_detail_item.4.69bd39d3pFY9NK&gatewayAdapt=glo2esp), model N8Pin (3,60€ / 5 units).

<center>
<img width="640px" src="img/n8pin.jpg"></img>
</center>

[Ardunio Micro Clone](https://www.amazon.es/ATmega32U4-Compatible-Arduino-Gen%C3%A9rica-incluidos/dp/B0C4TQM3T5/ref=sr_1_3_sspa?keywords=Arduino+Micro&qid=1688457493&sr=8-3-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1) Any model will work.

<center>
<img width="640px" src="img/arduino.jpg"></img>
</center>

## Connector Pinout and wiring

After reverse engineer the wiring, I get the following
table:

<center>
<img width="640px" src="img/8pinconnector.png"></img>
</center>

| **Connector PIN** | **Base PIN** | **Wiring color** | **Description** | **Arduino PIN** |
|-------------------|--------------|-----------------:|-----------------|-----------------|
| 1                 | E            | Red              | VCC +5V         |             VCC |
| 2                 | F            | White/Black      | -               |                 |
| 3                 | H            | Green            | From Keyboard   |        D10 (RX) |
| 4                 | A            | White            | To Keyboard     |         D9 (TX) |
| 5                 | G            | Black            | From Mouse      |                 |
| 6                 | D            | Yellow           | VCC +5V         |                 |
| 7                 | B            | Yellow/Black     | GND             |             GND |
| 8                 | C            | Grey             | GND             |                 |

## Software Install

See the guide on [Alexander Vollschwitz's suniversal adapter](https://codeberg.org/xelalexv/suniversal). Just download the sketch, select your board (arduino micro or leonardo) and download it. Just edit the
`config.h` file and select your options (mine where don't use mouse, and don't debug)