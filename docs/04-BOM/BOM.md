---
title: Module Bill of Materials
tags:
- tag1
- tag2
---

## Overview
Below is a table of the Bill of Materials used to design and implement the Actuation Module for Team 307's Submersible Exploration device 

*Table 1: Actuation Module BOM*

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacture** | **Manufacturer #** | **Vendor Link** |**Datasheet Link** | **Schematic Reference Designators** |
|:--------------------|:----|:---------------|:-----|:--------|:-----|:-----|:----|:-----|
ESP32-S3-WROOM WiFi/Bluetooth Microcontroller Module | 1 | $6.50 | $6.50 | Espressif | ESP32-S3-WROOM-1 | [DigiKey](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1/16162634) | [Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_datasheet_en.pdf) | U1 |
Motor Driver IC, Dual Half Bridge, PowerSO-20 | 1 | $8.14 | $8.14 | STMicroelectronics | L9958 | [DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/L9958/2746837) | [Datasheet](https://www.st.com/resource/en/datasheet/l9958.pdf) | U2 |
140 RPM 6–24V DC Gearmotor | 1 | $7.12 | $7.12 | SparkFun | ROB-15277 | [DigiKey](https://www.digikey.com/en/products/detail/sparkfun-electronics/15277/9995750) | [Datasheet](https://cdn.sparkfun.com/assets/parts/1/5/2/7/7/15277-DC_Gearmotor_140RPM.pdf) | M1 |
Adjustable Buck Switching Regulator, SOT-23-6 | 1 | $1.68 | $1.68 | Texas Instruments | TPS54202DDCT | [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/TPS54202DDCT/6021967) | [Datasheet](https://www.ti.com/lit/ds/symlink/tps54202.pdf) | U3 |
Green Indicator LED, 569nm, 0603 Package | 2 | $0.20 | $0.40 | Lite-On | LTST-C190GKT | [DigiKey](https://www.digikey.com/en/products/detail/liteon/LTST-C190GKT/269230) | [Datasheet](https://optoelectronics.liteon.com/upload/download/DS-22-99-0187/LTST-C190GKT.pdf) | D1, D2 |
LED Current Limiting Resistor, 330Ω, 0603 Package | 2 | $0.10 | $0.20 | Yageo | RC0603FR-07330RL | [DigiKey](https://www.digikey.com/en/products/detail/yageo/RC0603FR-07330RL/727424) | [Datasheet](https://www.yageo.com/upload/media/product/productsearch/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) | R1, R2 |
Buck Converter Inductor, 10µH Shielded Power Inductor | 1 | $0.85 | $0.85 | Bourns | SRN4018-100M | [DigiKey](https://www.digikey.com/en/products/detail/bourns-inc/SRN4018-100M/6152761) | [Datasheet](https://www.bourns.com/docs/product-datasheets/srn4018.pdf) | L1 |
Input Ceramic Capacitor, 10µF 25V X7R 0805 | 1 | $0.35 | $0.35 | Murata | GRM21BR71E106KA73L | [DigiKey](https://www.digikey.com/en/products/detail/murata-electronics/GRM21BR71E106KA73L/490-6478-1-ND) | [Datasheet](https://search.murata.co.jp/Ceramy/image/img/P02/JELF243A-9126.pdf) | C1 |
Output Ceramic Capacitor, 22µF 10V X7R 0805 | 1 | $0.42 | $0.42 | Murata | GRM21BR61A226ME44L | [DigiKey](https://www.digikey.com/en/products/detail/murata-electronics/GRM21BR61A226ME44L/490-10483-1-ND) | [Datasheet](https://search.murata.co.jp/Ceramy/image/img/P02/JELF243A-9126.pdf) | C2 |
Bulk Motor Supply Capacitor, 470µF 25V Electrolytic | 1 | $1.10 | $1.10 | Panasonic | EEU-FR1E471 | [DigiKey](https://www.digikey.com/en/products/detail/panasonic-electronic-components/EEU-FR1E471/2433607) | [Datasheet](https://industrial.panasonic.com/cdbs/www-data/pdf/RDF0000/ABA0000C1175.pdf) | C3 |
Feedback Resistor (Buck Converter), 100kΩ 0603 | 1 | $0.10 | $0.10 | Yageo | RC0603FR-07100KL | [DigiKey](https://www.digikey.com/en/products/detail/yageo/RC0603FR-07100KL/727498) | [Datasheet](https://www.yageo.com/upload/media/product/productsearch/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) | R3 |
Feedback Resistor (Buck Converter), 19.1kΩ 0603 | 1 | $0.10 | $0.10 | Yageo | RC0603FR-0719K1L | [DigiKey](https://www.digikey.com/en/products/detail/yageo/RC0603FR-0719K1L/727464) | [Datasheet](https://www.yageo.com/upload/media/product/productsearch/datasheet/rchip/PYu-RC_Group_51_RoHS_L_6.pdf) | R4 |


## Resouce

The Bill of Materials as a PDF download is available [*here*](PDF_For_BOM_EXAMPLE.pdf).


### Section A — Major Component Maximum Current Consumption

| **Component** | **Function** | **Operating Voltage** | **Absolute Max Current** | **Source (Datasheet)** |
|:--------------------|:-------------|:--------------------|:--------------------|:--------------------|
ESP32-S3-WROOM Microcontroller | Main system controller, SPI master | 3.3 V | 500 mA | Espressif ESP32-S3 Datasheet |
L9958 Motor Driver | Controls direction and speed of DC motor | 12 V | 20 mA (logic consumption) | ST L9958 Datasheet |
SparkFun 140 RPM Gearmotor | Propulsion actuator | 12 V | 3 A (stall current estimate) | SparkFun Motor Documentation |

### Section B — Power Rail Current Budget

| **Power Rail** | **Components on Rail** | **Max Current (A)** | **Current with 25% Margin (A)** |
|:--------------------|:--------------------|:--------------------|:--------------------|
3.3 V Logic Rail | ESP32-S3-WROOM | 0.50 A | 0.63 A |
12 V Motor Rail | DC Gearmotor + L9958 Driver | 3.02 A | 3.78 A |

### Section C — 3.3V Voltage Regulator Selection

*Table: Voltage Regulator Option 1*

**TPS54202 Buck Switching Regulator**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| TPS54202 Adjustable Buck Regulator<br>[DigiKey Link](https://www.digikey.com/en/products/detail/texas-instruments/TPS54202DDCT/6021967) | * High efficiency switching regulator<br>* Wide input voltage range supports 12V supply<br>* Adjustable output allows precise 3.3V regulation | * Requires external inductor and capacitors<br>* Slightly more complex PCB layout |

---

*Table: Voltage Regulator Option 2*

**AMS1117-3.3 Linear Regulator**

| **Component** | **Pros** | **Cons** |
|---|---|---|
| AMS1117-3.3 Linear Regulator<br>[DigiKey Link](https://www.digikey.com/en/products/detail/advanced-monolithic-systems-inc/AMS1117-3-3/116507) | * Very simple circuit design<br>* Requires minimal external components<br>* Low cost and widely available | * Poor efficiency when stepping down from 12V<br>* Generates significant heat at higher currents |

### Section D — External Power Source

| **Power Source** | **Output Voltage** | **Maximum Current** | **Current Required by System** | **Remaining Current Available** |
|:--------------------|:--------------------|:--------------------|:--------------------|:--------------------|
Regulated Wall Power Supply | 12 V | 5.0 A | 3.78 A | 1.22 A |

### Section E — Battery Life Calculation

This system uses a regulated 12V wall power supply instead of a battery.  
Therefore, battery life calculations are not applicable for this design.

3.3V rail current: 0.63A
12V rail current: 3.78A
External supply capacity: 5A

Remaining margin: ~1.22A
