---
slug: /
---

![SparkFun Gas Sensor - GM-XX2B (Qwiic) Hookup Guide Banner](/img/GMXX2B-HGBanner.png)

# Introduction

The SparkFun Gas Sensors - GM-XX2B (Qwiic) are a selection MEMS gas sensors useful for detecting concentrations of a wide variety of gases in indoor environments. The GM-XX2B are metal-oxide semiconductor sensors that react to their specified gas with an analog output that rises (or in the case of the GM-102B falls) with gas concentration. These gas sensor breakouts feed that analog signal into an onboard 10-bit I<sup>2</sup>C ADC to read gas levels over a Qwiic connection. The gas sensor breakouts covered in this guide are:

* [Nitrogen Dioxide Gas Sensor - GM-102B](https://www.sparkfun.com/sparkfun-nitrogen-dioxide-gas-sensor-gm-102b-qwiic.html)
* [Ethanol & Smoke Gas Sensor - GM-202B](https://www.sparkfun.com/sparkfun-ethanol-smoke-gas-sensor-gm-202b-qwiic.html)
* [Alcohol/Ethanol Gas Sensor - GM-302B](https://www.sparkfun.com/sparkfun-alcohol-ethanol-gas-sensor-gm-302b-qwiic.html)
* [Combustible Gas Sensor - GM-402B](https://www.sparkfun.com/sparkfun-combustible-gas-sensor-gm-402b-qwiic.html)
* [VOC Gas Sensor - GM-502B](https://www.sparkfun.com/sparkfun-voc-gas-sensor-gm-502b-qwiic.html)
* [Bad Breath Gas Sensor - GM-512B](https://www.sparkfun.com/sparkfun-bad-breath-gas-sensor-gm-512b-qwiic.html)
* [Hydrogen Sulfide Gas Sensor - GM-602B](https://www.sparkfun.com/sparkfun-hydrogen-sulfide-gas-sensor-gm-602b-qwiic.html)
* [Carbon Monoxide Gas Sensor - GM-702B](https://www.sparkfun.com/sparkfun-carbon-monoxide-gas-sensor-gm-702b-qwiic.html)
* [Ammonia Gas Sensor - GM-802B](https://www.sparkfun.com/sparkfun-ammonia-gas-sensor-gm-802b-qwiic.html)

In order to follow along with this tutorial, you'll need at least one of the GM-XX2B Gas Sensors along with the following items:

* [SparkFun IoT RedBoard - ESP32-P4 & ESP32-C5 (WiFi/BLE)](https://www.sparkfun.com/sparkfun-iot-redboard-esp32-p4-esp32-c5-wifi-ble.html) (or other Qwiic compatible development board)
* [Qwiic Cable](https://www.sparkfun.com/flexible-qwiic-cable-100mm.html)
* [USB-C Cable](https://www.sparkfun.com/catalog/product/view/id/7415/s/usb-c-to-usb-c-silicone-power-charging-cable-3m/)

## Topics Covered

This document contains three main sections: **Quick Start Guide**, **Hardware** and **Software**.

The Quick Start Guide goes over assembling the Gas Sensor in a Qwiic circuit with a compatible Arduino development board and jumps right into installing and uploading an example from the SparkFun GM-XX2B Arduino Library to get data from the sensors in just a few minutes.

The Hardware pages include a hardware overview that provides a detailed overview of the . The Hardware Assembly page goes over the steps required to assemble and use the board to detect gas concentrations with a compatible Arduino development board.

The Software pages give instructions on how to install the SparkFun GM-XX2B Arduino Library and use some of the examples included in it.

## Resources and Documentation

The **Resources** page has the board design files (KiCad files & schematic), relevant documentation (datasheets, white papers, etc.) and other helpful links. The **Support** page has a troubleshooting section that includes any helpful tips specific to this board as well as information on how to receive technical support from SparkFun.