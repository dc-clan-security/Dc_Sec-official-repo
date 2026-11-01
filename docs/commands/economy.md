# 💰 経済システム (Dcelia)

[← コマンド一覧に戻る](README.md)

Dc_Sec 内で使える通貨 **Dcelia** の管理と、商品ショップ・ロール自販機・個人招待報酬の設定です。メッセージ送信・お仕事・デイリーボーナス・トリビア・カジノなどで Dcelia を獲得できます。Dcelia はサーバーごとに独立した残高で、現実の金銭と交換することはできません。

## `/coin`

**通貨システム (残高/付与/設定)**

`/coin add`・`remove`・`set`・`salary`・`chat-reward`・`notify`・`name` はサーバー管理権限が必要です。`/coin daily` は連続取得でボーナス増加（+25/日・最大30日）、`/coin work` は1時間ごとに50〜300獲得、`/coin rob` は成功率40%で相手残高の20%を奪取（失敗すると自分に罰金）です。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/coin balance` | 自分または指定ユーザーの通貨残高を確認します | 一般 | `user` (任意) |
| `/coin add` | ユーザーに通貨を付与します | Mod以上 | `user` (必須)<br>`amount` (必須)<br>`reason` (任意) |
| `/coin remove` | ユーザーから通貨を減算します | Mod以上 | `user` (必須)<br>`amount` (必須)<br>`reason` (任意) |
| `/coin set` | ユーザーの残高を設定します | Mod以上 | `user` (必須)<br>`amount` (必須) |
| `/coin name` | 通貨の名前を変更します (ダッシュボードからも変更可) | Mod以上 | `name` (必須) |
| `/coin notify` | 通貨の付与を通知するチャンネルを設定します | Mod以上 | `channel` (必須) |
| `/coin chat-reward` | チャットでの通貨獲得量とクールダウンを設定します | Mod以上 | `amount` (必須)<br>`cooldown` (任意) |
| `/coin salary` | メッセージランキング1〜3位への給与を設定します | Mod以上 | `rank` (必須)<br>`amount` (必須)<br>`period` (任意) |
| `/coin ranking` | 通貨所持ランキング TOP10 | 一般 | — |
| `/coin daily` | デイリーボーナスを受け取ります (連続で報酬UP) | 一般 | — |
| `/coin work` | 働いて通貨を稼ぎます (1時間ごと) | 一般 | — |
| `/coin rob` | 他のユーザーから通貨を奪います (失敗すると罰金) | 一般 | `user` (必須) |
| `/coin pay` | 他のユーザーに通貨を送ります | 一般 | `user` (必須)<br>`amount` (必須) |

## `/shop`

**🛒 自販機 (Dceliaで商品を購入)**

在庫管理つき商品ショップです。`/shop dm` でギフトコード等のコード在庫商品に切り替えでき、購入すると未使用のコードを1件引き当てて購入者の DM へ自動配送します（コードは使い捨て・二重配布なし）。`/shop effect` でロール付与などの特典、`/shop items`・`/shop use` で消耗アイテムに対応します。パネルは再起動後もボタンが機能します。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/shop add` | 自販機に商品を追加します | Mod以上 | `name` (必須)<br>`price` (必須)<br>`description` (任意)<br>`role` (任意)<br>`stock` (任意)<br>`emoji` (任意) |
| `/shop restock` | 商品の在庫を追加補充します | Mod以上 | `item` (必須)<br>`amount` (必須) |
| `/shop setstock` | 商品の在庫を直接設定します (-1で無制限) | Mod以上 | `item` (必須)<br>`stock` (必須) |
| `/shop price` | 商品の価格を変更します | Mod以上 | `item` (必須)<br>`price` (必須) |
| `/shop remove` | 商品を販売終了にします | Mod以上 | `item` (必須) |
| `/shop panel` | 自販機パネルをこのチャンネルに設置します | Mod以上 | — |
| `/shop stats` | 商品の販売数を確認します | Mod以上 | `item` (必須) |
| `/shop dm` | 商品をDM配送商品に切替 (購入時にコードをDMへ自動送信) | Mod以上 | `item` (必須)<br>`state` (任意) |
| `/shop addstock` | DM配送コードを一括追加 (商品ID指定 / 1行1コード) | Mod以上 | `item` (必須)<br>`codes` (任意) |
| `/shop codes` | DM配送コードの在庫と送信済みを確認します | Mod以上 | `item` (必須)<br>`sent` (任意) |
| `/shop purge` | 送信済みコードの記録を物理廃棄します | Mod以上 | `item` (必須) |
| `/shop list` | 自販機の商品一覧を表示します | 一般 | — |
| `/shop buy` | 自販機で商品を購入します (個数指定可) | 一般 | `item` (必須)<br>`quantity` (任意) |
| `/shop inventory` | 自分 (または指定ユーザー) の購入履歴を表示します | 一般 | `user` (任意) |
| `/shop effect` | 商品に消耗アイテム効果を設定します (管理者) | Mod以上 | `item` (必須)<br>`kind` (必須)<br>`value` (任意)<br>`minutes` (任意) |
| `/shop items` | 所持している消耗アイテム一覧 (未使用) | 一般 | — |
| `/shop use` | 消耗アイテムを使用して効果を発動します | 一般 | `item` (必須) |

## `/roleshop`

**ロール自販機 (通貨でロールを購入)**

Dcelia でロールを購入できるロール自販機です。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/roleshop add` | ロール自販機に商品を追加します | Mod以上 | `role` (必須)<br>`price` (必須)<br>`description` (任意) |
| `/roleshop remove` | ロール自販機から商品を削除します | Mod以上 | `role` (必須) |
| `/roleshop list` | ロール自販機の商品一覧を表示します | Mod以上 | — |
| `/roleshop panel` | ロール自販機のパネルをこのチャンネルに設置します | Mod以上 | — |

## `/invite`

**個人招待リンクと招待報酬**

個人ごとの招待リンクを作成し、招いた人数に応じて報酬を支払います。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/invite create` | 自分専用の招待リンクを作成します (招待で通貨を獲得) | 一般 | — |
| `/invite mylinks` | 自分の招待リンク一覧と使用回数・獲得額を表示します | 一般 | — |
| `/invite reward` | 招待1人あたりの報酬を設定します | Mod以上 | `amount` (必須) |
| `/invite panel` | 招待リンク作成パネルをこのチャンネルに設置します | Mod以上 | — |

### d! プレフィックスでも実行可能

`d!coin` / `d!balance` / `d!bal`（残高）・`d!ranking` / `d!rich`（ランキング）・`d!daily`・`d!work`・`d!rob`・`d!pay`
