🌱 Smart Garden & Utility Monitoring System
This project is a comprehensive IoT-based automation and monitoring system that integrates garden irrigation, water tank management, and energy metering. All modules are powered by ESP32 microcontrollers and communicate via Firebase Realtime Database (RTDB). A custom Android application provides full control and monitoring in real-time.

🔧 Modules Overview
1. 🌿 Garden Automation Module
Hardware:

ESP32

MP1584 Buck Converter

2-Channel Relay Module

2x Capacitive Soil Moisture Sensors

1x DS18B20 Temperature Sensor

1x Rain Sensor

Features:

Monitors 2 individual plants using separate soil sensors.

Each plant can be assigned a name (e.g., Rose, Mango) via the app.

User-defined soil moisture thresholds stored in Firebase.

Automatic irrigation:

If soil moisture < set level, the pump turns ON for 10 seconds.

Prevents overwatering by cycling checks.

Rain detection halts all irrigation automatically.

Resumes irrigation once rain stops.

Settings persist via Firebase, even after power loss.

Manual control of the irrigation pump via app.

2. 💧 Tank Monitoring & Pump Control Module
Hardware:

ESP32

MP1584 Buck Converter

ACS712 (20A) Current Sensor

4x Water Level Sensors (Reed Switch Type)

Water Pump

Features:

Monitors tank water level at 25%, 50%, 75%, and 100%.

User sets desired water level threshold via app.

Automatically triggers pump when level falls below threshold.

Real-time current monitoring via ACS712.

App calculates energy consumption during pump operation.

Firebase stores settings and real-time data.

System resumes automatically after power interruptions.

3. ⚡ Energy Meter & Power Distribution Module
Hardware:

ESP32

12V 5A SMPS

MP1584 Buck Converter

ACS712 (30A) Current Sensor

ZMPT101B Voltage Sensor

4-Channel Relay Module

Features:

Supplies and controls power to other modules.

Real-time monitoring of:

Voltage

Current

Power consumption (calculated in app)

Controls individual relays via app.

Relay status and sensor data are pushed to Firebase.

📱 Android App Features
Authentication:

Secure login/signup (email + password)

Password recovery option

Dashboard:

Welcome message with user’s name

Four main tiles:

Garden

Tank

Energy Meter

Info/About

Each tile shows online/offline status with color-coded dots (🟢 = Online, 🔴 = Offline)

Tank Control:

Water level visualization

Pump control & status

Real-time current and power usage

User-defined pump trigger level

Energy Meter:

Real-time voltage, current, power

Relay controls and status indicators

Garden Control:

Temperature and humidity readings

Per-plant monitoring (custom plant names)

Default & user-defined soil moisture thresholds

Rain detection status

Manual pump control

Connectivity:

Built-in WiFi Manager for SSID and password configuration

☁️ Cloud Integration
All modules are connected to Firebase Realtime Database, which:

Stores user-defined settings

Sends commands to ESP32s

Receives real-time sensor data

Ensures data persistence during power outages

🛠️ Tech Stack
Microcontrollers: ESP32

Power Management: MP1584, SMPS 12V 5A

Sensors: ACS712, ZMPT101B, DS18B20, Capacitive Soil Sensors, Rain Sensor, Reed Switch Water Level Sensors

Cloud: Firebase Realtime Database

App: Android (Java/Kotlin)

Communication: WiFi + Firebase RTDB

📦 Future Improvements (Optional Section)
(Add this only if you're planning more features)

Data logging and analytics

Monthly water/power usage reports

Notification system (SMS/Email)

Remote OTA firmware updates

👨‍💻 About the Developer
Developed with passion to bring automation and resource efficiency to smart homes and gardens.
For queries or collaboration, feel free to reach out via the app's Info section.
