---
title: Module Schematic
---

## Overview

This schematic is designed to support the actuation module of Team 307. A through hole barrel jack connector is being fed 12V 5A. 12V 5A is branched into three lines. Line 1 is going into the team's 8-pin ribbon connector for shared power between all systems. Line 2 is going into the motor drivers motor power supply pins to directly power the motor with 12V. Line 3 is going into a buck power regulator to be stepped down to 3.3V

From there 3.3V is going into an SMT ESP32-WROOM-32D's 3V3 pin and the motor drivers logic supply pins.

ESP32 has an external USB for computer power and easy programmability 

The ESP has 3 LEDS connected to GPIO pins to indicate the motors levels of speed. 

PIN 2 is shared UART and PIN 8 is shared ground on the team's 8-pin connector. 


![schematic](){style width:"350" height:"300;"}


## Resouces

The schematic as a PDF download is available [*here*](ExampleSchematic.pdf), and the Zip folder of the project [*here*](dummyZip.zip).
