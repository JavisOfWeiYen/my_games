# 🏁 F1 Racing — Simplified Spec 簡化規格

A browser racing **simulator** (not arcade): real driving physics on a real
circuit, with a **broadcast-grade, polished** look. Distilled from the full
research doc (`f1_2026_racing_game_research_spec.html`) down to what we will
actually build. 規則真實、品牌虛構。

## 0. Pillars 核心原則
1. **Real handling 真實操控** — tyre grip + slip, weight transfer, lock-ups,
   understeer/oversteer, catchable slides. You really *drive*.
2. **Polished visuals 精緻美術** — the thing City Racer got wrong. Crisp,
   layered, broadcast-style. No crude flat shapes.
3. **Real circuit 真實賽道** — a designed closed track with proper corners,
   braking zones, apexes, kerbs and a racing line.
4. **Fictional brands 虛構品牌** — invented teams/liveries (no F1 licensing).

## 1. Tech 技術
- **No Unity/Unreal.** Single self-contained **HTML + Canvas 2D**, offline,
  double-click to play, mobile-friendly. 單一 HTML 檔、離線、手機可玩。
- Render at `devicePixelRatio` for crispness; everything anti-aliased.
- May split into a few classic `<script src>` files later if it grows, while
  staying double-click-playable. (No build step, no ES modules.)

## 2. View / Camera 視角
- Top-down, camera follows the car, **rotates with the car** (car points up),
  smooth follow + slight look-ahead. Zoom eases out with speed.

## 3. Physics 物理 (the realism core)
- Bicycle/two-axle model: separate **velocity vector** and **heading**.
- Per-axle tyre forces from **slip angle** + **slip ratio** (Pacejka-lite),
  grip clamped by a friction circle.
- **Weight transfer** front/rear (braking/accel) and left/right (cornering)
  changes per-tyre grip → understeer/oversteer emerges.
- Brake **lock-up** (loss of steering), throttle wheelspin, handbrake slides.
- Aero downforce raises grip with speed; drag sets top speed.
- Fixed-timestep integration for stability; deterministic.

## 4. Car systems 車輛系統 (simplified from spec)
- **Tyres 輪胎**: 3 compounds (soft/medium/hard) — grip vs durability; wear
  and temperature reduce grip; cold/overheated = less grip.
- **ERS 能量回收**: harvest under braking, deploy for a boost; on-screen bar.
- **Active aero / DRS**: low-drag mode on straights → higher top speed.
- **Fuel 油量**: mass decreases over a stint → car gets faster; affects grip.

## 5. Track 賽道
- One hand-designed circuit for Phase 0–2 (mix of slow hairpin, fast sweeper,
  chicane, long straight). Kerbs, runoff (grass/gravel that scrubs speed),
  start/finish line, sector splits. More tracks later.
- Stored as data (centreline + width + kerb/surface flags) so new tracks are
  easy to add.

## 6. AI opponents AI 對手
- Follow a precomputed **racing line** with target speeds per point; PID-style
  throttle/brake/steer to track it; adjustable skill; basic overtake/defend
  and collision avoidance. 可調強度。

## 7. Modes / Race 模式
- **Practice / Hotlap** → **Qualifying** (best lap sets grid) → **Race**
  (N laps, pit stop to change tyres, positions, lap/sector timing, best lap).
- Saved best lap (localStorage).

## 8. Visual treatment 美術 (priority — City Racer's weak point)
- Cars: gradient paint, glossy highlight, cockpit, wheels, **soft drop shadow**.
- Track: textured asphalt, red/white **kerbs**, painted lines, grass/gravel.
- Effects: **tyre smoke particles** + skid marks on slip, dust on grass,
  subtle speed lines, light camera shake at speed, vignette.
- HUD: clean type, telemetry-style ERS/fuel/tyre-temp bars, sector timing,
  position tower, minimap. Cohesive palette, broadcast-graphics feel.

## 9. Controls 操作
- Keyboard: accelerate / brake / steer / handbrake / ERS-boost / DRS / look.
- Touch: on-screen steer + pedals + boost (carefully laid out, not cramped).

## 10. Phases 開發階段
- **Phase 0** — car + physics + one circuit + follow camera + polished art + HUD basics. (playable hotlap that *feels* real and *looks* clean)
- **Phase 1** — tyres (wear/temp) + ERS + DRS + fuel + tyre smoke/skid FX.
- **Phase 2** — AI opponents + qualifying + race + pit stops + timing/positions.
- **Phase 3+** — more tracks, weather, simple career/championship.

## Out of scope (for now) 暫不做
Multiplayer, machine-learning AI, licensed F1 content, Unity/Unreal, full
24-race calendar, team-management economy.
