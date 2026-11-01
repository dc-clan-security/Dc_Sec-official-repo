<div align="center">

# 🛡️ Dc_Sec

**Discord 多機能セキュリティBot** — サーバーを荒らしから守り、コミュニティを育てる

![Discord](https://img.shields.io/badge/Discord-Bot-5865F2?logo=discord&logoColor=white)
![discord.py](https://img.shields.io/badge/framework-discord.py-0078D4)
![commands](https://img.shields.io/badge/slash%20commands-269-green)
![status](https://img.shields.io/badge/status-稼働中-brightgreen)
[![Discord](https://img.shields.io/badge/サポートサーバー-dc--clan-5865F2?logo=discord&logoColor=white)](https://discord.gg/dc-clan)

</div>

---

## Dc_Sec とは

**Dc_Sec** は、サーバーの安全を守るセキュリティ機能と、メンバーが楽しむコミュニティ機能を1つにまとめた Discord Bot です。

- 🛡️ **セキュリティ**: スパム・レイド・Nuke（サーバー破壊）・荒らし投稿を自動検知して対処
- 💾 **バックアップ**: サーバー構成を丸ごと JSON で保存・復元。Nuke 被害からの自動復元にも対応
- 🔨 **モデレーション**: 警告・タイムアウト・キック・BAN をケース番号付きで記録
- 💰 **経済 (Dcelia)**: 通貨・ショップ・ロール自販機・カジノ11種・トリビア
- 🏘️ **コミュニティ**: ウェルカム・レベル制・ギブアウェイ・チケット・グローバルチャット・お題・誕生日・結婚 など
- 🧰 **ツール**: AI チャット・翻訳・音楽プレイヤー・天気・地震速報・短縮リンク・捨てメアド など

## 📊 数字で見る Dc_Sec

| 項目 | 数 |
|---|---|
| スラッシュコマンド | **269個**（グループ56 + 単発） |
| `d!` プレフィックスコマンド | 66個以上（音楽・経済・カジノ・モデレート等） |
| カジノゲーム | 11種 |
| お題バンク | 8カテゴリ 144問 |
| トリビア | 260問 |
| 防御レイヤー | スパム/レイド/Nuke/コンテンツフィルター/ハニーポット/L7防御/攻撃IP自動ブロック |

## 📖 ドキュメント

| ドキュメント | 内容 |
|---|---|
| [🚀 はじめに](docs/getting-started.md) | 導入手順・初期設定・権限システムの仕組み |
| [📖 コマンドリファレンス](docs/commands/README.md) | 全269コマンドを種類別に解説 |
| [❓ よくある質問](docs/faq.md) | FAQ・トラブルシューティング |

コマンドの種類別ページ: [セキュリティ](docs/commands/security.md) ・ [モデレーション](docs/commands/moderation.md) ・ [バックアップ](docs/commands/backup.md) ・ [経済](docs/commands/economy.md) ・ [カジノ](docs/commands/casino.md) ・ [コミュニティ](docs/commands/community.md) ・ [交流・エンタメ](docs/commands/fun.md) ・ [ツール・通知](docs/commands/tools.md) ・ [AI](docs/commands/ai.md) ・ [音楽](docs/commands/music.md) ・ [Bot管理](docs/commands/admin.md)

## 📜 規約

- **[利用規約 (Terms of Service)](TERMS.md)** — Dc_Sec を利用する前に必ずお読みください。Bot をサーバーに招待した時点で規約に同意したものとみなされます
- **[プライバシーポリシー](PRIVACY_POLICY.md)** — 収集するデータの種類・利用目的・保存先・削除方法

## 🚀 導入方法

1. 下の招待リンクから Bot をサーバーに追加（**管理者権限を推奨**。バックアップ復元・Nuke 対処に広範な権限が必要です）
2. Bot のロールを**できるだけ上位**に配置（Bot より上位のロールのメンバーは処罰・復元の対象にできません）
3. `/log channel` でログチャンネルを設定 → `/modrole add` でモデレーターロールを登録
4. 詳細は **[🚀 はじめに](docs/getting-started.md)** を参照

> 🔗 **[Bot をサーバーに招待する](https://discord.com/oauth2/authorize?client_id=1563356132498481232&scope=bot%20applications.commands&permissions=8)**（管理者権限を付与して追加してください）

## 📮 サポート

- **サポートサーバー**: [discord.gg/dc-clan](https://discord.gg/dc-clan) — ご質問・不具合報告・データ削除依頼はこちらが最速です
- バグ報告・機能提案: [Issue](../../issues) からお願いします（[テンプレート](.github/ISSUE_TEMPLATE/) もご利用ください）

## ℹ️ 本リポジトリについて

本リポジトリは Dc_Sec の**公式ドキュメント**（利用規約・プライバシーポリシー・コマンドリファレンス）を管理するものです。
Bot 本体のソースコードは非公開です。Dc_Sec は運営者 **VEK**（Discord ユーザー名: `dcgen_9o0l`）がホスティングしており、ユーザーは招待するだけで利用できます。

---

© 2026 VEK / Dc_Sec Project
