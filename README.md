# AeroFit 展覽版網站

https://aerofit.advancedmediwatch.com

AeroFit（GST 舒活氣）咽喉肌運動處方訓練系統的介紹頁。2026 年 12 月醫療展起使用，給看展有興趣的人（醫療、研究人員、通路夥伴）掃 DM 上的 QR code 進來，進一步了解產品並聯絡我們。

**定位：暫時性官網。** 正式官網改版完成、可以對外之前，這個網站是對外介紹 AeroFit 的入口。

---

## 和公司其他系統的關係

```
advancedmediwatch.com（公司網域，DNS 在 Squarespace 網域後台）
│
├─ www.advancedmediwatch.com   正式官網 + 後台   → repo: gst-platform（apps/web），Vercel
├─ AeroFit App                 iOS / Android     → repo: gst-platform（apps/mobile），Firebase
│
└─ aerofit.advancedmediwatch.com  本網站          → repo: aerofit-site（本 repo），GitHub Pages
```

- **完全獨立。** 本網站和 gst-platform 沒有共用程式碼、部署、資料庫或帳號。修改本網站不會影響正式官網、後台或 App，反之亦然。
- **為什麼獨立：** gst-platform 由另一組工程師維護；這個網站需要在短時間內上線，又不能干擾他們的工作，所以另外建立。
- **唯一的交集是網域：** DNS 裡多了一筆 `aerofit` 紀錄指向這裡。刪掉那筆紀錄，本網站就從網域上消失，其他系統不受影響。

## 內容原則

- **內容來源：** 2026-11 展會 DM（主視覺與主軸）＋經銷小冊（段落順序與內容）。
- **保守口徑：** 本產品屬非醫療器材的呼吸訓練輔助工具，網站只描述訓練方法、機制與研發背景。不提疾病名稱、不做療效或改善宣稱、不與醫療器材比較。修改文字時請維持這個原則，對外前請相關人員審閱。
- **品名：** 主打「AeroFit」，「GST 舒活氣」以小字並列（與產品登記名稱一致），完整名稱為「咽喉肌運動處方訓練系統」。
- **不放個人資訊：** 聯絡管道只用公司官方 LINE（@141xfbrj），不放個人電話或信箱。
- **不收集資料：** 沒有表單、沒有追蹤碼，也不讓搜尋引擎收錄（入口只靠 QR code 與直接分享）。

## 怎麼修改

1. 改 `index.html`（文字）或 `style.css`（樣式）。圖片放 `assets/`。
2. 推到 `main` 分支，約 1 分鐘後線上自動更新。
3. 不需要安裝或建置任何東西；直接用瀏覽器開 `index.html` 就能預覽（YouTube 影片在本機開檔時可能無法播放，屬正常現象）。

## 結束使用時

正式官網可以對外後，擇一處理：

- **下線：** 刪除 DNS 的 `aerofit` 紀錄，並在 repo 的 Settings → Pages 關閉發佈。
- **導向正式官網：** 把 `index.html` 換成轉址頁，已印出去的 QR code 仍然有效。

印出去的 DM 會長期流通，建議優先選「導向正式官網」。

---

## 技術細節

**檔案**

| 路徑 | 用途 |
|---|---|
| `index.html` | 全部內容（單頁） |
| `style.css` | 樣式；手機優先，深色主題，配色取自展會 DM |
| `assets/` | 圖片（已壓縮為 WebP 並去除中繼資料）；`og.jpg` 是分享到社群時的預覽圖 |
| `CNAME` | GitHub Pages 綁定的網域，勿刪 |

**託管與網域**

- GitHub Pages：Settings → Pages，來源為 `main` 分支根目錄；已開啟 Enforce HTTPS，憑證由 GitHub 自動續約。
- DNS：`aerofit` CNAME → `advancedmediwatch.github.io`，在 Squarespace 網域後台（DNS → DNS Settings → Custom records）管理。網域原為 Google Domains，已移轉至 Squarespace。
- 本 repo 為公開（GitHub 免費方案的 Pages 只支援公開 repo），所以不要放任何內部資料。commit 請使用 GitHub noreply 信箱，避免個人信箱公開。

**外部依賴**

- 字型：Google Fonts（Noto Sans TC、Poppins）
- 影片：YouTube 內嵌（`GJtrVmGjoRE`，公司頻道 @AdvMediwatch），使用 youtube-nocookie 網域
- 頁尾 LINE QR 連到 `https://lin.ee/UzlP7HO`

**相關素材**

- 網站 QR code（PNG／SVG）與 DM 原檔：公司 Google Drive「行銷和宣傳素材製作 / 2026_Dec_醫療展」。
