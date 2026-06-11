# Wally 個人作品集網站

一個單一檔案的靜態個人網站，深色科技風格，為求職用途設計。
不需要安裝任何套件、不需要網路伺服器、不需要對外連線。

## 如何開啟

直接用瀏覽器打開 `index.html` 即可（雙擊檔案，或拖進 Chrome / Edge / Firefox）。

如果想用本地伺服器的方式跑（非必要）：

```bash
cd portfolio
python3 -m http.server 8000
# 然後開啟 http://localhost:8000
```

## 功能

- **中英文切換**：右上角 `EN / 中文` 按鈕，方便給外商或本土公司看
- **打字機效果**：首頁職稱輪播動畫
- **精選專案**：四個代表性專案（WeatherSAM、車輛定位、GeoCLIP、推論服務）+ 四個其他專案，全部連回 GitHub
- **離線可用**：大頭貼已以 base64 內嵌，完全離線也能正常顯示
- **響應式設計**：手機、平板、桌面都能正常瀏覽

## 如何修改內容

所有內容都在 `index.html` 一個檔案裡：

| 想改什麼 | 搜尋關鍵字 |
|---|---|
| 名字 | `<h1>Wally</h1>` |
| 職稱輪播文字 | `phrasesZh` / `phrasesEn` |
| 自我介紹 | `id="about"` 區塊 |
| 技能標籤 | `id="skills"` 區塊的 `<span class="tag">` |
| 專案說明 | `id="projects"` 區塊 |
| Email | `wally092426@gmail.com` |
| 主題色 | 最上方 CSS 的 `--accent: #4fd6c5` |

中英文對照的寫法：`data-zh` 屬性的元素只在中文模式顯示，`data-en` 只在英文模式顯示。
