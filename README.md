# 🛡️ NexaSafe – Smart Women's Safety System

> **Smart Safety. Instant Protection.**

NexaSafe is a smart wearable women's safety system designed to provide quick emergency assistance through a combination of **embedded hardware, GPS tracking, GSM communication, cloud connectivity, and a mobile application**.

The system is designed to detect an emergency through a dedicated SOS button, activate local alerts, obtain the user's location, send an emergency SMS, and synchronize safety information with a mobile application.

---

## 🚨 Problem Statement

Personal safety remains a major concern, especially during emergency situations where accessing a smartphone may not be practical.

Traditional safety applications often require the user to unlock a phone, open an application, and manually trigger an alert.

NexaSafe addresses this challenge by providing a **dedicated physical SOS mechanism** integrated into a compact wearable device.

---

## 💡 Proposed Solution

NexaSafe combines an ESP32-based hardware device with GPS, GSM, and a Flutter mobile application.

When the user presses the dedicated SOS button:

1. The ESP32 detects the emergency.
2. The LED is activated.
3. The buzzer provides a local audible alert.
4. The GPS module obtains the user's location.
5. The GSM module sends an emergency SMS containing the location.
6. Safety information can be synchronized with Firebase.
7. The Flutter application displays the device status and location.
8. Emergency events can be recorded in the application's history.

---

## ✨ Key Features

- 🆘 Dedicated physical SOS button
- 📍 GPS-based location tracking
- 📱 Emergency SMS through GSM
- 🔊 Local buzzer alert
- 💡 Emergency LED indicator
- ☁️ Firebase Realtime Database integration
- 🗺️ Google Maps location visualization
- 📊 Emergency history
- 📲 Flutter mobile application
- 🔄 Real-time hardware-to-app synchronization
- 🔌 ESP32-based embedded system

---

## 🏗️ System Architecture

```text
                    ┌──────────────────────┐
                    │   NexaSafe Wearable  │
                    └──────────┬───────────┘
                               │
                         ┌─────▼─────┐
                         │   ESP32   │
                         └─────┬─────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
          ┌───▼───┐        ┌───▼───┐        ┌───▼────┐
          │  SOS  │        │  GPS  │        │  GSM   │
          │Button │        │NEO-6M │        │SIM800L │
          └───┬───┘        └───┬───┘        └───┬────┘
              │                │                │
              │                │          Emergency SMS
              │                │
         ┌────▼────┐           │
         │LED +     │           │
         │Buzzer    │           │
         └──────────┘           │
                                │
                                ▼
                       ┌────────────────┐
                       │    Firebase    │
                       │ Realtime DB    │
                       └───────┬────────┘
                               │
                               ▼
                     ┌──────────────────┐
                     │ Flutter Mobile   │
                     │      App         │
                     └────────┬─────────┘
                              │
                              ▼
                     ┌──────────────────┐
                     │  Google Maps     │
                     │ Location View    │
                     └──────────────────┘
🔧 Hardware Components
Component	Purpose
ESP32 DevKit V1-Main microcontroller
NEO-6M GPS-Obtains geographical location
SIM800L GSM-Sends emergency SMS
Push Button-Dedicated SOS trigger
LED	Visual-emergency indication
Buzzer-Audible emergency indication
MAX30102-Pulse monitoring
MPU9250-Motion and fall detection
INMP441-Audio monitoring
Battery-Portable power source
Breadboard & Jumper Wires	Prototype connections

💻 Software Stack
Embedded System
ESP32
Arduino IDE
C/C++
GPS communication
GSM AT commands
I2C communication
Mobile Application
Flutter
Dart
Firebase Realtime Database
Google Maps Platform
Development Tools
VS Code
Arduino IDE
Git
GitHub

📱 Mobile Application

The NexaSafe Flutter application provides a user interface for monitoring the connected safety device.

Main Screens
🏠 Home
🗺️ Live Map
🕒 Emergency History
👤 Profile

The application can display:

Device status
SOS status
GPS coordinates
Current location
Emergency events
Map-based location information

🆘 Emergency Workflow
User presses SOS
        │
        ▼
ESP32 detects button press
        │
        ├──────────────► LED ON
        │
        ├──────────────► Buzzer ON
        │
        ▼
GPS obtains location
        │
        ▼
SIM800L sends emergency SMS
        │
        ▼
Firebase synchronization
        │
        ▼
Flutter application
        │
        ▼
Emergency status + location displayed
