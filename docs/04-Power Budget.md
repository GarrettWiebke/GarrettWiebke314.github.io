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
