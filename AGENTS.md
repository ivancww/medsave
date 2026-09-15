# AGENTS.md — Ivan Project Development Rules

本文件是此 Repository 的長期開發規則。
Codex 每次分析、修改、重構或新增功能時，都應遵守以下要求。
除非當次任務有明確相反指示，否則以下規則持續適用。

## 1. 核心原則

- 優先保持現有功能、計算邏輯、資料及使用流程。
- 不要因為修改一個功能而重寫或破壞其他無關部分。
- 優先作最小而有效的修改。
- 不要自行刪除現有功能。
- 不要隨意改變現有設計風格，除非任務明確要求。
- 修改前先理解相關 HTML、CSS、JavaScript 及相互依賴關係。
- 避免 hard-code 不必要的尺寸、位置或裝置解像度。

## 2. Responsive Design

所有介面必須同時適合：

- iPad / Tablet
- 一般手機
- HONOR Magic V5 摺機
- 摺機摺合狀態
- 摺機展開狀態

必須根據 viewport 自動調整版面。

不要只針對某一固定解像度設計。

優先使用：
- Responsive CSS
- Flexbox
- CSS Grid
- relative units
- max-width / min-width
- 適當 media queries / breakpoints

## 3. 手機版 UX

手機窄屏時：

- 如果橫向內容空間不足，應自動轉為上下排列。
- 不要單純將整個 UI 縮細塞入畫面。
- 文字必須保持容易閱讀。
- 按鈕必須保持容易點擊。
- 卡片、表格、圖表及輸入框不可超出 viewport。
- 不應出現不必要的 horizontal scrolling。
- 避免文字截斷、重疊或按鈕超出畫面。
- 保持合理 spacing 及 touch target。

## 4. iPad / Tablet UX

iPad 是主要使用及展示裝置之一。

- iPad 顯示不能因手機兼容而變得過細。
- 保持清晰字體大小。
- 保持適當留白。
- 卡片及按鈕應適合 touch 操作。
- 充分利用 iPad 螢幕空間，但不要令內容過度分散。

## 5. 字體與可讀性

- 不要使用過細或過小字體。
- 標題、正文、數字及輔助文字要有清晰層級。
- 手機版不能以大幅縮小文字作為 responsive 解決方法。
- 重要數字及結果必須容易閱讀。
- 保持現有整體視覺風格一致。

## 6. 修改安全

修改完成後必須確認：

- 原有功能仍然正常。
- 原有計算結果沒有意外改變。
- JavaScript 沒有 runtime error。
- 頁面不會出現白畫面。
- 沒有明顯 console error。
- 沒有因 CSS 修改造成其他頁面或元件錯位。
- 沒有 horizontal overflow。
- 不要修改與當次任務無關的程式碼。

## 7. Preview / Testing

每次完成 UI 或功能修改後：

1. 執行可用的測試或基本功能檢查。
2. 嘗試啟動 Preview。
3. 檢查修改後實際頁面。
4. 檢查 iPad / Tablet 顯示。
5. 檢查一般手機窄屏。
6. 檢查 foldable 不同 viewport 寬度。
7. 確認沒有白畫面、overflow、文字重疊或版面破裂。

如果 Preview 無法啟動：

- 應先找出原因。
- 嘗試使用項目現有方式啟動。
- 如果是純 HTML/CSS/JS 項目，可使用簡單 HTTP server 預覽。
- 不要為了建立 Preview 而大幅改動原有程式架構。
- 最後清楚說明 Preview 成功或失敗，以及原因。

## 8. 完成任務後回報

完成修改後，清楚列出：

- 修改了哪些檔案
- 每個檔案修改了什麼
- 是否完成測試
- Preview 是否成功
- Responsive 檢查結果
- 有沒有仍需注意的問題

如果任務要求 Commit / Pull Request，完成檢查後再執行。
