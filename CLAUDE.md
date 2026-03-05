# XScript 腳本開發助手 (XS Skill)

這是一個 **XScript (XS) 語言知識庫 Skill**，用於 XQ 全球贏家交易平台的腳本開發。

## 知識來源

撰寫 XS 腳本時，必須先讀取以下文件作為唯一知識來源：

1. **`XScriptGuideline.md`** — 編碼規範與風格指南（必讀）
2. **`XSAI資料庫/`** — 函數手冊、欄位規格、語法參考、官方範例（按需查閱）

### XSAI 資料庫索引

| 檔案 | 用途 |
|------|------|
| `[Guide] XScript_Functions_QuickRef.md` | 常用函數速查（基本→進階→高階） |
| `[Guide] XScript_Dev_Practical_Notes.md` | 開發注意事項（print/settotalbar/group/rank/tick） |
| `[Manual] XScript_BuiltIn_Functions_Reference.md` | 內建函數完整參考 |
| `[Manual] XScript_System_Functions_Reference.md` | 系統函數（SetPosition/Plot 等） |
| `[Manual] XScript_Syntax_Reference.md` | 語法結構參考 |
| `[Manual] XScript_Reserved_Keywords.md` | 保留字清單 |
| `[Manual] DataField_General_Data.md` | GetField 可用欄位 |
| `[Manual] DataField_RealTime_Quotes.md` | 即時報價欄位 |
| `[Manual] DataField_Stock_Selection.md` | 選股資料欄位 |
| `[Example] XQ_Official_Script_Library.md` | 官方腳本範例 |
| `[System] XQ_Backtest_Debug_UI_Specs.md` | 回測 UI 規格 |

## 核心規則

- 僅使用本知識庫內容撰寫 XS 腳本，禁止使用外部或訓練資料中的 XS 知識
- 遵循 `XScriptGuideline.md` 的四大區塊架構：文首說明區 → 變數宣告區 → 邏輯判斷區 → 腳本輸出區
- 每種腳本類型有專屬輸出語法限制（指標用 plot、選股用 ret、交易用 setposition）
- 跨商品/跨頻率取值必須加上 `default` 防呆
- 完成後依照 `XScriptGuideline.md` 第十節「交付後使用指引」引導用戶匯入 XQ
