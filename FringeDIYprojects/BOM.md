# 🧱 The Pillar v1: Minimal Parts Build (No Enclosure)

This document outlines the **first working build** of *The Pillar*, a modular field synthesis and sensing platform. This version focuses on getting core functionality working—field emission, signal detection, logging, and basic AI inference—without worrying about the physical mount or enclosure.

---

## 🧠 Core Brain & Storage

| Component | Description | Link |
|----------|-------------|------|
| **Jetson Orin Nano Developer Kit** | Central AI/control unit with GPIO, USB, I2C, and CUDA-enabled GPU for real-time inference and data control | https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin-nano-dev-kit/ |
| **128GB SD Card or USB/NVMe SSD** | Storage for logs, sensor data, ML models, etc. | [Samsung 128GB MicroSD](https://www.amazon.com/dp/B09B1GXM16) or [Kingston USB SSD](https://www.amazon.com/dp/B0B91RGK9F) |
| **GPIO Expansion Header (Optional)** | Makes Jetson GPIO more accessible (Dupont style) | [Adafruit Jetson GPIO Header Kit](https://www.adafruit.com/product/4763) |

---

## 🔌 Power Supply & Distribution

| Component | Description | Link |
|----------|-------------|------|
| **Bench Power Supply (0–30V, 5A)** | Clean, adjustable DC power for all modules | [Kaiweets Bench Power Supply](https://www.amazon.com/dp/B0B1WZHR7P) |
| **DC Buck Converter Modules (12V → 5V / 3.3V)** | Step-down for sensor rails or logic | [DROK Adjustable Buck Converter](https://www.amazon.com/dp/B01MQGMOKI) |
| **Terminal Block / Screw Bus Bar** | Power distribution rail for all modules | [WAGO-Style Terminal Block](https://www.amazon.com/dp/B07Z5JRT1S) |
| **Toggle Switches + LED Indicators** | For enabling/disabling module power | [Mini Toggle Switch Kit](https://www.amazon.com/dp/B082S8ZWT4) |
| **Fuses / Polyfuses (Optional)** | Inline safety for power rails | [Inline Blade Fuse Kit](https://www.amazon.com/dp/B0BLKTH6R2) |

---

## 📈 Sensor Modules (Receivers)

| Component | Function | Link |
|----------|----------|------|
| **A3144 Hall Effect Sensor** | Detect magnetic field changes or resonance | [Hall Effect Sensor Kit](https://www.amazon.com/dp/B07F3XNB6F) |
| **BPW34 PIN Photodiode** | Detect spikes from high-energy particles (cosmic rays) | [BPW34 Photodiode](https://www.digikey.com/en/products/detail/osram-opto-semiconductors-inc/BPW-34/1813486) |
| **Piezoelectric Disc (35mm)** | Detect vibration or pressure waves | [Piezo Disc Kit](https://www.amazon.com/dp/B083FJQ1L5) |
| **MEMS Microphone (I2C, like INMP441)** | Detect acoustic emissions, cavitation, resonance | [INMP441 I2S MEMS Microphone](https://www.adafruit.com/product/3421) |
| **Homemade Capacitive Sensor** | Plates + op-amp for detecting nearby fields or shielding effectiveness | No link (DIY from foil + LM358 op-amp) |

---

## ⚡ Emitter Modules (Signal Generators)

| Component | Function | Link |
|----------|----------|------|
| **Electromagnetic Coil (DIY)** | Generates a pulsed magnetic field | Use 26 AWG copper magnet wire, 100–200 turns |
| **IRF520 MOSFET Driver Module** | Drive coil from GPIO PWM | [IRF520 Module](https://www.amazon.com/dp/B082YYR6QD) |
| **Piezo Transducer** | Emits ultrasonic or subsonic tone | [Piezo Buzzer or Transducer](https://www.amazon.com/dp/B0BBX7GH4W) |
| **HV Plate Setup (Capacitive Emitter)** | Static field generation (12–40V test mode) | Use 2 aluminum plates, variable spacing, 12V input |

---

## 🔗 Backbone Interface (Control + Debug)

| Component | Function | Link |
|----------|----------|------|
| **Breadboard or ProtoBoard** | Connect signal wires, prototype circuits | [Solderless Breadboard Kit](https://www.amazon.com/dp/B07TYV8GZ4) |
| **Dupont Wires (Male/Female)** | Flexible wiring to GPIO or breakout boards | [Dupont Cable Kit](https://www.amazon.com/dp/B07GD2BWPY) |
| **Logic Level Shifter (3.3V ↔ 5V)** | Protect sensors when interfacing with different logic levels | [4-Channel Logic Level Converter](https://www.adafruit.com/product/757) |

---

## 📟 Optional Add-ons

| Component | Purpose | Link |
|----------|---------|------|
| **0.96" OLED Display (I2C)** | Field status readout, sensor debug | [I2C OLED Screen](https://www.amazon.com/dp/B01N9GR9S1) |
| **Real-Time Clock (DS3231)** | Timestamping sensor data | [DS3231 RTC Module](https://www.adafruit.com/product/3013) |
| **8-Channel Relay Module** | Power switching for future high-voltage modules | [8-Channel Relay Board](https://www.amazon.com/dp/B07GV1WXWF) |

---

## 🧪 First Assembly Checklist

- [ ] Connect Orin Nano to SSD or SD card
- [ ] Power Orin via USB-C or 12V barrel jack
- [ ] Set up terminal block and power rails (12V → 5V, 3.3V)
- [ ] Add Hall sensor and photodiode on analog lines
- [ ] Add coil + MOSFET driver for EM pulsing
- [ ] Write simple Python script on Orin for PWM + sensor polling

---

## 🧠 Next Steps

Once this build is running:
- Add your logging pipeline (store time series CSV or SQLite)
- Plot sensor data with Python or push to dashboard
- Train or test a small model to detect field events (e.g. spikes, oscillations, anomalies)
- Prepare modules for casing or modular plug-in system

