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
