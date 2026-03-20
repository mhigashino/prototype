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

- **デフォルトパスワード**: `mirai`
- セキュリティのため、`index.html` の冒頭にある `PASS` の値を変更することを推奨します。

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

## ファイル構成

```
index.html          # メインファイル（全画面・CSS・JSを含む）
assets/
  images/           # 商品画像・アイコン等
CLAUDE.md           # Claude Code向け開発ルール
```

## 開発ルール

- CSS・JSはすべて `index.html` 内にインラインで記述
- デザインシステムは Mercari DS4 のトークン・コンポーネント仕様に準拠
- 追加・更新する画像は **1MB以下** にすること（超える場合は `sips` で圧縮）
- 変更後は必ず commit & push する
