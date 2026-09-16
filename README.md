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
