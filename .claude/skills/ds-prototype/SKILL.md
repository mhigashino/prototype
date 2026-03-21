---
name: ds-prototype
description: Mercari Design System 統合リファレンス（DS3.0 Figmaトークン × DS4.0 MerUI Web実装）。prototypeリポジトリのHTML/CSSプロトタイプ実装に使用する。
---

# Mercari Design System — prototype実装リファレンス

Figma「Design Tokens」「DS-Master」と MerUI Web (DS4.0) を統合したリファレンス。
prototypeリポジトリ（HTML + CSS変数）での実装を前提とする。

---

## トークンアーキテクチャ

```
Figma Global Tokens（原色スケール）
  └─ Figma Alias Tokens（セマンティック: Background_Accent_Default）
       └─ CSS Custom Properties（--color-bg-accent）
            └─ PandaCSS Semantic Tokens（background.accent.primary.default）
```

---

## 1. カラー — CSS変数マッピング（Light mode）

### Background

| Figma Alias Token | CSS変数 | Light値 | PandaCSS Token |
|---|---|---|---|
| Background_Primary | `--color-bg-primary` | `#FFFFFF` | `background.basic.primary` |
| Background_Secondary | `--color-bg-secondary` | `#F0F0F0` | `background.basic.secondary` |
| Background_Tertiary | `--color-bg-tertiary` | `#E0E0E0` | `background.basic.tertiary` |
| Background_Disabled | `--color-bg-disabled` | `#E0E0E0` | `background.basic.disabled` |
| Background_Accent_Default | `--color-bg-accent` | `#006ED1` | `background.accent.primary.default` |
| Background_Accent_Light | `--color-bg-accent-light` | `#EFF7FF` | `background.accent.primary.disabled` |
| Background_Bold_Default | `--color-bg-bold` | `#222222` | `background.basic.inverse` |
| Background_Bold_Light | `--color-bg-bold-light` | `#F0F0F0` | — |
| Background_Attention_Default | `--color-bg-attention` | `#FF333F` | `background.attention.primary.default` |
| Background_Attention_Light | `--color-bg-attention-light` | `#FEF5F7` | `background.attention.primary.disabled` |
| Background_Success_Default | `--color-bg-success` | `#3BAF2D` | `background.success.primary.default` |
| Background_Success_Light | `--color-bg-success-light` | `#E3FFEA` | — |
| Background_Notice_Default | `--color-bg-notice` | `#FFB818` | `background.notice.primary.default` |
| Background_Notice_Light | `--color-bg-notice-light` | `#FFF5D0` | — |
| Background_Expectation_Default | `--color-bg-expectation` | `#FC6500` | `background.expectation.primary.default` |
| Background_Expectation_Light | `--color-bg-expectation-light` | `#FFF2E9` | — |
| Background_Brand_Default | `--color-bg-brand` | `#FF333F` | `background.brand.primary.default` |
| Background_Brand_Light | `--color-bg-brand-light` | `#FEF5F7` | — |

### Foreground（Text / Icon）

| Figma Alias Token | CSS変数 | Light値 | PandaCSS Token |
|---|---|---|---|
| Foreground_Primary | `--color-fg-primary` | `#222222` | `color.basic.primary` |
| Foreground_Secondary | `--color-fg-secondary` | `#4C4C4C` | `color.basic.secondary` |
| Foreground_Tertiary | `--color-fg-tertiary` | `#949494` | `color.basic.tertiary` |
| Foreground_Disabled | `--color-fg-disabled` | `#C7C7C7` | `color.basic.disabled` |
| Foreground_Accent | `--color-fg-accent` | `#006ED1` | `color.accent.primary` |
| Foreground_Bold | `--color-fg-bold` | `#FFFFFF` | `color.basic.inverse` |
| Foreground_Attention | `--color-fg-attention` | `#FF333F` | `color.attention.primary` |
| Foreground_AttentionBold | `--color-fg-attention-bold` | `#FFFFFF` | — |
| Foreground_Success | `--color-fg-success` | `#1F6C27` | `color.success.primary` |
| Foreground_Notice | `--color-fg-notice` | `#805A00` | `color.notice.primary` |
| Foreground_Expectation | `--color-fg-expectation` | `#A34100` | `color.expectation.primary` |
| Foreground_Brand | `--color-fg-brand` | `#FF333F` | `color.brand.primary` |

### Border

| Figma Alias Token | CSS変数 | Light値 | PandaCSS Token |
|---|---|---|---|
| Border_Primary | `--color-border-primary` | `#E0E0E0` | `border.basic.primary.default` |
| Border_Secondary | `--color-border-secondary` | `#F0F0F0` | `border.basic.secondary.default` |
| Border_Accent | `--color-border-accent` | `#006ED1` | `border.accent.primary.default` |
| Border_Attention | `--color-border-attention` | `#FF333F` | `border.attention.primary.default` |
| Border_Success | `--color-border-success` | `#3BAF2D` | `border.success.primary.default` |

---

## 2. CSS変数 — 完全定義（prototype用）

```css
:root {
  /* === Background === */
  --color-bg-primary: #FFFFFF;
  --color-bg-secondary: #F0F0F0;
  --color-bg-tertiary: #E0E0E0;
  --color-bg-disabled: #E0E0E0;
  --color-bg-accent: #006ED1;
  --color-bg-accent-light: #EFF7FF;
  --color-bg-bold: #222222;
  --color-bg-bold-light: #F0F0F0;
  --color-bg-attention: #FF333F;
  --color-bg-attention-light: #FEF5F7;
  --color-bg-success: #3BAF2D;
  --color-bg-success-light: #E3FFEA;
  --color-bg-notice: #FFB818;
  --color-bg-notice-light: #FFF5D0;
  --color-bg-expectation: #FC6500;
  --color-bg-expectation-light: #FFF2E9;
  --color-bg-brand: #FF333F;
  --color-bg-brand-light: #FEF5F7;

  /* === Foreground (Text / Icon) === */
  --color-fg-primary: #222222;
  --color-fg-secondary: #4C4C4C;
  --color-fg-tertiary: #949494;
  --color-fg-disabled: #C7C7C7;
  --color-fg-accent: #006ED1;
  --color-fg-bold: #FFFFFF;
  --color-fg-attention: #FF333F;
  --color-fg-attention-bold: #FFFFFF;
  --color-fg-success: #1F6C27;
  --color-fg-notice: #805A00;
  --color-fg-expectation: #A34100;
  --color-fg-brand: #FF333F;

  /* === Border === */
  --color-border-primary: #E0E0E0;
  --color-border-secondary: #F0F0F0;
  --color-border-accent: #006ED1;
  --color-border-attention: #FF333F;
  --color-border-success: #3BAF2D;

  /* === Overlay === */
  --color-overlay-dark-80: rgba(34, 34, 34, 0.80);
  --color-overlay-dark-60: rgba(34, 34, 34, 0.60);
  --color-overlay-dark-40: rgba(34, 34, 34, 0.40);
  --color-overlay-dark-20: rgba(34, 34, 34, 0.20);
  --color-overlay-mid-20: rgba(102, 102, 102, 0.20);
  --color-overlay-mid-10: rgba(102, 102, 102, 0.10);
  --color-overlay-light-80: rgba(240, 240, 240, 0.80);
  --color-overlay-white-80: rgba(255, 255, 255, 0.80);
  --color-overlay-white-20: rgba(255, 255, 255, 0.20);

  /* === Shadow === */
  --shadow-layer2: 0 2px 4px rgba(0, 0, 0, 0.2);   /* BottomNav, Header */
  --shadow-layer3: 0 4px 8px rgba(0, 0, 0, 0.2);   /* Modal, BottomSheet */
  --shadow-layer4: 0 8px 10px rgba(0, 0, 0, 0.2);  /* Dialog, Tooltip */
  --shadow-bottom: 0 0 16px rgba(0, 0, 0, 0.2);    /* FloatingButton */

  /* === Border Radius === */
  --radius-full: 9999px;    /* ピル型、タグ、バッジ */
  --radius-large: 16px;     /* 大きいカード、モーダル */
  --radius-medium: 8px;     /* 標準（基本はこれ） */
  --radius-small: 4px;      /* 24px以下のコンポーネント */
  --radius-none: 0px;

  /* === Border Width === */
  --border-bold: 3px;
  --border-medium: 2px;
  --border-thin: 1px;

  /* === Spacing === */
  --spacing-0: 0px;
  --spacing-2: 2px;
  --spacing-4: 4px;
  --spacing-6: 6px;
  --spacing-8: 8px;
  --spacing-12: 12px;
  --spacing-16: 16px;
  --spacing-20: 20px;
  --spacing-24: 24px;
  --spacing-28: 28px;
  --spacing-32: 32px;
  --spacing-36: 36px;
  --spacing-40: 40px;
  --spacing-44: 44px;
  --spacing-48: 48px;
  --spacing-56: 56px;
  --spacing-64: 64px;
  --spacing-80: 80px;
  --spacing-96: 96px;
  --spacing-128: 128px;

  /* === Opacity === */
  --opacity-100: 1.0;
  --opacity-80: 0.8;
  --opacity-60: 0.6;
  --opacity-40: 0.4;
  --opacity-30: 0.3;
  --opacity-20: 0.2;
  --opacity-10: 0.1;
  --opacity-5: 0.05;
  --opacity-0: 0;

  /* === Motion: Duration === */
  --duration-0: 0ms;
  --duration-50: 50ms;
  --duration-150: 150ms;
  --duration-200: 200ms;
  --duration-250: 250ms;
  --duration-300: 300ms;
  --duration-500: 500ms;
  --duration-750: 750ms;
  --duration-1000: 1000ms;

  /* === Motion: Easing === */
  --ease-strong-out: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-strong-in: cubic-bezier(0.84, 0, 0.78, 0);
  --ease-strong-inout: cubic-bezier(0.83, 0, 0.17, 1);
  --ease-middle-out: cubic-bezier(0.33, 1, 0.68, 1);
  --ease-middle-in: cubic-bezier(0.32, 0, 0.67, 0);
  --ease-middle-inout: cubic-bezier(0.65, 0, 0.35, 1);
  --ease-weak-out: cubic-bezier(0.61, 1, 0.88, 1);
  --ease-weak-in: cubic-bezier(0.12, 0, 0.39, 0);
  --ease-weak-inout: cubic-bezier(0.37, 0, 0.63, 1);
}
```

---

## 3. タイポグラフィ

### フォントファミリー（Web）
```css
font-family: "Hiragino Kaku Gothic ProN", "Hiragino Sans", "Helvetica Neue", Arial, sans-serif;
```

### グローバルスケール

| グローバルサイズ | font-size | font-weight(Bold) | font-weight(Regular) | line-height(Normal) |
|---|---|---|---|---|
| X4Large | 28px | 800 | 300 | 1.4 |
| X3Large | 24px | 600 | 300 | 1.4 |
| X2Large | 20px | 600 | 300 | 1.4 |
| XLarge  | 18px | 600 | 300 | 1.4 |
| Large   | 17px | 600 | 300 | 1.4 |
| WebInput | 16px | — | 300 | 1.4 |
| Medium  | 15px | 600 | 300 | 1.4 |
| Small   | 14px | 600 | 300 | 1.4 |
| XSmall  | 12px | 600 | 300 | 1.4 |
| X2Small | 11px | 600 | 300 | 1.4 |
| X3Small | 10px | 600 | 300 | 1.4 |

### セマンティックロール → CSS実装例

| ロール | バリアント | CSS |
|---|---|---|
| Heading H1 | — | `font-size: 24px; font-weight: 600;` |
| Heading H2 | — | `font-size: 20px; font-weight: 600;` |
| Title | Large | `font-size: 17px; font-weight: 600;` |
| Title | Medium | `font-size: 15px; font-weight: 600;` |
| Title | Small | `font-size: 14px; font-weight: 600;` |
| Body | Medium | `font-size: 15px; font-weight: 300; line-height: 1.4;` |
| Body | Small | `font-size: 14px; font-weight: 300; line-height: 1.4;` |
| Caption | Small | `font-size: 12px; font-weight: 300;` |
| Caption | XSmall | `font-size: 11px; font-weight: 300;` |
| Label | Medium | `font-size: 15px; font-weight: 600;` |
| Label | Small | `font-size: 14px; font-weight: 600;` |
| Button | Large | `font-size: 17px; font-weight: 600; line-height: 1.1;` |
| Button | Medium | `font-size: 15px; font-weight: 600; line-height: 1.0;` |
| Price | Large | `font-size: 17px; font-weight: 600; font-variant-numeric: tabular-nums;` |
| Price | Medium | `font-size: 15px; font-weight: 600; font-variant-numeric: tabular-nums;` |

---

## 4. エレベーション（レイヤー）システム

| Layer | Shadow変数 | border | 主なコンポーネント |
|---|---|---|---|
| Canvas | なし | なし | コンテンツ本体 |
| Layer 1 | なし | なし | FixedPanel |
| Layer 2 | `--shadow-layer2` | `--color-border-primary` | BottomNavigation, HeaderBar |
| Layer 3 | `--shadow-layer3` | `--color-border-primary` | Modal, BottomSheet, SideSheet |
| Layer 4 | `--shadow-layer4` | `--color-border-primary` | Dialog, Tooltip, Popup |

---

## 5. コンポーネントリファレンス

### ボタン系（MerUI: Button, IconButton, ToggleButton）

| バリアント | 背景 | テキスト | ボーダー |
|---|---|---|---|
| Primary | `--color-bg-brand` | `--color-fg-bold` | なし |
| Secondary | `--color-bg-accent-light` | `--color-fg-accent` | `--color-border-accent` |
| Tertiary | `--color-bg-primary` | `--color-fg-primary` | `--color-border-primary` |
| Ghost | transparent | `--color-fg-accent` | なし |
| Disabled | `--color-bg-disabled` | `--color-fg-disabled` | なし |

サイズ（height × padding）:
- Large: `48px` / padding `--spacing-16`
- Medium: `40px` / padding `--spacing-12`
- Small: `32px` / padding `--spacing-8`

### インプット系（MerUI: TextInput, SearchInput）

```css
/* TextField 基本スタイル */
background: var(--color-bg-primary);
border: var(--border-thin) solid var(--color-border-primary);
border-radius: var(--radius-medium);
padding: var(--spacing-12) var(--spacing-16);
font-size: 15px; /* Medium */
color: var(--color-fg-primary);

/* フォーカス時 */
border-color: var(--color-border-accent);
outline: none;

/* エラー時 */
border-color: var(--color-border-attention);
```

### チップ系（MerUI: FilterChip, SuggestionChip, RemovableChip）

```css
/* FilterChip */
border-radius: var(--radius-full);
padding: var(--spacing-4) var(--spacing-12);
border: var(--border-thin) solid var(--color-border-primary);
font-size: 14px;

/* 選択時 */
background: var(--color-bg-accent-light);
border-color: var(--color-border-accent);
color: var(--color-fg-accent);
```

### ナビゲーション系（MerUI: BottomNavigation, HeaderBar）

```css
/* BottomNavigation */
height: 56px; /* + safe-area-inset-bottom */
background: var(--color-bg-primary);
border-top: var(--border-thin) solid var(--color-border-primary);
box-shadow: var(--shadow-layer2);

/* HeaderBar */
height: 56px;
background: var(--color-bg-primary);
border-bottom: var(--border-thin) solid var(--color-border-primary);
box-shadow: var(--shadow-layer2);
```

### モーダル・オーバーレイ系（MerUI: Dialog, Modal, BottomSheet）

```css
/* Overlay背景 */
background: var(--color-overlay-dark-60);

/* BottomSheet */
border-radius: var(--radius-large) var(--radius-large) 0 0;
background: var(--color-bg-primary);
box-shadow: var(--shadow-layer3);

/* Dialog */
border-radius: var(--radius-large);
background: var(--color-bg-primary);
box-shadow: var(--shadow-layer4);
padding: var(--spacing-24);
```

### フィードバック系（MerUI: Snackbar, Badge, Tag）

```css
/* Snackbar */
background: var(--color-bg-bold);
color: var(--color-fg-bold);
border-radius: var(--radius-medium);
padding: var(--spacing-12) var(--spacing-16);
box-shadow: var(--shadow-layer3);

/* Badge（数字） */
background: var(--color-bg-attention);
color: var(--color-fg-bold);
border-radius: var(--radius-full);
min-width: 16px; height: 16px;
font-size: 11px; font-weight: 600;

/* Tag */
border-radius: var(--radius-full);
padding: var(--spacing-2) var(--spacing-8);
font-size: 12px;
```

---

## 6. MerUI Webコンポーネント一覧（参照用）

### ボタン・インタラクション
`Button` `ButtonGroup` `IconButton` `ToggleButton` `ToggleSwitch`
`ActionButton` `OverlayToggleButton` `WrapperButton` `WrapperLink`

### インプット
`TextInput` `PasswordInput` `TextArea` `CheckBox` `CheckBoxGroup`
`RadioButton` `RadioButtonGroup` `Select` `SearchInput` `PriceInput`

### テキスト・タイポグラフィ
`HeadingText` `BodyText` `ButtonText` `CaptionText` `LabelText` `TitleText`
`PriceText` `LinkText` `TextLink`

### ナビゲーション
`HeaderBar` `BottomNavigation` `NavigationBar` `TopNavigation` `BreadcrumbNav`

### レイアウト
`Flex` `Grid` `Box` `Panel` `Main` `FixedPanel`
`ObjectLayout` `TitleLayout` `TwoColumnLayout`

### データ表示
`Table` `Avatar` `Thumbnail` `ItemTile` `Image` `Price` `PriceLabel`
`Tag` `ItemThumbnail` `Separator`

### モーダル・オーバーレイ
`Dialog` `Modal` `SideSheet` `LoadingModal` `Popup` `InformationPopup`
`ToolTip` `Snackbar` `BalloonTip` `BottomSheet`（ActionSheet相当）

### フィードバック・ステータス
`Badge` `ProgressBar` `LoadingSpinner` `Skeleton`
`ErrorHint` `Hint` `Rating` `ShowMore`

### 行・リスト
`BaseRow` `ClickableRow` `SelectableRow` `DrillDownRow` `AccordionRow`

### チップ
`FilterChip` `RemovableChip` `SuggestionChip`

### カルーセル
`SingleItemCarousel` `MultiItemCarousel`

---

## 7. 実装ルール（IMPORTANT）

1. **必ずCSS変数を使用** — 生の16進数カラーコード・px値を直接書かない
2. **エイリアストークン優先** — グローバルカラー（`#006ED1`）ではなく意味を持つ変数（`--color-bg-accent`）を使う
3. **スペーシングは`--spacing-*`変数のみ** — 基本は8の倍数、小コンポーネントは4の倍数
4. **角丸は基本 `--radius-medium` (8px)** — 24px以下のコンポーネントは `--radius-small` (4px)
5. **アニメーションはモーション変数を使用** — `transition: all var(--duration-200) var(--ease-middle-out)`
6. **エレベーション順守** — z-indexと shadow は Layer定義に従う

---

## 8. ブランドテーマ（MerUI対応）

| テーマ | 用途 | ブランドカラー |
|---|---|---|
| default | メルカリ標準 | Attention500 `#FF333F` |
| gop | メルカリShops | 別途定義 |
| holistic | — | 別途定義 |

---

## 9. アイコン・ロゴ リファレンス

出典: `assets/icons/` に格納されたローカルSVGファイル（kouzoh/merui-web の `packages/icons/src/svg/` から取得）

```
assets/icons/
  fill/      # Fill スタイル（119個）
  outline/   # Outline スタイル（185個）
```

### 使用ルール
- **全アイコンはローカルに揃っている。Figmaへのアクセスは不要。**
- ファイルパス: `assets/icons/fill/{IconName}.svg` または `assets/icons/outline/{IconName}.svg`
- アイコンが必要になったら Read ツールで該当SVGファイルを読み込み、中身をインラインで貼り付けること
- SVGはインライン展開して使うこと（`<img>` タグ不可。`currentColor` で色制御するため）
- カラーは `currentColor` を使い、親要素の `color` で制御する
- サイズは `width` / `height` 属性または CSS で指定する（デフォルト 24×24px）

### SVG の使い方

```
1. Read ツールで assets/icons/fill/Coins.svg を読む
2. ファイルの中身をそのままインラインで貼り付ける
3. Figmaや外部ソースは使わない
```

---

### アイコン一覧 — Standard/Relative（Fill と Outline の両方あり）

Icon Name で呼び出す。全てに `Outline` / `Fill` の 2 スタイルが存在する。

| Icon Name | 用途 |
|---|---|
| Guide | ガイド・案内 |
| Attention | 警告・エラー（感嘆符） |
| Delete | 削除・閉じる（×） |
| Like | いいね・ハート |
| Home | ホーム |
| User | ユーザー・プロフィール |
| Notification | お知らせ・ベル |
| Camera | カメラ |
| Garbage | ゴミ箱・削除 |
| Search | 検索・虫眼鏡 |
| Comment | コメント・吹き出し |
| HappyFace / SadFace / NeutralFace / SmileFace / DownFace | 評価・感情 |
| GridView | グリッドレイアウト |
| Done | 完了・チェックマーク |
| Point | ポイント |
| Bitcoin | 暗号通貨 |
| SimpleQRCode | QRコード |
| Work | 仕事・ブリーフケース |
| SaveToLibrary | ライブラリに保存 |
| BrandTag | ブランドタグ |
| Flag | フラグ・通報 |
| Lock | ロック・鍵 |
| Microphone | マイク |
| Announcement | アナウンス・メガフォン |
| Coin | コイン |
| Flash / FlashOff / FlashAuto | フラッシュ |
| ChatbotSupport | チャットボット |
| Send | 送信 |
| Backspace | バックスペース |
| Present | プレゼント・ギフト |
| Reaction | リアクション |
| Location | 位置・ピン |
| Eco | エコ |
| Bundle | まとめ売り |
| Save | 保存（ブックマーク） |
| ThumbDown / ThumbUp | 評価（サムズ） |
| Pin | ピン留め |
| FollowList | フォローリスト |
| Wallet | ウォレット |
| Coins | コイン複数 |
| CoinWithArrow | コイン送受信 |
| Users | 複数ユーザー |
| Phone | 電話 |
| CameraFlip | カメラ切り替え |
| Calendar | カレンダー |
| EditPencil | 編集（鉛筆） |
| Add | 追加（＋） |
| ZoomIn / ZoomOut | ズーム |
| Time | 時計 |
| WaterDrop | 水滴 |
| Apparel | アパレル・服 |
| ChatBubble | チャットバブル |
| Cart | カート |
| EditDraft | 下書き編集 |
| Mail | メール |
| Article | 記事 |
| Supermarket | スーパーマーケット |
| Setting | 設定・歯車 |
| MultilingualSupport | 多言語サポート |
| SoundOn / SoundOff | サウンド |
| LightBubble | ヒント・電球 |
| Coupon | クーポン・チケット |
| Discover | ディスカバー |
| Fashion | ファッション |
| Baby | ベビー |
| Games | ゲーム |
| Hobby | ホビー |
| Book | 本 |
| MobilePhone | スマートフォン |
| Sports | スポーツ |
| Beauty | ビューティー |
| Health | 健康 |
| Beverage | 飲み物 |
| Furniture | 家具 |
| Pet | ペット |
| Handmade | ハンドメイド |
| Car | 車 |
| Gardening | ガーデニング |
| HomeAppliances | 家電 |
| DIY | DIY・工具 |
| Kitchen | キッチン |
| CD | CD・DVD・音楽 |
| Outdoor | アウトドア |
| Ticket | チケット |
| Electronics | 電子機器 |
| AuctionHammer | オークションハンマー |
| Badge | バッジ |
| Hello | ウェルカム |
| OfficialShopBadge | 公式ショップ |
| Tips | ヒント・コツ |
| Info | 情報（ℹ） |
| Anshin | あんしん |
| AI | AI |

### アイコン一覧 — Standard/Fill（Fill のみ）

| Icon Name | 用途 |
|---|---|
| Star | 評価・星 |
| StarHalf | 半星 |
| Track | 追跡 |
| OverseasPurchase | 海外購入 |
| LoyaltyProgram | ロイヤルティプログラム |
| ServiceLogo | サービスロゴ |
| Fire | 人気・HOT |
| Blur / Unblur | ぼかし |
| LightOff / LightOn | ライト |
| Beginner | 初心者 |
| SellerAchievementBadge | セラー実績バッジ |
| Airplane | 飛行機 |
| Shield | シールド・保護 |
| ExcellentShop | 優良ショップ |
| VerifiedBrand | 認証ブランド |
| Play | 再生 |

### アイコン一覧 — Standard/Outline（Outline のみ）

| Icon Name | 用途 |
|---|---|
| Loop | ループ・再読み込み |
| PurchasedItems | 購入済み |
| Visibility / VisibilityOff | 表示・非表示 |
| ChevronRight / ChevronLeft / ChevronUp / ChevronDown | 矢印（山形） |
| OffsetChevronRight / OffsetChevronLeft | オフセット矢印 |
| ArrowRight / ArrowLeft / ArrowUp / ArrowDown / ArrowUpDown | 矢印 |
| Box | ボックス |
| LeftDouble / RightDouble | 二重矢印 |
| Facebook / SnsLine | SNS |
| EditVert / EditHoriz | 縦横編集 |
| Close | 閉じる（×） |
| Todo | やること |
| CheckBold | チェック（太） |
| PhotoAlbum | フォトアルバム |
| Filter | フィルター |
| Block | ブロック |
| Plus | プラス |
| ExternalLink | 外部リンク |
| ImageLoadingFailed | 画像読み込みエラー |
| EditImage | 画像編集 |
| CustomerSupport | カスタマーサポート |
| Refund | 返金 |
| ID | ID確認 |
| Share (iOS, Web) / Share (Android) | シェア |
| CodeScan | コードスキャン |
| QRCode | QRコード |
| MercariShops | メルカリShops |
| Bullet | 箇条書き |
| DownloadPage | ダウンロード |
| OperationalCertification | 運営認証 |
| RefundYen | 返金（円） |
| Cleaning | クリーニング |
| Preorder | 予約 |
| CreditCard | クレジットカード |
| DataStats | データ統計 |
| BulkPurchase | まとめ買い |
| BrowsingHistory | 閲覧履歴 |
| Store | ストア |
| CloseSmall | 閉じる（小） |
| Minus | マイナス |
| ThumbnailInfo | サムネイル情報 |
| ListView | リスト表示 |
| GridSquare | グリッド表示 |
| ImageSearch | 画像検索 |
| SimilarSearch | 類似検索 |
| Outreach | アウトリーチ |
| Focus | フォーカス |
| CodeScanning | コードスキャン |
| Copy | コピー |
| Swap | 入れ替え |
| Menu | メニュー（ハンバーガー） |
| International | 国際 |
| Bank | 銀行 |
| A4Envelope | 封筒（A4） |
| Calculator | 計算機 |
| ImageFilter | 画像フィルター |
| ConvenienceStore | コンビニ |
| ImgSearchEdit | 画像検索編集 |
| Crop | クロップ |
| BookOpen | 開いた本 |
| Meal / Bar / Cafe / FastFood | 飲食 |
| DepartmentStore | デパート |
| Karaoke | カラオケ |
| Entertainment | エンターテインメント |
| Cut | カット |
| School / Medical | 学校・医療 |
| OnePiece | ワンピース |
| SellingTool | 出品ツール |

---

### アイコンの参照方法

アイコンを使う際は `assets/icons/` 内の該当SVGファイルを Read ツールで読み込み、中身をインラインで貼り付けること。

```
# Fill スタイル
assets/icons/fill/Home.svg
assets/icons/fill/Search.svg
assets/icons/fill/Like.svg
... など

# Outline スタイル
assets/icons/outline/Home.svg
assets/icons/outline/Search.svg
assets/icons/outline/Notification.svg
... など
```

SVGファイルの中身は `currentColor` ベースなので、親要素の `color` で色を制御できる。

#### ナビゲーション矢印系

```html
<!-- ChevronRight / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M9 18l6-6-6-6"/>
</svg>

<!-- ChevronLeft / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M15 18l-6-6 6-6"/>
</svg>

<!-- ChevronDown / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M6 9l6 6 6-6"/>
</svg>

<!-- ChevronUp / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M18 15l-6-6-6 6"/>
</svg>

<!-- ArrowRight / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <line x1="5" y1="12" x2="19" y2="12"/>
  <polyline points="12,5 19,12 12,19"/>
</svg>

<!-- Close / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <line x1="18" y1="6" x2="6" y2="18"/>
  <line x1="6" y1="6" x2="18" y2="18"/>
</svg>
```

#### アクション系

```html
<!-- Add (Plus) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <line x1="12" y1="5" x2="12" y2="19"/>
  <line x1="5" y1="12" x2="19" y2="12"/>
</svg>

<!-- Done (Check) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <polyline points="20,6 9,17 4,12"/>
</svg>

<!-- Delete / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <polyline points="3,6 5,6 21,6"/>
  <path d="M19 6l-1 14a2 2 0 01-2 2H8a2 2 0 01-2-2L5 6"/>
  <path d="M10 11v6M14 11v6"/>
  <path d="M9 6V4a1 1 0 011-1h4a1 1 0 011 1v2"/>
</svg>

<!-- Garbage / Outline（Deleteと同形） -->

<!-- EditPencil / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M11 4H4a2 2 0 00-2 2v14a2 2 0 002 2h14a2 2 0 002-2v-7"/>
  <path d="M18.5 2.5a2.121 2.121 0 013 3L12 15l-4 1 1-4 9.5-9.5z"/>
</svg>

<!-- Setting (Gear) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <circle cx="12" cy="12" r="3"/>
  <path d="M19.4 15a1.65 1.65 0 00.33 1.82l.06.06a2 2 0 010 2.83 2 2 0 01-2.83 0l-.06-.06a1.65 1.65 0 00-1.82-.33 1.65 1.65 0 00-1 1.51V21a2 2 0 01-4 0v-.09A1.65 1.65 0 009 19.4a1.65 1.65 0 00-1.82.33l-.06.06a2 2 0 01-2.83-2.83l.06-.06A1.65 1.65 0 004.68 15a1.65 1.65 0 00-1.51-1H3a2 2 0 010-4h.09A1.65 1.65 0 004.6 9a1.65 1.65 0 00-.33-1.82l-.06-.06a2 2 0 012.83-2.83l.06.06A1.65 1.65 0 009 4.68a1.65 1.65 0 001-1.51V3a2 2 0 014 0v.09a1.65 1.65 0 001 1.51 1.65 1.65 0 001.82-.33l.06-.06a2 2 0 012.83 2.83l-.06.06A1.65 1.65 0 0019.4 9a1.65 1.65 0 001.51 1H21a2 2 0 010 4h-.09a1.65 1.65 0 00-1.51 1z"/>
</svg>

<!-- Share (iOS, Web) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M4 12v8a2 2 0 002 2h12a2 2 0 002-2v-8"/>
  <polyline points="16,6 12,2 8,6"/>
  <line x1="12" y1="2" x2="12" y2="15"/>
</svg>

<!-- Save (Bookmark) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M19 21l-7-5-7 5V5a2 2 0 012-2h10a2 2 0 012 2z"/>
</svg>

<!-- Save (Bookmark) / Fill -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
  <path d="M19 21l-7-5-7 5V5a2 2 0 012-2h10a2 2 0 012 2z"/>
</svg>
```

#### 情報・ステータス系

```html
<!-- Attention (Warning) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M10.29 3.86L1.82 18a2 2 0 001.71 3h16.94a2 2 0 001.71-3L13.71 3.86a2 2 0 00-3.42 0z"/>
  <line x1="12" y1="9" x2="12" y2="13"/>
  <line x1="12" y1="17" x2="12.01" y2="17"/>
</svg>

<!-- Info / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <circle cx="12" cy="12" r="10"/>
  <line x1="12" y1="8" x2="12" y2="12"/>
  <line x1="12" y1="16" x2="12.01" y2="16"/>
</svg>

<!-- LightBubble / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <line x1="9" y1="18" x2="15" y2="18"/>
  <line x1="10" y1="22" x2="14" y2="22"/>
  <path d="M12 2a7 7 0 017 7c0 3.5-2 6-5 7v2H10v-2c-3-1-5-3.5-5-7a7 7 0 017-7z"/>
</svg>

<!-- Time (Clock) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <circle cx="12" cy="12" r="10"/>
  <polyline points="12,6 12,12 16,14"/>
</svg>

<!-- Flag / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M4 15s1-1 4-1 5 2 8 2 4-1 4-1V3s-1 1-4 1-5-2-8-2-4 1-4 1z"/>
  <line x1="4" y1="22" x2="4" y2="15"/>
</svg>
```

#### 取引・決済系

```html
<!-- Cart / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <circle cx="9" cy="21" r="1"/>
  <circle cx="20" cy="21" r="1"/>
  <path d="M1 1h4l2.68 13.39a2 2 0 002 1.61h9.72a2 2 0 002-1.61L23 6H6"/>
</svg>

<!-- Wallet / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M20 12V7a2 2 0 00-2-2H4a2 2 0 00-2 2v10a2 2 0 002 2h14a2 2 0 002-2v-5h-5a2 2 0 010-4h5z"/>
  <circle cx="17" cy="14" r="1" fill="currentColor" stroke="none"/>
</svg>

<!-- Coin / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <circle cx="12" cy="12" r="10"/>
  <circle cx="12" cy="12" r="6"/>
</svg>

<!-- Coupon (Ticket) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M2 9V6a1 1 0 011-1h18a1 1 0 011 1v3a2 2 0 000 4v3a1 1 0 01-1 1H3a1 1 0 01-1-1v-3a2 2 0 000-4z"/>
  <line x1="9" y1="5" x2="9" y2="19" stroke-dasharray="2 2"/>
</svg>

<!-- Point / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <circle cx="12" cy="12" r="10"/>
  <path d="M9 9h1.5a2.5 2.5 0 010 5H9v4"/>
  <line x1="9" y1="9" x2="9" y2="13"/>
</svg>
```

#### コミュニケーション系

```html
<!-- Comment (ChatBubble) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/>
</svg>

<!-- Mail / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
  <polyline points="22,6 12,13 2,6"/>
</svg>

<!-- Announcement (Megaphone) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <polygon points="11,5 6,9 2,9 2,15 6,15 11,19"/>
  <path d="M19.07 4.93a10 10 0 010 14.14"/>
  <path d="M15.54 8.46a5 5 0 010 7.07"/>
</svg>

<!-- Send / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <line x1="22" y1="2" x2="11" y2="13"/>
  <polygon points="22,2 15,22 11,13 2,9"/>
</svg>
```

#### UI コントロール系

```html
<!-- Lock / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <rect x="3" y="11" width="18" height="11" rx="2" ry="2"/>
  <path d="M7 11V7a5 5 0 0110 0v4"/>
</svg>

<!-- Calendar / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <rect x="3" y="4" width="18" height="18" rx="2" ry="2"/>
  <line x1="16" y1="2" x2="16" y2="6"/>
  <line x1="8" y1="2" x2="8" y2="6"/>
  <line x1="3" y1="10" x2="21" y2="10"/>
</svg>

<!-- Location (Pin) / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/>
  <circle cx="12" cy="10" r="3"/>
</svg>

<!-- Phone / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 10.8 19.79 19.79 0 01.88 2.18 2 2 0 012.86 0h3a2 2 0 012 1.72 12.84 12.84 0 00.7 2.81 2 2 0 01-.45 2.11L7.09 7.91a16 16 0 006 6l1.27-1.27a2 2 0 012.11-.45 12.84 12.84 0 002.81.7A2 2 0 0122 16.92z"/>
</svg>

<!-- Microphone / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M12 1a3 3 0 00-3 3v8a3 3 0 006 0V4a3 3 0 00-3-3z"/>
  <path d="M19 10v2a7 7 0 01-14 0v-2"/>
  <line x1="12" y1="19" x2="12" y2="23"/>
  <line x1="8" y1="23" x2="16" y2="23"/>
</svg>

<!-- GridView / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <rect x="3" y="3" width="7" height="7"/>
  <rect x="14" y="3" width="7" height="7"/>
  <rect x="3" y="14" width="7" height="7"/>
  <rect x="14" y="14" width="7" height="7"/>
</svg>

<!-- AuctionHammer / Outline -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
  <path d="M14.5 2.5l3 3-10 10-3-3z"/>
  <path d="M18 9l3 3"/>
  <path d="M3 18l6-6"/>
  <line x1="2" y1="22" x2="10" y2="22"/>
</svg>
```

---

### ロゴ一覧

Figma `ImageAssets/Logo` セクションのロゴ名。

#### サービスロゴ（`ImageAssets/Logo/Service/`）
`buyee` `ems` `yamato` `smari` `7eleven` `Pudo` `FamilyMart` `JPPost` `Mercari` `Cainiao` `Lawson` `YamatoPickUp` `PostBox` `Okihasso`

#### ブランドロゴ（`ImageAssets/Logo/`）
`mercari`（フルロゴ） `mercariMono`（モノクロ） `mercariWordmark`（ワードマーク） `mercariSymbolMono`（シンボル単体） `mercard` `shops` `d_point` `d_account` `google` `facebook` `Apple` `Android` `Instagram` `X` `Tiktok` `Youtube` `note` `amazon` `LoyaltyProgram` `Line` `Hallo` `FIDO`

#### 決済ロゴ（`ImageAssets/Logo/Payment/`）
`Visa` `mastercard` `JCB` `AmericanExpress` `DinersClub` `Discover` `Paypal` `Merpay` `Mercard` `Card` `ID` `Amazon` `Bank`

#### 銀行ロゴ（`ImageAssets/Logo/Bank/`）
`SMBC` `Resona`

---

## 参照リンク

- Figma DS-Master (Icon/Logo フレーム): https://www.figma.com/design/lrDLgQNy8Py3RwR9cQllT9/-v4.0--DS-Master?node-id=2135-53794
- Figma Design Tokens: https://www.figma.com/design/CuiPudjknxh3udQR3OlSdp/
- MerUI Storybook: https://pages-jp.mercari.in/merui-web/main/react/index.html
