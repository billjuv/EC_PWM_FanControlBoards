# EC-PWM Fan Control Boards — USB-C

These boards were designed for controlling EC fans that use USB-C connectors for PWM speed control. They are modifications of [Kyle Gabriel's](https://github.com/kizniche) (Mycodo) fan control boards for TerraBloom EC fans, adapted to use USB-C connectors instead of audio connectors.

The boards provide voltage level shifting for safe use with Raspberry Pi GPIO pins or ESP32 pins, and support monitoring of tach signals (RPM) from compatible fans.

---

## Overview

You can safely control the PWM speed of EC fans supplied with 10VDC via USB-C cable — such as AC Infinity ("UIS") or Vivosun ("SGS") fans, and possibly others — without the need for proprietary controllers.

### Tested and Verified

| Fan | PWM Control | Tach (RPM) |
|-----|-------------|------------|
| AC Infinity Airlift S Series Shutter Fan | ✅ | ✅ |
| AC Infinity Cloudray S6 6" Clip Fan | ✅ | ❌ |
| Vivosun AeroWave E6 Gen2 6" Clip Fan | ✅ | ❌ (larger models unknown) |

Testing was done using a Raspberry Pi 4 with Mycodo, and ESP32 boards with ESPHome and MQTT.

---

## Board Variations

Three board variations are included (see README in Gerber folder for details):

<img src=Attachments/IMG_1477.jpg width="60%"/>
<img src=Attachments/IMG_1484.jpg width="60%"/>

| Board | Description |
|-------|-------------|
| **Left** — `USB-C_Breakout_x_2.54` | Gerber modified for offset transistor lead footprint (not as shown) |
| **Center** — `2.54x2_Breadboard` | Short enough for jumpers on both ends |
| **Right** — `JST-PH_x_2.54` | Designed for use with the 'xiwai' 4-pin cabinet mount USB-C cable (link below) |

All boards include 10V and GND pads for tapping into fan power if needed.

> **Note:** Both transistors are 2N3904.

---

## Schematic

![GPIO Header](Attachments/Screenshot%202025-08-11%20at%205.42.39%E2%80%AFPM.PNG)

---

## Cable

These fans use a USB-C style cable carrying PWM and tach signals — not USB data. The JST-PH board variant was specifically designed around the cabinet-mount cable linked below.

[Amazon — USB-C Pigtail Extension Cable][cable]

<img src=Attachments/cable.jpg width="50%"/>

<img src=Attachments/IMG_4349.jpg width="50%"/>

*Hole sizes for the above cable mount*

---

## Background — Why the JST-PH Version?

The two photos below show the original setup using Kyle's boards with cabinet-mounted USB-C cables. The awkward wiring is exactly what motivated the JST-PH board redesign.

<img src=Attachments/IMG_0289.jpg width="60%"/>
<img src=Attachments/IMG_0293.jpg width="60%"/>

---

## What's Included

- Gerber files for all three board variations
- Schematic/GPIO header diagram
- Links to compatible parts

---

## Related Project

For a stand-alone ESP32/ESPHome fan control box, incorporating the circuitry used these boards, see the companion repository:
[EC Fan Control using ESP32, ESPHome and MQTT](https://github.com/billjuv/EC_Fan_ESPHome)

---

[cable]: https://www.amazon.com/Female-Waterproof-Terminal-Pigtail-Extension/dp/B0D7CN4BTV/ref=sr_1_1?crid=22DIPVZJ6NLNA&dib=eyJ2IjoiMSJ9.5A5gh8wlE1dA5xzyWRfnF6wJ0fd9cFGKaGoMoL32RONrxG9_nN8LmJ9rJli3ujotLw90tzZNpYxllE3eMCpda7KoQPOh_-vPp3rROVUxTw11IfYGYRkTlLA7TaCoP3jR.uXNtln_9dJgcMFb5AaFasS38uiNJQxI2SMAjDUyGoKk&dib_tag=se&keywords=xiwai%2B5pcs%2FSet&qid=1761968034&sprefix=xiwai%2B5pcs%2Fset%2Caps%2C101&sr=8-1&th=1
