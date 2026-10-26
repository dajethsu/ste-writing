# STE Writing｜清楚寫作與文字潤飾

一個可安裝到 Codex 的通用寫作 skill，依 ASD-STE100 的具體規則與跨語言調整方法，讓 AI 生成的文字清楚、具體、自然。

適用於日常回覆、信件、文章、社群貼文、報告、學術文字、介面文案與技術文件。支援生成、改寫、潤飾、摘要和翻譯；可輸出純文字、Markdown 或其他格式。

## 使用效果

原文：

> 本次已完成快取配置的優化落地：將有效時間由 30 秒調為 60 秒；預期可降低資料庫負載，實際效果尚待量測。

改寫：

> 已將快取有效時間從 30 秒改為 60 秒。預期這項調整能降低資料庫負載，但尚未量測實際效果。

保留原意、數字與不確定性，將抽象措辭換成具體動作。不同文體保留各自的語氣，例如信件的禮貌、文章的節奏，以及學術文字的論證與限制。

## 安裝到 Codex

### 請 Codex 安裝

在另一台裝置開啟 Codex，貼上：

```text
請使用 $skill-installer，從以下 GitHub 目錄安裝 ste-writing：
https://github.com/dajethsu/ste-writing/tree/main/ste-writing
```

### 手動下載

1. [下載 ZIP](https://github.com/dajethsu/ste-writing/archive/refs/heads/main.zip) 並解壓縮。
2. 將解壓縮後的 `ste-writing` 資料夾整個複製到下方位置。請複製包含 `SKILL.md` 的內層資料夾，而非整個 repo 資料夾。

| 系統 | 安裝後的 skill 資料夾 |
|---|---|
| Windows | `%USERPROFILE%\.codex\skills\ste-writing\` |
| macOS / Linux | `~/.codex/skills/ste-writing/` |

如果自訂了 `CODEX_HOME`，請改放在該目錄下的 `skills/ste-writing/`。

安裝後，在下一輪對話使用 `$ste-writing`。更新時，先備份自己修改過的檔案，再以新版 skill 資料夾取代舊版。

## 如何使用

生成新稿：

```text
使用 $ste-writing，幫我寫一封請同事確認附件的信。
語氣禮貌、直接，請對方在週五前回覆需要修改的地方。
```

潤飾既有文字：

```text
使用 $ste-writing 潤飾以下文字，保留原意與原本語氣：
（貼上文字）
```

其他例子：

```text
使用 $ste-writing，把這份工作紀錄整理成交接說明。
使用 $ste-writing，將這篇文章改寫成自然易懂的社群貼文。
使用 $ste-writing，將以下內容翻譯成英文，保留數字與不確定性。
```

## 包含的內容

```text
ste-writing/
├── SKILL.md                       寫作流程、跨語言與文體調整
├── agents/
│   └── openai.yaml                Codex 顯示資訊
└── references/
    ├── asd-ste100-rules.md        官方九章重點規則摘要與編號
    └── genre-examples.md          六種情境的改寫範例
```

每次使用時會讀取具體規則摘要，再依讀者、語言和文體處理文字。需要改寫示範時，再讀取情境範例。

可直接查看 [skill 指令](ste-writing/SKILL.md)、[規則摘要](ste-writing/references/asd-ste100-rules.md) 和 [改寫範例](ste-writing/references/genre-examples.md)。

## ASD-STE100 來源與適用範圍

規則摘要依據 [ASD-STE100 Issue 9（2025-01-15）](https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf)，並附對應規則編號。完整資訊請見 [官方網站](https://www.asd-ste100.org/)。

本 repo 收錄自行整理的重點摘要、跨語言調整指令與自寫範例，未收錄官方 PDF、完整規範或完整受控詞典。它可協助寫作，但不代表輸出已通過 ASD-STE100 完整合規檢查。

中文與其他語言採用清楚表達的方法，依當地語法和自然用法調整；英文詞數與語法限制不直接換算成其他語言的硬性規則。

## 授權

本 repo 的原創指令、說明與範例採 [MIT License](LICENSE)。ASD-STE100 的官方標準、詞典與商標權利仍屬各自權利人；詳見 [來源註記](NOTICE.md)。本專案與 ASD 或 STEMG 無隸屬或背書關係。
