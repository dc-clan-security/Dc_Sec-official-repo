# 🤖 AI機能

[← コマンド一覧に戻る](README.md)

Groq API による AI チャット・翻訳と、Gemini による過疎診断パネルを提供します。AI の API キーは `/ai setkey` で登録します（管理者が共有キーを設定するか、ユーザーが自分のキーを登録）。

## `/ai`

**AIとのチャット (Groq / 設定)**

`ask` は会話コンテキストを記憶するチャット（`reset` で初期化）、`translate` は AI 翻訳です。Bot をメンションしたり AI の発言に返信すると短く応答し、`setting`・`chsetting` で相槌・割り込みの頻度とチャンネルごとの ON/OFF を調整できます。`models` で利用可能なモデルを一覧表示します。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/ai ask` | AIに質問・会話をします (Groq) | 一般 | `message` (必須) |
| `/ai setkey` | Groq APIキーを登録します (管理者・オーナー) | Mod以上 | `api_key` (必須) |
| `/ai keys` | 登録済みAPIキーの状態を確認します | Mod以上 | — |
| `/ai reset` | 自分の会話履歴をリセットします | 一般 | — |
| `/ai models` | 現在のAIモデルとフォールバック一覧を表示します | Mod以上 | — |
| `/ai setting` | AIチャット(メンション応答・割り込み)のオン/オフと頻度を設定・確認します | Mod以上 | `enabled` (任意)<br>`frequency` (任意) |
| `/ai chsetting` | 指定チャンネルでAIが自発的に発言(相槌・割り込み)するかを設定します | Mod以上 | `spontaneous` (任意)<br>`channel` (任意) |
| `/ai translate` | AI (Groq) でテキストを翻訳します | Mod以上 | `text` (必須)<br>`target` (任意) |

## `/kaso`

**過疎診断 (Gemini AI)**

過疎気味のサーバーを Gemini が診断し、活性化のための提案パネルを生成します。

| コマンド | 説明 | 実行権限 | 引数 |
|---|---|---|---|
| `/kaso now` | 今すぐ過疎診断を実行します (Gemini AI) | Mod以上 | — |
| `/kaso panel` | 過疎診断パネルを設置します (誰でもボタンで診断可能) | Mod以上 | `channel` (任意) |
