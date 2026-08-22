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

Instead of keeping sensor

