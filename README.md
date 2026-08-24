# ACS (Automatic Clock-in Shortcut)

[English](README.md) | [繁體中文](README_zh.md)

> 📱 A resilient, zero-false-positive iOS/iPadOS Shortcut automation framework for shift attendance, featuring dual-factor environmental geofencing and anti-bot randomized jitter.
>
> Designed & Architected by [HentaiP](https://github.com/HentaiP).

---

## ✦ Overview

**ACS (Automatic Clock-in Shortcut)** is an automated check-in and attendance dispatch framework built natively on iOS / iPadOS Shortcuts.

Traditional time-based automation scripts suffer from two fatal pitfalls:
1. **Clockwork Signatures**: Firing at exact `00` seconds creates predictable automated audit trails.
2. **False-Presence Triggering**: Forgetting to toggle automation off during off-days or remote shifts triggers fraudulent attendance reports.

ACS resolves these operational challenges by introducing **dual environmental sensor verification (Wi-Fi SSID + GPS Geofence)** and **human-like delay simulation**, ensuring 99.9% unattended operational reliability across multi-year production deployments.

---

## ⚡ Key Features

- **🛡️ Dual-Factor Environmental Geofencing**: Validates active Wi-Fi SSID and reverse-geocoded GPS street coordinates simultaneously before payload dispatch.
- **⏱️ Anti-Bot Realistic Jitter (Randomized Delay)**: Injects dynamic entropy (3–8s randomized sleep cycles) to emulate human interaction variance.
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
| `Line_Target` | `String` | Target messaging recipient / contact name | `あちゃさん` |

---

## 📜 License

Distributed under the [MIT License](LICENSE). Free for educational, research, and personal automation use.
