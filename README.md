# Make.OpenData.ch Smart Meter Interop
A [make.opendata.ch](https://make.opendata.ch/), [Energy Hackdays 2020](https://hack.opendata.ch/event/31) ([#EnergyHack2020](https://twitter.com/hashtag/energyhack2020)) project.

> Work in progress, so far we have a rough concept only.

## Challenge
[Read your own smart meter](https://hack.opendata.ch/project/466) and [unleash its consumer information interface (CII)](https://hack.opendata.ch/project/582).

## Team
Hermann and [@tamberg](https://twitter.com/tamberg).

## Idea
Provide a "universal" adapter from smart meters to home automation / IoT platforms.

<img src="../../blob/master/interop-gateway.png" width="540">

<img src="../../blob/master/integration-points.png" width="540">

<img src="../../blob/master/http-push-pull.png" width="540">

<img src="../../blob/master/mqtt-builtin-generic.png" width="540">

<img src="../../blob/master/information-model.png" width="540">

<img src="../../blob/master/template-mechanism.png" width="540">

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
* [PoC 2](#poc-2-arduino--mqtt) to show what a simple information model and templating mechanism could look like.

### Open questions
* Can any (custom) library implementing DLMS (https://www.dlms.com/) be licensed as open source?
* Can a "universal" adapter be simpler than using home automation IoT platform specific plugins?

## PoC 0: Smart Meter, Serial USB
### Get the hardware
* Smart Meter (available at Hackday, see [challenge #466](https://hack.opendata.ch/project/466))
### Read data from the smart meter
* TODO: Connect your computer to the smart meter via Serial
  * https://icube.ch/DLMSSurvivalKit/params.gif
* TODO: Get data on a serial console, e.g. screen or PuTTY

## PoC 1: Raspberry Pi & Node-RED
### Get the hardware
* https://www.raspberrypi.org/products/raspberry-pi-3-model-b/
* https://thepihut.com/products/modmypi-serial-hat-rs232 (if no USB Serial)
* Smart Meter (available at Hackday, see [challenge #466](https://hack.opendata.ch/project/466))
### Set up the software
* On your computer, install https://www.openhab.org/
* On the Pi, install https://nodered.org/
### Open the configuration Web UI
* TODO: https://LOCAL_IP/ Node-RED instance, e.g. via https://yaler.net/
### Read data from the smart meter
* TODO: e.g. https://flows.nodered.org/node/node-red-contrib-smartmeter
* TODO: or a custom node based on https://icube.ch/demo_projects.html
### Publish data to the OpenHAB platform
* TODO: e.g. https://flows.nodered.org/node/node-red-contrib-openhab2

## PoC 2: Arduino & MQTT
### Get the hardware
* e.g. https://store.arduino.cc/arduino-mkr-wifi-1010
* and https://store.arduino.cc/arduino-mkr-485-shield
### Set up the software
* TODO: implement firmware .ino
* TODO: define simple information model
* TODO: develop moustache-like templating mechanism
* TODO: On your computer, e.g. mqtts://test.mosquitto.org/
### Open the configuration Web UI
* TODO: https://LOCAL_IP/
### Read data from the smart meter
* TODO: learn relevant parts of DLMS
* TODO: read variable values from smart meter
* e.g. https://www.arduino.cc/en/ArduinoModbus/ArduinoModbus
### Publish data to any MQTT broker
* TODO: insert variable values into topic / payload tempate
* e.g. https://www.arduino.cc/reference/en/libraries/mqtt-client/

## Resources
### IoT
* http://www.tamberg.org/fhnw/2019/hs/IoT07MessagingProtocols.pdf
* http://www.tamberg.org/fhnw/2019/hs/IoT10RuleBasedIntegration.pdf

### IoT platforms
* https://thingsboard.io/smart-metering/
* https://github.com/tamberg/fhnw-iot/wiki/IoT-Platforms

### Home automation
* https://www.openhab.org/docs/
* https://www.openhab.org/addons/
* https://www.openhab.org/addons/bindings/mqtt/
* https://www.openhab.org/docs/developer/bindings/
* https://www.openhab.org/docs/configuration/restdocs.html
* https://github.com/openhab/openhab-addons
* https://github.com/openhab/openhab-addons/tree/2.5.x/bundles/org.openhab.binding.mqtt.generic
* https://github.com/openhab/openhab-addons/tree/2.5.x/bundles/org.openhab.binding.smartmeter (Serial)

### Arduino
* https://store.arduino.cc/arduino-mkr-485-shield
* https://github.com/roarfred/MBusMqttLogger

### Raspberry Pi
* https://thepihut.com/blogs/raspberry-pi-tutorials/how-to-use-the-modmypi-serial-hat

### Smart meters
* https://www.landisgyr.com/webfoo/wp-content/uploads/2012/09/D000028191_E450_f_en.pdf
* [https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf](https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf)
* https://github.com/aselviar/cii_read_your_sm
* https://volkszaehler.org/
* https://github.com/volkszaehler
* https://www.netzburgenland.at/kundenservice/smart-metering/smart-metering/kundenschnittstelle.html

### DLMS
* [https://icube.ch/DLMSSurvivalKit/dsk1.html](https://icube.ch/DLMSSurvivalKit/dsk1.html)
* https://icube.ch/demo_projects.html
* https://icube.ch/demo_projects/java/dlms_java_demo.zip (includes proprietary DLMS Library)
* https://www.dlms.com/
* https://www.dlms.com/news-new-blue-book-and-green-book
* https://www.dlms.com/files/Blue_Book_Edition_13-Excerpt.pdf (COSEM Interface Classes and OBIS Object Identification System)
* https://www.dlms.com/files/Green_Book_Edition_9-Excerpt.pdf (DLMS/OSEM Architecture and Protocols)
* https://github.com/Gurux/Gurux.DLMS.cpp (licensed under GPL v2.0)
* https://github.com/roarfred/AmsToMqttBridge

### M-Bus
* https://zeta-eng.ch/produkte/interfaces/zeta-usb-interfaces/m-bus-slave/
* https://zeta-eng.ch/fileadmin/zeta/images/PDF%20Dateien/ZETA_USB_Interfaces_-_Treiberinstallation.pdf (Serial via USB)
* https://m-bus.com/documentation-wired/04-physical-layer

### Optical
* https://forum.arduino.cc/index.php?topic=119247.0
* https://en.wikipedia.org/wiki/High-Level_Data_Link_Control

## License
* Conceptual work is licensed under [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).
* Source code is licensed under the [MIT license](https://tamberg.mit-license.org/).
