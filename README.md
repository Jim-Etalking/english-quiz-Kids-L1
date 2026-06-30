# English Quiz Kids L1

這是一個給兒童使用的英文聽力與互動測驗小遊戲。孩子會依照英文語音指令，在畫面中點選物件或拖曽物件，完成房間與公園兩個場景的任務。

## 專案內容

- `index.html`：早期版本/備用頁面。
- `drag.html`：目前主要互動遊戲頁面。
- `assets/images/`：圖片素材。
- `assets/audio/`：題目語音與互動音效。

## 素材資料夾結構

```text
assets/
  images/
    backgrounds/   # 房間、公園等背景圖
    characters/    # 導引角色圖片
    objects/       # 玩具、動物、翹翹板等互動物件
  audio/
    questions/
      room/        # 房間關卡題目語音
      park/        # 公園關卡題目語音
    effects/       # 答對、答錯、動物叫聲等音效
```

## 如何預覽

這個專案目前是純 HTML/CSS/JavaScript，不需要安裝套件。

直接用瀏覽器打開：

```text
drag.html
```

建議優先測試：

- START 按鈕是否正常進入遊戲
- 第一關房間背景、物件、題目語音是否正常
- 答對與答錯音效是否正常
- 進入第二關公園後，背景與公園題目語音是否正常
- 貓、狗、鳥與翹翹板互動是否正常

## 新增素材規則

為了讓專案長期好維護，新增圖片或語音時建議遵守這些規則：

- 檔名使用小寫英文與連字號，例如 `blue-bear.png`。
- 不使用空白、中文或混合大小寫檔名。
- 題目語音依照關卡放進 `assets/audio/questions/room/` 或 `assets/audio/questions/park/`。
- 答對、答錯、動物叫聲等共用音效放進 `assets/audio/effects/`。
- 新增或移動素材後，要同步更新 `drag.html` 裡的路徑。

## 評分規則

目前 ROOM + PARK 兩關用來判斷孩子接近 Pre-Starter 或 Starter。評分會考慮題目難度、錯誤次數與反應秒數，並保留小小孩操作時的容錯。

詳細規則請看：

```text
SCORING.md
```

## 改版資訊

### 2026-06-30 評分規則

- 新增 `SCORING.md`，記錄目前 ROOM + PARK 的評分邏輯。
- 每題加入難度權重，區分簡單題、中等題與拖曳方位題。
- 報表改為依照加權分數推薦 Pre-Starter、Pre-Starter Plus 或 Starter。
- Starter 結果會建議進入第三關，用來進一步判斷 Starter / L1。

### 2026-06-30

- 新增 `assets/` 資料夾，整理圖片與語音素材。
- 將背景圖移至 `assets/images/backgrounds/`。
- 將角色圖移至 `assets/images/characters/`。
- 將互動物件圖移至 `assets/images/objects/`。
- 將房間關卡語音移至 `assets/audio/questions/room/`。
- 將公園關卡語音移至 `assets/audio/questions/park/`。
- 將答對、答錯、貓狗音效移至 `assets/audio/effects/`。
- 更新 `drag.html` 中所有圖片與音檔路徑。
- 保留原本遊戲邏輯與互動流程，只調整素材管理方式。

## 維護備註

目前 `drag.html` 同時包含畫面、樣式、題目資料與遊戲邏輯。若未來關卡變多，可以再考慮把題目資料拆成獨立檔案，例如：

```text
data/
  room-questions.js
  park-questions.js
```

現階段先保持純 HTML 專案即可，避免一次改動太大。
