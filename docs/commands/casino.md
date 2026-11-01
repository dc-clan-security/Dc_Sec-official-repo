# 🎰 カジノ

[← コマンド一覧に戻る](README.md)

Dcelia を賭けて遊ぶ11種のカジノゲームと、戦績・ランキングの管理です。全ゲーム `d!` プレフィックスでも遊べます（例: `d!slots 100`、`d!roulette 100 red`）。

## `/casino`

**カジノ (通貨で遊ぶ)**

進行型ゲーム（ブラックジャック/ハイロー/マインスイーパー等）は再起動で中断した場合に賭け金を自動返金します。ハイローとマインスイーパーはタイムアウト時、その時点の倍率で自動清算します。遊び方は `/casino rules` で確認できます。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/casino slots` | スロットで遊びます (3つ揃いで高配当) | 一般 | `bet` (必須) |
| `/casino coinflip` | コイントス (当たると2倍) | 一般 | `bet` (必須)<br>`side` (必須) |
| `/casino dice` | サイコロ (ゾロ目で出目倍・最大6倍) | 一般 | `bet` (必須) |
| `/casino blackjack` | ブラックジャック (勝つと2倍) | 一般 | `bet` (必須) |
| `/casino roulette` | ルーレット (数字当ては36倍) | 一般 | `bet` (必須)<br>`bet_type` (必須)<br>`number` (任意) |
| `/casino baccarat` | バカラ (プレイヤー2倍 / バンカー1.95倍 / タイ9倍) | 一般 | `bet` (必須)<br>`side` (必須) |
| `/casino hilo` | ハイロー (予想を連鎖させて倍率UP / いつでも降りられる) | 一般 | `bet` (必須) |
| `/casino mines` | マインスイーパー (宝石を開けて倍率UP / 爆弾に注意) | 一般 | `bet` (必須)<br>`bombs` (任意) |
| `/casino crash` | クラッシュ (割れる前に降りろ! / 最高50倍) | 一般 | `bet` (必須) |
| `/casino scratch` | スクラッチカード (3マッチで当選) | 一般 | `bet` (必須) |
| `/casino stats` | カジノ戦績を確認します (ゲーム別) | 一般 | `user` (任意) |
| `/casino top` | カジノ純損益ランキング TOP10 | 一般 | — |
| `/casino rules` | カジノの遊び方と配当表を表示します | 一般 | — |

### d! エイリアス

`d!slots` / `d!slot` / `d!slot777`（スロット）・`d!cf` / `d!coinflip`（コイントス）・`d!dice` / `d!roll`（ダイス）・
`d!bj` / `d!blackjack`・`d!roulette` / `d!rl`・`d!baccarat` / `d!baka`・`d!hilo` / `d!highlow` / `d!hl`・
`d!mines` / `d!mine`・`d!crash`・`d!scratch`
