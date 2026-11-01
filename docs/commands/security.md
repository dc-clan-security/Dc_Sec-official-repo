# 🛡️ セキュリティ・防衛

[← コマンド一覧に戻る](README.md)

Dc_Sec の根幹となるセキュリティ機能群です。スパム・レイド・Nuke（サーバー破壊）・荒らし投稿を自動検知して対処し、その設定をここで管理します。防御は常時バックグラウンドで動作しており、コマンドは主に設定変更に使います。

## `/security`

**その他のセキュリティ機能**

防御設定の入口となるグループです。ハニーポット（非公開の罠チャンネルへの投稿＝攻撃者確定で即処置）、NGワード、URLホワイトリスト、フィッシング/短縮URL検知、大文字連打・絵文字過剰・Zalgo 検知、@everyone 即処罰、anti-alt（新規アカウント制限）などは `/security content`・`/security advanced` で細かく調整できます。検知内容は累積ストライク制（タイムアウト積み重ね→警告→自動BAN）でエスカレートします。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/security botadd` | 未許可Bot追加ブロック | Mod以上 | `enabled` (必須) |
| `/security raid` | レイドモード(新規アカウントの参加拒否) | Mod以上 | `enabled` (必須)<br>`days` (任意)<br>`action` (任意) |
| `/security mention` | 大量メンション対策 | Mod以上 | `enabled` (必須)<br>`limit` (任意) |
| `/security linkspam` | リンクスパム対策 | Mod以上 | `enabled` (必須)<br>`limit` (任意)<br>`seconds` (任意) |
| `/security spam` | 連投スパム対策(ユーザー/Bot/Webhook/類似文/複数アカウント) | Mod以上 | `enabled` (必須)<br>`limit` (任意)<br>`seconds` (任意)<br>`action` (任意)<br>`minutes` (任意)<br>`blockbots` (任意)<br>`similarity` (任意)<br>`repeat_limit` (任意)<br>`repeat_hours` (任意)<br>`raid_accounts` (任意)<br>`raid_seconds` (任意) |
| `/security logchannel` | ログ送信先チャンネル | Mod以上 | `channel` (必須) |
| `/security honeypot` | ハニーポット(罠)chを設定 — 非公開chへの投稿=攻撃者として自動処置 | Mod以上 | `channel` (任意) |
| `/security honeypot-action` | ハニーポット検知時の処置を変更します | Mod以上 | `action` (必須) |
| `/security honeypot-off` | ハニーポットを無効化します | Mod以上 | — |
| `/security addword` | NGワードフィルターに単語を追加します | Mod以上 | `word` (必須) |
| `/security removeword` | NGワードフィルターから単語を削除します | Mod以上 | `word` (必須) |
| `/security wordlist` | 現在のNGワード一覧を表示します | Mod以上 | — |
| `/security urlwhitelist-add` | URLブロックの対象外にするドメインを追加します | Mod以上 | `domain` (必須) |
| `/security urlwhitelist-remove` | URLブロックのホワイトリストからドメインを削除します | Mod以上 | `domain` (必須) |
| `/security channel-allowed` | 実行したチャンネルのURL関連監視をオン/オフ切り替えします | Mod以上 | — |
| `/security bot-whitelist` | 指定Botを監視対象から除外します(リンク投稿等を許可) | Mod以上 | `bot` (必須) |
| `/security bot-whitelist-remove` | Botを監視除外リストから削除します | Mod以上 | `bot` (必須) |
| `/security content` | コンテンツフィルター(NGワード/URL/caps/絵文字/Zalgo)の設定 | Mod以上 | `wordfilter` (任意)<br>`urlblock` (任意)<br>`phishing` (任意)<br>`zalgo` (任意)<br>`caps` (任意)<br>`capsthreshold` (任意)<br>`emoji` (任意)<br>`emojilimit` (任意)<br>`everyone` (任意) |
| `/security advanced` | 高度な設定(anti-alt/ストライク/権限昇格監視/タイムアウト時間) | Mod以上 | `antialt` (任意)<br>`minhours` (任意)<br>`permesc` (任意)<br>`warn` (任意)<br>`ban` (任意)<br>`minutes` (任意) |

## `/antinuke`

**Nuke対策の設定**

監査ログをリアルタイム監視し、短時間に大量の破壊的操作（チャンネル/ロールの削除・大量BAN等、16項目）を検知したら実行者を排除し、**Nuke直前のバックアップから自動復元**、実行者の操作を巻き戻します。正規に大量操作する管理者は `/whitelist add` で対象外にしてください。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/antinuke status` | 現在の設定を表示 | Mod以上 | — |
| `/antinuke toggle` | Nuke対策のON/OFF | Mod以上 | `enabled` (必須) |
| `/antinuke set` | 検知条件を設定 | Mod以上 | `type` (必須)<br>`limit` (任意)<br>`seconds` (任意)<br>`enabled` (任意) |
| `/antinuke response` | 発動時の動作 | Mod以上 | `punish` (任意)<br>`autorestore` (任意)<br>`dm` (任意) |

## `/modrole`

**通知を受け取るモデレーターロール**

Dc_Sec のコマンドを実行できるモデレーターロールを指定します（Discord 権限の「サーバーを管理」を持つ人は常に利用できます）。通知の宛先にもなります。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/modrole add` | 追加 | Mod以上 | `role` (必須) |
| `/modrole remove` | 削除 | Mod以上 | `role` (必須) |
| `/modrole list` | 一覧 | Mod以上 | — |

## `/whitelist`

**Nuke検知の対象外ユーザー(信頼するユーザー/Bot)**

Anti-Nuke 検知の対象外にする信頼できるユーザー/Bot を管理します。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/whitelist add` | 追加 | Mod以上 | `user` (必須) |
| `/whitelist remove` | 削除 | Mod以上 | `user` (必須) |
| `/whitelist list` | 一覧 | Mod以上 | — |

## `/status`

**Dc_Sec/VPS の稼働状況**

Bot/VPS の稼働状況パネルを設置します。負荷・メモリ・fd・conntrack・防御システムの状態を自動更新。外部ハートビート (healthchecks.io) を組み合わせれば VPS ごと落ちた場合も検知できます。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/status panel` | Dc_Sec/VPSの稼働状況パネルを設置します (自動更新) | Mod以上 | `channel` (任意)<br>`interval` (任意) |
| `/status remove` | 稼働状況パネルの自動更新を停止します | Mod以上 | — |
| `/status now` | 今すぐBot/VPSの稼働状況を表示します | Mod以上 | — |
| `/status heartbeat` | VPS停止を外部から検知するハートビート監視の案内 | Mod以上 | — |

## `/webauth`

**Web認証 (Discord OAuth2メール確認)**

入室者にメール認証 (Webページ経由) を求める認証システムです。捨てメアドドメインのブロック、IP重複チェック（重複アカウント検知）も設定できます。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/webauth setup` | Web認証パネルを設置します | Mod以上 | `role` (必須)<br>`channel` (任意) |
| `/webauth disable` | Web認証を無効化します | Mod以上 | — |
| `/webauth dup-ip` | 同一IPからの複数アカウント認証をブロックするか設定します | Mod以上 | `enabled` (必須) |
| `/webauth list` | 認証済みユーザーの一覧を表示します | Mod以上 | — |
| `/webauth block-domain` | 指定ドメインのメールアドレスでの認証をブロックします (捨てメアド対策) | Mod以上 | `domain` (必須) |
| `/webauth unblock-domain` | ブロック済みメールドメインのブロックを解除します | Mod以上 | `domain` (必須) |
| `/webauth domains` | ブロック済みメールドメインの一覧を表示します | Mod以上 | — |
