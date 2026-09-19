# 我的生活管理網站

這是一個純靜態的單頁生活管理網站，可以直接部署到 GitHub Pages、Netlify 或 Vercel。

## 檔案

- `index.html`：網站主檔，包含畫面、樣式與互動功能。

## 目前資料儲存方式

網站使用瀏覽器 `localStorage` 儲存專案、任務與約會資料。部署到雲端後，每台裝置與每個瀏覽器仍會各自保存資料；若要跨裝置同步，下一步需要加入登入與雲端資料庫。

## GitHub Pages 部署

1. 建立 GitHub repository。
2. 將此資料夾內容推到 repository。
3. 到 repository 的 Settings -> Pages。
4. Source 選擇 `Deploy from a branch`。
5. Branch 選擇 `main`，資料夾選擇 `/root`。
