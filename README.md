# ACS (Automatic Clock-in Shortcut)

[English](README.md) | [繁體中文](README_zh.md)

> 📱 An iOS/iPadOS Shortcuts workflow for location-aware attendance messaging, with Wi-Fi and street-address checks, configurable delays, and debug output.
>
> Designed & Architected by [HentaiP](https://github.com/HentaiP).

---

## ✦ Overview

**ACS (Automatic Clock-in Shortcut)** is an automated check-in and attendance dispatch framework built natively on iOS / iPadOS Shortcuts.

The workflow checks the current Wi-Fi SSID and reverse-geocoded street before dispatching a message. A randomized delay is part of the workflow; it is not proof of human interaction or authorization by an attendance system.

These checks reduce accidental triggering, but location accuracy, Wi-Fi availability, permissions and iOS background execution can affect results. No quantified reliability or zero-false-positive guarantee is claimed.

---

## ⚡ Key Features

- **🛡️ Dual-Factor Environmental Geofencing**: Validates active Wi-Fi SSID and reverse-geocoded GPS street coordinates simultaneously before payload dispatch.
- **⏱️ Randomized Delay**: Includes 3–8s randomized sleep cycles; timing varies and is not a security or anti-detection guarantee.
- **📊 Embedded Debug & Telemetry Dashboard**: Real-time debug popups capturing Message, Mode, GPS, Wi-Fi, Delay jitter, and dispatch results.

---

## 📥 Getting Started

- **ACS Debug Edition**: [Get iCloud Shortcut](https://www.icloud.com/shortcuts/9d525a05dccf4326a101a49a29a25cdf)

> *Open via Safari on iOS / iPadOS 16.0+ to import directly into your Shortcuts library.*

---

## 🛠️ Configuration Parameters

| Parameter | Type | Description | Default / Example |
|---|---|---|---|
| `Target_SSID` | `String` | Target workplace Wi-Fi SSID / keyword filter | `Your_Workplace_WiFi` |
| `Target_Street` | `String` | Target workplace GPS street address substring | `Your_Workplace_Street` |
| `Line_Target` | `String` | Target messaging recipient / contact name | `Your_Contact` |

---

## Usage notes

Configure your own location and recipient, then test with debug output before enabling automation. The linked Shortcut is distributed separately through iCloud; this repository documents its configuration, not a source-verifiable export of every action. Only use it for attendance or messaging workflows you are authorized to automate.

## 📜 License

Distributed under the [MIT License](LICENSE). See the license text for permissions and conditions.
