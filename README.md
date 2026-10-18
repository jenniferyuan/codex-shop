# 禾家小館

Vue 3 + Vite + JavaScript 餐廳首頁，使用 Composition API 與單檔元件。

## 開發與建置

```sh
npm install
npm run dev
npm run build
npm run preview
```

透過終端顯示的 HTTP 網址開啟。`src/` 為原始碼；`dist/` 是建置產物，請勿直接編輯。
餐點與分類資料位於 `src/data/menu.js`，共用樣式位於 `src/styles.css`。
訂位僅為頁面內示範，不會送出或持久儲存。關閉後重新開啟會回到表單並保留本次頁面輸入。
照片與字型使用原有外部服務，需要網路連線。
保留 `.openai/hosting.json` 的網站識別與靜態輸出路徑。
