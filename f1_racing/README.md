# 🏁 Apex GP — Racing Sim 賽車模擬

A first-person racing **simulator** (not an arcade game): real tyre grip and slip,
weight transfer, lock-ups and catchable slides — you really *drive* it, from the
cockpit with a steering wheel, **racing up to 7 AI rivals** styled after real 2026
F1 teams.

第一人稱賽車**模擬**(不是街機):真實的輪胎抓地與滑移、配重轉移、煞車鎖死與可控甩尾
— 你是真的在「開」車,從座艙裡握著方向盤,跟**最多 7 台 AI 對手**(取材自 2026 真實 F1 車隊)同場競速。

## ▶️ Play 開始玩

Double-click `index.html`, or play online:
點兩下 `index.html`,或線上玩:
https://javisofweiyen.github.io/my_games/f1_racing/

New to it? Read **[`the-science.html`](the-science.html)** — the physics & cornering
explained in plain language. 第一次玩?先看 **[`the-science.html`](the-science.html)**:用白話講解背後的物理與過彎技巧。

## 🕹️ From the main menu 主選單可選

- **Circuit 賽道** — three hand-built tracks: *Apex GP* (mixed), *Velocity* (fast,
  flowing), *Hairpin Park* (tight & technical). 三條手工賽道:混合、高速流暢、狹窄技術。
- **Rivals 對手** — race **0 to 7** opponents. 同場對手 0–7 台。
- **Difficulty 難度** — **Easy 容易** (clean, careful AI) or **Hard 困難** (aggressive,
  fastest-lap AI that brakes late and runs to — sometimes past — the limit). 容易(乾淨保守)或困難(積極、晚煞車、逼極限、偶爾跑寬)。

## 🚦 A race 一場比賽

Lights out after a 3-second countdown → race the set number of laps → a **standings
screen** shows the finishing order (your row highlighted) and your best lap. Press
**R** to race again. 3 秒燈滅起跑 → 跑完設定圈數 → **名次結算畫面**(你的列會highlight)+最佳單圈,按 **R** 再比一場。

The field lines up in a **proper grid behind the start line** and accelerates across
it when the lights go out. Rivals appear both on the **minimap** and in the cockpit
view, and you can **bump and trade paint** — contact shoves cars around and a
side-swipe twists them off line. 車隊在**起跑線後**排成正規起跑格,燈滅後一起衝線;對手會出現在**小地圖**與座艙視野中,而且**會碰撞卡位**——追撞會推擠、側撞會把車轉歪。

## 🎮 Controls 操作

| Action 動作 | Keyboard 鍵盤 | Touch 觸控 |
|---|---|---|
| Throttle 油門 | `W` / `↑` | ▲ |
| Brake 煞車 | `S` / `↓` | ▼ |
| Steer 轉向 | `A` `D` / `←` `→` | ◀ ▶ |
| Handbrake 手煞 | `Space` | 手煞 |
| ERS boost 能量加速 | `Shift` | ERS ⚡ |
| DRS (low drag) 低阻力 | `F` | DRS |
| Change tyres 換胎 | `T` | 胎 TYRE |
| Reset / race again 回起點/再比 | `R` | Reset |
| Pause 暫停 | `P` | Pause |

## 💡 Tips 小技巧

- **Brake before the corner, not in it. 進彎前先煞車,別在彎中才煞。** Braking and turning
  at the same time uses up all the grip and pushes you wide. 邊煞邊轉會用光抓地力而推頭跑寬。
- Hit the **apex** (clip the inside kerb) and feed the throttle back in on the way out.
  切 **Apex**(貼著內側路肩),出彎再慢慢補油。
- Run onto the grass and you'll slow right down — lift off and steer back onto the
  asphalt to recover. 跑到草地上會大減速 — 先鬆油、把車轉回柏油路面就能恢復。
- **Soft tyres** grip best but wear and overheat fastest; **hard** last longest. Sliding
  cooks and wears them — watch the TYRE bar. 軟胎抓地最好但磨耗/過熱最快,硬胎最耐;猛滑會把胎搞爛,注意 TYRE 條。
- Save **ERS** for corner exits and the straight, harvest it back under braking; pop **DRS**
  on the straights for more top speed. ERS 留到出彎和直線放、煞車回充;直線開 DRS 拉極速。

## 🛠️ How It's Made 怎麼做的

One self-contained **HTML + Canvas 2D** file — no build, no libraries. Highlights:

- **Physics** — a two-axle (bicycle) model with per-tyre slip angles and a
  friction-circle grip limit; power-limited engine, rolling + aero drag, weight
  transfer, tyre temperature/wear, ERS & DRS.
- **Tracks as data** — each circuit is just a list of control points splined into a
  Catmull-Rom centreline; the same physics & renderer drive any track.
- **AI rivals** — every car (player and AI) runs the *same* `step()` physics; an AI
  driver reads the track ahead, computes a safe corner speed and decides
  brake/throttle/steer. Cars collide with momentum + side-swipe deflection.
- **Rendering** — chase/cockpit perspective; rivals are distance-scaled billboards in
  their team liveries, depth-sorted onto the road.

單一 **HTML + Canvas 2D** 檔,無需編譯、無外部函式庫。重點:雙軸(自行車)物理模型+每輪滑移角
與抓地力圓、功率受限引擎、配重轉移、輪胎溫度磨耗、ERS/DRS;賽道資料化(Catmull-Rom 中線);
所有車共用同一套物理,AI 看前方算安全速度再決定油門煞車轉向,並有動量碰撞與側撞偏轉;
座艙透視渲染,對手以隊色看板依距離縮放、深度排序畫在賽道上。

See the **[development log](the-making-of.html)** for how it was built, step by step,
and [`SPEC.md`](SPEC.md) for the original design spec. 逐步開發歷程見
**[開發歷程](the-making-of.html)**,原始設計規格見 [`SPEC.md`](SPEC.md)。
