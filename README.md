# FemFlow Firmware (STM32WB55)

This repository contains the embedded firmware developed for the **FemFlow SmartCup**, a product created as my Mechatronics Engineering fourth-year design project exploring **menstrual fluid volume monitoring** using embedded sensing and inter-device communication.

The system integrates **strain gauge–based force sensing** into a custom menstrual cup to estimate fluid mass in real time and transmit measurements to a database, to be displayed on a user application.

---

## Project Overview

FemFlow addresses a gap in menstrual health technology by enabling **quantitative, real-time tracking** of menstrual flow volume.

Key contributions of this project include:

- Laminated **strain gauges** bonded to the bottom diaphragm of a custom menstrual cup
- Analog front-end signal amplification using a **load cell + HX711**
- Embedded firmware for:
  - High-resolution mass sensing
  - Calibration and volume estimation
  - Data transmission to a remote database and a web application
- End-to-end validation using real fluid mass measurements

---

## Hardware

- **MCU:** STM32WB55 (Cortex-M4 + wireless coprocessor)
- **Sensor:** Strain gauge load cell
- **ADC:** HX711 24-bit ADC
- **Interfaces:**
  - GPIO (HX711 clock/data)
  - UART (debug / data output)
  - BLE (application-level data transmission)

---

## Firmware Features
- Bit-banged HX711 driver for raw 24-bit load cell readings
- Multi-point calibration for volume estimation (mL)
- Noise-tolerant sampling suitable for low-force measurements
- Designed for low-power, wearable operation

---

## Calibration Method

Volume estimation is derived from experimentally measured calibration points, and an average slope is computed across these segments to convert raw ADC counts into fluid volume (mL), ensuring robustness across the operating range.

---

## Validation

The system was validated by:
- Incrementally adding known fluid volumes
- Measuring raw HX711 output
- Comparing estimated vs actual volume

Results demonstrated reliable, repeatable measurements suitable for real-world use within the intended volume range.

---

## Development Environment

- **IDE:** STM32CubeIDE / VS Code
- **Toolchain:** arm-none-eabi-gcc
- **Language:** C / C++
- **HAL:** STM32WBxx HAL

---

## Future Work

- Improved digital filtering and drift compensation
- BLE power optimization
- Long-term wear and durability testing
- Expanded volume range and adaptive calibration

---

## License

This project was developed as part of an academic design course.  
All rights reserved unless otherwise stated.

---

## Author

**Nava Wu**  
Firmware Developer, building human-centered sensing systems. <br>
*B.A.Sc. Honours Mechatonics Engineering from the University of Waterloo*

