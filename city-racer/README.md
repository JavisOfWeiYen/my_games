# 🏎️ City Racer 城市賽車 🏎️

A pseudo-3D racing game in a single file — no installs needed.
車內第一人稱視角的賽車遊戲，單一檔案、免安裝。

## How to play 怎麼玩

**Double-click `index.html`** and it opens in your browser. 用瀏覽器打開 `index.html` 就可以玩了！

You sit **in the driver's seat** — dashboard, speed + rev gauges, and half
the steering wheel in view — racing down a neon night highway. Hold the gas,
lean into the curves, and overtake the traffic ahead without crashing.
你坐在**駕駛座**裡：看得到儀表板、時速錶與轉速錶、還有半個方向盤，飆過霓虹夜間
高速公路。催油門、順著彎道過彎、超越前車別撞上。

### Levels 關卡

Each level gives you a **time limit to reach the finish line**. Make it in
time and you advance to the next level — which is faster and has more traffic.
Run out of time and it's **Game Over**. Your best level reached is saved.
每一關都有**到達終點線的時間限制**：時間內衝過終點就晉級下一關（更快、車更多）；
時間到還沒到終點就 **Game Over**。會記住你達到的最高關卡。

The road is drawn with a classic "pseudo-3D" trick — flat road segments
projected into the distance — so it runs smoothly anywhere, even on a phone.
道路是用經典的 pseudo-3D 技巧畫出來的（把平面路段投影到遠方），所以到處都跑得很順，手機也行。

### Controls 操作

**Keyboard 鍵盤**

| Key 按鍵 | Action 動作 |
|---|---|
| W / ↑ | Accelerate 油門 |
| S / ↓ | Brake 煞車 |
| A / D or ← / → | Steer 轉向 |
| P | Pause 暫停 |
| R | Restart 重新開始 |

**Phone 手機** — use the on-screen buttons: ◀ ▶ to steer, ▲ gas, ▼ brake.
用畫面上的按鈕：◀ ▶ 轉向、▲ 油門、▼ 煞車。

💡 Tip: lift off the gas before a sharp curve, and don't run onto the
verge — going off-road scrubs your speed. 小技巧：急彎前放油門，別開到路肩，
壓到草地會掉速。

## Make it your own! 自己改改看！

Open `index.html` in a text editor and find the **CONFIG** block near the
top of the `<script>`. 打開 `index.html`，找到 `<script>` 上方的 **CONFIG** 區塊。

```js
const MAXSPEED = SEG * 64;     // top speed — shows as 200 km/h 極速
const CENTRIFUGAL = 0.18;      // how hard curves push you out (lower = easier) 彎道甩出力
const CAM_H = 720;             // camera height (lower = more in-car) 視角高度
const FOV = 98;                // field of view 視野廣度
```

Easy experiments 簡單的小實驗：

- Raise `MAXSPEED` for a faster car. 把 `MAXSPEED` 調大車更快。
- Make the levels easier/harder by editing `timeLimit()` (seconds per level).
  改 `timeLimit()` 調整每關的限時，讓關卡更簡單或更難。
- Edit `buildTrack()` to design your own course — add `curve()`, `hill()`,
  `straight()` and `sCurves()`. 改 `buildTrack()` 設計自己的賽道。
- Change the neon colours in `LIGHT` / `DARK` / `CAR_COLORS`. 改霓虹配色。
- More traffic per level? Tweak the `TOTAL` formula inside `resetCars()`.
  想要更多車流就改 `resetCars()` 裡的 `TOTAL` 公式。

Save the file, refresh the browser, and your changes appear in the game!
存檔、重新整理瀏覽器，改動就出現在遊戲裡了！
