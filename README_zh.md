# ACS (Automatic Clock-in Shortcut)

[English](README.md) | [繁體中文](README_zh.md)

> 📱 具備雙重環境感知安全鎖、擬真隨機延遲與自適應路由機制的 iOS / iPadOS 自動化簽到捷徑。
> 由 [HentaiP](https://github.com/HentaiP) 設計與架構。

---

## ✦ 專案簡介

**ACS (Automatic Clock-in Shortcut)** 是一套專為排班值勤、多哨點人員設計的高穩定度 iOS / iPadOS 自動化簽到框架。

傳統定時打卡腳本常見兩大致命缺陷：
1. **死板整點特徵**：固定於 `00` 秒打卡，容易產生明顯的機器人日誌特徵。
2. **偽出勤自爆**：排休或調哨時忘記關閉自動化，導致在非目標地點誤觸簽到。

ACS 透過「Wi-Fi SSID + GPS 地理圍欄雙重驗證」與「動態隨機延遲演技模組」，在受限的 Apple Shortcuts 沙盒中實現了高穩定性、零誤觸、免維護的生產級自動化閉環。

---

## ⚡ 核心機制

- **🛡️ 雙重環境安全鎖（Geofencing & Wi-Fi Check）**：
  - 整合當前 GPS 街道位置與 Wi-Fi SSID 進行比對。
  - 當且僅當「處於目標案場 Wi-Fi」或「處於目標街道」時方可觸發簽到，人在家或外出時絕對拒絕執行。
- **⏱️ 擬真隨機延遲（Anti-Bot Jitter）**：
  - 動態生成 3～8 秒的隨機延遲迴圈，模擬真人掏出手機操作的非固定時間差，打破機器人 audit 軌跡。
- **🔄 自適應哨點分流（ACS Duo 架構）**：
  - 支援根據不同哨點連線的專屬 Wi-Fi SSID，動態切換簽到文本（例如：車道哨 / 櫃台哨）。
- **📍 實體邊緣節點部署（Edge Node）**：
  - 支援專用邊緣 iPad 常駐案場部署，自帶物理位置錨定，免除移動設備隨身攜帶之誤觸風險。
- **📊 完整 Debug Report 儀表板**：
  - 內建排錯彈窗與詳細日誌，清晰顯示 Message、Mode、GPS、Wi-Fi、Delay 秒數與執行結果。

---

## 📥 取得與安裝

1. 將 Shortcuts 捷徑匯入 iOS / iPadOS 裝置（建議 iOS 16.0+）。
2. 開啟捷徑並自訂開頭之案場參數。
3. 於「捷徑自動化」設定觸發條件（如：特定時間點或自動連線 Wi-Fi）。

---

## 🛠️ 變數設定指南

| 變數名稱 | 型態 | 說明 | 預設 / 範例值 |
|---|---|---|---|
| `Force_Switch` | `Integer` | 強制停止開關（`0` 為強制終止，非 `0` 為正常執行） | `114514` |
| `Target_SSID` | `String` | 目標案場 Wi-Fi 名稱（支援模糊比對） | `Your_Workplace_WiFi` |
| `Target_Street` | `String` | 目標案場街道名稱（GPS 街道字串） | `Your_Workplace_Street` |
| `Report_Target` | `String` | 接收簽到回報之 LINE 對象 / 群組名稱 | `Supervisor_Or_Group` |

---

## 📜 授權協議

本專案採用 [MIT License](LICENSE) 授權釋出，僅供個人自動化研究與學習交流使用。
