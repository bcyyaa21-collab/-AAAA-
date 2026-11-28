# 是人，是工具？更是工具人！──社工的勞動權益之路

一款以台灣基層社工職場處境為背景的 30 天互動文字模擬遊戲。玩家將扮演一名基層社工，在面對薪資回捐、評鑑造假、高風險訪視與無薪加班等體制考驗時，抉擇隱忍妥協或蒐集事證捍衛勞動權益。

## 專案結構

```text
├── index.html                  # 網頁主結構
├── README.md                   # 專案說明文件
└── assets/
    ├── css/
    │   └── style.css           # 全域與手機自適應（RWD）樣式表
    ├── js/
    │   └── main.js             # 遊戲狀態引擎、30 天劇本事件與結算系統
    └── images/
        ├── bg-office.webp      # 第 1–10 天背景（深夜辦公室）
        ├── bg-corridor.webp    # 第 11–20 天背景（高風險家訪走廊）
        ├── bg-dark.webp        # 第 21–30 天背景（喘息與諮商室）
        └── ending-fallback.webp # 結算卡片本地備援圖
```

## 本次優化與修復項目

1. **程式碼分離**：將原本單一 `index.html` 內的 CSS 與 JavaScript 拆分為 `assets/css/style.css` 與 `assets/js/main.js`，方便日後維護與修改。
2. **圖片壓縮與轉檔**：將原本總計 2.66 MB 的 JPG 圖片轉換為現代網頁格式 `.webp` 並統一歸檔於 `assets/images/`，總體積縮減至約 400 KB（減少約 85%），大幅提升網頁載入速度。
3. **Bug 修復**：
   - 修復 Google Fonts（Noto Sans TC）與 `html2canvas` 截圖套件的外部 CDN 連結，使「下載結算圖」功能恢復正常。
   - 修復結算卡片的 Unsplash 圖片網址拼寫錯誤，並加上本地圖片備援機制避免破圖。
   - 修復 CSS 多餘大括號與重複的 `@media (max-width: 768px)` 區塊，補上選項點擊時浮動數值提示（`.floating-indicator`）的動畫樣式。
   - 移除結算頁重複顯示的「真實台灣社工生存數據環境」區塊與 SVG 圖示錯誤網址。
