---
title: Hardware V2.0
---

# Hardware Design Version 2.0 Improvements

---

## Proposed Hardware Improvements for Version 2.0

The current hardware design successfully meets the project requirements by integrating an ESP32-S3 microcontroller, L9958 motor driver, DC motor, buck regulator, and status LEDs into a surface-mount PCB design. The design supports SPI communication with the motor driver, PWM motor speed control, UART mesh communication, and visual system feedback. While functional, several improvements could be made in a Version 2.0 hardware revision to improve reliability, manufacturability, debugging capability, and long-term robustness.

### 1. Improve Motor Driver Power Architecture

In the current design, the **L9958 motor driver** uses a motor supply voltage on the **VS pin** while logic-related communication is handled through SPI and PWM from the ESP32-S3. Although this satisfies functionality, Version 2.0 should include improved power filtering and decoupling around the motor driver.

Recommended improvements:

- Add dedicated bulk capacitance near the motor supply input (VS)
- Add local ceramic bypass capacitors close to:
  - VSO
  - VS
  - logic supply pins
- Separate motor power and logic ground return paths before joining at a common ground plane

**Why this should be improved:**

DC motors introduce switching noise, voltage ripple, and transient current spikes. Since the motor driver and microcontroller share the same PCB, these disturbances could introduce:

- SPI communication instability
- PWM noise coupling
- ESP32 brownout resets
- unreliable UART behavior

Improved filtering would reduce electrical noise and improve subsystem reliability during motor startup and stall conditions.

---

### 2. Add Motor Current Sensing or Diagnostics

The current Version 1 design controls motor speed and direction but does not directly measure motor current or detect load conditions.

Version 2.0 should include:

- inline current sensing resistor
- current sense amplifier or ADC measurement path
- fault monitoring from motor driver diagnostics if available

**Why this should be improved:**

Without current monitoring, the subsystem cannot detect:

- motor stall conditions
- excessive mechanical load
- abnormal current draw
- early hardware faults

This would improve safety and make future software upgrades possible, such as:

- overcurrent shutdown
- jam detection
- adaptive speed control

This is especially useful for submersible or propulsion systems where mechanical access may be limited.

---

### 3. Improve LED Status Feedback Design

The current design uses three LEDs connected to:

- IO16
- IO17
- IO18

These indicate:

- stopped
- 50% speed
- full speed

While functional, Version 2.0 could improve usability by standardizing LED meanings and improving visibility.

Recommended changes:

- Red = fault or stopped
- Yellow = reduced speed / warning
- Green = active or full speed

Additional improvements:

- use identical LED package footprints
- standardize resistor values
- position LEDs near PCB edge for visibility after enclosure installation

**Why this should be improved:**

Current LED documentation and software behavior evolved during development, causing some inconsistencies between fault indicators and speed indicators. A clearer status convention would improve debugging and operator understanding.

---

### 4. Add Dedicated Debug/Test Headers

The current design exposes functional pins but could be improved with dedicated debugging access.

Version 2.0 should include test pads or headers for:

- UART TX/RX
- SPI signals
- PWM output
- 3.3V
- GND
- EN/reset line

**Why this should be improved:**

This would simplify:

- firmware flashing
- oscilloscope debugging
- UART packet verification
- SPI troubleshooting

It also improves maintainability if the PCB must be tested after assembly or deployed in-field.

---

### 5. Improve Thermal Management of L9958

The schematic notes correctly specify that the **L9958 heat slug must be connected to GND**.

Version 2.0 should further improve thermal performance by adding:

- larger copper pour connected to heat slug
- multiple thermal vias beneath exposed pad
- thicker copper if board manufacturing permits

**Why this should be improved:**

The L9958 may drive significant motor current, causing heat generation under:

- high duty cycle operation
- motor startup current spikes
- stall or load conditions

Better thermal dissipation improves:

- component lifespan
- driver reliability
- sustained motor operation

This is particularly important in enclosed systems with limited airflow.

---

### 6. Add Reverse Polarity and Input Protection

The current design assumes proper supply polarity and stable input voltage.

Version 2.0 should include:

- reverse polarity protection
- input fuse or resettable fuse
- transient voltage suppression

**Why this should be improved:**

This protects the subsystem from:

- wiring mistakes
- power supply faults
- accidental battery reversal
- voltage spikes from motors or connectors

These additions significantly improve robustness during testing and deployment.

---

## Summary

The Version 1 hardware design successfully demonstrates functional motor control, communication, and subsystem integration. However, a Version 2.0 revision would improve the design by focusing on:

- cleaner power delivery
- thermal management
- fault detection
- debugging accessibility
- protection circuitry
- improved human-readable indicators

These changes would make the hardware more robust, easier to debug, safer to operate, and better suited for long-term deployment in future revisions of the project.

---
