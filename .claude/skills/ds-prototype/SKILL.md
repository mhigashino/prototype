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

## 参照リンク

- Figma DS-Master: https://www.figma.com/design/lrDLgQNy8Py3RwR9cQllT9/
- Figma Design Tokens: https://www.figma.com/design/CuiPudjknxh3udQR3OlSdp/
- MerUI Storybook: https://pages-jp.mercari.in/merui-web/main/react/index.html
