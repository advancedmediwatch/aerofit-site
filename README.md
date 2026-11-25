# AeroFit 展覽版網站

https://aerofit.advancedmediwatch.com

AeroFit 產品介紹頁，供展覽及 DM 上的 QR code 使用。

- 這是獨立的靜態網站，與公司其他網站、App 沒有共用程式碼或服務；修改這裡不會影響其他系統。
- 以 GitHub Pages 發佈，網域透過 DNS 的 `aerofit` CNAME 紀錄指向這裡。

## 修改

改 `index.html`（內容）或 `style.css`（樣式），圖片放 `assets/`。推到 `main` 後約 1 分鐘自動上線。不需建置，直接用瀏覽器開 `index.html` 即可預覽。

`CNAME` 檔是網域設定，請勿刪除。

## 停用

刪除 DNS 的 `aerofit` 紀錄並關閉 Pages；或把 `index.html` 改成轉址到正式官網，讓已印出的 QR code 繼續有效。
