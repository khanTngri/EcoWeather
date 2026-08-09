# EcoWeatherX — Open Source Portable Weather Station

This is the official repository for **EcoWeather**, a portable open-source weather station designed for precise environmental and atmospheric monitoring. 

> **Status: Prototype (v0.1)**
> This is the initial alpha hardware revision (August 2026). It is currently undergoing testing and validation. Use at your own risk.

---

## Licensing & Trademark Protection

This project is fully open-source, but it uses a **Strong Copyleft + Trademark Protection** model to prevent proprietary exploitation and unauthorized commercial cloning under the original brand name.

### 1. Hardware Licensing
The hardware design (schematics, PCB layouts, BOM, and production files) is licensed under the **CERN Open Hardware Licence Version 2 - Strongly Reciprocal** ([CERN-OHL-S-2.0](https://spdx.org)).
* You are free to study, modify, and manufacture this hardware.
* **Crucial:** If you modify this hardware and distribute your version, you **must** release your modifications under the exact same CERN-OHL-S-2.0 license.

### 2. Firmware Licensing
The source code for the microcontroller firmware is licensed under the **GNU GPL v3** ([GNU GPLv3](https://gnu.org)).
* Any derivative firmware or commercial products shipping with this software must also be fully open-source under the GPLv3.

### 3. Trademark & Brand Protection
* **"EcoWeatherX"** and the project logos are the exclusive trademarks of **Tenri** (Copyright © 2026).
* **All rights to brand/logo reserved.**
* You **may NOT** manufacture and sell commercial clones of this hardware using the name "EcoWeather" or the original logos without explicit written permission from Tenri. 
* Commercial forks must be completely rebranded (e.g., sold as *"Weather Station based on EcoWeather open source files"* but not as *EcoWeather* itself).

---

## Hardware Specifications (v0.1)

* **Designer:** Tenri
* **Release Date:** August 2026
* **Revision:** Proto v0.1

### Sensor Array:
* **Pressure, Temperature & Humidity:** `Bosch BME280` (I2C)
* **UVA / UVB Light Intensity:** `Vishay VEML6075` (I2C)
* **Non-Contact Infrared Temperature:** `Melexis MLX90614 (GY-906)` (I2C)
* **Ambient Light / Lux Sensor:** `Texas Instruments OPT3007` (I2C)
* **Particulate Matter (PM1.0, PM2.5, PM4.0, PM10):** `Sensirion SPS30` (UART/I2C optical particle counter)

### UI / Display:
* **Display:** 1.8" TFT LCD Display with `ST7735` driver (SPI)

### Power Management System (PMS):
* **Battery Configuration:** 1S2P Li-ion (using 2x Panasonic `NCR18650B` cells, 3.7V)
* **Battery Charger & Power Path:** `Microchip MCP73871` (System power prioritisation)
* **Battery Protection IC:** `TI BQ29700DSER` + `NexFET CSD16406Q3` dual N-channel MOSFET for overvoltage/undervoltage protection
* **3.3V Power Rail:** `TI TPS63070` High-Efficiency Buck-Boost Converter (for MCU and sensors)
* **5V Power Rail:** `TI TPS63070` High-Efficiency Buck-Boost Converter (for SPS30 particulate sensor and display backlight)

---

## Getting Started

### Hardware Production
To manufacture this board, use the Gerber files located in the `/hardware/production/` directory. 
* *Note: The PCB includes the mandatory licensing silkscreen on the layer as specified by OSHW rules.*

### Firmware Installation
1. Open the `/firmware/` folder in your preferred IDE (e.g., VS Code + PlatformIO / Arduino IDE).
2. Configure your target microcontroller pinout mapping for I2C and SPI buses.
3. Flash the microcontroller.

---

## Contact & Contribution

If you want to contribute to the project, report bugs, or discuss commercial licensing options for the **EcoWeather** brand, please open an Issue or contact **Tenri** directly via GitHub.
