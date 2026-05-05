---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The following sections are the selected major components necessary for the actuation module of Team 307's submersible exploration device.

The component selection showcases the type of microcontroller used for the module, a DC motor for propulsion, a power regulator for motor power supply and logic voltage, as well as indicator LEDS for when the motor is stopped, 50% speed, or at full speed. All components were selected to meet project constraints and to be surface mount. 


# Microcontroller

---

*Table 14: Microcontroller Option 1*

**PIC18F47K42 Microcontroller**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Micro1.png)<br>PIC18F47K42 Microcontroller<br>$2.79 each<br>[link to product](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F47K42-I-PT/7561733) | * Inexpensive<br>* Easy debugging tools available | * Requires Microchip IDE environment |

**Specifications**

- Microcontroller Family: PIC18  
- Package Type: Surface Mount  
- Core: 8-bit MCU  
- Development Environment: Microchip MPLAB IDE  
- Manufacturer: Microchip Technology  

---

*Table 15: Microcontroller Option 2*

**ESP32-S3-WROOM-1-N4**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Micro2.png)<br>ESP32-S3-WROOM-1-N4 Module<br>$5.06 each<br>[link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639) | * Easy coding environment<br>* Strong SPI integration<br>* Integrated WiFi and Bluetooth capability | * Slightly more expensive |

**Specifications**

- Processor: Dual-core Xtensa LX7  
- Wireless Connectivity: WiFi and Bluetooth  
- Interface Support: SPI, I2C, UART, PWM  
- Package Type: Module with integrated antenna  
- Manufacturer: Espressif Systems  

---

*Table 16: Microcontroller Option 3*

**ESP32-S3-MINI-1**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Micro3.png)<br>ESP32-S3-MINI-1 Module<br>$5.28 each<br>[link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-MINI-1U-N8/17728863) | * Extremely small package<br>* Integrated WiFi and Bluetooth<br>* USB support | * Harder to work with due to small form factor |

**Specifications**

- Processor: Dual-core Xtensa LX7  
- Wireless Connectivity: WiFi and Bluetooth  
- Interfaces: SPI, I2C, UART, PWM, USB  
- Package Type: Compact module  
- Manufacturer: Espressif Systems  

---

## Microcontroller Choice: Option 2 — ESP32-S3-WROOM-1-N4
![](Micro2.png)

**Rationale**

The ESP32-S3-WROOM-1 module provides a strong balance between performance and ease of development. It offers built-in WiFi and Bluetooth capabilities, making wireless communication possible without additional hardware. The module also supports SPI communication, which simplifies integration with motor drivers and other peripherals. Compared to the smaller ESP32-S3-MINI package, the WROOM module is easier to work with and debug during development.

# Regular DC Motor

---

*Table 17: DC Motor Option 1*

**GEARMOTOR 140 RPM 6–24V**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](DC1.png)<br>GEARMOTOR 140 RPM 6–24V<br>$7.12 each<br>[link to product](https://www.digikey.com/en/products/detail/sparkfun-electronics/15277/9995750) | * High torque output<br>* Easy to control<br>* Wide operating voltage range | * Lower RPM (slower speed)<br>* Larger than some other motor options |

**Specifications**

- Type: DC Motor  
- Function: Gearmotor  
- Motor Type: Brushed  
- Rated Voltage: 6 – 24 VDC  
- Speed: 140 RPM  
- Rated Torque: 20.83 oz-in (147.1 mNm)  
- Rated Power: 1.6 W  
- Diameter: 22 mm (0.866 in)  
- Shaft Diameter: 6 mm (0.236 in)  
- Shaft Length: 14 mm (0.551 in)  
- Mounting Hole Spacing: 18 mm (0.709 in)  
- Termination Style: Solder Tab  

---

*Table 18: DC Motor Option 2*

**STANDARD MOTOR 12850 RPM 12V**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](DC2.png)<br>STANDARD MOTOR 12850 RPM 12V<br>[link to product](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/PAN14EE12AA1/2417070) | * Extremely high rotational speed | * Easy to stall<br>* Requires significant gear reduction |

**Specifications**

- Type: DC Motor  
- Function: Standard Motor  
- Motor Type: Brushed  
- Rated Voltage: 12 VDC  
- Speed: 12,850 RPM  
- Rated Torque: 0.694 oz-in (4.9 mNm)  
- Diameter: 24.2 mm (0.953 in)  
- Shaft Diameter: 1.5 mm (0.059 in)  
- Shaft Length: 11.5 mm (0.453 in)  
- Termination Style: Connector  

---

*Table 19: DC Motor Option 3*

**STANDARD MOTOR 6600 RPM 12V**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](DC3.png)<br>STANDARD MOTOR 6600 RPM 12V<br>[link to product](https://www.digikey.com/en/products/detail/sparkfun-electronics/11696/6163657) | * Moderate rotational speed | * Low torque<br>* Harder to control precisely |

**Specifications**

- Type: DC Motor  
- Function: Standard Motor  
- Rated Voltage: 12 VDC  
- Speed: 6,600 RPM  
- Termination Style: Wire Leads  

---

## DC Motor Choice: Option 1 — GEARMOTOR 140 RPM 6–24V
![](DC1.png)

**Rationale**

This gearmotor provides high torque with a manageable rotational speed, making it well-suited for applications requiring controlled motion. Its wide voltage range also makes integration easier within the system’s power architecture. Although it operates at a lower RPM than the other options, the higher torque and controllability make it a better fit for precise mechanical actuation.

# SMT Motor Driver

---

*Table 20: Motor Driver Option 1*

**L9958 Motor Driver (STMicroelectronics)**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Driver1.png)<br>L9958 Motor Driver IC<br>$8.14 each<br>[link to product](https://www.digikey.com/en/products/detail/stmicroelectronics/L9958/2746837) | * SPI controlled interface<br>* Integrated H-bridge driver<br>* Supports wide motor voltage range | * Slightly limited logic supply voltage |

**Specifications**

- Manufacturer: STMicroelectronics  
- Motor Type Supported: Brushed DC, Bipolar Stepper  
- Driver Type: Fully integrated motor driver  
- Output Configuration: Half Bridge (2)  
- Interface: SPI  
- Technology: CMOS  
- Output Current: 8.6 A  
- Supply Voltage: 4.5 – 5.5 V  
- Load Voltage Range: 4 – 28 V  
- Operating Temperature: -40°C to 150°C  
- Mounting Type: Surface Mount  
- Package: PowerSO-20  

---

*Table 21: Motor Driver Option 2*

**DRV8701 Motor Driver (Texas Instruments)**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Driver2.png)<br>DRV8701 Motor Driver IC<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/DRV8701PRGET/5299247) | * High voltage support<br>* Flexible current management | * Requires external MOSFET H-bridge<br>* More complex circuit design |

**Specifications**

- Manufacturer: Texas Instruments  
- Motor Type Supported: Brushed DC  
- Function: Motor Controller with Current Management  
- Output Configuration: Pre-driver Half Bridge  
- Interface: PWM  
- Technology: Power MOSFET Driver  
- Supply Voltage: 5.9 – 45 V  
- Load Voltage: 5.9 – 45 V  
- Operating Temperature: -40°C to 125°C  
- Mounting Type: Surface Mount  
- Package: 24-VQFN  

---

*Table 22: Motor Driver Option 3*

**MC33926 Motor Driver (NXP)**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Driver3.png)<br>MC33926 Motor Driver IC<br>[link to product](https://www.nxp.com/products/MC33926) | * SPI communication capability<br>* Easy motor control integration<br>* Low profile design | * Complex package and integration |

**Specifications**

- Manufacturer: NXP Semiconductors  
- Operating Voltage: 8 – 28 V continuous (5 – 40 V transient)  
- Maximum RDS(on): 225 mΩ (per MOSFET)  
- Logic Input Compatibility: 3.0 V and 5.0 V TTL/CMOS  
- Protection Features:  
  - Overcurrent limiting  
  - Short circuit protection  
  - Thermal protection  
- Low Power Mode: < 50 µA sleep current  
- Mounting Type: Surface Mount  

---

*Table 23: Motor Driver Option 4*

**IFX9201SG Full Bridge Motor Driver** This is the one provided in class

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](Driver4.png)<br>IFX9201SG Motor Driver<br>[link to product](https://www.digikey.com/en/products/detail/infineon-technologies/IFX9201SGAUMA1/5415542) | * Designed specifically for 12 V brushed DC motor applications<br>* Simple PWM and direction control interface<br>* Integrated protection features (overcurrent, overtemperature, short circuit) | * Does not support SPI communication<br>* Lower peak current capability than some automotive drivers<br>* Limited configuration and diagnostic feedback |

**Specifications**

- Manufacturer: Infineon Technologies  
- Motor Type Supported: Brushed DC  
- Output Configuration: Full H-Bridge  
- Supply Voltage Range: 6 – 28 V  
- Peak Output Current: ~6 A  
- Control Interface: PWM / Direction  
- Protection Features:  
  - Overcurrent protection  
  - Thermal shutdown  
  - Short circuit protection  
- Mounting Type: Surface Mount  
- Package: DSO-14  

---

## Motor Driver Choice: Option 1 — L9958 Motor Driver
![](Driver1.png)

**Rationale**

The L9958 motor driver provides a fully integrated motor control solution with an SPI interface, allowing the microcontroller to easily communicate with and control the motor system. The integrated H-bridge simplifies circuit design and reduces the number of additional components required on the PCB. Its wide load voltage range and high current capability also make it well-suited for driving the selected DC motor within the system.


# Voltage Regulator

---

*Table 23: Voltage Regulator Option 1*

**TPS54202 Adjustable Buck Switching Regulator**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](REG1.png)<br>TPS54202 Buck Switching Regulator<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/TPS54202DDCT/6021967) | * Wide input voltage range supports a 12 V power supply<br>* Adjustable output allows generation of the required 3.3 V logic rail<br>* High efficiency synchronous buck regulator reduces heat and power loss | * Requires external components such as an inductor and capacitors<br>* PCB layout must be carefully designed to minimize switching noise<br>* 2 A current limit may restrict future expansion of peripherals |

**Specifications**

- Manufacturer: Texas Instruments  
- Function: Step-down (Buck) Regulator  
- Output Configuration: Positive  
- Topology: Buck  
- Output Type: Adjustable  
- Number of Outputs: 1  
- Input Voltage Range: 4.5 – 28 V  
- Output Voltage Range: 0.596 – 28 V  
- Output Current: 2 A  
- Switching Frequency: 500 kHz  
- Synchronous Rectifier: Yes  
- Operating Temperature: -40°C to 125°C  
- Mounting Type: Surface Mount  
- Package: SOT-23-6 Thin (TSOT-23-6)  

---

*Table 24: Voltage Regulator Option 2*

**MP1584 Adjustable Buck Switching Regulator**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](REG2.png)<br>MP1584 Buck Switching Regulator<br>[link to product](https://www.digikey.com/en/products/detail/monolithic-power-systems-inc/MP1584EN-LF-Z/5291742) | * Higher output current capability (3 A)<br>* Adjustable output voltage allows flexible power rail design<br>* Wide switching frequency range enables flexible regulator design | * Listed as **Not Recommended for New Designs (NRND)**<br>* Requires additional passive components for proper operation<br>* Larger package size increases PCB footprint |

**Specifications**

- Manufacturer: Monolithic Power Systems  
- Function: Step-down (Buck) Regulator  
- Output Configuration: Positive  
- Topology: Buck  
- Output Type: Adjustable  
- Number of Outputs: 1  
- Input Voltage Range: 4.5 – 28 V  
- Output Voltage Range: 0.8 – 25 V  
- Output Current: 3 A  
- Switching Frequency: 100 kHz – 1.5 MHz  
- Synchronous Rectifier: No  
- Operating Temperature: -20°C to 85°C  
- Mounting Type: Surface Mount  
- Package: 8-SOIC (Exposed Pad)  

---

*Table 25: Voltage Regulator Option 3*

**LM2596 Fixed 12V Buck Switching Regulator**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](REG3.png)<br>LM2596 Buck Switching Regulator<br>[link to product](https://www.digikey.com/en/products/detail/texas-instruments/LM2596S-12-NOPB/363703) | * High current output capability (3 A)<br>* Reliable and widely used regulator design<br>* Wide input voltage range supports many power sources | * Fixed 12 V output cannot generate the required 3.3 V logic rail<br>* Larger package compared to modern switching regulators<br>* Lower switching frequency requires larger external components |

**Specifications**

- Manufacturer: Texas Instruments  
- Function: Step-down (Buck) Regulator  
- Output Configuration: Positive  
- Topology: Buck  
- Output Type: Fixed  
- Number of Outputs: 1  
- Input Voltage Range: 4.5 – 40 V  
- Output Voltage: 12 V  
- Output Current: 3 A  
- Switching Frequency: 150 kHz  
- Operating Temperature: -40°C to 125°C  
- Mounting Type: Surface Mount  
- Package: TO-263 (D2PAK)  

---

## Voltage Regulator Choice: Option 1 — TPS54202 Adjustable Buck Switching Regulator
![](REG1.png)

**Rationale**

The TPS54202 switching regulator provides an efficient and compact solution for stepping down the system voltage to the required logic voltage levels. Its wide input voltage range allows it to easily regulate a 12 V supply, while the adjustable output enables the generation of the 3.3 V rail required by the ESP32 microcontroller and supporting electronics. The small surface-mount package also makes it well-suited for integration on the project PCB.


# Indicator LEDs

---

*Table 26: LED Option 1*

**Infrared (IR) LED Emitter 940 nm — 0603 Package**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](LED1.png)<br>Infrared LED Emitter 940 nm<br>[link to product](https://www.digikey.com/en/products/detail/kingbright/APT1608F3C/2163696) | * Useful for sensing and communication applications<br>* Very compact 0603 SMT footprint<br>* Low forward voltage and efficient operation | * Not visible to the human eye<br>* Not suitable for status indication<br>* Requires sensor to detect emission |

**Specifications**

- Type: Infrared LED Emitter  
- Wavelength: 940 nm  
- Forward Voltage: 1.2 V (typical)  
- Forward Current: 50 mA max  
- Radiant Intensity: 1.2 mW/sr @ 20 mA  
- Viewing Angle: 150°  
- Mounting Type: Surface Mount  
- Package: 0603 (1608 Metric)  

---

*Table 27: LED Option 2*

**Green Indicator LED — 0603 Package**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](LED2.png)<br>Green Indicator LED 569 nm<br>[link to product](https://www.digikey.com/en/products/detail/liteon/LTST-C190GKT/269230) | * Highly visible indicator color<br>* Compact SMT footprint ideal for PCB integration<br>* Low power consumption | * Lower brightness than larger LEDs<br>* Small package may be harder to solder manually<br>* Limited viewing distance |

**Specifications**

- Color: Green  
- Dominant Wavelength: 569 nm  
- Forward Voltage: 2.1 V (typical)  
- Test Current: 10 mA  
- Luminous Intensity: 6 mcd  
- Viewing Angle: 130°  
- Mounting Type: Surface Mount  
- Package: 0603 (1608 Metric)  

---

*Table 28: LED Option 3*

**Red Indicator LED — 2-PLCC Surface Mount**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| ![](LED3.png)<br>Red Indicator LED 625 nm<br>[link to product](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/VLMR334BACB-GS08/4563545) | * Very bright output for clear visibility<br>* Easily recognizable status indicator color<br>* Wide viewing angle | * Larger package footprint<br>* Higher forward current than smaller LEDs<br>* Slightly higher power consumption |

**Specifications**

- Color: Red  
- Dominant Wavelength: 625 nm  
- Peak Wavelength: 632 nm  
- Forward Voltage: 2.2 V (typical)  
- Test Current: 50 mA  
- Luminous Intensity: 2200 mcd  
- Viewing Angle: 120°  
- Mounting Type: Surface Mount  
- Package: 2-PLCC (J-Lead)  

---

## Indicator LED Choice: Option 2 — Green Indicator LED (0603 Package)
 ![](LED2.png)

**Rationale**

The green 0603 LED provides a compact and efficient indicator solution for PCB integration. Its small surface-mount footprint minimizes board space while still providing adequate brightness for status indication. Additionally, the low power consumption and common indicator color make it well-suited for visual feedback in the system.

## Final Selected Major Components Summary

The following table summarizes the final major components selected for the actuation module design. Only major active components and electromechanical devices are included.

| **Subsystem** | **Selected Component** | **Primary Function** | **Final Selection Reason** |
|---|---|---|---|
| Microcontroller | ESP32-S3-WROOM-1-N4 | Main system controller, SPI communication, PWM generation, wireless capability | Easy development environment, integrated WiFi/Bluetooth, strong peripheral support |
| DC Motor | GEARMOTOR 140 RPM 6–24V | Mechanical propulsion / actuation output | High torque, controllable speed, compatible voltage range |
| Motor Driver | L9958 Motor Driver | Brushed DC motor driving and SPI motor control | Integrated H-bridge, SPI diagnostics/control, reduced external circuitry |
| Voltage Regulator | TPS54202 Adjustable Buck Regulator | Steps system voltage down to 3.3 V logic rail | High efficiency, adjustable output, compact SMT footprint |
| Indicator LEDs | Green Indicator LED (0603 Package) + Red/Yellow/Green Status LEDs | Visual system state indication (stopped, 50% speed, full speed, fault/status) | Compact SMT package, low power, simple visual feedback |

---

## Pinout table (Motor driver, LEDS, ESP32)

# L9958 Motor Driver Pinout

| **L9958 Pin** | **Function** | **ESP32-S3 Connection / Notes** |
|---|---|---|
| **1** | DIR | IO39 |
| **2** | VSO | 3.3V |
| **3** | SO (MISO) | IO48 |
| **4** | VS | Motor Supply (6V or 12V) |
| **5** | OUT1 | Motor Terminal 1 |
| **6** | GND | GND |
| **7** | OUT2 | Motor Terminal 2 |
| **8** | SI (MOSI) | IO47 |
| **9** | CSN | IO45 |
| **10** | SCK | IO21 |
| **11** | DIS (Enable) | IO40 |
| **12** | PWM | IO41 |
| **Heat Slug** | Thermal Pad | **GND (Required)** |

## Status LEDs

| **LED** | **Purpose** | **ESP32-S3 Pin** | **Notes** |
|---|---|---|---|
| ![](LED_Red.png)<br>Red LED | Motor Stopped | IO16 | Use ~220Ω series resistor |
| ![](LED_Yellow.png)<br>Yellow LED | Motor Slow (50% PWM) | IO17 | Use ~220Ω series resistor |
| ![](LED_Green.png)<br>Green LED | Motor Full Speed (100% PWM) | IO18 | Use ~220Ω series resistor |

## Wiring Notes

- **Heat slug must be connected to GND** for thermal dissipation and proper grounding.
- Connect both **Pin 6 (GND)** and **Heat Slug** directly to the ground plane.
- Motor supply on **VS** should match motor voltage (**6V or 12V**).
- Add current-limiting resistors (~220Ω–330Ω) in series with each LED.
- OUT1 and OUT2 connect directly to the DC motor terminals.

