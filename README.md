# XS Skill — XScript 腳本開發知識庫

這是一個 **純知識庫 Skill**，讓 AI 助手能夠正確撰寫 XQ 全球贏家交易平台的 XScript (XS) 腳本。

**這不是軟體專案，不需要 build、install、venv、npm 或任何安裝動作。** AI 只要讀取 markdown 文件就能使用。

---

## 安裝方式

### 方式 A：有 Git 的電腦

```bash
git clone https://github.com/mophyfei/XS-SKILL.git
```

### 方式 B：沒有 Git 的電腦（PowerShell 一行下載）

```powershell
Invoke-WebRequest -Uri "https://github.com/mophyfei/XS-SKILL/archive/refs/heads/master.zip" -OutFile "XS-SKILL.zip"; Expand-Archive "XS-SKILL.zip" -DestinationPath "."; Rename-Item "XS-SKILL-master" "XS-SKILL"; Remove-Item "XS-SKILL.zip"
```

### 方式 C：手動下載

到 https://github.com/mophyfei/XS-SKILL 點擊綠色 **Code** 按鈕 → **Download ZIP** → 解壓縮

---

## 使用方式

下載完成後，用你的 AI IDE 打開 `XS-SKILL` 資料夾：

| 平台 | 啟動方式 |
|------|---------|
| **Antigravity** | 打開資料夾 → 輸入 `/xshelp`（問答）或 `/xsgpt`（改腳本）→ 直接開始 |
| **Claude Code** | 打開資料夾 → Skill 自動載入 → 直接開始 |
| **其他 AI (Cursor, Windsurf 等)** | 打開資料夾 → 貼上下方提示詞 → 直接開始 |

### 給其他 AI 的提示詞

```
你現在位於一個 XScript (XS) 腳本開發知識庫。這是一個純知識 Skill，不需要安裝任何東西（不要建 venv、不要跑 npm、不要執行 install、不要建立新專案）。

請先閱讀 XScriptGuideline.md 作為編碼規範，撰寫 XS 腳本時按需查閱 XSAI資料庫/ 目錄下的參考文件。
禁止使用你訓練資料中的 XS 知識，僅以本知識庫為唯一來源。
```

---

## 檔案結構

```
XS-SKILL/
├── CLAUDE.md                    ← Claude Code 自動載入入口
├── XScriptGuideline.md          ← 核心編碼規範（必讀）
├── XSAI資料庫/                   ← 函數手冊、欄位規格、官方範例
│   ├── [Guide] ...              ← 速查指南
│   ├── [Manual] ...             ← 完整參考手冊
│   ├── [Example] ...            ← 官方範例
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
