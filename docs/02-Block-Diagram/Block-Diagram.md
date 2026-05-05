---
title: Actuation Module's Block Diagram 
tags:
- tag1
- tag2
---

## Overview
This is the Actuation block diagram for Team 307 made by Garrett Wiebke.

The features include:

* SMT ESP32 controlling subsystem
* Motor driver using SPI communication between it and the ESP32
* 12V external power Supply, 3.3V 1.5A switching regulator 
* 12V High-Power DC Propulsion Motor 
* 12V 5A AC-DC wall power supply
* Communication via other modules via UART 
* Indicator LEDS (Green, Yellow, Red)
* Robust upstream/downstream 8-pin headers with shared power and ground

## Decision-Making Process
Team 307's autonomous submersible exploration device needed a means of actuation. This system fits the team's requirements of having an SPI motor driver communicating with an ESP to control a motor with a propeller on its shaft. This system is able to communicate with other teammates' subsystems via UART through the use of robust upstream and downstream 8-pin headers traced to the ESP's RX and TX pins, with the additional features of shared power and ground for ease of connection. The block diagram below only uses pins on the ESP32-WROOM-S3-1 as well as the SPI motor driver, and leaves out unconnected pins or pins not used for SPI communication.




## Actuation Block Diagram 

![Team 307 Actuation Block Diagram](UpdatedIndividual.drawio.png)
