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

## PoC 1: Raspberry Pi, Serial & Node-RED
### Get the hardware
* https://www.raspberrypi.org/products/raspberry-pi-3-model-b/
* https://thepihut.com/products/modmypi-serial-hat-rs232 (depends on smart meter)
* Smart Meter (available at Hackday? See [challenge #466](https://hack.opendata.ch/project/466))
### Set up the software
* On your computer, install https://www.openhab.org/
* On the Pi, install https://nodered.org/
### Read data from the smart meter
* https://flows.nodered.org/node/node-red-contrib-smartmeter
### Publish data to the OpenHAB platform
* https://flows.nodered.org/node/node-red-contrib-openhab2
### Provide a Web UI to configure templates
* https://nodered.org/ via https://yaler.net/

## PoC 2: Arduino, ModBUS & MQTT
### Get the hardware
* TODO
### Set up the software
* TODO
### Read data from the smart meter
* TODO
### Provide a Web UI to configure templates
* TODO

## Resources
### Hardware
* https://thepihut.com/blogs/raspberry-pi-tutorials/how-to-use-the-modmypi-serial-hat

### Home Automation
* https://www.openhab.org/addons/

### Smart Meters
* [https://icube.ch/DLMSSurvivalKit/dsk1.html](https://icube.ch/DLMSSurvivalKit/dsk1.html)
* [https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf](https://www.netbeheernederland.nl/_upload/Files/Slimme_meter_15_a727fce1f1.pdf)
