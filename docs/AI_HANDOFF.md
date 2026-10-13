# 2D 製作器 v2.14 接手說明

發佈基底 https://anshaer.github.io/2D/ 。檔案 maker.html、mobile.html、tablet.html、receiver.html、index.html、404.html。

maker.html 基於 v2.13.0，保留圖片、網格、姿態、圖片組、渲染與 ZIP/角色輸出。新加入 Vmc2DReceiver，製作頁與 playerHTML 匯出的角色頁共用同一 runtime。角色專案格式仍為 ansha-2d-face version3。

VMC 開關清除本機辨識模型，remote frame 直接寫入 signals 與 distanceScale，不再次加增益。clean() 保留 vmcReceive；playerHTML 保留開關，清空連接碼、條碼、QR、來源清單與OBS臨時網址，預設隱藏設定。

Vmc2DReceiver 基於多來源 PeerJS protocol2，最多8來源。每個子連線獨立握手、heartbeat、seq；父接收器合併 OSC。scope 支援 all/face/head/eyes/brows/mouth；3秒資料逾時，連線順序優先，新鮮備援可接手。

面部訊息分類：Head與ANSHA深度→head；Blink/Eye與眼球骨骼→eyes；Brow→brows；其他Blend值及Jaw骨骼→mouth。
這是依名字的分類規則，不是自動推測任意自訂表情語意。未知自訂Blend預設落入嘴型區；既有2D訊號只解析VMC_FACE_KEYS，不會自動產生新模型表情。
合併從中性OSC起步，按區取值，最後放Blend Apply。忽略身體骨骼，不導入MOBILE_BONES或3D重定向。

方向事件全域重編號，ack回原來源，維持服裝／表情疊加。來源編號是當前連線識別，不是傳輸計數。

2D phone新增傳送區域selector，ready及改區送scope；平板新增head/eyes/brows/mouth選項。老Universal-VMC傳送端仍可整面接入。

不代表 /Universal-VMC/ 儲存庫檔案已更新。本包的2D分區是細面部版本，不能把通用Warudo的body scope直接視作2D面部分區。

404 位於專案目錄；使用者網站子資料夾的自動404仍由網站發佈根目錄負責。不得擅自覆蓋既有根目錄404。

測試使用DOM、模擬Peer與既有專案harness；實體相機與平板需要後續實測。

Copyright © 2026-2030 anshaer.com. All rights reserved.
