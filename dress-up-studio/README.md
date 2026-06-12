# ✨ Dress-Up Studio 換裝小遊戲 ✨

A dress-up game in a single file — no installs needed.

## How to play 怎麼玩

**Double-click `index.html`** and it opens in your browser. 用瀏覽器打開 `index.html` 就可以玩了！

- Click the tabs (Hair, Hat, Clothes, Skirt, Shoes, Extras, Background) and pick anything you like. 點分類選衣服。
- Pick a color for each piece with the round color buttons. 每件衣服都可以換顏色。
- **Extras 配件** can be worn together — glasses AND wings AND a magic wand!
- 🎲 **Surprise!** dresses her in a random outfit. 隨機穿搭。
- 📷 **Save** downloads a picture of your outfit. 把作品存成圖片。
- The game remembers your outfit next time you open it. 下次打開衣服還在！

![screenshot](screenshot.png)

## Make your own clothes! 自己畫新衣服！

All the clothes are little drawings made of code (SVG). Open `index.html`
in a text editor (like Notepad or VS Code) and find the `items:` lists.

Each item looks like this:

```js
{ name: 'Crown', zh: '皇冠', emoji: '👑', svg: `
  <path d="M120 56 L120 28 ... Z" fill="{{c}}"/>` },
```

- `{{c}}` becomes whatever color you picked, `{{cd}}` is a darker version of it.
- Copy a whole item, paste it below, change the name and the shapes — save the
  file, refresh the browser, and your new clothes appear in the game!
- Easy first experiments: change an emoji, change a color like `#ff5d8f`
  (search "hex color picker" to find new ones), or make the crown taller by
  making its numbers smaller (smaller = higher up on the doll).

The doll lives on a grid that is 300 wide and 520 tall.
Her head is around (150, 100), her waist around (150, 250),
and her feet around (150, 450).
