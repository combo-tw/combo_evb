# Combo EVB 第一次會議紀錄

**會議名稱**：開發板規格討論會議  
**日期**：2025/07/18（22:00 - 23:00）  
**出席人員**：Haru、Sean、Darnell、Ben、Mes  
**紀錄整理**：ChatGPT based on notes from all attendees  

---

## 🌱 會議開場 & 破冰
- Haru 進行專案簡介
- Github Repo 已建置：
  🔗 [combo_evb GitHub](https://github.com/combo-tw/combo_evb)

---

## 🔧 專案方向與目標

### ✅ 專案命名與協作平台
- 專案暫定名稱：**Combo EVB**
- 社群名稱：**Combo Taiwan**
- 使用 Github 管理專案內容（會議紀錄、Kernel Commit、參考資料）
- Git Merge Request 操作需成員熟悉  

### ✅ 開發板設計方向
- **目標**：實作一塊具備基本功能的 EVB 板  
- **原則**：不從零寫 driver、選擇支援 upstream 的平台  
- **建議**：優先考慮 MediaTek Genio 系列（G520/G720），支援 OSM 模組（降低高速訊號設計難度），但可能會太貴

---

## ⚙️ 硬體規格討論（Spec）

### 🔸 I/O 接口與需求

| 項目        | 建議規格                      | 備註                            |
|-------------|-------------------------------|---------------------------------|
| Ethernet    | 100M 至 1G                    | 視應用情境評估                   |
| Wi-Fi / BT  | 可有可無                      | SDIO 接口，考慮成本              |
| USB         | 至少 Type-A x2、Type-C x1     | Type-C 可考慮支援 PD/DP         |
| RAM         | 最少 1GB DDR4                 | 避免卡頓                        |
| 儲存        | eMMC 或 SD 卡                 | 傾向 eMMC                       |
| GPIO        | 預留 I2C、SPI、PinMux         | 開發/擴充用                     |
| Display     | HDMI 輸出                    | DP 次之；D-sub 不列入            |
| UART        | Tx/Rx，轉 USB 模組整合建議    | UART 適合 early boot debug     |
| GPU         | SoC 內建即可                 | 用於顯示基本畫面                |
| Audio       | 不納入基本需求               | 使用率低                        |
| 電源        | 12V 輸入，轉 5V/3.3V 等       | 配合 SoC 需求                   |

---

### 🧠 SoC 與元件候選

| 類別       | 候選項目                                      |
|------------|-----------------------------------------------|
| SoC        | MediaTek G520/G720、Realtek RTD1395、Rockchip、Amlogic、Rockchip 等 |
| Ethernet   | Realtek                                       |
| Wi-Fi/BT   | Realtek（SDIO）                               |
| USB/Power | Richtek                                       |
| eMMC      | 品牌與封裝待決定                                  |
| 記憶體     | DDR4，品牌與封裝待決定                        |

---

## 🧩 應用場景與設計模式

- 主要應用：**IoT 裝置 / 嵌入式核心板**  
- 採 **模組化架構**：核心板 + 周邊 I/O 擴充板  
- 系統需求：可顯示畫面、有 GPIO、可開機、基本 I/O
- 使用 Buildroot 為主，便於自訂裁切、快速啟動
- 類比參考：Banana Pi、Raspberry Pi（但規格與定位不同）  

---

## 🔍 討論重點彙整

### 🎯 設計考量
- 避免設計高速差動訊號（如 DRAM trace）→ 使用 OSM 模組降低複雜度  
- USB、HDMI 為基礎配置，Type-C 可支援更多功能（PD、DP）  
- 以簡單穩定的設計為優先，非強調極致性能

### ❓ 開放問題
- 是否導入 Wi-Fi / BT 模組？
- 使用哪一款 SoC？ 偏好 ARM？  
- 如何安排 UART to USB debug 接口？  

---

## 📅 後續計畫與工作分配

### ✅ 下一步行動

| 工作項目                           | 負責人        | 期限     |
|------------------------------------|---------------|----------|
| 整理會議內容並同步至 HackMD/Github | Haru          | TBD      |
| SoC、RAM、儲存等規格進一步調查比較 | 全體成員      | TBD      |
| Layout 與設計初稿                  | Sean          | TBD      |
| 持續補充需求於 HackMD / Discord    | 全體成員      | 持續進行 |
| 軟體開發規劃與啟動                | 全體成員      | TBD      |

---

## 😊 團隊氣氛觀察

- 討論氛圍開放積極  
- 成員對專案方向有初步共識  
- 願意投入協作與後續優化  

---

## 📎 附錄連結與資源

- 🔗 Github Repo: [combo_evb](https://github.com/combo-tw/combo_evb)  
- 🔗 OSM 資源：  
  - https://www.geniatech.com/products/osm/  
  - https://www.advantech.com/zh-tw/products/open-standard-module-(osm)/  
- 🔗 MediaTek Genio OSM Blog：  
  - https://genio.mediatek.com/blog/accelerating-industrial-iot-innovation-with-osm-and-mediatek-genio-solutions  
- 🔗 BEN整理連結：  
  - [Haru 與 AI 討論記錄](https://github.com/combo-tw/combo_evb/blob/main/other-references/2025-07-16_Haru_chatting_with_AI.md)
