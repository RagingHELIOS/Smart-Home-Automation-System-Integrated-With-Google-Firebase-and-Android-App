# 🌱 Smart Garden & Utility Monitoring System

This project is a comprehensive IoT-based automation and monitoring system that integrates **garden irrigation**, **water tank management**, and **energy metering**. All modules are powered by **ESP32 microcontrollers** and communicate via **Firebase Realtime Database (RTDB)**. A custom Android application provides full control and monitoring in real-time.

---

## 🔧 Modules Overview

### 1. 🌿 Garden Automation Module

**Hardware:**
- ESP32
- MP1584 Buck Converter
- 2-Channel Relay Module
- 2x Capacitive Soil Moisture Sensors
- 1x DS18B20 Temperature Sensor
- 1x Rain Sensor

**Features:**
- Monitors 2 individual plants using separate soil sensors.
- Each plant can be assigned a name (e.g., *Rose*, *Mango*) via the app.
- User-defined soil moisture thresholds stored in Firebase.
- **Automatic Irrigation Logic:**
  - If soil moisture < set level → pump turns **ON** for 10 seconds.
  - Rechecks moisture to avoid overwatering.
- **Rain Detection:**  
  - If rain is detected, all pumps stop.
  - Operation resumes automatically once rain stops.
- Settings persist via Firebase even after power loss.
- Manual control of the irrigation pump from the app.

---

### 2. 💧 Tank Monitoring & Pump Control Module

**Hardware:**
- ESP32
- MP1584 Buck Converter
- ACS712 (20A) Current Sensor
- 4x Water Level Sensors (reed switch type)
- Water Pump

**Features:**
- Monitors tank levels at 25%, 50%, 75%, and 100%.
- User sets trigger threshold via app.
- Automatically turns pump **ON** when level drops below threshold.
- Real-time current monitoring with ACS712.
- App calculates power consumption during pump activity.
- All data and settings are synced with Firebase.
- Auto recovery after power failures using stored settings.

---

### 3. ⚡ Energy Meter & Power Distribution Module

**Hardware:**
- ESP32
- 12V 5A SMPS
- MP1584 Buck Converter
- ACS712 (30A) Current Sensor
- ZMPT101B Voltage Sensor
- 4-Channel Relay Module

**Features:**
- Powers and controls the other two modules.
- Monitors:
  - **Voltage**
  - **Current**
  - **Real-time Power Consumption**
- Controls relays via app.
- All relay statuses and sensor data are updated in Firebase.

---

## 📱 Android App Features

### 🔐 Authentication
- Login with email and password.
- Sign up with name, email, and password.
- Password reset feature.

### 🏠 Dashboard
- Welcome message with user’s name.
- Four main tiles:
  - **Garden**
  - **Tank**
  - **Energy Meter**
  - **Info/About**
- Online/offline status of each module (🟢 = Online, 🔴 = Offline).

### 💧 Tank Module
- Real-time water level display.
- Pump switch and current status.
- Current and total power consumption.
- User-configured trigger level (saved in Firebase).

### ⚡ Energy Meter Module
- Real-time voltage, current, and power monitoring.
- Relay control interface (🟥 = OFF, 🟩 = ON).
- Displays relay status and device uptime.

### 🌿 Garden Module
- Soil temperature reading.
- Per-plant moisture levels.
- Plant names and target humidity set via app.
- Manual pump control.
- Rain detection status.

---

## ☁️ Cloud Integration

All three modules communicate with **Firebase Realtime Database** to:
- Sync user settings
- Send commands to ESP32s
- Receive sensor data in real-time
- Restore configuration after power outages

---

## 🛠️ Tech Stack

- **Microcontrollers:** ESP32
- **Power:** MP1584 Buck Converter, 12V 5A SMPS
- **Sensors:**  
  - ACS712 (20A/30A)  
  - ZMPT101B Voltage Sensor  
  - DS18B20 Temperature Sensor  
  - Capacitive Soil Moisture Sensors  
  - Reed Switch Water Level Sensors  
  - Rain Sensor
- **Cloud Platform:** Firebase Realtime Database
- **App Platform:** Android (Java)
- **Communication Protocol:** Wi-Fi (via WiFiManager for user setup)

---

## 📦 Future Improvements *(Optional)*
- OTA firmware updates
- Monthly consumption reports
- SMS/email alerts
- Advanced data analytics and charting

---

## 👨‍💻 About the Developer

Built with passion to bring automation and efficiency to home gardening and utilities.  
For queries, feedback, or collaboration, please use the contact information available in the app's **Info/About** section.

---
