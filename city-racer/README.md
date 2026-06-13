# 🏎️ City Racer 城市賽車 🏎️

A top-down driving simulator in a single file — no installs needed.
俯視角的開車模擬遊戲，單一檔案、免安裝。

## How to play 怎麼玩

**Double-click `index.html`** and it opens in your browser. 用瀏覽器打開 `index.html` 就可以玩了！

Drive around the city! The car has **real momentum** — it keeps sliding,
so ease off and steer into corners. Pull the **handbrake** to break the
rear wheels loose and **drift** around tight turns. 車子有真實的慣性會滑動，
入彎要提早轉；按**手煞車**讓後輪打滑就能**甩尾**過彎！

### Two modes 兩種模式

- 🚗 **Free 探索** — roam the whole city, no timer. 自由開車兜風，不計時。
- 🏁 **Race 競速** — drive through the 8 checkpoints in order. Your lap is
  timed and your **best lap** is saved. 依序開過 8 個檢查點，計算單圈時間並記住**最佳成績**。

A glowing ring 🚩 marks your next checkpoint, with an arrow and minimap to
guide you. 發光的旗子是下一個檢查點，畫面有箭頭和小地圖帶路。

### Controls 操作

**Keyboard 鍵盤**

| Key 按鍵 | Action 動作 |
|---|---|
| W / ↑ | Gas 油門 |
| S / ↓ | Brake / reverse 煞車・倒車 |
| A / D or ← / → | Steer 轉向 |
| Space 空白鍵 | Handbrake (drift!) 手煞車（甩尾！） |
| R | Reset car 車子歸位 |
| P | Pause 暫停 |

**Phone 手機** — use the on-screen buttons (steer, gas ▲, brake ▼, 手煞),
or just **drag your finger** on the road to drive. 用畫面上的按鈕，或直接在馬路上**滑動手指**開車。

## Make it your own! 自己改改看！

Open `index.html` in a text editor and find the **PHYSICS** constants near
the top of the `<script>`. 打開 `index.html`，找到 `<script>` 上方的 **PHYSICS** 區塊。

```js
const ENGINE = 430;       // how fast it speeds up 加速力
const TURN   = 3.3;       // how sharply it steers 轉向靈敏度
const GRIP   = 0.86;      // tire grip (lower = stickier) 抓地力
const DRIFT_GRIP = 0.975; // grip while handbraking (higher = more slide) 甩尾滑度
```

Easy experiments 簡單的小實驗：

- Make `ENGINE` bigger for a faster car. 把 `ENGINE` 調大，車更快。
- Raise `DRIFT_GRIP` toward `0.99` for wild, slidey drifts. 把 `DRIFT_GRIP` 調高，甩尾更誇張。
- Change `BLOCK` and `GRID` to resize the city. 改 `BLOCK`、`GRID` 改變城市大小。
- Edit the `CP_GRID` list to move the race checkpoints around. 改 `CP_GRID` 移動賽道檢查點。

Save the file, refresh the browser, and your changes appear in the game!
存檔、重新整理瀏覽器，改動就出現在遊戲裡了！
