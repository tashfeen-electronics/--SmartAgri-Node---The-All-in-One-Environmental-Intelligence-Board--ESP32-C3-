# 🌾 SmartAgri Node — The All-in-One Environmental Intelligence Board— ESP32-C3 Environmental Monitoring PCB

A custom 4-layer PCB designed in KiCad for smart agriculture and environmental data logging — built around the **ESP32-C3-WROOM-02-H4**, with onboard sensing, local storage, and off-grid power management.
<img width="774" height="484" alt="image" src="https://github.com/user-attachments/assets/1d27216a-63c2-452a-8151-a8cc61c1e1ce" />

![Designed with KiCad](https://img.shields.io/badge/Designed%20with-KiCad-orange)
![Layers](https://img.shields.io/badge/PCB-4--Layer-blue)
![MCU](https://img.shields.io/badge/MCU-ESP32--C3-green)

---

## 🚀 Overview

## 🌾 SmartAgri Node — The All-in-One Environmental Intelligence Board

*A masterclass in compact IoT engineering — built for the field, engineered for the future.*

Powered by the **ESP32-C3-WROOM-02-H4**, this board isn't just a sensor node — it's a complete edge-computing ecosystem packed into a single, elegant design. Whether you're building smart farms, weather networks, or next-gen IoT products, this board is your foundation.

### 🚀 Flagship Applications

- **🌱 Precision Agriculture Systems** — Real-time climate intelligence (temp, humidity, pressure, light) empowers farmers to optimize irrigation, planting, and harvest cycles like never before
- **☀️ Off-Grid Solar Monitoring Stations** — Autonomous, self-charging design (USB-C + battery + MCP73871 power management) means true "install and forget" reliability in remote locations
- **📡 Enterprise-Grade IoT Weather Networks** — Wi-Fi/BLE connectivity turns every unit into a live data point in a scalable, cloud-connected sensor mesh
- **💾 Mission-Critical Data Logging** — Onboard microSD ensures zero data loss, even in connectivity dead zones — perfect for research-grade field studies
- **🔊 Smart Environmental Surveillance** — Integrated mic input opens doors to acoustic monitoring: pest detection, livestock sounds, equipment health diagnostics
- **🔆 Intelligent Light Management** — TEMT6000 sensor enables automated greenhouse shading, grow-light control, and crop exposure analytics
- **🔌 Plug-and-Play Expansion Platform** — I2C/GPIO breakout headers make this a launchpad for custom sensor arrays: soil moisture, pH, EC, CO2, and beyond
- **🛡️ Industrial-Grade Power Protection** — ESD protection, fuse safeguarding, and regulated 3.3V rail deliver rock-solid reliability in harsh outdoor conditions
- **☁️ OTA-Ready Firmware Architecture** — Onboard SPI flash means remote fleets can be updated instantly — no truck rolls, no manual reflashing
- **🎓 Premier Prototyping & Education Platform** — USB-C programming, dedicated BOOT/RESET buttons, and SPI test points make this the go-to dev board for makers, students, and R&D teams alike

### 💎 Why This Board Stands Out

One design. Ten industries. Infinite possibilities — from **precision farming** to **smart cities**, **environmental research** to **industrial IoT**. This isn't just a PCB — it's a **scalable platform** ready to power the next generation of connected, autonomous sensing solutions.

---

## 🌾 Applications

- **Smart agriculture field monitoring** — logs temperature, humidity, pressure, and light intensity across crop fields or greenhouses
- **Solar/battery-powered remote sensor node** — runs unattended in the field, rechargeable via USB-C or solar panel
- **Soil/climate data logging station** — SD card backup for areas with weak or no Wi-Fi coverage
- **IoT weather station** — pushes live BME280 readings to a cloud dashboard or local server
- **Sunlight exposure tracking** — monitors sun exposure for crop growth optimization
- **Acoustic/pest monitoring** — mic input can detect insect activity, animal presence, or equipment sound
- **Expandable sensor hub** — I2C/GPIO headers for adding soil moisture, pH, or EC sensors
- **Battery-backed edge logger** — continues sensing during power outages or disconnection
- **OTA-capable firmware node** — onboard SPI flash supports remote firmware updates
- **General-purpose outdoor IoT dev board** — reusable prototyping platform beyond agriculture

---

## 🧩 Hardware Overview

### 🧠 Core Processing & Connectivity
| Component | Part | Purpose |
|---|---|---|
| U3 | ESP32-C3-WROOM-02-H4 | Main MCU — Wi-Fi/BLE, RISC-V core, chosen for wireless field data transmission without an external radio module |
| U4 | CP2102N | USB-to-UART bridge for programming/serial debug over USB-C |
| U2 | W25Q32JVSSIQ (32Mbit SPI Flash) | Extra non-volatile storage for OTA updates and log buffering |
| J3 | GSD090012SEU (microSD slot) | Local offline data logging when Wi-Fi is unavailable |

### 🌡️ Sensors
| Component | Part | Purpose |
|---|---|---|
| U6 | BME280 | Temperature, humidity & barometric pressure sensing |
| Q1 | TEMT6000X01 | Ambient light intensity sensing for crop exposure analysis |
| U7 | MAX4466EXK | Mic amplifier for acoustic sensing (pest/environmental sound) |

### 🔋 Power Management
| Component | Part | Purpose |
|---|---|---|
| J1 | USB-C (2338792-1) | Primary power/data input |
| J2 | JST connector (B2B-PH-SM4-TB) | Li-ion/LiPo battery input |
| U1 | MCP73871 | Battery charge management + power path — charges while running on USB |
| VR1 | LM1117MPX-3.3 | Regulates supply to a clean 3.3V rail |
| U5 | USBLC6-2SC6 | ESD protection on USB data lines |
| F1 | 0ZCH0110AF2E | Resettable fuse — overcurrent protection |
| Q2, Q3 | BC817 | Power switching/load gating for sleep-mode power savings |
| MK1 | CMC-5042PF-AC | Inductor/choke for power line filtering |

### 🕹️ User Interface
| Component | Part | Purpose |
|---|---|---|
| S1 | BOOT button | Puts ESP32 into flashing/bootloader mode |
| S2 | RESET button | Manual MCU reset |
| D1, D5 | Blue LEDs | Status indicators |
| D2, D6 | Green LEDs | Status indicators |
| D3, D4 | Red LEDs | Fault/error indicators |

### 🔧 Debug & Expansion
| Component | Purpose |
|---|---|
| TP1–TP5 | SPI bus test points (MOSI, MISO, SCLK, CS, CS-SD) for debugging flash/SD card |
| J4 | 4-pin header — I2C expansion (GND/SCL/SDA/3.3V) for external sensors |
| J5 | 5-pin header — additional GPIO/power expansion |

### ⚙️ Passives
- **Capacitors (C1–C25):** Decoupling and bulk capacitance for clean power delivery, especially during Wi-Fi transmit bursts
- **Resistors (R1–R35):** Pull-ups (I2C/reset lines), LED current limiting, and voltage divider/feedback networks

---

## 🧱 PCB Stackup — Why 4 Layers?

This board uses a **4-layer stackup (Signal / GND / PWR / Signal)** instead of a simpler 2-layer design, chosen specifically for better signal integrity given the mix of RF, digital, analog, and power circuitry on one small board.

**Benefits realized:**
- ✅ Dedicated, uninterrupted ground plane — critical for ESP32-C3 RF performance and reducing noise coupling into analog sensors
- ✅ Shorter, controlled return paths for high-speed SPI signals (flash + SD card), reducing EMI and reflections
- ✅ Dedicated power plane for cleaner, lower-impedance power delivery — especially during Wi-Fi TX current spikes
- ✅ Better isolation between noisy switching regulator circuitry and sensitive analog front-end (mic amp, light sensor)
- ✅ Tighter, more professional routing without sacrificing signal quality

---

## 🛠️ Tools Used

- **KiCad** — schematic capture, PCB layout, and 3D visualization

---

## 📸 Board Preview

*(Add board render/photo here)*

---

## 📋 Bill of Materials

Full BOM with quantities and footprints is available in <a href="https://github.com/tashfeen-electronics/--SmartAgri-Node---The-All-in-One-Environmental-Intelligence-Board--ESP32-C3-/blob/main/ESP32%20Project/bom/ibom.html" class="button">BOM</a>

---

## 📄 License

<a href="https://github.com/tashfeen-electronics/--SmartAgri-Node---The-All-in-One-Environmental-Intelligence-Board--ESP32-C3-/blob/main/LICENSE" class="button">
  ***LICENSE***
</a>

---

## 🙌 Author

**Tashfeen Electronics**
Designed with ❤️ in KiCad
