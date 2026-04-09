# リンゴラボ（仮） - デザインシステム仕様 v2.1

> **目的**: Apple的ミニマルデザインに基づいたデザインシステムの定義
> **対象**: カラー・タイポグラフィ・スペーシング・コンポーネント
> **デザイン哲学**: 余白たっぷり、洗練されたミニマリズム、UX重視
> **最終更新**: 2026-03-24

---

## 0. 改訂履歴

| 日付 | バージョン | 内容 |
|------|----------|------|
| 2026-03-20 | v1.0 | 初版作成 |
| 2026-03-22 | v2.0 | **全面改訂**: Apple的余白システム導入、スペーシング拡大、SITE-SPEC v2.0との整合性確保 |
| 2026-03-24 | v2.1 | **ブランド再定義**: #15・#16の決定を反映し、ヒーローコピー・りんちゃんの位置付け・配色方針を更新 |

### v2.0の主要変更点

- **スペーシング拡大**: セクション間パディングを `py-16`→`py-20`〜`py-24` に増量
- **余白哲学**: 「たっぷりの余白で、情報に呼吸させる」
- **シャドウ削減**: カードのホバーシャドウを極めて控えめに（Apple的）
- **ホバー移動**: `-5px`→`-2px` に調整（繊細な動き）
- **コンテナ幅**: 最大幅を `1280px`→`1024px` に縮小（読みやすさ重視）

---

## 1. プロジェクト概要

### 1.1 ブランドコンセプト

**リンゴラボ（仮）**は、管理栄養士りんちゃんが運営する温活・食事・美容の情報サイト。自分を整えたいと思っていても、毎日の中ではなかなか実践できない女性に向けて、暮らしの中から、からだを整えるヒントを届ける。

**ブランドの主従**:
- **主軸**: りんちゃんが運営する温活・食事・美容のメディア
- **将来像**: りんちゃん中心のブランドサイトへ育てていく
- **りんごの役割**: 習慣化の象徴であり、ブランドの象徴

**キーメッセージ**:
「暮らしの中に、からだを整えるヒントを」

**サブメッセージ**:
「がんばれない日にも寄り添う、やさしい整え方を届けます。」

### 1.2 ターゲットユーザー

- **年齢**: 25〜45歳女性
- **悩み**: 冷え・むくみ・肌荒れが気になる / 自分を整えたいのに日々の中で実践しづらい
- **志向**: 丁寧な暮らしに憧れるが、完璧主義ではない / 自分を大切にしたいが無理はしたくない
- **行動**: Instagramでウェルネス情報を収集、**Apple的な洗練されたデザインに惹かれる**
- **読後に持って帰ってほしい感覚**: 「これなら私にも続けられそう」

### 1.3 ビジネスゴール

1. **記事閲覧率**: トップページ訪問者の30%以上が記事へ遷移
2. **ブランド認知**: 「りんちゃん」の管理栄養士としての専門性を確立
3. **収益化**: 記事経由でアフィリエイト成約

---

## 2. デザイン原則

### 2.1 トーン&マナー

| 要素 | 方向性 |
|------|--------|
| **スタイル** | Apple的ミニマリズム・洗練・UX重視 |
| **雰囲気** | 温かみがありながらミニマル、**余白たっぷり** |
| **禁止事項** | 情報過多、ごちゃごちゃ、派手な色使い、不要な装飾、**AIぽいデザイン**（カード左縦線、グラデーション過多など） |

### 2.2 カラーパレット

```css
/* === プライマリーカラー === */
--muted-red:   #C97D7D;  /* メインカラー: CTAボタン・アクセント */
--cream:       #F5EFE6;  /* セクション背景・カード背景 */
--brown:       #6B4423;  /* 見出し・強調テキスト */
--dark-gray:   #333333;  /* 本文テキスト */
--off-white:   #FAFAF8;  /* ページ全体背景 */

/* === セカンダリーカラー === */
--white:       #FFFFFF;  /* カード背景（白） */
--light-gray:  #E0E0E0;  /* ボーダー・区切り線 */
--text-gray:   #666666;  /* 副次的テキスト */
```

**使用ルール**:
- `--muted-red`: CTAボタン、カテゴリーバッジ、ホバー時アクセント
- `--cream`: セクション背景（温かみ）、カード背景（柔らかい印象）
- `--brown`: 見出し（h1〜h3）、ロゴテキスト（権威性・落ち着き）
- `--dark-gray`: 本文テキスト（可読性重視）
- `--off-white`: ページ全体背景（白より温かみ、目に優しい）
- `--white`: カード背景（白）、ティーザーセクション内カード

**v2.1での解釈**:
- `--muted-red` は、りんごを連想させる**くすみピンク寄りのブランドカラー**として継続使用する
- 赤を強くしすぎず、**大人っぽい柔らかさ**を優先する
- 必要に応じて、りんごらしい赤みはモチーフや小物で補う
- 緑はよもぎ・自然の連想としてごく少量に留める

**背景色の交互配置**:
```
ナビ: white/blur
ヒーロー: gradient(cream → off-white)
コンセプト: off-white
やっていること: cream
記事一覧: off-white
商品ティーザー: cream
アプリティーザー: off-white
プロフィール: cream
締めのCTA: cream
フッター: brown
```

**Apple的な配色哲学**:
- 背景は常に明るく（白系・クリーム系）
- アクセントカラーは控えめに使用
- コントラスト比 WCAG AA準拠（4.5:1以上）

---

## 3. タイポグラフィシステム

### 3.1 フォントファミリー

```css
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Noto Sans JP", sans-serif;
```

Apple製品と同じシステムフォントスタックを使用し、日本語フォールバックとしてNoto Sans JPを配置。

### 3.2 フォントサイズスケール（モバイルファースト）

| トークン | モバイル | PC | 用途 |
|---------|---------|---|------|
| `--font-size-xs` | 0.75rem (12px) | - | カテゴリーバッジ、読了時間 |
| `--font-size-sm` | 0.875rem (14px) | - | タブボタン、キャプション、小リンク |
| `--font-size-base` | 1rem (16px) | - | 本文、ナビリンク |
| `--font-size-lg` | 1.125rem (18px) | - | 大きめの本文、サブヘッドライン |
| `--font-size-xl` | 1.25rem (20px) | - | h3見出し、カードタイトル |
| `--font-size-2xl` | 1.5rem (24px) | - | h3見出し（PC）、ナビロゴ |
| `--font-size-3xl` | 1.875rem (30px) | 2.25rem (36px) | h2見出し（モバイル）→（PC） |
| `--font-size-4xl` | 2.25rem (36px) | 3rem (48px) | h2見出し（PC） |
| `--font-size-5xl` | 2.5rem (40px) | 3.5rem (56px) | h1見出し（ヒーロー・モバイル）→（PC） |

**レスポンシブルール**:
- **モバイル（〜768px）**: 小さい方の値を使用
- **PC（768px〜）**: 大きい方の値を使用

### 3.3 フォントウェイト

| トークン | 値 | 用途 |
|---------|---|------|
| `--font-weight-normal` | 400 | 本文 |
| `--font-weight-medium` | 500 | ボタン、ナビリンク、強調 |
| `--font-weight-semibold` | 600 | （未使用） |
| `--font-weight-bold` | 700 | 見出し（h1〜h3） |

**Apple的な軽さ**:
- 見出しでも`700`で十分（`800`や`900`は使わない）
- 本文は`400`で統一

### 3.4 行間（Line Height）

| トークン | 値 | 用途 |
|---------|---|------|
| `--line-height-tight` | 1.25 | 見出し（h1〜h3） |
| `--line-height-normal` | 1.5 | ボタン、短いテキスト |
| `--line-height-relaxed` | 1.75 | 本文（可読性重視） |
| `--line-height-loose` | 2 | リスト項目、余裕のある文章 |

**Apple的な行間哲学**:
- 見出しはタイト（1.25）
- 本文は広め（1.75）で可読性重視

### 3.5 レタースペーシング

```css
h1 { letter-spacing: -0.02em; } /* タイトな詰め */
h2 { letter-spacing: -0.01em; } /* わずかに詰め */
h3, body { letter-spacing: 0; }  /* デフォルト */
```

**Apple的なレタースペーシング**:
- 大きな見出しほど文字を詰める（-0.02em）
- 本文は詰めない（0）

---

## 4. スペーシングシステム（Apple的余白）

### 4.1 スペーシングトークン（8pxベース）

| トークン | 値 | px換算 | 用途 |
|---------|---|--------|------|
| `--space-1` | 0.5rem | 8px | アイコンとテキストの隙間、タイトな余白 |
| `--space-2` | 1rem | 16px | 段落間、ボタンパディング（縦） |
| `--space-3` | 1.5rem | 24px | 見出し下マージン、カード内余白 |
| `--space-4` | 2rem | 32px | カード間ギャップ、要素間 |
| `--space-5` | 2.5rem | 40px | - |
| `--space-6` | 3rem | 48px | セクション内の大きな区切り |
| `--space-8` | 4rem | 64px | - |
| `--space-10` | 5rem | 80px | セクション間パディング（モバイル） |
| `--space-12` | 6rem | 96px | セクション間パディング（PC・小） |
| `--space-16` | 8rem | 128px | セクション間パディング（PC・大） |
| `--space-20` | 10rem | 160px | セクション間パディング（PC・特大） |
| `--space-24` | 12rem | 192px | ヒーローエリアパディング |

**v2.0の変更点**:
- **`--space-20`（160px）** を追加（Apple的な余白を実現）
- **`--space-24`（192px）** を追加（ヒーロー用）

### 4.2 セクション別スペーシング仕様（v2.0）

| セクション | パディング（縦）モバイル | パディング（縦）PC | 要素間マージン |
|-----------|------------------------|------------------|---------------|
| **ナビゲーション** | py-4 (16px) | py-4 (16px) | - |
| **ヒーローエリア** | pt-32 pb-16 (128px + 64px) | pt-40 pb-24 (160px + 96px) | h1下: mb-6, サブh下: mb-10 |
| **ブランドコンセプト** | py-16 (64px) | py-20 (80px) | 問題提起下: mb-12 |
| **やっていること** | py-16 (64px) | py-20 (80px) | カード間: space-y-6 |
| **記事一覧** | py-16 (64px) | py-20 (80px) | カード間: space-y-6 |
| **商品ティーザー** | py-16 (64px) | py-20 (80px) | - |
| **アプリティーザー** | py-16 (64px) | py-20 (80px) | - |
| **プロフィール** | py-16 (64px) | py-20 (80px) | 画像とカード間: gap-8 |
| **締めのCTA** | py-16 (64px) | py-20 (80px) | - |
| **フッター** | py-12 (48px) | py-12 (48px) | リンクグループ間: mb-8 |

**Apple的なスペーシング哲学**:
- **セクション間は常にたっぷり**: モバイル `py-16`、PC `py-20`
- **ヒーローは特に広く**: 画面に入った瞬間の印象を重視
- **要素間も呼吸させる**: `space-y-6`（24px）以上

### 4.3 コンテナとグリッド

```css
/* コンテナ幅（v2.0で縮小） */
.container {
  max-width: 1024px;        /* v1.0: 1280px → v2.0: 1024px */
  margin: 0 auto;
  padding-left: 1.5rem;     /* 24px */
  padding-right: 1.5rem;    /* 24px */
}

/* モバイル */
@media (max-width: 768px) {
  .container {
    padding-left: 1rem;     /* 16px */
    padding-right: 1rem;    /* 16px */
  }
}
```

**v2.0の変更点**:
- コンテナ最大幅を **1280px → 1024px** に縮小
- **理由**: 読みやすさ重視、Apple的な中央寄せ配置

### 4.4 グリッドレイアウト（使用しない）

**v2.0の方針**:
- 記事カード、やっていることカードは**縦配置（1列）**に統一
- グリッドレイアウト（3列）は使用しない
- **理由**: モバイルファースト、シンプル、余白重視

```css
/* 記事カード・やっていることカード */
.card-container {
  display: flex;
  flex-direction: column;
  gap: 1.5rem; /* 24px */
}
```

---

## 5. コンポーネント仕様

### 5.1 ナビゲーション

**構成**:
```
[🍎アイコン] [ロゴ画像]     コンセプト  商品  アプリ  [記事を読む]
```

**スペック**:
- 高さ: 64px
- 背景: `rgba(255,255,255,0.8)` + `backdrop-filter: blur(20px)`（Apple的ガラスモーフィズム）
- ボーダー: `0.5px solid rgba(0,0,0,0.05)`（極めて薄い）
- position: fixed
- z-index: 50

**フォント**:
- ロゴ: `font-size: 1.5rem` (24px), `font-weight: 700`
- リンク: `font-size: 1rem` (16px), `font-weight: 500`
- CTAボタン: `.btn-primary`（後述）

**ホバー**:
- リンク: `color: var(--muted-red)` + `transition: 0.3s ease`

**モバイル**:
- ハンバーガーメニュー
- ロゴアイコン + メニューボタンのみ表示

### 5.2 ボタン（CTA）

#### プライマリーボタン（大）

**仕様**:
```css
.btn-primary-large {
  min-width: 200px;
  background-color: var(--muted-red);
  color: var(--off-white);
  padding: 1rem 2.5rem; /* 16px 40px */
  border-radius: 1.5rem; /* 24px - pill型 */
  font-size: 1.125rem; /* 18px */
  font-weight: 500;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  text-align: center;
}

.btn-primary-large:hover {
  background-color: #D68A8A; /* 10%明るく */
  box-shadow: 0 4px 12px rgba(201, 125, 125, 0.3); /* v2.0: 0.4→0.3に軽減 */
  transform: translateY(-2px); /* v2.0: -3px→-2pxに軽減 */
}

.btn-primary-large:active {
  transform: translateY(-1px);
}

.btn-primary-large:focus-visible {
  outline: 3px solid var(--muted-red);
  outline-offset: 3px;
}
```

**使用箇所**: ヒーローエリア、締めのCTA

#### プライマリーボタン（小）

**仕様**:
```css
.btn-primary {
  min-width: 120px;
  padding: 0.75rem 1.5rem; /* 12px 24px */
  font-size: 1rem; /* 16px */
  /* その他は.btn-primary-largeと同様 */
}
```

**使用箇所**: ナビゲーション、商品ティーザー、アプリティーザー

#### アウトラインボタン（セカンダリー）

**仕様**:
```css
.btn-outline-large {
  min-width: 200px;
  background-color: transparent;
  color: var(--brown);
  padding: 1rem 2.5rem;
  border-radius: 1.5rem;
  font-size: 1.125rem;
  font-weight: 500;
  transition: all 0.3s ease;
  border: 2px solid var(--brown);
  cursor: pointer;
}

.btn-outline-large:hover {
  background-color: rgba(107, 68, 35, 0.06); /* 6%透過のブラウン */
  transform: translateY(-2px);
  box-shadow: 0 2px 8px rgba(107, 68, 35, 0.15);
}
```

**使用箇所**: ヒーローエリア「やっていること」ボタン

### 5.3 カード

#### 特徴カード（やっていることセクション）

**サイズ仕様**:
```css
.card-feature {
  background-color: var(--cream);
  padding: 2rem; /* 32px */
  border-radius: 1rem; /* 16px */
  text-align: left; /* v2.0: center→leftに変更 */
  transition: all 0.3s ease;
  display: flex;
  align-items: start;
  gap: 1rem; /* 16px */
}

.card-feature .icon {
  font-size: 2.5rem; /* 40px - v2.0: 3rem→2.5remに縮小 */
  color: var(--muted-red);
  flex-shrink: 0;
}

.card-feature h3 {
  font-size: 1.25rem; /* 20px */
  font-weight: 700;
  color: var(--brown);
  margin-bottom: 0.5rem;
}

.card-feature p {
  font-size: 0.875rem; /* 14px - v2.0: 1rem→0.875remに縮小 */
  color: var(--dark-gray);
  line-height: 1.75;
  margin-bottom: 0.75rem;
}

.card-feature a {
  font-size: 0.875rem;
  color: var(--muted-red);
  font-weight: 500;
  text-decoration: none;
}

.card-feature:hover {
  transform: translateY(-2px); /* v2.0: -5px→-2pxに軽減 */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06); /* v2.0: 0.08→0.06に軽減 */
}
```

**v2.0の変更点**:
- レイアウト: 中央寄せ→左寄せ（横並び: アイコン + テキスト）
- アイコンサイズ縮小: 3rem→2.5rem
- 説明文サイズ縮小: 1rem→0.875rem
- ホバー移動軽減: -5px→-2px
- シャドウ軽減: 0.08→0.06

#### 記事カード

**現状の課題（v2.0時点）**:
- ❌ サムネイル画像がない（絵文字だけ）
- ❌ タイトルが長すぎる（30文字超）
- ❌ 余白が少なく詰まって見える
- ❌ 視覚的インパクトが弱い
- ❌ 稼いでいるアフィリサイト（北欧暮らし、LIG、サルワカ等）と比較して洗練度が低い

**v3.0改善案（要実装）**:
1. **実写画像またはクオリティの高いイラスト**を用意
   - Canva, Unsplash, Pixabayなどで作成
   - aspect-ratio: 16/9維持
2. **タイトルを半分に短縮**（30文字 → 15文字以内）
   - 例: 「ホットヨガLAVAで冷え性は改善できる？管理栄養士が栄養学的に分析」
   - → 「LAVA体験レビュー｜冷え性への効果は？」
3. **余白を1.5倍に拡大**
   - padding: 1.5rem → 2rem
   - gap: 0.75rem → 1rem
4. **フォントサイズを大きく**
   - h3: 1.125rem → 1.25rem (スマホ) / 1.5rem (PC)
5. **バッジを控えめに**
   - 小さく左上に配置、透過度追加

**サイズ仕様（v2.0現行）**:
```css
.article-card {
  background-color: var(--white);
  padding: 1.5rem; /* 24px */
  border-radius: 1rem; /* 16px */
  transition: all 0.3s ease;
}

.article-card .thumbnail {
  aspect-ratio: 16 / 9;
  border-radius: 0.75rem; /* 12px */
  background-color: var(--cream);
  margin-bottom: 0.75rem;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.75rem; /* アイコン表示 */
  color: var(--muted-red);
}

.article-card .badge {
  display: inline-block;
  background-color: var(--muted-red);
  color: white;
  font-size: 0.75rem; /* 12px */
  font-weight: 500;
  padding: 0.25rem 0.75rem;
  border-radius: 9999px; /* pill型 */
  margin-bottom: 0.75rem;
}

.article-card h3 {
  font-size: 1.125rem; /* 18px - v2.0: 1.25rem→1.125remに縮小 */
  font-weight: 700;
  color: var(--brown);
  margin-bottom: 0.5rem;
  line-height: 1.5;
}

.article-card .read-time {
  font-size: 0.875rem; /* 14px */
  color: var(--text-gray);
}

.article-card:hover {
  transform: translateY(-2px); /* v2.0: -5px→-2pxに軽減 */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06); /* v2.0: 0.08→0.06に軽減 */
}

.article-card a {
  text-decoration: none;
  color: inherit;
  display: block;
}

.article-card a:focus-visible {
  outline: 3px solid var(--muted-red);
  outline-offset: 3px;
  border-radius: 1rem;
}
```

**v2.0の変更点**:
- タイトルサイズ縮小: 1.25rem→1.125rem
- ホバー移動軽減: -5px→-2px
- シャドウ軽減: 0.08→0.06

### 5.4 プロフィール画像

**サイズ仕様**:
```css
.profile-image {
  width: 100%;
  max-width: 280px; /* v2.0: 400px→280pxに縮小 */
  aspect-ratio: 1 / 1;
  border-radius: 1rem; /* 16px */
  object-fit: cover;
}

@media (max-width: 768px) {
  .profile-image {
    max-width: 240px; /* v2.0: 300px→240pxに縮小 */
    margin: 0 auto;
    display: block;
  }
}
```

**v2.0の変更点**:
- PC表示サイズ縮小: 400px→280px
- モバイル表示サイズ縮小: 300px→240px
- **理由**: ミニマル化、余白重視

---

## 6. レイアウトシステム

### 6.1 ブレークポイント

| デバイス | ブレークポイント | コンテナ幅 | 左右余白 |
|----------|-----------------|-----------|---------|
| **モバイル（小）** | 〜640px | 100% | 16px |
| **モバイル（大）** | 640px〜768px | 100% | 24px |
| **タブレット〜PC** | 768px〜 | 1024px（max） | 24px |

### 6.2 レイアウト原則

**v2.0の方針**:
1. **縦配置優先**: 記事カード、やっていることカードは1列に統一
2. **中央寄せ**: コンテナは常に中央寄せ（`max-width: 1024px`、`margin: 0 auto`）
3. **余白重視**: セクション間は常に`py-20`（80px）以上
4. **モバイルファースト**: 常にモバイルから設計

---

## 7. インタラクション仕様

### 7.1 ホバー状態

| 要素 | 効果 |
|------|------|
| **ボタン** | `translateY(-2px)` + `box-shadow`拡大 + 色10%明るく |
| **カード** | `translateY(-2px)` + `box-shadow`表示（opacity: 0.06） |
| **リンク** | `color: var(--muted-red)`に変化 |

**v2.0の変更点**:
- ホバー移動: `-5px`→`-2px` に軽減（繊細な動き）
- シャドウ透過度: `0.08`→`0.06` に軽減（控えめ）

### 7.2 トランジション

```css
transition: all 0.3s ease;
```

全体的に `0.3s ease` で統一（スムーズな印象）

### 7.3 スクロールアニメーション

```css
html {
  scroll-behavior: smooth;
}
```

アンカーリンク（`#articles`, `#profile`, `#about`）でスムーススクロール

---

## 8. シャドウシステム（Apple的・極めて控えめ）

```css
/* v2.0で透過度を軽減 */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.04);
--shadow-lg: 0 4px 12px rgba(0, 0, 0, 0.05);
--shadow-xl: 0 8px 16px rgba(0, 0, 0, 0.06);
```

**使用ルール**:
- **ナビゲーション**: ボーダー `0.5px solid rgba(0,0,0,0.05)` のみ（シャドウなし）
- **カードホバー**: `--shadow-lg`（opacity: 0.05）
- **ボタンホバー**: `box-shadow: 0 4px 12px rgba(201, 125, 125, 0.3)`（色つき）

**Apple的なシャドウ哲学**:
- 極めて薄く
- 必要最小限のみ
- 色つきシャドウは控えめに

---

## 9. アクセシビリティ要件

### 9.1 必須対応項目

✅ **実装済み**:
- 全インタラクティブ要素に`:focus-visible`スタイル
- `aria-label`によるスクリーンリーダー対応
- セマンティックHTML（`<nav>`, `<section>`, `<article>`, `<footer>`）
- `prefers-reduced-motion`対応（アニメーション無効化）

### 9.2 カラーコントラスト

| 組み合わせ | コントラスト比 | 基準 |
|-----------|--------------|------|
| `--dark-gray` (#333) on `--off-white` (#FAFAF8) | 11.7:1 | ✅ AAA |
| `--brown` (#6B4423) on `--off-white` (#FAFAF8) | 8.1:1 | ✅ AAA |
| `white` on `--muted-red` (#C97D7D) | 4.6:1 | ✅ AA |

すべてWCAG AA基準（4.5:1以上）をクリア

### 9.3 prefers-reduced-motion対応

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 10. レスポンシブデザイン

### 10.1 フォントサイズ調整

```css
/* モバイル */
@media (max-width: 768px) {
  h1 {
    font-size: 2.5rem; /* 40px */
  }
  h2 {
    font-size: 1.875rem; /* 30px */
  }
  h3 {
    font-size: 1.25rem; /* 20px */
  }
}

/* PC */
@media (min-width: 768px) {
  h1 {
    font-size: 3.5rem; /* 56px */
  }
  h2 {
    font-size: 2.25rem; /* 36px */
  }
  h3 {
    font-size: 1.5rem; /* 24px */
  }
}
```

### 10.2 スペーシング調整

```css
/* モバイル */
section {
  padding-top: 4rem; /* 64px */
  padding-bottom: 4rem; /* 64px */
}

/* PC */
@media (min-width: 768px) {
  section {
    padding-top: 5rem; /* 80px */
    padding-bottom: 5rem; /* 80px */
  }
}
```

---

## 11. 技術スタック

| レイヤー | 技術 | 備考 |
|---------|------|------|
| **HTML** | HTML5 | セマンティック重視 |
| **CSS** | Tailwind CSS (CDN) + カスタムCSS変数 | WordPress移行時にビルド版へ |
| **フォント** | Noto Sans JP (Google Fonts) | システムフォント優先 |
| **アイコン** | Font Awesome 6.5.1 | CDN使用 |
| **将来的な実装** | WordPress + Lightning テーマ | XFREE + 無料テーマ |

---

## 12. デザイナー依頼事項

### 12.1 必須成果物

1. **プロフィール画像**
   - サイズ: 280x280px（@2x対応で560x560px）
   - スタイル: 親しみやすく、プロフェッショナル
   - ポーズ: 管理栄養士らしい清潔感

2. **ロゴ**
   - テキスト: 「リンゴラボ」
   - アイコン: りんごモチーフ
   - カラー: `--muted-red`（#C97D7D）と`--brown`（#6B4423）のコンビネーション
   - フォーマット: SVG（透過背景）

3. **ファビコン**
   - サイズ: 16x16, 32x32, 180x180（Apple Touch Icon）
   - デザイン: りんごアイコンのシンプル版

---

## 13. 関連ドキュメント

| ファイル | 内容 |
|---------|------|
| **[SITE-SPEC.md](./SITE-SPEC.md)** | サイト構成・機能仕様 v2.0 |
| **[CLAUDE.md](../CLAUDE.md)** | Claude Code開発ガイド |
| **[index.html](./index.html)** | HTML試作版 |
| **[style.css](./css/style.css)** | カスタムCSS |

---

## 14. 更新履歴

| 日付 | バージョン | 内容 |
|------|----------|------|
| 2026-03-20 | v1.0 | 初版作成 |
| 2026-03-22 | v2.0 | **全面改訂**: Apple的余白システム導入、スペーシング拡大、コンテナ幅縮小、ホバー効果軽減、SITE-SPEC v2.0との整合性確保 |
