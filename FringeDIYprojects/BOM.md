# 🧱 The Pillar v1: Minimal Parts Build (No Enclosure)

This document outlines the first working build of *The Pillar*, a modular platform for field synthesis, anomaly detection, and AI-driven signal interpretation. This version skips the physical mount/enclosure and focuses purely on acquiring the essential components for sensors, emitters, and Orin Nano–based control.

---

## 🧠 Core Brain & Storage

| Component | Description |
|----------|-------------|
| **Jetson Orin Nano Developer Kit** | Small embedded AI board with 67 TOPS, GPIO/I2C/SPI interfaces, and CUDA support. Powers all AI inference, sensor polling, and emitter control. |
| **MicroSD card or SSD** | At least 128GB preferred. Used for local logging, model files, and boot OS. NVMe drives are fastest, but USB SSDs also work well. |
| **GPIO breakout or header expansion** | Optional adapter to access the Orin Nano’s GPIO pins cleanly. Look for ribbon-style or labeled pin headers if needed. |

---

## 🔌 Power Supply & Distribution

| Component | Description |
|----------|-------------|
| **Bench power supply (0–30V, 5A)** | Adjustable power source with digital display. Use for sensor/emitter power rails and high-voltage experiments. Alternatively, use an ATX power supply for fixed 12V/5V/3.3V rails. |
| **DC-DC buck converters** | Step-down voltage regulators to convert 12V to 5V or 3.3V for sensors or logic-level subsystems. Prefer ones with adjustable output and onboard display. |
| **Terminal blocks or bus bars** | Used to distribute power cleanly across all modules. Choose screw-in terminal strips or press-in bus bars depending on your wiring style. |
| **Toggle switches + indicator LEDs** | Control power to each module manually. Useful for debugging and safe startup sequencing. |
| **Inline fuses or resettable polyfuses** | Optional but recommended for protecting each power rail from overcurrent or shorts. Choose based on current draw (e.g., 1A, 2A). |

---

## 📈 Sensor Modules (Receivers)

| Component | Description |
|----------|-------------|
| **Hall effect sensor** | Detects magnetic field strength and polarity. Choose a digital sensor (like A3144) for edge detection or analog for field strength measurement. |
| **Photodiode (PIN type)** | For spike or radiation detection. Use a PIN photodiode like BPW34 with an op-amp amplifier if needed. Best for high-speed event detection. |
| **Piezoelectric disc** | Senses pressure changes, vibration, or mechanical stress. Can be used as a simple analog microphone or vibration detector. |
| **MEMS microphone** | Digital or analog microphone for detecting audio-frequency field emissions or acoustic anomalies. I2S-based MEMS mics are quiet and precise. |
| **Capacitive sensor (DIY)** | Made from two aluminum or copper plates. Detects nearby objects or electrostatic fields. Use with an op-amp buffer or capacitive touch controller. |

---

## ⚡ Emitter Modules (Signal Generators)

| Component | Description |
|----------|-------------|
| **Copper wire coil (hand-wound)** | Create a solenoid or air-core coil for generating pulsed magnetic fields. Use magnet wire (26–30 AWG) and wind 100–300 turns. |
| **MOSFET or H-bridge driver** | Interfaces between GPIO and high-current coil. IRF520 modules are easy, or use full H-bridge boards for polarity switching. |
| **Piezo transducer (buzzer-style)** | Used for acoustic emission—can generate ultrasonic or subsonic tones. Connect to PWM output via transistor or driver. |
| **Parallel plate capacitor setup** | Two metal plates held at fixed or adjustable distance. Apply 12–40V across plates for static EM field testing or shielding response. Optional HV driver for advanced testing. |

---

## 🔗 Signal Backbone & Debug Tools

| Component | Description |
|----------|-------------|
| **Breadboard or protoboard** | Used for central wiring and signal routing between modules and Orin Nano. Solderless boards are good for prototyping; later switch to PCB or screw terminals. |
| **Jumper wires or JST cables** | For connecting modules to breadboard or pin headers. Use both male/male and male/female types for flexibility. |
| **Logic level shifter** | Translates signals between 3.3V logic (Orin) and 5V devices (common in Arduino-compatible sensors). Use 4- or 8-channel bidirectional shifters. |
| **Analog multiplexer (optional)** | Expand the number of analog inputs. A chip like CD4051 or CD74HC4067 gives you many sensor lines using one ADC. |
| **External ADC module (SPI/I2C)** | Orin Nano has limited analog inputs. Use an ADC like MCP3008 (SPI) or ADS1115 (I2C) to read analog sensors accurately. |

---

## 📟 Optional Add-ons

| Component | Description |
|----------|-------------|
| **OLED or e-ink display** | I2C-based module to show field readings, logging status, or active modules. A 0.96" or 1.3" screen is ideal. |
| **Real-time clock (RTC module)** | Keeps accurate time when Orin is off. Helps timestamp sensor data. Look for DS3231 modules with onboard coin cell. |
| **Relay board (4 or 8 channel)** | Use for switching high-voltage emitters or disabling modules during idle. Triggered from GPIO, handles AC or DC. |
| **Cooling fan** | If placing Orin Nano in enclosed space, add a 5V or 12V fan. Ensure airflow near power components. |

---

## 🧪 First Assembly Steps

1. Mount Orin Nano on static-safe surface, connect storage and power.
2. Build power rail (12V from PSU → buck converters → 5V and 3.3V rails).
3. Connect one sensor (e.g., Hall sensor) to breadboard and GPIO.
4. Connect one emitter (e.g., hand-wound coil + MOSFET).
5. Write Python script on Orin to:
   - PWM drive the emitter
   - Log or print sensor values
6. Use terminal or OLED screen for basic feedback.

---

## 🚀 Next Steps After First Build

- Add more sensors (piezo, mic, capacitive plate)
- Add event logging with timestamps
- Begin capturing time series data for anomaly detection
- Deploy a trained PyTorch model for signal classification
- Expand to high-voltage modules and shielding experiments

