# 🛠️ Physical Signal Browser

A **Physical-Signal Browser** is a new kind of tool — a *real-world browser* that lets humans explore ambient, structured signals in the environment: RF, EM fields, BLE, LoRa, ADS-B, and more. Like Mosaic for the web in the early 1990s, this browser reveals a dormant, richly structured medium that already exists, but remains invisible without specialized tools.

This project also ties into **The Pillar**, a modular, field-based device envisioned to read, map, and synthesize physical and informational layers from the world around us.

---

## 📈 What This Browser Does

* **Receives** ambient signals: electromagnetic, acoustic, thermal, and radio
* **Indexes** structured communication (A → B): sensors to base stations, beacons to receivers
* **Visualizes** signal layers (heatmaps, frequency spectrums, overlays)
* **Unifies** multiple protocols into one exploratory interface
* **Empowers** users to see infrastructure, not just content

---

## 🔌 Core Mediums Being Surfed

| Signal Type         | Examples                        | Protocols or Frequencies          |
| ------------------- | ------------------------------- | --------------------------------- |
| **Wi-Fi/Bluetooth** | BLE beacons, smart devices      | 2.4 GHz, 5 GHz                    |
| **LoRa / ISM RF**   | IoT sensors, LoRaWAN nodes      | 433 MHz, 868/915 MHz              |
| **ADS-B**           | Aircraft broadcast              | 1090 MHz                          |
| **AIS**             | Ship navigation                 | \~162 MHz                         |
| **EM Fields**       | Transformers, motors            | Low-frequency EMI                 |
| **Ultrasound**      | Chirps, motion, echolocation    | 20 kHz+                           |
| **Infrared**        | Remote signals, thermal cameras | IR light, thermal gradients       |
| **Magnetometers**   | Orientation, field mapping      | Earth's magnetic field, anomalies |
| **Acoustic**        | Urban sound, nature, machinery  | Full audible spectrum             |
| **Air Quality**     | VOCs, PM2.5, CO2                | Sensor output                     |

---

## 🛠️ Starter Hardware: Sensors & Modules

### 📅 Wideband SDR (General Signal Intake)

#### 1. RTL-SDR (\~\$30–\$50)

* USB dongle for passive listening
* Range: \~500 kHz to \~1.7 GHz
* Great for ADS-B, pagers, FM, weather satellites
* Software: SDR#, GQRX, CubicSDR

#### 2. HackRF One (\~\$300)

* Transmit + receive
* Range: \~1 MHz to 6 GHz
* Explore LoRa, ZigBee, GSM, BLE
* Active experimentation, spoofing

---

### 📝 Specialized Protocol Modules (Focused Input)

| Module Type       | Examples / Notes                             |
| ----------------- | -------------------------------------------- |
| **LoRa**          | Heltec, LilyGO, HopeRF modules (433/868 MHz) |
| **BLE**           | nRF52840 dongle, ESP32                       |
| **ZigBee**        | CC2531, Xbee, etc.                           |
| **RFID/NFC**      | PN532, MFRC522, etc.                         |
| **Infrared (IR)** | Flipper Zero, TSOP IR receivers              |
| **Thermal**       | FLIR Lepton, AMG8833 thermal cameras         |
| **Ultrasound**    | HC-SR04, MEMS mic arrays + FFT               |
| **Air Quality**   | PMS5003 (PM2.5), MQ sensors (VOCs), SCD30    |
| **EM Fields**     | Coils, Hall effect sensors, Gaussmeters      |
| **Magnetometers** | HMC5883L, QMC5883L                           |

---

### 🔐 Multi-tool Devices

#### 3. Flipper Zero (\~\$200)

* Sub-GHz RF (315/433/868/915 MHz)
* NFC, RFID, BLE sniffing, IR blasting
* Hacker interface; not full SDR but versatile

---

## 🔄 How It All Comes Together

1. **Signal Collection**: Physical modules (SDR, LoRa, BLE, etc.) capture ambient data
2. **Interpretation Layer**: Software decodes, parses, and labels structured protocols
3. **Indexing**: Store and organize signal metadata (time, source, type, payload)
4. **Visualization**: Real-time overlays, frequency maps, directional arrows, time graphs
5. **Interaction**: Click-to-explore packets, send test pings (if active), replay echoes

---

## 🤖 Why This Is a "Browser"

* It reveals a **layered, structured medium** already present
* It enables **exploration, understanding, and navigation**
* It has **A → B messages** like HTTP traffic: beacon → base station, aircraft → tower
* It unifies fragmented access into a **human-accessible interface**
* Like Mosaic in 1993, it **turns infrastructure into experience**

---

## 👩‍💻 Suggested Next Steps

* Start with **RTL-SDR** + BLE sniffer
* Build a basic Python or web dashboard for packet visualization
* Add LoRa and EM sensors as modules
* Design a UI with tabs or layers (like browser tabs)
* Expand to modular field device (e.g., **The Pillar**)

---

## 💡 Final Thought

> **This is not an app. It’s a window.**
> A browser into the invisible scaffolding of modern civilization.
> Not just to see *what is said*, but *what is constantly being said around you.*

---

### 🔗 Optional Project Name Ideas

* **Waveframe**
* **Signalglass**
* **EtherScope**
* **Ambient Mosaic**
* **The Pillar**
