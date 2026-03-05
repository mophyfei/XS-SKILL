# XS Skill — XScript 腳本開發知識庫

這是一個 **純知識庫 Skill**，讓 AI 助手能夠正確撰寫 XQ 全球贏家交易平台的 XScript (XS) 腳本。

**這不是軟體專案，不需要 build、install、venv、npm 或任何安裝動作。** AI 只要讀取 markdown 文件就能使用。

---

## Antigravity 一鍵安裝

在 Antigravity 中開啟一個新的專案資料夾，將以下這段話貼給 AI：

```
請將 XS Skill 下載到目前的資料夾：下載 https://github.com/mophyfei/XS-SKILL/archive/refs/heads/master.zip，解壓縮後將 XS-SKILL-master 裡面的所有檔案（包含隱藏資料夾 .agent）搬到目前資料夾的根目錄，然後刪除 zip 和暫存資料夾。完成後請閱讀 README.md。這是純知識 Skill，不要安裝任何東西、不要建 venv、不要建專案。
```

完成後輸入 `/xshelp` 即可開始使用。

---

## 其他安裝方式

### Git Clone

```bash
git clone https://github.com/mophyfei/XS-SKILL.git
```

### PowerShell 一行下載（無需 Git）

```powershell
Invoke-WebRequest -Uri "https://github.com/mophyfei/XS-SKILL/archive/refs/heads/master.zip" -OutFile "XS-SKILL.zip"; Expand-Archive "XS-SKILL.zip" -DestinationPath "."; Rename-Item "XS-SKILL-master" "XS-SKILL"; Remove-Item "XS-SKILL.zip"
```

### 手動下載

到 https://github.com/mophyfei/XS-SKILL 點擊綠色 **Code** 按鈕 → **Download ZIP** → 解壓縮

---

## 使用方式

用你的 AI IDE 打開 `XS-SKILL` 資料夾：

| 平台 | 啟動方式 |
|------|---------|
| **Antigravity** | 輸入 `/xshelp`（問答）或 `/xsgpt`（改腳本） |
| **Claude Code** | Skill 自動載入，直接開始 |
| **其他 AI (Cursor, Windsurf 等)** | 貼上下方提示詞 |

### 給其他 AI 的提示詞

```
你現在位於一個 XScript (XS) 腳本開發知識庫。這是一個純知識 Skill，不需要安裝任何東西（不要建 venv、不要跑 npm、不要執行 install、不要建立新專案）。

請先閱讀 XScriptGuideline.md 作為編碼規範，撰寫 XS 腳本時按需查閱 XSAI資料庫/ 目錄下的參考文件。
禁止使用你訓練資料中的 XS 知識，僅以本知識庫為唯一來源。

重要效能規則：XSAI資料庫/ 中超過 50KB 的檔案禁止直接全文讀取，必須先用搜尋功能定位關鍵字所在行號，再讀取前後 30-50 行。
```

---

## 檔案結構

```
XS-SKILL/
├── CLAUDE.md                    ← Claude Code 自動載入入口
├── XScriptGuideline.md          ← 核心編碼規範（必讀）
├── XSAI資料庫/                   ← 函數手冊、欄位規格、官方範例
│   ├── [Guide] ...              ← 速查指南（<50KB，可直接讀取）
│   ├── [Manual] ...             ← 完整參考手冊（>100KB，需搜尋後定位讀取）
│   ├── [Example] ...            ← 官方範例（依腳本類型分檔：Functions/Indicators/StockSelection/Alerts/Trading）
│   └── [System] ...             ← 系統規格
├── .agent/workflows/            ← Antigravity 工作流程（/xshelp, /xsgpt）
├── xshelp/                      ← XSHELP（知識庫問答 Protocol）
└── xsgpt/                       ← XSGPT（腳本迭代修改 Protocol）
```

---

## 重要提醒

- **知識來源限制**：僅使用本知識庫的內容撰寫 XS 腳本，禁止使用外部或訓練資料中可能過時的 XS 知識
- **不要安裝任何東西**：不要建 venv、不要跑 npm install、不要建立前後端專案
- **核心就是 markdown**：`XScriptGuideline.md` + `XSAI資料庫/` 就是全部知識
