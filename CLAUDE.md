# prototype

## このプロジェクトについて
iOSアプリのWebプロトタイプ。単一HTMLファイルで全画面を管理。

## 編集ルール
- `index.html` がメインファイル
- CSS・JSはすべて `index.html` 内にインラインで記述
- デザインシステムは `/ds-prototype` スキルを参照し、定義されたCSS変数・トークン・コンポーネントルールに従うこと

## 画像ルール
- このリポジトリに追加・更新する画像は1MB以下にすること
- 1MBを超える画像は `sips -s format jpeg -s formatOptions 75 -Z 1200` で圧縮してから使用すること

## コミット・プッシュ
- すべての変更後に commit & push すること

## 実装済み挙動仕様

### タブ別ナビゲーション状態の保持
- タブを切り替える際、現在のナビゲーションスタック（`_navStack`）と商品詳細（IDP）の状態を `_tabStates` に保存する
- 元のタブに戻ったとき、保存されていた状態を復元してIDPを再表示する
- ホームタブをダブルタップ（同じタブを再タップ）すると、保存状態をクリアしてホーム画面のルートに戻る
- サーチタブは別途 `_idpStackBeforeSearch` で管理するため、この仕組みの対象外

### IDP（商品詳細）の状態変数
- `_currentItemId` — 現在表示中の商品ID
- `_currentItemIsAuction` — オークションIDPかどうか（出品タブからの遷移時 `true`）
- `_currentItemIsListing` — 出品画面からの遷移かどうか（出品タブのリスト画面からの遷移時 `true`）

### 出品画面からの商品詳細
- 出品画面（`screen-list`）から商品詳細を開いた場合、`_currentItemIsListing = true` となる
- このとき購入ボタンのラベルは「商品を編集する」に変わり、ボタンスタイルは secondary（白背景・赤テキスト・赤ボーダー1px）になる

### コメント欄のユーザー表示
- IDPのコメント欄に表示されるユーザーは、商品ID（数値）をシードとした疑似乱数で決定する
- アバター画像は `assets/images/profile-icon.png` 〜 `profile-icon-9.png` の10種からランダム選択
- ユーザー名は `_USER_NAMES` 配列（15種の日本語名）からランダム選択
- 同じ商品IDなら常に同じユーザーが表示される（再現性あり）

### プロフィール画像
- マイページ（自分）以外のユーザーアバターはすべて `assets/images/profile-icon*.png` を使用する

### 商品画像
- 商品画像は `assets/items/` フォルダの実商品画像（`m{id}_1.{ext}` 形式）を使用する
- UI素材・背景画像は `assets/images/` に置く
- 使用されていない画像ファイルは削除して管理する

### チェックアウトシートのレイヤー・状態管理
- `closeCheckout()` は `checkout-confirm` の open 状態も同時にリセットする（再オープン時に確認画面が残るバグを防ぐ）
- `.checkout-sheet-header` / `.checkout-confirm-header` は `position: absolute` でスクロールbodyに重なり、グラデーション（`to bottom`）でコンテンツのフェードを実現する
- z-index 構造: `checkout-sheet-header`（2）← `checkout-confirm`（3）で確認画面がヘッダーを覆う
