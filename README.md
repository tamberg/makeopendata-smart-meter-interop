# Make.OpenData.ch Smart Meter Interop
A [make.opendata.ch](https://make.opendata.ch/) [#EnergyHack2020](https://twitter.com/hashtag/energyhack2020) project.

## Challenge
[Read your own smart meter](https://hack.opendata.ch/project/466) and [unleash its consumer information interface (CII)](https://hack.opendata.ch/project/582).

## Team
* [@tamberg](https://twitter.com/tamberg)
* You?

## Idea
Provide a "universal" adapter from smart meters to home automation IoT platforms.

* Connected device with Web UI
* Simple information model
* Serial or M-BUS input
* MQTT or HTTP based
* Template mechanism

## PoC 1: Raspberry Pi & Node-RED
* Get hardware
    * https://www.raspberrypi.org/products/raspberry-pi-3-model-b/
    * https://thepihut.com/products/modmypi-serial-hat-rs232
    * Smart Meter
* Read data from a smart meter
    * https://flows.nodered.org/node/node-red-contrib-smartmeter
* Publish data to the OpenHAB platform
    * https://flows.nodered.org/node/node-red-contrib-openhab2
* Provide a Web UI to configure templates
    * https://nodered.org/ via https://yaler.net/

## Resources
### Hardware
* https://thepihut.com/blogs/raspberry-pi-tutorials/how-to-use-the-modmypi-serial-hat

### Home Automation
* https://www.openhab.org/addons/

### Smart Meters
* [https://icube.ch/DLMSSurvivalKit/dsk1.html](https://icube.ch/DLMSSurvivalKit/dsk1.html)
* [https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf](https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf)
