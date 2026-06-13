# 🧱 Block Drop 方塊掉掉樂 🧱

A cute Tetris-style game in a single file — no installs needed.
可愛粉彩風的俄羅斯方塊，單一檔案、免安裝。

## How to play 怎麼玩

**Double-click `index.html`** and it opens in your browser. 用瀏覽器打開 `index.html` 就可以玩了！

Blocks fall from the top. Move and rotate them so each row fills up
completely — full rows disappear and you score points!
方塊會從上面掉下來，把它們排滿一整列，那一列就會消除得分！

### Controls 操作

**Keyboard 鍵盤**

| Key 按鍵 | Action 動作 |
|---|---|
| ← → | Move 左右移動 |
| Space 空白鍵 | Rotate 旋轉 |
| ↓ | Hard drop 直接落到底 |
| C | Hold 暫存方塊 |
| P | Pause 暫停 |

**Touch 手機觸控**

- Tap the big buttons under the board. 點下方的大按鈕。
- On the board itself: **swipe left/right** to move, **swipe down** to drop,
  **tap** to rotate. 在棋盤上：左右滑動移動、往下滑落下、輕點旋轉。

### Scoring 計分

- Clear 1 / 2 / 3 / 4 rows at once for 100 / 300 / 500 / 800 points (× level).
  一次消 1~4 行分別得 100/300/500/800 分（乘上等級）。
- Every 10 lines you level up and the blocks fall faster! 每消 10 行升一級，方塊掉得更快！
- 🏆 Your best score is remembered. 最高分會自動記住。

## Make it your own! 自己改改看！

Open `index.html` in a text editor (like Notepad or VS Code) and find the
`PIECES` list near the top of the `<script>`. 打開 `index.html`，找到 `<script>` 開頭的 `PIECES`。

Each piece is just a little grid of `1`s (filled) and `0`s (empty), with a color:
每個方塊就是一張由 `1`（有）和 `0`（沒有）組成的小格子圖，加上一個顏色：

```js
T: { color: '#b388ff', cells: [
      [0,1,0],
      [1,1,1],
      [0,0,0] ] },
```

Easy first experiments 簡單的小實驗：

- Change a color like `#b388ff` (search "hex color picker" for new ones). 換顏色。
- Flip a `0` to a `1` (or back) to draw a brand-new block shape! 把 `0` 改成 `1` 畫出新形狀！
- Make the board bigger by changing `COLS` and `ROWS`. 改 `COLS`、`ROWS` 改變棋盤大小。

Save the file, refresh the browser, and your changes appear in the game!
存檔、重新整理瀏覽器，改動就出現在遊戲裡了！
