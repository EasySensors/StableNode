**The StableNode is a low cost wireless Arduino IDE compatible (the Atmel ATMega328P 8MHz) microcontroller with The Nordic nRF24L01+ 2.4 GHz Radio transceiver on board.** 
------------------------------------------------------------------------

Best sutable for Home Automation, IOT. Could be used as core board for radio controlling any DIY project. Accurate designed RF subsystem based on NRF24L01+ chip with optimal tunned pcb antenna

![enter image description here](https://github.com/EasySensors/StableNode/blob/master/pics/StableNode.jpg?raw=true)
![enter image description here](https://github.com/EasySensors/StableNode/blob/master/pics/StableNode2.jpg?raw=true)


## Specification: ##
 - Dimensions 59mm x 18mm
 - The Nordic nRF24L01+ 2.4 GHz Radio transceiver on board
 - Supply voltage up to 6.5 Volts
 - The Digital and Analog pins are 5 volts
 - 4 battery connector pins
 - FTDI  header for programming
 

**Pin out:** 


Arduino Pins|	Description
------------|--------------
A0, A2, A3, A4, A5, A6,  A7 |	Available ARDUINO analog GPIO / DIGITAL GPIO
D2, D9, D10, D11,D12, D13 |	Connected to nRF24L01+ 2.4 GHz Radio 
D3, D4, D5, D6, D7, D8 |	Available ARDUINO digital GPIO
Bat+ | Unregulated power up to 6.5 Volts
Bat- | Ground
Scissors line | you cat cut with scissors, sensors and battery holder part, if you need just controller and radio


**Arduino IDE Settings**

![Arduino IDE Settings](https://github.com/EasySensors/ButtonSizeNode/blob/master/pics/IDEsettings.jpg?raw=true)


How to use it as home automation (IOT) node controller
------------------------------------------------------


StableNode.ino is the Arduino example sketch using [MySensors](https://www.mysensors.org/) API. 

- **Controller Setup.**  
Burn the StableNode.ino sketch into the board and it will became  one of the MySensors home automation network Sensor's Node. 
To create the home automation network you need smarthome controller and at least two Nodes one as a Sensor, a Relay or an Actuator Node and the other one as the “Gateway Serial” connected to a smarthome controller. I personally love [Domoticz](https://domoticz.com/) as a smarthome controller. Please check this [HowTo](https://github.com/EasySensors/ButtonSizeNode/blob/master/DomoticzInstallMySensors.md) to install Domoticz.

- **No Controller setup.** 
However, for no-controller setup, as example, you can use 3 nodes - first node as the “Gateway Serial”, second node as a Relay and last one as a Switch for that Relay. No controller needed then, keep the Switch and the Relay on the same address and the switch will operate the relay. 


Things worth mentioning about the  [MySensors](https://www.mysensors.org/) Arduino sketch: 


Arduino Pins|	Description
------------|--------------
#define MY_RADIO_NRF24|	Define the radio we use – here is nRF24L01+ 2.4 GHz Radio 
#define MY_NODE_ID 0xE0 | Define Node address (0xE0 here). I prefer to use static addresses<br> and in Hexadecimal since it is easier to identify the node<br> address in  [Domoticz](https://domoticz.com/) devices list after it<br> will be discovered by controller ( [Domoticz](https://domoticz.com/)).<br> However, you can use AUTO instead of the hardcoded number<br> (like 0xE0) though.  [Domoticz](https://domoticz.com/) will automatically assign node ID then.

Connect the Node to FTDI USB adaptor, Select Pro Mini 8MHz board in Arduino IDE and upload the StableNode.ino sketch.

**Done**

The board is created by  [Koresh](https://www.openhardware.io/user/143/projects/Koresh)


>Schematic:

![enter image description here](https://github.com/EasySensors/StableNode/blob/master/pics/StableNodeSchematic.jpg?raw=true)

[**The board schematics Pdf link**](https://github.com/EasySensors/StableNode/blob/master/pdf/Schematic__1_03.PDF)


P.S. Always mind! if your Arduino code fails you need some backup plan. Put some candles and matches in your bathroom )))))... hope you understand. Start your automation wisely. Like auotomate your doghouse first. Then checkenshed and so on!!!
