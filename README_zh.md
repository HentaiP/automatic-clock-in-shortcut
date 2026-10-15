# ACS (Automatic Clock-in Shortcut)

[English](README.md) | [繁體中文](README_zh.md)

> 📱 依 Wi-Fi 與街道位置判斷是否發送簽到訊息的 iOS / iPadOS 捷徑，含隨機延遲與除錯輸出。
> 由 [HentaiP](https://github.com/HentaiP) 設計與架構。

---

## ✦ 專案簡介

**ACS (Automatic Clock-in Shortcut)** 是一套專為排班值勤人員設計的高穩定度 iOS / iPadOS 自動化簽到框架。

捷徑在發送訊息前比對目前的 Wi-Fi SSID 與反向地理編碼取得的街道。隨機延遲是流程的一部分，不代表真人操作證明，也不代表出勤系統已授權。

環境比對可減少誤觸，但定位精度、Wi-Fi、權限與 iOS 背景執行限制都會影響結果；本專案不宣稱零誤觸或未經量測的可靠度數字。

---

## ⚡ 核心機制

- **🛡️ 雙重環境安全鎖（Geofencing & Wi-Fi Check）**：整合當前 GPS 街道位置與 Wi-Fi SSID 進行比對，條件不符時不發送；實際判斷仍受感測資料與字串比對影響。
- **⏱️ 隨機延遲**：流程包含 3～8 秒隨機等待；不保證規避偵測或通過任何系統的安全檢查。
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
| `Line_Target` | `String` | 接收簽到回報之 LINE 對象 / 聯絡人名稱 | `Your_Contact` |

---

## 使用範圍

請設定自己的位置與收件人，先以除錯輸出驗證再啟用自動化。捷徑透過 iCloud 另行發佈；本倉庫提供設定說明，並非可逐一審核全部動作的原始碼匯出。僅在獲准自動化的出勤或訊息流程中使用。

## 📜 授權協議

本專案採用 [MIT License](LICENSE) 授權釋出，具體權利與條件以授權原文為準。
