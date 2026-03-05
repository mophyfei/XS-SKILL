---
description: 啟動 Xshelp Skill
---

// turbo-all

# Xshelp 工作流程

此 Workflow 用於啟動 **Xshelp** Skill（XScript 知識庫助手）。

## 強制載入順序

**必須嚴格按照以下順序讀取，不可跳過任何步驟。**

### Step 1: 載入編碼規範（必讀）
讀取並內化 XS 語法的絕對規則與風格標準：
```
@XScriptGuideline.md
```
這是撰寫所有 XS 代碼的**唯一風格依據**。

### Step 2: 載入 Skill Protocol
閱讀 SOP 流程與執行規範：
```
@xshelp/XSHELP.md
```

### Step 3: 依照 Protocol 執行
按照 Protocol 中的 **執行流程 (SOP)** 依序執行任務。

> **注意：** Protocol 中的 Phase 2 (Load Guidelines) 已在 Step 1 完成，可直接跳到 Phase 3。

## 效能規則

- **禁止直接讀取 >50KB 的檔案全文**。必須先用 Grep 搜尋關鍵字定位行號，再用 Read 讀取前後 30-50 行。
- XSAI 資料庫路徑：`./XSAI資料庫/`
- 根據腳本類型選擇對應的範例檔：函數→Functions、指標→Indicators、選股→StockSelection、警示→Alerts、交易→Trading
