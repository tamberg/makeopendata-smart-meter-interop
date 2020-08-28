# Make.OpenData.ch Smart Meter Interop
A [make.opendata.ch](https://make.opendata.ch/), [Energy Hackdays 2020](https://hack.opendata.ch/event/31) ([#EnergyHack2020](https://twitter.com/hashtag/energyhack2020)) project.

## Challenge
[Read your own smart meter](https://hack.opendata.ch/project/466) and [unleash its consumer information interface (CII)](https://hack.opendata.ch/project/582).

## Team
Hermann and [@tamberg](https://twitter.com/tamberg).

## Idea
Provide a "universal" adapter from smart meters to home automation IoT platforms.

### Requirements
* Physical adapter
* Minimal configuration, Web UI
* Allows a range of smart meter models
* Allows a range of home automation IoT platforms
* Keeps (personal) smart meter data in the local network

### Proposed solution
* Connected device with Web UI
* Simple information model
* Serial or Ethernet input
* MQTT or HTTP based
* Template mechanism

### How to get there?
Proof of Concept (PoC) prototypes, sketched out below as step-by-step instructions with TODOs to be filled in.
* [PoC 0](#poc-0-smart-meter-serial-usb) to get an idea about how the smart meter interface works at all.
* [PoC 1](#poc-1-raspberry-pi--node-red) to get an idea about the complexity of smart meter / IoT platform interfaces.
* [PoC 2](#poc-2-esp32--mqtt) to show what a simple information model and templating mechanism could look like.

### Open questions
* Can this be simpler than using a home automation IoT platform specific plugin?

## PoC 0: Smart Meter, Serial USB
### Read data from the smart meter
* TODO: Connect your computer to the smart meter via Serial
* TODO: Get data on a serial console, e.g. screen or PuTTY

## PoC 1: Raspberry Pi & Node-RED
### Get the hardware
* https://www.raspberrypi.org/products/raspberry-pi-3-model-b/
* https://thepihut.com/products/modmypi-serial-hat-rs232
* Smart Meter (available at Hackday? See [challenge #466](https://hack.opendata.ch/project/466))
### Set up the software
* On your computer, install https://www.openhab.org/
* On the Pi, install https://nodered.org/
### Open the configuration Web UI
* TODO: https://LOCAL_IP/ Node-RED instance, e.g. via https://yaler.net/
### Read data from the smart meter
* TODO: e.g. https://flows.nodered.org/node/node-red-contrib-smartmeter
### Publish data to the OpenHAB platform
* TODO: e.g. https://flows.nodered.org/node/node-red-contrib-openhab2

## PoC 2: ESP32 & MQTT
### Get the hardware
* https://www.adafruit.com/product/3405
* TODO: FeatherWing Serial, RJ485 or Ethernet adapter?
### Set up the software
* TODO: implement firmware .ino
* TODO: define simple infomration model
* TODO: develop moustache-like templating mechanism
* TODO: On your computer, e.g. mqtts://test.mosquitto.org/
### Open the configuration Web UI
* TODO: https://LOCAL_IP/
### Read data from the smart meter
* TODO: read variable values from smart meter
* e.g. https://www.arduino.cc/en/ArduinoModbus/ArduinoModbus
### Publish data to any MQTT broker
* TODO: insert variable values into topic / payload tempate
* e.g. https://www.arduino.cc/reference/en/libraries/mqtt-client/

## Resources
### IoT
* http://www.tamberg.org/fhnw/2019/hs/IoT07MessagingProtocols.pdf
* http://www.tamberg.org/fhnw/2019/hs/IoT10RuleBasedIntegration.pdf

### Home Automation
* https://www.openhab.org/addons/

### ESP32
* https://learn.adafruit.com/adafruit-huzzah32-esp32-feather

### Raspberry Pi
* https://thepihut.com/blogs/raspberry-pi-tutorials/how-to-use-the-modmypi-serial-hat

### Smart Meters
* https://www.landisgyr.com/webfoo/wp-content/uploads/2012/09/D000028191_E450_f_en.pdf
* [https://icube.ch/DLMSSurvivalKit/dsk1.html](https://icube.ch/DLMSSurvivalKit/dsk1.html)
* [https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf](https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf)

### M-Bus Adapter
* https://zeta-eng.ch/produkte/interfaces/zeta-usb-interfaces/m-bus-slave/
* https://zeta-eng.ch/fileadmin/zeta/images/PDF%20Dateien/ZETA_USB_Interfaces_-_Treiberinstallation.pdf (Serial via USB)
* https://m-bus.com/documentation-wired/04-physical-layer

## License
* Conceptual work is licensed under [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).
* Source code is licensed under the [MIT license](https://tamberg.mit-license.org/).
