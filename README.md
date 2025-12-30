# PROJECT: wit-ai-strategy-room

## 概要
- 目的：AI戦略会議室（指示書作成／コードレビュー／共有ログ運用）
- 形態：Google Apps Script（Webアプリ）＋ GitHub（コード正本）＋ Drive/Sheet（ログ）

## 重要リンク（あとで埋める）
- GitHub（正本）：https://github.com/wit-ai-apps/wit-ai-strategy-room
- GAS編集URL：
- 配布URL（必ず ?b=BUILD_ID）：
- ログ用スプレッドシート：
- Driveフォルダ（画像/添付）：
- GitHub Token（保存場所メモ）：※トークン自体は書かない

## UI凍結ルール（最重要）
- UI（見た目）は完全固定（変更禁止）
  - HTML構造 / 文言 / 配置 / サイズ / 色 / 余白 / クラス名
- 変更してよいのは「内部処理（ロジック）」のみ
- UI差分が出たら **差し戻し優先**
- 例外を作る場合：なべさんの明示許可がある時だけ

## 依頼文の固定フレーズ（Rex/Gemini/ユイ共通）
依頼の先頭に必ず書く：
> UI凍結で、中身だけ。UI差分が出たら差し戻し。

## 版管理ルール（固定）
- VERSION：vX.Y.Z
- BUILD_ID：YYYY-MM-DD_HHMM_<tag>
- 配布URL：必ず `?b=BUILD_ID`（検証のみ `&debug=1`）

## 運用メモ（短く）
- GASは毎回「新しいデプロイ」
- 配布前は通常タブで開いて確認（PWA/ホーム追加は後）
