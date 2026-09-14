# rs — ROPPONGI SURVIVOR の共有カード

リザルトの QR（ゲーム側の `Core/Progression/ShareLink`）の行き先。
問い合わせ文字列だけ読んで canvas でカードを描くので、**サーバも DB も要らない**。

```
https://pincool.github.io/rs/?v=1&sc=2128&kv=kv_c
```

| 名前 | 中身 |
|---|---|
| `v` | 問い合わせ文字列の版（いま 1） |
| `sc` | スコア。**画面に出すのはこれだけ** |
| `kv` | 下地（`kv_a`〜`kv_d`）。ゲーム側がランごとに引いた結果 |

## 置き方

`docs/` の中身だけが公開される（Settings → Pages → Source は「Deploy from a branch」の `main` / `/docs`）。
push すれば数十秒で反映される。

**GitHub Actions で出す形にも切り替えられる** —— `.github/workflows/pages.yml` を置いて
Source を「GitHub Actions」にするだけ（`upload-pages-artifact` の `path` をこのフォルダに向ける）。
新しく作るならそちらが素直で、理由は本体リポジトリの `Docs/ShareQrPrompt.md` に書いてある。

版面（数字の位置・大きさ・縁・影）は**ゲーム側の `Game/UI/ShareCard` と 1 対 1**。
片方を動かしたら両方直すこと。作り方の全体は本体リポジトリの `Docs/ShareQrPrompt.md`。

QRコードは株式会社デンソーウェーブの登録商標です。
