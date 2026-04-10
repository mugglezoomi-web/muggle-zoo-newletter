# muggle-zoo-newletter
muggle-zoo-newletter

Muggle Zoo Newsletter — `muggle-zoo-newletter`
> **給下一個 AI 看的工作手冊。**  
> 這個 repo 是 Muggle Zoo 電子報系統。直接讀這份 README，就能接手繼續做。
---
Repo 基本資料
項目	內容
GitHub Repo	`mugglezoomi-web/muggle-zoo-newletter`
GitHub Pages URL	`https://mugglezoomi-web.github.io/muggle-zoo-newletter/`
擁有者	`mugglezoomi-web` 帳號（Muggle Zoo 的前台帳號）
相關帳號	`mis23ms`（投資工具後台，獨立運作，不在這裡）
---
現有檔案結構
```
muggle-zoo-newletter/
├── README.md                  ← 你正在讀的這份
├── index.html                 ← 電子報 archive 列表頁（首頁）
├── logo-chinese.png           ← 麻瓜婆婆動物園 中文 logo
├── logo-mugglezoo.png         ← Muggle Zoo 英文 logo（小）
└── (未來)
    ├── 001.html               ← 第一期電子報
    ├── 002.html               ← 第二期電子報
    └── ...
```
---
電子報 Template 規格
設計系統（Design Tokens）
這套系統和 Muggle Zoo 主站（`muggle.zoo`）完全一致，不能亂改：
```
背景色       #050d1a   (深夜藍，主背景)
卡片背景     #0d1a2e   (稍淺深藍，卡片)
金色主色     #f5c842   (按鈕、強調、標題)
金色暗版     #c9a235   (副標、期號)
金色光暈     rgba(245,200,66,.12)
奶油白       #f8f7f2   (白色卡片背景)
主文字       #e8dcc8   (深色背景上的文字)
暗文字       #a09480   (說明文字)
邊框色       #1a2a45
外部背景     #f0ede6   (email 信封外框)
```
字體

標題：`Georgia, 'Noto Serif TC', serif`（用於大標、三件事標題）

內文：`Arial, 'Noto Sans TC', sans-serif`（用於所有內文、按鈕）

數字/代號：`JetBrains Mono`（工具頁用，電子報不一定需要）

Layout（郵件安全格式）

全部用 `<table>` layout（不用 flexbox / grid，email client 不支援）

容器寬度：`640px`，`max-width: 640px`

圓角：`border-radius: 20px–24px`（容器）、`16px–18px`（卡片）

手機響應：`@media screen and (max-width:640px)` 控制縮放
---
每期電子報內容結構
每期 HTML 檔案（如 `001.html`）固定有以下區塊，順序不變：
```
1. 中文 Logo（logo-chinese.png）— 置頂置中，寬度 160px
2. 英文 Logo（logo-mugglezoo.png）— 小版，80px，輔助識別
3. 期號 + 日期（格式：Issue 001 · 2026-04-10）
4. 主標題（固定：給想懂的你：本週三件事）
5. 副標語（固定，麻瓜婆婆定位文字）
6. 本期摘要卡（奶油白卡片，2–3 句摘要 + 看網頁版按鈕）
7. 本週三件事（3 個深色卡片，左側 border 三色：金 / 暗金 / 灰藍）
8. Tool Spotlight（奶油白卡片，本週推薦工具 + 連結按鈕）
9. 一句結論（金色 border 深色卡片，居中）
10. Footer（YouTube / Threads / 網站連結 + 取消訂閱）
```
---
填寫每期內容的 Checklist
每次新增一期，需要更換的欄位：
[ ] 檔名：`001.html` → `002.html`（依序）
[ ] `<title>` 裡的期號和日期
[ ] 期號 + 日期（`Issue 001 · 2026-04-10`）
[ ] 本期摘要（2–3 句，說明這期帶走什麼）
[ ] 重點 01 標題 + 內容（2–3 段）
[ ] 重點 02 標題 + 內容
[ ] 重點 03 標題 + 內容（或收尾句 + 提醒）
[ ] Tool Spotlight：工具名稱、一句說明、連結 URL
[ ] 一句結論（整期最重要的一句話）
[ ] 「看本週影片」按鈕的 YouTube 連結（如有新影片）
[ ] 「看網頁版」按鈕的 URL（`https://mugglezoomi-web.github.io/muggle-zoo-newletter/00X.html`）
---
重要連結
用途	URL
Muggle Zoo 主站	`https://mugglezoomi-web.github.io/muggle.zoo/`
電子報 Archive	`https://mugglezoomi-web.github.io/muggle-zoo-newletter/`
工具頁	`https://mugglezoomi-web.github.io/muggle-zoo-tools/dashboard.html`
YouTube	`https://youtube.com/@muggle-zoo`
Threads	`https://www.threads.com/@muggle.zoo`
Mi's Marketing	`https://mismkt.com/zh/home/`
---
目前尚未建立的（待做）
[ ] `index.html` — 電子報 archive 列表頁（已有 `index.html` 但內容待補）
[ ] `001.html` — 第一期正式內容
[ ] 訂閱機制（現在自己寄，之後才接電子報系統如 Mailchimp / ConvertKit）
---
工作流程（現階段）
```
1. 影片週六上線（YouTube）
2. 週日整理本週三件事，填入 template
3. 複製 template → 改成 00X.html，填入內容
4. 上傳到 GitHub repo（Upload file）
5. 手動寄給訂閱者（BCC 方式）
6. 未來訂閱人數足夠後，接電子報服務商
```
---
Template 來源
Template 由 Claude（Anthropic）設計，GPT 提供初版結構
最新 template 以本 repo 的 `index.html` 為準（或當期最新的 `00X.html`）
設計系統與 `muggle.zoo` 主站共用，改顏色需兩邊同步
---
Content IP under Mi's Marketing  
Muggle Zoo 麻瓜婆婆動物園
