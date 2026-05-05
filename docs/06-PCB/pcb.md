---
title: Module PCB
---

## Overview

This PCB was designed to connect multiple surface-mount components featuring an ESP32-WROOM-S3-1, a SPI motor driver system, and a switching power regulator system 

From there, 3.3V is going into an SMT ESP32-WROOM-32D's 3V3 pin and the motor drivers' logic supply pins.

ESP32 has an external USB for computer power and easy programmability 

The ESP has 3 LEDS connected to GPIO pins to indicate the motor's levels of speed. 

PIN 2 is the shared UART, and PIN 8 is the shared ground on the team's 8-pin connector. 

---

## PCB
<img width="867" height="868" alt="image" src="https://github.com/user-attachments/assets/a356023b-80f4-4a36-8c08-11ee3c10cb74" />

---

## Resouces

The schematic as a PDF download is available [*here*](schematic314.pdf), and the Zip folder of the project [*here*](schematic314.zip).
