# XS Skill — XScript 腳本開發知識庫

## 這是什麼？

這是一個 **純知識庫 Skill**，讓 AI 助手能夠正確撰寫 XQ 全球贏家交易平台的 XScript (XS) 腳本。

**不需要安裝任何東西。** 不需要 Python 環境、不需要 npm、不需要 venv。AI 只要讀取 markdown 文件就能使用。

---

## 如何使用

### 快速開始（任何 AI 模型）

1. 讀取 `XScriptGuideline.md` — 這是編碼規範，必須先讀
2. 按需查閱 `XSAI資料庫/` 目錄下的參考文件
3. 依照規範撰寫 XS 腳本

### 各平台入口

| 平台 | 入口文件 | 說明 |
|------|---------|------|
| **Claude Code** | `CLAUDE.md` | 自動載入的 skill 設定 |
| **Antigravity (Gemini)** | `.agent/workflows/xshelp.md` 或 `xsgpt.md` | 透過 `/xshelp` 或 `/xsgpt` 指令啟動 |

---

## 檔案結構

```
xs-skill/
├── README.md                    ← 你在這裡
├── CLAUDE.md                    ← Claude Code 入口
├── XScriptGuideline.md          ← 核心編碼規範（必讀）
├── XSAI資料庫/                   ← 函數手冊、欄位規格、範例
│   ├── [Guide] ...              ← 速查指南
│   ├── [Manual] ...             ← 完整參考手冊
│   ├── [Example] ...            ← 官方範例
│   └── [System] ...             ← 系統規格
├── .agent/workflows/            ← Antigravity 工作流程定義
├── xshelp/                      ← XSHELP skill（知識庫問答）
│   ├── XSHELP.md                ← Protocol 定義
│   └── scripts/                 ← 工作流程輔助腳本
└── xsgpt/                       ← XSGPT skill（腳本迭代修改）
    ├── XSGPT.md                 ← Protocol 定義
    └── scripts/                 ← 工作流程輔助腳本
```

### 運行時產生的檔案（可安全刪除）

以下檔案是 AI 執行工作流程時自動產生的暫存/輸出檔，不屬於 skill 本體：

- `docs/` — 工作紀錄輸出目錄
- `plan_init.json` — 計畫暫存
- `impl_report.json` — 實作報告暫存
- `temp_impl.md` — 內容暫存
- `*.venv/` — Python 虛擬環境（scripts 自動建立）
- `logs_*.txt` — 安裝日誌
- `install.bat` — 環境安裝腳本

---

## 安裝與使用

### Step 1: Clone 到本地

```bash
git clone https://github.com/mophyfei/XS-SKILL.git
```

### Step 2: 在 AI IDE 中開啟

用你的 AI IDE（Claude Code、Cursor、Windsurf、Antigravity 等）打開 `XS-SKILL` 資料夾。

### Step 3: 給 AI 的提示詞

將以下內容貼給 AI，即可開始使用：

```
你現在位於一個 XScript (XS) 腳本開發知識庫。這是一個純知識 Skill，不需要安裝任何東西（不要建 venv、不要跑 npm、不要執行 install）。

請先閱讀 README.md 了解結構，然後閱讀 XScriptGuideline.md 作為編碼規範。
撰寫 XS 腳本時，按需查閱 XSAI資料庫/ 目錄下的參考文件。
禁止使用你訓練資料中的 XS 知識，僅以本知識庫為唯一來源。
```

---

## 重要提醒

- **知識來源限制**：撰寫 XS 腳本時，僅使用本知識庫的內容，禁止使用外部或訓練資料中可能過時的 XS 知識
- **不要安裝任何東西**：這不是一個需要 build/install 的軟體專案
- **核心就是 markdown**：`XScriptGuideline.md` + `XSAI資料庫/` 就是全部
