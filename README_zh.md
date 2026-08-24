# ACS (Automatic Clock-in Shortcut)

[English](README.md) | [繁體中文](README_zh.md)

> 📱 具備雙重環境感知安全鎖與擬真隨機延遲機制的 iOS / iPadOS 自動化簽到捷徑。
> 由 [HentaiP](https://github.com/HentaiP) 設計與架構。

---

## ✦ 專案簡介

**ACS (Automatic Clock-in Shortcut)** 是一套專為排班值勤人員設計的高穩定度 iOS / iPadOS 自動化簽到框架。

傳統定時打卡腳本常見兩大致命缺陷：
1. **死板整點特徵**：固定於 `00` 秒打卡，容易產生明顯的機器人日誌特徵。
2. **偽出勤自爆**：排休時忘記關閉自動化，導致在非目標地點誤觸簽到。

ACS 透過「Wi-Fi SSID + GPS 地理圍欄雙重驗證」與「動態隨機延遲演技模組」，在受限的 Apple Shortcuts 沙盒中實現了高穩定性、零誤觸、免維護的生產級自動化閉環。

---

## ⚡ 核心機制

- **🛡️ 雙重環境安全鎖（Geofencing & Wi-Fi Check）**：整合當前 GPS 街道位置與 Wi-Fi SSID 進行比對，非目標案場絕對拒絕執行。
- **⏱️ 擬真隨機延遲（Anti-Bot Jitter）**：動態生成 3～8 秒的隨機延遲迴圈，打破固定時間打卡的機器人軌跡。
- **📊 完整 Debug Report 儀表板**：內建排錯彈窗與詳細日誌，清晰顯示 Message、Mode、GPS、Wi-Fi、Delay 秒數與執行結果。

---

## 📥 取得與安裝

- **ACS Debug 開發版**：[點此取得 iCloud 捷徑連結](https://www.icloud.com/shortcuts/9d525a05dccf4326a101a49a29a25cdf)

> *需於 iOS / iPadOS 裝置（建議 iOS 16.0+）使用 Safari 開啟並加入捷徑庫。*

---

## 🛠️ 變數設定指南

| 變數名稱 | 型態 | 說明 | 預設 / 範例值 |
|---|---|---|---|
| `Target_SSID` | `String` | 目標案場 Wi-Fi 名稱（支援模糊比對） | `Your_Workplace_WiFi` |
| `Target_Street` | `String` | 目標案場街道名稱（GPS 街道字串） | `Your_Workplace_Street` |
| `Line_Target` | `String` | 接收簽到回報之 LINE 對象 / 聯絡人名稱 | `あちゃさん` |

---

## 📜 授權協議

本專案採用 [MIT License](LICENSE) 授權釋出，僅供個人自動化研究與學習交流使用。
