<div align="center">

![header](https://capsule-render.vercel.app/api?type=waving&color=0:F8BBD0,50:CE93D8,100:B39DDB&height=180&section=header&text=Watchly&fontSize=36&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=AI%2FIoT%20Smart%20Band%20for%20Child%20Safety&descAlignY=58&descSize=15)

</div>

## Overview

Watchly is a wearable safety system built for parents who want real peace of mind. It pairs a custom ESP32 firmware with live GPS geofencing and a Vision Transformer based surveillance layer, so a child's location and surrounding activity can be tracked and understood at the same time, not just plotted on a map.

## Key Features

### Live GPS geofencing
The band streams its coordinates continuously and checks them against a parent defined safe zone using the Haversine formula, so distance calculations stay accurate on the curved surface of the Earth rather than a flat approximation.

### Vision Transformer surveillance layer
A ViT model analyzes activity and behavior around the child, converting what it sees into risk signals that feed directly into the alert pipeline instead of sitting in a separate, disconnected system.

### Non blocking buzzer alert state machine
Alerts are driven by a dedicated state machine on the firmware side, so the buzzer can escalate or reset without ever freezing the rest of the device's loop.

### OLED status display
Built with the U8g2 library, the on device screen shows connectivity, battery and safe zone status at a glance.

### Firebase Realtime Database sync
Telemetry is pushed to Firebase every 2 seconds, giving the companion app a near live view of location and device health.

### Companion Android app
A parent only Java application shows dynamic child profiles backed by Firebase, and automatically sends WhatsApp alerts formatted for Pakistan phone numbers the moment something needs attention.


## Tech Stack

<div align="center">
<img src="https://skillicons.dev/icons?i=cpp,java,firebase,androidstudio" />
</div>

ESP32 firmware in C and C++, Java for the Android companion app, Firebase Realtime Database for live sync, GPS and BLE modules, OLED display via U8g2, and a PyTorch based Vision Transformer for the surveillance layer.

## How It Works

The ESP32 handles sensing and local alert logic, streaming raw telemetry to Firebase. The ViT surveillance model runs alongside the location pipeline and publishes risk scores to the same backend, which the Android app subscribes to in real time. When a geofence is broken or a risk score crosses a threshold, the app triggers a WhatsApp notification to the parent.

## Setup and Run

1. Flash the ESP32 firmware from `/firmware` using Arduino IDE or PlatformIO.
2. Add your Firebase project credentials to `firebase_config.h`.
3. Define the safe zone center point and radius used by the geofencing logic.
4. Open `/app` in Android Studio, connect it to the same Firebase project, and build the parent app.
5. Pair the band over BLE, power it on, and monitor live status and alerts from the app.

## Roadmap

- Expand the ViT risk model with additional behavior classes
- Add multi child support in the companion app
- Battery usage optimization for the ESP32 firmware

## Status

> **Status:** This repository was scaffolded from the project description on the author's resume. Source code is being migrated and added here in stages. Reach out using the contact links below if you would like early access to the implementation.

## Let's Connect

<div align="center">

[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rawish0922@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rawishsarfraz)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Rawishs-2882)
[![Phone](https://img.shields.io/badge/Call-+92--332--8747138-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](tel:+923328747138)

</div>

<div align="center">

![footer](https://capsule-render.vercel.app/api?type=waving&color=0:B39DDB,50:CE93D8,100:F8BBD0&height=80&section=footer)

</div>
