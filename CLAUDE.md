# XScript 腳本開發助手 (XS Skill)

這是一個 **XScript (XS) 語言知識庫 Skill**，用於 XQ 全球贏家交易平台的腳本開發。

## 知識來源

撰寫 XS 腳本時，必須先讀取以下文件作為唯一知識來源：

1. **`XScriptGuideline.md`** — 編碼規範與風格指南（必讀，~10KB）
2. **`XSAI資料庫/`** — 函數手冊、欄位規格、語法參考、官方範例（按需查閱）

### XSAI 資料庫索引

| 檔案 | 大小 | 用途 |
|------|------|------|
| `[Guide] XScript_Functions_QuickRef.md` | 6KB | 常用函數速查（基本→進階→高階） |
| `[Guide] XScript_Dev_Practical_Notes.md` | 8KB | 開發注意事項（print/settotalbar/group/rank/tick） |
| `[Manual] XScript_BuiltIn_Functions_Reference.md` | 229KB | 內建函數完整參考 |
| `[Manual] XScript_System_Functions_Reference.md` | 192KB | 系統函數（setposition/plot 等） |
| `[Manual] XScript_Syntax_Reference.md` | 9KB | 語法結構參考 |
| `[Manual] XScript_Reserved_Keywords.md` | 37KB | 保留字清單 |
| `[Manual] DataField_General_Data.md` | 359KB | getfield 可用欄位 |
| `[Manual] DataField_RealTime_Quotes.md` | 119KB | 即時報價欄位 |
| `[Manual] DataField_Stock_Selection.md` | 457KB | 選股資料欄位 |
| `[Example] XQ_Scripts_Functions.md` | 164KB | 官方函數腳本範例（224個） |
| `[Example] XQ_Scripts_Indicators.md` | 282KB | 官方指標腳本範例（395個） |
| `[Example] XQ_Scripts_StockSelection.md` | 156KB | 官方選股腳本範例（324個） |
| `[Example] XQ_Scripts_Alerts.md` | 203KB | 官方警示腳本範例（359個） |
| `[Example] XQ_Scripts_Trading.md` | 59KB | 官方交易腳本範例（64個） |
| `[System] XQ_Backtest_Debug_UI_Specs.md` | 7KB | 回測 UI 規格 |

## 核心規則

- 僅使用本知識庫內容撰寫 XS 腳本，禁止使用外部或訓練資料中的 XS 知識
- 遵循 `XScriptGuideline.md` 的四大區塊架構：文首說明區 → 變數宣告區 → 邏輯判斷區 → 腳本輸出區
- 每種腳本類型有專屬輸出語法限制（指標用 plot、選股用 ret、交易僅用 setposition/buy/sell，嚴禁 plot 和 ret）
- 所有英文字母一律小寫（getfield 非 GetField、setposition 非 SetPosition）
- 跨商品/跨頻率取值必須加上 `default` 防呆
- 完成後依照 `XScriptGuideline.md` 第十節「交付後使用指引」引導用戶匯入 XQ

## 效能優化：搜尋優先協議

**禁止直接讀取大型檔案（>50KB）的全部內容。** 必須先用 Grep 搜尋關鍵字，定位相關段落後，再用 Read 工具讀取特定行範圍。

### 查閱流程

1. **小型檔案（<50KB）**：Guide、Syntax、System 類檔案可直接讀取
2. **大型檔案（>50KB）**：Manual、Example、DataField 類檔案必須：
   - 先用 Grep 搜尋函數名、欄位名或關鍵字
   - 根據搜尋結果的行號，用 Read 工具讀取前後 30-50 行
   - 禁止一次讀取整個檔案

### 範例查閱優先順序

撰寫腳本時，根據腳本類型選擇對應的範例檔：
- 函數腳本 → `[Example] XQ_Scripts_Functions.md`
- 指標腳本 → `[Example] XQ_Scripts_Indicators.md`
- 選股腳本 → `[Example] XQ_Scripts_StockSelection.md`
- 警示腳本 → `[Example] XQ_Scripts_Alerts.md`
- 交易腳本 → `[Example] XQ_Scripts_Trading.md`
