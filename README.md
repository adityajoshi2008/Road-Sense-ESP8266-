# 🚧 RoadSense

### 🌐 Smart Road Monitoring • ESP32 • IoT • Web Dashboard

<p align="center">
  <strong>Detect. Connect. Visualize.</strong><br>
  An ESP32-based system for monitoring road irregularities using motion sensing and a connected web dashboard.
</p>

<p align="center">

[![ESP32](https://img.shields.io/badge/ESP32-IoT-blue?style=for-the-badge\&logo=espressif)](https://www.espressif.com/)
[![KiCad](https://img.shields.io/badge/KiCad-PCB%20Design-red?style=for-the-badge\&logo=kicad)](https://www.kicad.org/)
[![C++](https://img.shields.io/badge/C%2FC%2B%2B-Firmware-blue?style=for-the-badge\&logo=cplusplus)](https://isocpp.org/)
[![MPU6050](https://img.shields.io/badge/MPU6050-Motion%20Sensor-orange?style=for-the-badge)](https://invensense.tdk.com/products/motion-tracking/6-axis/mpu-6050/)
[![Status](https://img.shields.io/badge/Status-Prototype-yellow?style=for-the-badge)](#-project-status)

</p>

<p align="center">
  <a href="https://roadsense-pwa-ka6v.bolt.host/">
    <img src="https://img.shields.io/badge/🚀%20OPEN%20ROADSense%20DASHBOARD-00C853?style=for-the-badge" alt="Open RoadSense Dashboard">
  </a>
</p>

---

## 🧭 Navigate

**[🚀 Dashboard](#-live-dashboard)** •
**[⚡ How It Works](#-how-it-works)** •
**[🔧 Hardware](#-hardware)** •
**[📐 PCB](#-pcb-design)** •
**[🌐 IoT](#-connected-road-monitoring)** •
**[🔮 Roadmap](#-future-roadmap)**

---

# 🚀 Live Dashboard

### 🌐 RoadSense Web App

> **Your road data, accessible from anywhere.**

<p align="center">

### 👉 [OPEN THE ROADSense DASHBOARD](https://roadsense-pwa-ka6v.bolt.host/)

</p>

The RoadSense system is designed to connect the embedded hardware with a web-based interface so that road-condition information can be viewed from a **phone, laptop, or desktop browser**.

📱 **Mobile friendly**
💻 **Web based**
📡 **IoT connected**

---

# 🧠 What is RoadSense?

RoadSense is an **ESP32-based smart road monitoring system** that uses an **MPU6050 accelerometer and gyroscope** to detect sudden changes in vehicle motion.

The basic idea is simple:

```text
🚗 Vehicle
   │
   ▼
📈 Motion changes
   │
   ▼
🧠 ESP32
   │
   ├──────────────► 🖥️ OLED
   │
   ▼
📡 Wi-Fi
   │
   ▼
🌐 RoadSense Web
   │
   ▼
📱 User
```

Instead of keeping sensor data trapped inside the vehicle, RoadSense is designed to bring the data into a connected environment.

---

# ⚡ How It Works

### 01 • SENSE 📡

The **MPU6050** continuously measures acceleration and rotational movement.

⬇️

### 02 • PROCESS 🧠

The **ESP32** receives the sensor readings through I²C and processes the motion data.

⬇️

### 03 • DETECT 🚧

Large or unusual changes in acceleration can indicate a road disturbance such as a bump or pothole.

⬇️

### 04 • CONNECT 🌐

The ESP32's built-in Wi-Fi provides the connection between the hardware and the online system.

⬇️

### 05 • VISUALIZE 📱

RoadSense data can be presented through the web dashboard.

---

# 🔧 Hardware

| Component           | Purpose                          |
| ------------------- | -------------------------------- |
| 🧠 **ESP32**        | Main controller + Wi-Fi          |
| 📈 **MPU6050**      | Acceleration + gyroscope sensing |
| 🖥️ **0.96" OLED**  | Local information display        |
| 🔌 **Custom PCB**   | Hardware integration             |
| 🔋 **Power Supply** | System power                     |

---

<details>
<summary><strong>🔌 Click to see the communication connections</strong></summary>

<br>

### I²C Bus

The MPU6050 and OLED can communicate with the ESP32 through the I²C interface.

| Signal | ESP32   |
| ------ | ------- |
| SDA    | GPIO 21 |
| SCL    | GPIO 22 |
| GND    | GND     |
| VCC    | 3.3V*   |

* Verify the voltage requirements of the exact modules before powering them.

### Typical I²C Addresses

```text
MPU6050  → 0x68
OLED     → 0x3C
```

</details>

---

# 📐 PCB Design

The RoadSense hardware was designed using **KiCad**.

The repository contains the project's hardware design files:

```text
📁 RoadSense
│
├── 📐 RoadSense esp32(2).kicad_sch
│       └── Schematic
│
├── 🟩 RoadSense esp32(2).kicad_pcb
│       └── PCB Layout
│
└── 📖 README.md
        └── Documentation
```

### 🛠️ Design Flow

```text
Circuit Idea
     ↓
Schematic
     ↓
ERC / Connection Check
     ↓
PCB Layout
     ↓
Routing
     ↓
3D / Manufacturing Review
     ↓
🚧 RoadSense Hardware
```

---

# 🌐 Connected Road Monitoring

This is where RoadSense becomes more than a sensor experiment.

### Traditional approach

```text
Sensor → Microcontroller → Local Display
```

### RoadSense approach

```text
Sensor
   ↓
ESP32
   ↓
Wi-Fi
   ↓
🌐 Web Platform
   ↓
📱 Phone / 💻 Computer
```

The goal is to eventually transform individual vehicle measurements into useful road-condition information.

---

# 📊 Project Architecture

```text
                    🚗 ROAD
                      │
                      ▼
             ┌─────────────────┐
             │     MPU6050     │
             │                 │
             │ Accelerometer   │
             │ + Gyroscope     │
             └────────┬────────┘
                      │
                     I²C
                      │
                      ▼
             ┌─────────────────┐
             │      ESP32      │
             │                 │
             │ Data Processing │
             │ Wi-Fi           │
             └───────┬─────────┘
                     │
             ┌───────┴────────┐
             │                │
             ▼                ▼
       ┌──────────┐      ┌──────────────┐
       │  OLED    │      │    Wi-Fi     │
       │ Display  │      │ Connectivity │
       └──────────┘      └───────┬──────┘
                                 │
                                 ▼
                         ┌───────────────┐
                         │   RoadSense   │
                         │  Web Dashboard│
                         └───────┬───────┘
                                 │
                                 ▼
                            📱 USER
```

---

# 🧪 Technology Stack

### 🔩 Hardware

`ESP32` `MPU6050` `OLED`

### 💻 Embedded

`C/C++` `I²C` `Wi-Fi`

### 📐 Hardware Design

`KiCad`

### 🌐 Web

`RoadSense Web Dashboard`

---

# 🎯 Why RoadSense?

Road infrastructure problems are often noticed only after they become a serious issue.

RoadSense explores a different approach:

> **What if vehicles themselves could become road-condition sensors?**

A large number of connected vehicles could potentially generate a much larger picture of road conditions.

---

# 🔮 Future Roadmap

RoadSense is only the beginning.

### 🟢 Current

* [x] ESP32-based hardware
* [x] MPU6050 motion sensing
* [x] OLED integration
* [x] KiCad schematic
* [x] KiCad PCB design
* [x] Web dashboard

### 🟡 Next

* [ ] 📍 GPS location tracking
* [ ] 🗺️ Interactive pothole map
* [ ] 📊 Historical sensor graphs
* [ ] ☁️ Cloud database
* [ ] 🔔 Real-time notifications
* [ ] 📱 Improved mobile interface

### 🔴 Future

* [ ] 🤖 Machine-learning-based road classification
* [ ] 📷 Camera verification
* [ ] 🚗 Multi-vehicle data collection
* [ ] 🌍 Large-scale road-condition mapping
* [ ] 🧠 Intelligent road-quality scoring

---

# 📸 Project Showcase

Add your project images here to make the repository visually pop:

```markdown
## 📸 Project Showcase

<p align="center">
  <img src="images/schematic.png" width="80%">
</p>

<p align="center">
  <img src="images/pcb.png" width="80%">
</p>

<p align="center">
  <img src="images/3d-model.png" width="80%">
</p>

<p align="center">
  <img src="images/dashboard.png" width="80%">
</p>
```

💡 **Tip:** A screenshot of the live dashboard next to the physical PCB would make the project look much more complete.

---

# 📁 Repository Structure

```text
RoadSense/
│
├── 📐 Hardware/
│   ├── RoadSense esp32(2).kicad_sch
│   └── RoadSense esp32(2).kicad_pcb
│
├── 💻 Firmware/
│   └── ESP32 code
│
├── 🌐 Web/
│   └── RoadSense dashboard
│
├── 📸 Images/
│   ├── schematic.png
│   ├── pcb.png
│   ├── 3d-model.png
│   └── dashboard.png
│
└── 📖 README.md
```

---

# 🚦 Project Status

<p align="center">

### 🟡 PROTOTYPE / ACTIVE DEVELOPMENT

RoadSense is an evolving electronics + IoT project.

</p>

New hardware, software and data-processing features can be added as development continues.

---

# 🌐 Try It Yourself

<p align="center">

## 🚀 Ready to explore RoadSense?

### [🔗 OPEN THE LIVE DASHBOARD](https://roadsense-pwa-ka6v.bolt.host/)

</p>

---

# 👨‍💻 Author

## Aditya Joshi

🎓 **B.Tech ECE • Semiconductor Technology**
🏫 **The NorthCap University**

### Interests

`Embedded Systems` • `Semiconductors` • `VLSI` • `PCB Design` • `IoT` • `Electronics`

---

# ⭐ Support

If you find this project interesting:

⭐ **Star** the repository
🍴 **Fork** the project
🐛 **Report** issues
💡 **Suggest** improvements

---

<p align="center">

### 🚧 RoadSense

**Turning motion data into smarter roads.**

<br>

📡 **Sense** → 🧠 **Process** → 🌐 **Connect** → 📊 **Visualize**

<br>

[🚀 Launch RoadSense](https://roadsense-pwa-ka6v.bolt.host/)

</p>
