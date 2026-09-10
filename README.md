# Watchly

AI/IoT smart wearable band for child safety, combining ESP32 firmware, real-time GPS geofencing, and Vision Transformer-based behavior surveillance.

## Features
- Real-time GPS tracking with geofencing around safe zones using the Haversine formula
- OLED status display (U8g2 library) and a non-blocking buzzer alert state machine
- Vision Transformer (ViT)-based surveillance layer for behavior/activity monitoring, feeding risk signals into the alert pipeline
- Device telemetry streamed to Firebase Realtime Database every 2 seconds
- Companion Java-based Android app (parent-only flow) with dynamic child profile display and automated WhatsApp alerts formatted for Pakistan numbers

## Tech Stack
ESP32 (C/C++ firmware), Vision Transformer (PyTorch), Java (Android), Firebase Realtime Database, GPS module, OLED / U8g2, BLE

## Setup & Run
1. Flash the ESP32 firmware from `/firmware` using Arduino IDE or PlatformIO.
2. Configure your Firebase project credentials in `firebase_config.h`.
3. Build and install the Android app from `/app` via Android Studio.
4. Pair the device, set a safe zone, and monitor live status from the app.

## Status
This repository was scaffolded from the project description in the author's resume. Source code is being migrated/added here — check back for updates, or reach out below.

## 📫 Contact
- **Email:** rawish0922@gmail.com
- **Phone:** +92-332-8747138
- **LinkedIn:** [linkedin.com/in/rawishsarfraz](https://linkedin.com/in/rawishsarfraz)
- **GitHub:** [github.com/Rawishs-2882](https://github.com/Rawishs-2882)

