# 🏁 Apex GP — Racing Sim 賽車模擬

A first-person racing **simulator** (not an arcade game): real tyre grip and slip,
weight transfer, lock-ups and catchable slides — you really *drive* it, on a
hand-built circuit, from the cockpit with a steering wheel.

第一人稱賽車**模擬**(不是街機):真實的輪胎抓地與滑移、配重轉移、煞車鎖死與可控甩尾
— 你是真的在「開」車,在手工設計的賽道上,從座艙裡握著方向盤過彎。

## ▶️ Play 開始玩

Double-click `index.html`, or play online:
點兩下 `index.html`,或線上玩:
https://javisofweiyen.github.io/my_games/f1_racing/

## 🎮 Controls 操作

| Action 動作 | Keyboard 鍵盤 | Touch 觸控 |
|---|---|---|
| Throttle 油門 | `W` / `↑` | ▲ |
| Brake 煞車 | `S` / `↓` | ▼ |
| Steer 轉向 | `A` `D` / `←` `→` | ◀ ▶ |
| Handbrake 手煞 | `Space` | 手煞 |
| Reset 回起點 | `R` | Reset |
| Pause 暫停 | `P` | Pause |

## 💡 Tips 小技巧

- **Brake before the corner, not in it. 進彎前先煞車,別在彎中才煞。** Braking and turning
  at the same time uses up all the grip and pushes you wide. 邊煞邊轉會用光抓地力而推頭跑寬。
- Hit the **apex** (clip the inside kerb) and feed the throttle back in on the way out.
  切 **Apex**(貼著內側路肩),出彎再慢慢補油。
- Run onto the grass and you'll slow right down — steer back onto the asphalt to recover.
  跑到草地上會大減速 — 把車轉回柏油路面就能恢復。

## 🛠️ How It's Made 怎麼做的

One self-contained **HTML + Canvas 2D** file — no build, no libraries. The car uses a
two-axle (bicycle) physics model with per-tyre slip angles and a friction-circle grip
limit; the track is a Catmull-Rom centreline drawn in a chase/cockpit perspective.

單一 **HTML + Canvas 2D** 檔,無需編譯、無外部函式庫。車輛用雙軸(自行車)物理模型,
每個輪胎各自算滑移角並受抓地力圓限制;賽道是 Catmull-Rom 中線,用透視投影畫出座艙視角。

See [`SPEC.md`](SPEC.md) for the full design spec. 完整設計規格見 [`SPEC.md`](SPEC.md)。
