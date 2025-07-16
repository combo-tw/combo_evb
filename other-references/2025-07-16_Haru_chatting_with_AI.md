# 與 AI 做基本規劃的討論
> - 時間: 2025/07/16 上午
> - 地點: 線上
> - 大綱: 與 AI (GPT-4.1) 討論 EVB 開發討論事項

這是一個具有挑戰性又充滿學習價值的專案。建立自己的 EVB（Evaluation Board，評估開發板）並建立相對應的 Open Source Linux Kernel DTS（Device Tree Source）檔案，將有助於 hardware/firmware 開發、生態系推廣以及為開源社群貢獻。

## 專案任務說明

我們是開源社群軟體工程師兼系統規劃師，目標如下：

- **建立自主設計的 EVB（Evaluation Board, 評估開發板）**
- **撰寫並開源對應的 Linux Kernel DTS（Device Tree Source）**
- **推廣開源硬體軟體生態**

---

## 初步專案規劃步驟

### 1. 硬體設計（EVB Board）
- **需求分析與規格訂定**
  - 處理器選型（如 ARM/RISC-V）
  - 記憶體與 I/O 設計
  - 其他週邊元件、電源管理
- **原理圖設計與 PCB 布局**
  - KiCAD、Altium 等電子設計工具
- **打樣與硬體 Bring-up**
  - 小批次生產、焊接與測試

### 2. Linux Kernel Device Tree 製作
- **SoC/MCU Vendor 基本 DTS 研究**
  - 查閱官方/社群現有 Device Tree 範例
- **製作 EVB 專屬 DTS 檔案**
  - 增加所需 device node（pinmux、clock、interrupt 等）
  - 撰寫文件說明
- **Kernel 編譯與 Boot 測試**
  - 驅動調校
  - Debug 與 log 紀錄

### 3. Open Source 生態串接
- **技術文件撰寫**
  - 原理圖、BOM、連接說明
  - Linux DTS 教學與程式碼釋出
- **GitHub/開源社群倉庫建立**
  - schematic、gerber、DTS 檔案、README
- **協作與進度管理**
  - Issue Tracker、貢獻指南

### 4. 社群推廣與生態貢獻
- 教學文章與系列分享
- Pull Request 貢獻至 Linux 上游
- 參加開源研討會 or 社群活動

---

## 適合團隊成員討論項目清單

### 1. 專案目標與範圍
- 專案最終目標（開源/商業/教育）
- 規格與需求範圍

### 2. SoC/MCU 選型與評估
- 可行平台選擇
- 開源支援度
- 成本與供應鏈

### 3. 硬體結構規劃
- 電源管理方案
- 記憶體配置
- I/O 與擴充介面（GPIO、UART、SPI、USB、Ethernet、Audio、Display…）
- pinmux 分配
- 週邊元件選型

### 4. 原理圖與 PCB 設計
- 繪圖工具選擇
- 分工與佈局原則
- 層數與封裝規範

### 5. Linux Kernel & Device Tree 支援
- 參考現有 DTS 範例
- 必須新增的 device node
- Upstream 驅動/第三方驅動支援
- DTS 編修與驗證
- Kernel 版本選擇

### 6. 協作流程與版本管理
- Git 倉庫架構
- 分支與版本策略
- 文件共同維護

### 7. 測試與除錯機制
- Bring-up 步驟
- 故障排除流程
- 單元測試/自動化建置
- CI/CD 相關規劃

### 8. 文件撰寫與開源推廣
- 專案說明文件、快速入門
- 貢獻給上游（Pull Request 提交流程）
- 社群推廣與教學策略

### 9. 量產與後續維運（如有考慮）
- 小批量打樣、生產 S.O.P.
- 組裝測試流程
- 社群持續維護計劃

---

Bear 說:
- 公司基本上不愛 open source... 所以沒有 open source 相關社團.
- SoC很複雜，很難從 SoC 做，從 SoC -> 板子 不容易
- 我會建議你們先買 OSM, 然後洗底板 - https://genio.mediatek.com/blog/accelerating-industrial-iot-innovation-with-osm-and-mediatek-genio-solutions
- 高速訊號不容易, 洗板子打樣非常貴，OSM 把高速訊號都做在上面, 底板就很簡單。會建議要開始先從這樣開始，之後真的想在玩，再去從 SoC 做。G520/G720 我覺得會好玩, AI 有 10Tops, 可以支持 LLM。
  - https://genio.mediatek.com/download/c158bd68-1fa1-4fb6-b8b7-16079b0429b3?allowTab=true
