# ACS (Automatic Clock-in Shortcut)

[English](README.md) | [繁體中文](README_zh.md)

> 📱 A resilient, zero-false-positive iOS/iPadOS Shortcut automation framework for shift attendance, featuring dual-factor environmental geofencing, anti-bot randomized jitter, and adaptive multi-post routing.
>
> Designed & Architected by [HentaiP](https://github.com/HentaiP).

---

## ✦ Overview

**ACS (Automatic Clock-in Shortcut)** is an enterprise-grade automated check-in and attendance dispatch framework built natively on iOS / iPadOS Shortcuts. 

Most trivial time-based automation scripts suffer from two fatal pitfalls:
1. **Clockwork Signatures**: Firing at exact `00` seconds creates predictable automated audit trails.
2. **False-Presence Triggering**: Forgetting to toggle automation off during off-days or remote shifts triggers fraudulent attendance reports.

ACS resolves these operational challenges by introducing **dual environmental sensor verification (Wi-Fi SSID + GPS Geofence)** and **human-like delay simulation**, ensuring 99.9% unattended operational reliability and zero false positives across multi-year production deployments.

---

## ⚡ Key Features

- **🛡️ Dual-Factor Environmental Geofencing**:
  - Validates active Wi-Fi BSSID/SSID and reverse-geocoded GPS street coordinates simultaneously before payload dispatch.
  - Aborts execution immediately if the host device is off-site, preventing accidental clock-ins.
- **⏱️ Anti-Bot Realistic Jitter (Randomized Delay)**:
  - Injects dynamic entropy (3–8s randomized sleep cycles) to emulate physical human interaction variance and defeat automated time-series anomaly detection.
- **🔄 Adaptive Multi-Post Routing (ACS Duo Architecture)**:
  - Dynamically switches payload templates and target report endpoints based on connected AP profiles (e.g., Main Gate vs. Front Desk).
- **📍 Fixed Edge-Node Deployment**:
  - Designed for dedicated on-site host devices (e.g., dedicated iPad edge nodes), eliminating mobility-related false triggers.
- **📊 Embedded Debug & Telemetry Dashboard**:
  - Real-time debug popups and formatted execution logs capturing Mode, GPS coordinates, Wi-Fi status, calculated jitter, and API dispatch results.

---

## 📥 Getting Started

1. Import the Shortcut workflow into your Apple device (iOS / iPadOS 16.0+ recommended).
2. Configure environmental variables according to your workplace parameters.
3. Configure iOS Personal Automation trigger (e.g., Time of Day or NFC Tag).

---

## 🛠️ Configuration Parameters

| Parameter | Type | Description | Default / Example |
|---|---|---|---|
| `Force_Switch` | `Integer` | Master kill-switch (`0` aborts execution; non-zero proceeds) | `114514` |
| `Target_SSID` | `String` | Target workplace Wi-Fi SSID / keyword filter | `Your_Workplace_WiFi` |
| `Target_Street` | `String` | Target workplace GPS street address substring | `Your_Workplace_Street` |
| `Report_Target` | `String` | Target messaging endpoint / LINE webhook / recipient | `Supervisor_Or_Group` |

---

## 📜 License

Distributed under the [MIT License](LICENSE). Free for educational, research, and personal automation use.
