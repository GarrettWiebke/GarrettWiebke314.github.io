---
title: Module API
---

# Subsystem API Description

---

## Overview

Node G is the motor actuation subsystem responsible for receiving UART network commands, controlling the motor driver through SPI and PWM, and reporting subsystem status back onto the team communication mesh.

The subsystem supports:

- Motor speed control (`fast`, `slow`, `stop`)
- Motor direction toggling
- Status reporting
- UART message relaying for frames not addressed to Node G

---

## Message Frame Format

All UART messages follow the standardized team frame format.

| **Field** | **Bytes** | **Description** |
|---|---|---|
| Start Marker | `AZ` | Indicates start of valid message |
| Sender ID | 1 byte | Sending node identifier |
| Receiver ID | 1 byte | Destination node identifier |
| Payload | Variable | Command or status message |
| End Marker | `YB` | Indicates end of valid message |

### General Message Format

```text
AZ [Sender] [Receiver] [Payload] YB
```

### Example

```text
AZJGfastYB
```

Meaning:

- Start = `AZ`
- Sender = `J`
- Receiver = `G`
- Payload = `fast`
- End = `YB`

---

## Accepted Incoming API Commands

Node G accepts the following incoming commands.

| **Sender** | **Receiver** | **Payload** | **Function** | **Subsystem Action** |
|---|---|---|---|---|
| J | G | `fast` | Set motor high speed | PWM set to 75% duty cycle |
| J | G | `slow` | Set motor reduced speed | PWM set to 25% duty cycle |
| J | G | `stop` | Stop motor | PWM set to 0% |
| A | G | `button on` | Toggle motor direction | Switch forward/reverse SPI command |

---

## Outgoing API Messages

Node G generates the following messages.

| **Sender** | **Receiver** | **Payload** | **Purpose** |
|---|---|---|---|
| G | A | `MotorOn` | Announces Node G is online after boot |
| G | D | `motorfast` | Reports motor currently at fast speed |
| G | D | `motorslow` | Reports motor currently at slow speed |
| G | D | `motorstop` | Reports motor currently stopped |

---

## Relay Behavior

If Node G receives a valid UART frame not addressed to itself, the frame is retransmitted unchanged.

| **Condition** | **Action** |
|---|---|
| Receiver ≠ G | Relay message unchanged onto UART network |

This allows Node G to act as a network relay participant in the UART mesh.

---

## Motor Control API Behavior

### Speed Commands

| **Command** | **PWM Duty Cycle** | **Motor Result** |
|---|---|---|
| `fast` | 75% (767 / 1023) | High-speed operation |
| `slow` | 25% (255 / 1023) | Reduced-speed operation |
| `stop` | 0% | Motor disabled |

### Direction Command

| **Command** | **Action** |
|---|---|
| `button on` | Toggles forward ↔ reverse motor direction |

Direction is updated through SPI command bytes sent to the L9958 motor driver.

---

## Indicator LED Behavior

Node G provides visual feedback using three onboard LEDs.

| **LED Pin** | **Behavior Trigger** | **Indication** |
|---|---|---|
| IO16 | `fast` command | Rapid flashing (5x, 100 ms) |
| IO17 | `slow` command | Slow flashing (3x, 500 ms) |
| IO18 | `stop` command | Single long blink (1000 ms) |

---

## Initialization Sequence

On boot, Node G performs the following startup actions:

1. Initializes UART communication
2. Initializes SPI motor driver
3. Sets default motor direction to forward
4. Sets PWM duty cycle to 0% (motor stopped)
5. Sends boot announcement:

```text
AZGAMotorOnYB
```

---

## Error Handling / Validation

Node G validates received UART messages before execution.

| **Validation Check** | **Behavior** |
|---|---|
| Invalid sender ID | Warning printed |
| Invalid receiver ID | Warning printed |
| Message length > 64 bytes | Message discarded |
| Message too short | Ignored |

---

## Node Identifier Information

| **Constant** | **Value** |
|---|---|
| Node ID | `G` |
| Broadcast ID | `M` |
| Max Message Length | 64 bytes |

---
