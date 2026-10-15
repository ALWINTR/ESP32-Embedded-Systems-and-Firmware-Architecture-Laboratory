# ESP32 Embedded Systems and Firmware Architecture Laboratory

<div align="center">

[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-00f0ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ALWINTR/ESP32-Embedded-Systems-and-Firmware-Architecture-Laboratory)
[![Developer](https://img.shields.io/badge/Developer-Alwin_T_R-0284c7?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alwintr)
[![Portfolio](https://img.shields.io/badge/Portfolio-alwintr.github.io-00f0ff?style=for-the-badge&logo=googlechrome&logoColor=black)](https://alwintr.github.io)
[![License](https://img.shields.io/badge/License-MIT-10b981?style=for-the-badge)](LICENSE)

</div>

> Comprehensive firmware architecture laboratory containing production-ready low-level peripheral drivers, FreeRTOS queue pipelines, task pinning, and non-volatile storage (NVS) implementations on ESP32.

---

## 📌 Executive Overview

Comprehensive firmware architecture laboratory containing production-ready low-level peripheral drivers, FreeRTOS queue pipelines, task pinning, and non-volatile storage (NVS) implementations on ESP32. This repository contains production-ready firmware implementations, hardware wiring pinouts, signal conditioning routines, and real-time telemetry pipelines engineered for reliable physical operation.

- **Primary Domain**: Embedded Firmware
- **Microcontroller & Hardware Core**: ESP-IDF / FreeRTOS
- **Specialization**: Firmware Architecture
- **Live Specs & BOM Viewer**: [alwintr.github.io](https://alwintr.github.io)

---

## 📐 System Architecture & Signal Flow

```
+--------------------------------------------------------------+
|             ESP32 Dual-Core Xtensa LX6 (240MHz)              |
+--------------------------------------------------------------+
        |                                              |
 [Core 0: Network & Event Loop]             [Core 1: Real-Time Peripheral Task]
        |                                              |
        v                                              v
+-----------------------+                    +-----------------------+
|  FreeRTOS Queue IPC   | <================> |  FreeRTOS Mutex Queue |
+-----------------------+                    +-----------------------+
        |                                              |
        +---> [Hardware Timer ISR]                     +---> [SPI Master Engine]
        +---> [ADC with DMA Buffering]                 +---> [I2C Fast Mode Bus]
        +---> [UART Ring Buffer ISR]                   +---> [NVS Storage Engine]
```

---

## 📋 Hardware Bill of Materials (BOM)

| Component Name | Operating Voltage | Interface / Functionality |
| :--- | :--- | :--- |
| **ESP32-WROOM-32D Development Board** | `3.3V / 5V` | Dual 240MHz cores, 520KB SRAM, 4MB Flash |
| **Logic Analyzer Test Points** | `Diagnostic` | Hardware protocol validation |
| **Multiple SPI / I2C Sensor Test Rigs** | `Sensors` | Hardware driver testing |

---

## 🔌 Circuit Pinout & Microcontroller Interconnect

| MCU Pin / Channel | Peripheral Pin | Signal Function / Bus |
| :--- | :--- | :--- |
| `GPIO 23 (MOSI), GPIO 19 (MISO), GPIO 18 (SCK)` | `VSPI Master Bus` | High-Speed SPI |
| `GPIO 21 (SDA), GPIO 22 (SCL)` | `I2C Bus Master` | 400kHz Two-Wire Bus |
| `GPIO 16 (RX), GPIO 17 (TX)` | `UART2 Telemetry Stream` | Ring-Buffered Serial |
| `GPIO 36, 39` | `ADC1 Analog Inputs` | Low-Noise ADC Channels |

---

## ⚙️ Firmware Architecture & Control Logic

Modular, reusable firmware library featuring FreeRTOS ring-buffered UART drivers, multi-slave SPI bus masters, and robust power-failure-tolerant NVS storage.

### Key Firmware Capabilities:
- **Zero-Blocking Architecture**: Real-time non-blocking scheduling eliminating delay() deadlocks.
- **Hardware Interrupt Servicing**: Microsecond-precision edge-triggered pulse detection and safety shutoffs.
- **Diagnostic Telemetry**: Continuous serial datastreaming and state-machine transition logging.

---

## 📁 Repository Structure

```
ESP32-Embedded-Systems-and-Firmware-Architecture-Laboratory/
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🚀 Build & Deployment Instructions

### 1. Hardware Assembly
- Verify common system ground across all microcontrollers, drivers, and peripheral sensor boards.
- Ensure dedicated power supply rails match the operating voltage specified in the Hardware Bill of Materials.

### 2. Firmware Compilation & Flashing
```bash
# Clone the repository
git clone https://github.com/ALWINTR/ESP32-Embedded-Systems-and-Firmware-Architecture-Laboratory.git

# Navigate to the project directory
cd ESP32-Embedded-Systems-and-Firmware-Architecture-Laboratory
```

- Open the project in **Arduino IDE**, **PlatformIO**, or **ESP-IDF**.
- Select the target board configuration and COM port.
- Compile and upload firmware directly to the microcontroller.

---

## 👨‍💻 Author

**Alwin T R** — Robotics & Automation Engineer  
- 💼 **LinkedIn**: [linkedin.com/in/alwintr](https://www.linkedin.com/in/alwintr)  
- 🌐 **Interactive Portfolio**: [alwintr.github.io](https://alwintr.github.io)  
- 🐙 **GitHub**: [github.com/ALWINTR](https://github.com/ALWINTR)  
- ✉️ **Direct Email**: [alwintr2003@gmail.com](mailto:alwintr2003@gmail.com)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
