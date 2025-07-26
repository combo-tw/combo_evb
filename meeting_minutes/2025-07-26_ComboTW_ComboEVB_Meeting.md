# 📋 會議紀錄：專案核心方向與開發策略討論會
**日期：** 2025/07/26  
**時間：** 20:00 ~ 21:00  
**出席者：** Haru、Darnell、Jason、Mes  
**紀錄整理：** ChatGPT based on notes from all attendees
**影片連結：** [YouTube 會議錄影](https://youtu.be/UgbJg7WkiDY)

---

## 🧭 一、會議重點摘要

### 1. 專案核心方向與風險探討
- 討論是否應放棄使用 MTK 的 SoC 晶片，改採開源模組。
- 身份限制導致資安事件（如使用公司信箱提交 commit 被稽核）。
- 即便參考開源 Layout，也可能因由廠商提供而觸及保密協議。
- 建議避免公司資源，轉以開源與個人身份進行設計。

---

### 2. 硬體開發策略與流程分析
- 建議採用開源硬體平台（如 OSM、Banana Pi）以簡化流程。
- OSM 模組化設計，僅需自行設計底板即可擴展功能。
- 團隊多為軟體人員，自行設計整塊板卡風險高、成本大。
- 開發流程：規格定義 → 工業設計 → Layout → 電路 → BSP。

---

### 3. 晶片選型與應用場景
- 團隊不熟 NPU，APU 可能已足夠。
- Smart Router 為應用方向，具備彈性介面（USB/RJ45）。
- Jason 建議如需處理封包應使用 ASIC，避免 CPU 處理延遲。
- 晶片建議參考：RK（4核 A55、2G DDR4、16G ROM）、MTK 510/520。

---

### 4. 合作與推廣機會探索
- 潛在合作對象：
  - MOXA（HR）
  - D-Link、Asus、小型 ODM 廠
- 合作建議：
  - 系統廠製板，團隊專注 OS/應用。
  - 車用交換器為潛在高利潤應用方向。
- 開源疑慮：
  - 安全性問題仍存疑。
  - 優勢在於社群能補漏洞、減少長期維護成本。

---

## ✅ 二、行動項目與後續安排

| 編號 | 行動項目 | 負責人 | 備註 |
|------|-----------|--------|------|
| 1 | 是否放棄 MTK SoC，改用開源模組 | 全體 | - |
| 2 | 評估硬體策略（自行設計或套用方案） | Haru | - |
| 3 | 研究 Smart Router/工業電腦應用 | 全體 | - |
| 4 | 探討開源設計圖修改應用（EgoBone/TI 等） | 全體 | - |
| 5 | 尋找企業贊助與合作目標 | Haru | - |
| 6 | 聯繫 MOXA HR、D-Link | Haru | - |
| 7 | 尋找其他潛在合作廠商 | 全體 | - |
| 8 | 準備 COSCUP Lighting Talk / 海報 | Haru | - |
| 9 | 評估 NPU 在開源場景中之可行性 | 全體 | - |
| 10 | 評估車用交換器產品方向 | 全體 | - |

---

## 🔗 三、參考資料：OSM 模組

- [Digikey - OSM標準說明](https://www.digikey.tw/zh/articles/the-osm-standard-for-system-on-modules-explained)
- [Advantech - OSM產品頁](https://www.advantech.com/zh-tw/products/open-standard-module-(osm))
- [ADLINK - OSM模組](https://www.adlinktech.com/tw/computer_on_modules_osm)
- [Geniatech - OSM商城頁](https://shop.geniatech.com/product/osm-module/)

---

## 📌 潛在應用場景與合作對象
- Smart Router（流量調控、降低遊戲延遲）
- 車用交換器（高傳輸需求）
- 合作對象建議：
  - MOXA（HR 接洽）
  - D-Link（Email）
  - Asus、小型 ODM 廠
  - COSCUP 活動中尋找廠商或開源贊助者

