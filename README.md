# iOS App Prototype

iOSアプリのWebプロトタイプです。単一の `index.html` で全画面を管理しています。

## 起動方法

サーバーは不要です。`index.html` をブラウザで開くだけで動作します。

```bash
git clone https://github.com/mhigashino/prototype.git
open index.html
```

または GitHub Pages のURL（ `https://mhigashino.github.io/prototype/` ）にアクセスしてください。

### パスワード認証

ページを開くとパスワード入力が求められます。

- デフォルトパスワード: `mirai`
- セキュリティのため、`index.html` の冒頭にある `PASS` の値を変更することを推奨します。
- パスワードの変更は Claude Code に「パスワードを〇〇に変更して」と伝えることでも対応できます。

```js
var PASS = 'mirai'; // ← ここを変更
```

## 環境・表示について

### 自動リロード

タブを切り替えて戻ったとき（`visibilitychange`）に自動でリロードされる設定になっています。GitHub Pages にプッシュ後、タブを再表示するだけで最新版が反映されます。

### Safari PWA（推奨）

iPhoneのSafariで開き、「ホーム画面に追加」するとPWAとして起動できます。OSのアドレスバーやタブバーが非表示になり、よりネイティブアプリに近い見た目で確認できます。

1. SafariでGitHub PagesのURLを開く
2. 共有ボタン → 「ホーム画面に追加」
3. ホーム画面のアイコンから起動

## Claude Code スキル

このリポジトリには `.claude/skills/ds-prototype/` にプロジェクト固有のスキルが含まれています。

- `ds-prototype` — Mercari DS4 のデザイントークン・コンポーネントルールをまとめたスキルです。
- リポジトリをcloneすると `SKILL.md` も一緒にコピーされます。
- プロジェクトローカルのスキルはグローバルに設定されたスキルより優先して適用されるため、このリポジトリ内では `ds-prototype` が自動的に参照されます。

## ファイル構成

```
index.html               # メインファイル（全画面・CSS・JSを含む）
assets/
  images/                # 商品画像・アイコン等
CLAUDE.md                # Claude Code向け開発ルール
.claude/
  skills/
    ds-prototype/
      SKILL.md           # DS4デザインシステムスキル定義
```

## 注意事項

### 画像素材について

`assets/images/` 内の商品画像はメルカリで出品された商品の画像を使用しています。

- 社内でのプロトタイプ確認・検討目的での利用は問題ありません
- 社外への公開・共有は基本NGです（GitHub Pages のURLの取り扱いにご注意ください）

### このプロトタイプについて

- あくまでデザイン検討用のプロトタイプとして擬似的に構築されたサイトです
- メルカリアプリ・メルカリWebのソースコードは使用していません
- UIのインタラクション（画面遷移・アニメーション等）はすべて Claude Code で生成したものです

## 開発ルール

- CSS・JSはすべて `index.html` 内にインラインで記述
- デザインシステムは Mercari DS4 のトークン・コンポーネント仕様に準拠
- 追加・更新する画像は 1MB以下 にすること（超える場合は `sips` で圧縮）
- 変更後は必ず commit & push する
