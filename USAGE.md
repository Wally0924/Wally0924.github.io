# 網站使用說明

這份文件說明這個個人網站如何瀏覽、發布與修改。
網站是**單一檔案的靜態網頁**（`index.html`），不依賴任何框架或套件。

## 📂 檔案結構

```
Wally0924.github.io/
├── index.html   ← 網站本體（HTML + CSS + JS 全部在這一個檔案）
├── README.md    ← 倉庫首頁顯示的個人簡介
└── USAGE.md     ← 本說明文件
```

## 🌐 三種瀏覽方式

### 1. 線上瀏覽（GitHub Pages）

檔案放在 `Wally0924.github.io` 這個倉庫的 `main` 分支後，GitHub 會自動發布到：

> **https://wally0924.github.io**

- 每次 commit 後約 1–2 分鐘自動更新
- 發布狀態可到倉庫的 **Settings → Pages** 查看
- 這個網址可以直接放在履歷、LinkedIn 或 GitHub 個人資料上

### 2. 本地離線開啟

下載 `index.html` 後直接用瀏覽器打開（雙擊檔案即可）。
大頭貼已用 base64 內嵌在檔案中，**完全離線也能正常顯示**。

### 3. 本地伺服器（非必要）

```bash
python3 -m http.server 8000
# 開啟 http://localhost:8000
```

## ✨ 網站功能

| 功能 | 說明 |
|---|---|
| 中英文切換 | 右上角 `EN / 中文` 按鈕，投外商可切英文版 |
| 打字機效果 | 首頁職稱輪播動畫（電腦視覺工程師 → 深度學習研究者 → …） |
| 區塊導覽 | 上方導覽列：01. 關於我 / 02. 技能 / 03. 專案 / 04. 聯絡 |
| 專案連結 | 每張專案卡片都連回對應的 GitHub 倉庫 |
| 響應式設計 | 手機、平板、桌面自動適應版面 |

## ✏️ 如何修改內容

所有內容都在 `index.html` 一個檔案裡。可以直接在 GitHub 網頁上編輯
（打開 `index.html` → 點右上角鉛筆圖示 → 修改後 Commit changes），
或下載修改後重新上傳。

| 想改什麼 | 在 index.html 搜尋 |
|---|---|
| 名字 | `<h1>Wally</h1>` |
| 職稱輪播文字 | `phrasesZh` 和 `phrasesEn`（在最下方 `<script>` 裡） |
| 自我介紹 | `id="about"` 區塊 |
| 技能標籤 | `id="skills"` 區塊裡的 `<span class="tag">` |
| 專案名稱與說明 | `id="projects"` 區塊 |
| Email | 搜尋 `wally092426@gmail.com` |
| 大頭貼 | 搜尋 `data:image/jpeg;base64`，替換成新圖片的 base64 編碼 |
| 主題色（青色） | 最上方 CSS 變數 `--accent: #4fd6c5` |
| 背景色 | CSS 變數 `--bg: #0a0e14` |

### 中英文雙語的寫法

網頁中帶有 `data-zh` 屬性的元素只在中文模式顯示，`data-en` 只在英文模式顯示：

```html
<p data-zh>這段只有中文模式會出現</p>
<p data-en>This only shows in English mode</p>
```

新增內容時，記得兩種語言各寫一份，切換功能才會正常。

## 🔧 常見問題

**網站沒有出現 / 顯示 404？**
1. 確認倉庫名稱是 `Wally0924.github.io`（一字不差）且為 Public
2. 確認 `index.html` 在 `main` 分支的根目錄（不是資料夾裡）
3. 到 **Settings → Pages** 確認 Source 是 `main` 分支
4. 第一次發布可能需要等幾分鐘

**改了內容但網站沒更新？**
GitHub Pages 有快取，等 1–2 分鐘後用 `Ctrl + F5`（強制重新整理）再看。

**想換大頭貼？**
最簡單的方式：把新照片轉成 base64（搜尋「image to base64」線上工具），
替換 `index.html` 中 `data:image/jpeg;base64,` 後面那一長串文字。
