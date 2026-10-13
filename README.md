# ANSHA 2D 角色製作與 VMC

2D 角色圖片與網格編輯、姿態記錄、角色 HTML 匯出，以及手機面捕／平板分區控制。

**正式網站：** [https://anshaer.github.io/2D/](https://anshaer.github.io/2D/)

製作器版本：**v2.14.0**。2D 發佈包版本：**v1.0**。

## 網頁與下載

| 項目 | 連結 |
| --- | --- |
| 首頁 | [開啟首頁](https://anshaer.github.io/2D/) |
| 製作器 | [maker.html](https://anshaer.github.io/2D/maker.html) |
| 手機面捕端 | [mobile.html](https://anshaer.github.io/2D/mobile.html) |
| 平板手動控制端 | [tablet.html](https://anshaer.github.io/2D/tablet.html) |
| VMC 接收診斷端 | [receiver.html](https://anshaer.github.io/2D/receiver.html) |
| 製作器單一 HTML 下載 | [maker.html](https://anshaer.github.io/2D/maker.html)；首頁提供下載按鈕 |
| 完整發佈包 | [ANSHA_2D_VMC_v1.0.zip](https://anshaer.github.io/2D/releases/ANSHA_2D_VMC_v1.0.zip) |
| 通用 VMC／Warudo 方案 | [Universal-VMC](https://anshaer.github.io/Universal-VMC/) |

角色頁由製作器依你的角色專案匯出，不提供固定的空白角色頁。接收診斷頁只顯示資料，不能取代匯出的角色 HTML。

## 製作器功能

- 圖片載入、圖層排序、複製、刪除及替換。
- 移動、旋轉、縮放、透明度與網格變形，網格長寬分別設定。
- 身體、頭部、左右眼、左右眉與嘴等圖層分組。
- 基準姿態與其他姿態記錄、圖片組及服裝／表情疊加。
- 角色專案 ZIP 載入／儲存。
- 匯出單一角色 HTML，或 HTML＋圖檔 ZIP。
- 匯出時可設定檔名、頁簽名稱與版權；版權留白時不顯示。
- 角色頁支援拖移、滾輪縮放、背景切換與隱藏設定。

本次保留既有編輯／渲染功能，整合新版 VMC 接收，沒有重新繪製或修改角色素材。

## 製作頁測試

1. 開啟 [製作器](https://anshaer.github.io/2D/maker.html)。
2. 載入原角色專案 ZIP，或加入圖片建立角色。
3. 勾選 **VMC 接收（手機／平板）**，等待產生 12 碼與一維碼。
4. 手機開 [面捕端](https://anshaer.github.io/2D/mobile.html)，選傳送區域、掃描或輸入碼，再開辨識。
5. 或用平板開 [控制端](https://anshaer.github.io/2D/tablet.html)，選控制區域、輸入相同碼並連線。
6. 製作頁的模擬數值跟隨收到的資料，角色使用既有姿態與圖層邏輯動作。

開啟 VMC 時，製作器會停止電腦本機相機／辨識模型，停用本機面捕與模擬控制；角色渲染、待機與髮尾效果仍由電腦執行。關閉 VMC 可回到模擬編輯。

## 多來源分區

最多 **8 台**同時使用同一接收碼，可選：

| 區域 | 內容 |
| --- | --- |
| 整個面部 | 以下所有面部區域 |
| 頭部／前後 | 左右轉頭、抬低頭、歪頭、2D 前後大小 |
| 眼睛／視線 | 左右閉眼與視線數值 |
| 眉毛 | 眉心、左右眉抬高／壓低 |
| 嘴型／微笑 | 張嘴、嘟嘴、左右嘴角微笑與其他嘴型表情數值 |

例如：手機選「頭部／前後」、平板 A 選「眼睛／視線」、平板 B 選「嘴型／微笑」。

同區先連線且資料新鮮的來源優先；3 秒未更新時可由備援接手。無資料的區域使用中性值；全部失去資料時清除收到的面部數值。這是控制分工，不是多相機三維融合。

2D 只套用面部與頭部資料。Warudo／3D 的手腳骨骼不會自動控制 2D 圖層。舊版通用手機端仍可配對，通常視作整個面部來源；要細分區域請使用本包的手機／平板頁。

## 匯出角色頁

1. 開啟 VMC 並測試完成後，使用製作器的角色匯出功能。
2. 設定檔名、頁簽名稱與版權，選單一 HTML 或 ZIP。
3. 匯出角色頁保留 VMC 開關與接收程式，**不保存製作頁的臨時配對碼、來源清單或 QR**。
4. 開角色頁後，點角色顯示設定與新碼，再讓手機／平板配對。
5. 若使用 OBS Browser Source，將角色 HTML 放到自己的 HTTPS 網址，再使用角色頁的「OBS 接收網址」。

設定預設隱藏。角色可拖移與縮放。服裝與表情圖片組維持疊加，方向事件切換服裝／表情。

**既有角色專案 ZIP 可載入；舊版已匯出的角色 HTML 不會自動更新。** 要使用新版分區接收，請用 v2.14.0 重新匯出。

## GitHub Pages 上傳

本包解壓後直接有 `index.html`、`404.html`、`maker.html`、`mobile.html`、`tablet.html`、`receiver.html`、`docs` 與 `releases`。

- 在 `anshaer.github.io` 儲存庫內，將全部內容放進 **`2D` 資料夾**。
- 保留 `docs`、`releases` 的名稱與階層。
- GitHub Pages 發佈來源需已設定；本包不替你變更帳號設定。
- 發佈網址：[https://anshaer.github.io/2D/](https://anshaer.github.io/2D/)。

GitHub 自動 404 必須在 Pages 發佈根目錄。若 `2D` 是使用者網站子資料夾，資料夾內的 `404.html` 可直接開啟，但自動錯誤頁仍由網站根目錄的 404 負責；根目錄已有其他用途的 404 時請保留並整合。

## 文件

- [製作與匯出流程](https://anshaer.github.io/2D/docs/WORKFLOW.md)
- [VMC 配對與分區](https://anshaer.github.io/2D/docs/VMC_SETUP.md)
- [AI 技術接手說明](https://anshaer.github.io/2D/docs/AI_HANDOFF.md)
- [測試與限制](https://anshaer.github.io/2D/docs/TESTING.md)

## 使用條件

手機相機需要 HTTPS 與權限，配對需要 PeerJS Cloud 網路。受限網路可能需要 TURN。電腦不需要 UDP 插件即可接收本方案的 WebRTC 資料；瀏覽器不直接接一般 UDP VMC。

## 版權

Copyright © 2026-2030 anshaer.com. All rights reserved.

第三方程式庫保留原授權聲明。本專案未附開源授權條款。
