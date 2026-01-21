# [SERIAL:2026-01-21_135900_airoom-upload-btndead] AI会議室｜Rexへ「アップ指示」テンプレ（ボタン不動のまま）

**TO:** Rex  
**FROM:** なべさん  
**SOURCE:** Yui（整理）  
**DATE:** 2026-01-21 13:59:00 JST

---

## 0) 目的（最重要）

GASへ反映しても“ボタンが不動”のまま。原因切り分け→修正→GitHubへアップ（Push）までを一気通貫でお願いします。

---

## 1) 「アップ」の定義（ここを厳守）

### GitHub repo
`wit-ai-apps/wit-ai-strategy-room`

### 作業ブランチ
`fix/button-dead-compat`（※別ブランチにするなら“ブランチ名を明記”）

### アップ対象ファイル（最低限）
- `Code.gs`
- `index.html`

### アップ完了の納品物（必須）
1. **Compare URL**（base→作業ブランチ）
2. **最新コミットSHA**
3. **変更点の短い箇条書き**（3〜7行）

---

## 2) 追加ルール（リンク切れ防止）

このチャット添付（Download）に依存しないため、指示書・修正報告もGitHubに置く。

### リポジトリに以下を追加してコミット：
- `handoff/2026-01-21/AI会議室_アップ指示_ボタン不動.md`
- `handoff/2026-01-21/修正レポート_vXX.md`

### 納品時に GitHub上のファイルURL（閲覧できるリンク） も添付

---

## 3) 技術メモ（ボタン不動の典型原因）

GAS（IFRAME）環境で `onclick`属性が効かない／JSが落ちて止まっている可能性が高い。

### まず「JSが動いてるか」を確実に見える化：
- `&debug=1` のとき、画面上に **JS起動OK** / **BUILD** / **最後に捕まえたclick** を表示
- クリックイベントを `capture=true` で拾って、拾えてるかを記録（拾えてるのに動かない＝ハンドラ側、拾えない＝上に何か被ってる/無効化されてる）

### 修正後、なべさん側は：
ChromeでGASへPull→新しいデプロイ→URLに `?b=...&debug=1` で検証する

---

## 4) なべさんへの「最初の1アクション」も書いて返して

例：
1. ChromeでGASを開く → GitHub AssistantでPull
2. デプロイ→新しいデプロイ
3. `.../exec?b=XXXX&debug=1` を開いてスクショ1枚

---

## 5) 期待される動作（debug=1時）

### 画面上部バナーに以下が表示される：
- `JS起動OK | v17.0.7-upload-btndead | BUILD=2026-01-21_1406_airoom-upload-btndead | 最後のclick: BUTTON#xxx | debug=1`

### コンソールに以下が表示される：
- `[AI会議室] JS起動OK | VERSION: v17.0.7-upload-btndead BUILD: 2026-01-21_1406_airoom-upload-btndead`
- `[クリックキャプチャ] 捕まえたclick: BUTTON#xxx`（クリック時に表示）

---

以上、お願いします。
