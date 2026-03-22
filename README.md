# QoL Database

温活・美容・健康をテーマにした管理栄養士監修のメディアサイト「リンゴラボ（仮）」のプロトタイプ開発リポジトリ

## プロジェクト概要

**コンセプト**: 「1日1個のりんご習慣」から、整える生活へ

管理栄養士の専門性を活かし、冷え性・むくみ・肌荒れに悩む20-40代女性に向けた、科学的根拠に基づく温活・美容・健康コンテンツを提供するメディアサイトです。

### 主要コンテンツ

- **記事**: 温活・美容・食事に関する専門記事
- **商品**: りんごティー（温活商品）
- **アプリ**: 体調管理アプリ（プロトタイプ）

## リポジトリ構成

```
qol-database/
├── prototype/           # HTMLプロトタイプ
│   ├── index.html      # トップページ
│   ├── product-tea.html        # りんごティー商品ページ
│   ├── app-health.html         # 体調管理アプリページ
│   ├── article-lava-review.html    # LAVAホットヨガ記事
│   ├── css/
│   │   └── style.css   # カスタムスタイル（Apple-likeデザイン）
│   ├── images/         # 画像素材
│   │   ├── logo.png
│   │   └── profile.png
│   ├── DESIGN.md       # デザイン仕様書
│   └── SITE-SPEC.md    # サイト仕様書
└── README.md           # このファイル
```

## aff-hunter 連携

このプロジェクトは、**aff-hunter**（アフィリエイト自動化プラットフォーム）のデータベースとスキルを活用しています。

### データソース

- **案件データベース**: `/Users/rin5uron/github-local/personal/aff-hunter/analysis_data.json`
  - A8.netの149,014件の案件データ
  - 記事テーマ選定・案件優先度の分析に使用

### スキル統合

- **Copywriting**: `/Users/rin5uron/github-local/personal/aff-hunter/.claude/skills/copywriting/`
  - 記事・LP制作時のコピーライティング原則
- **Product Marketing Context**: `/Users/rin5uron/github-local/personal/aff-hunter/.claude/product-marketing-context.md`
  - ブランドコンセプト・ターゲットオーディエンス・専門性の定義

### 記事制作フロー

1. **aff-hunter**のデータベースから高収益案件を抽出
2. **copywriting**スキルを適用してコンテンツ作成
3. **qol-database**のプロトタイプに実装
4. 管理栄養士の専門性（E-E-A-T）を前面に出したコンテンツ設計

## デザインシステム

### カラーパレット

| 用途 | カラー | 変数名 |
|------|--------|--------|
| メインカラー | `#C97D7D` | `--color-primary` |
| セカンダリー | `#F5EFE6` | `--color-secondary` |
| アクセント | `#6B4423` | `--color-accent` |
| 本文テキスト | `#333333` | `--color-text-primary` |
| 背景 | `#FAFAF8` | `--color-bg-primary` |

### タイポグラフィ

- **フォント**: -apple-system, BlinkMacSystemFont, "Noto Sans JP"
- **スケール**: 12px〜60px（8pxベースのスペーシングシステム）
- **スタイル**: iPhone UI風の洗練されたデザイン

詳細は `prototype/DESIGN.md` を参照

## 技術スタック

- **HTML5 + Tailwind CSS**: レスポンシブデザイン
- **Font Awesome 6**: アイコン
- **Google Fonts**: Noto Sans JP
- **カスタムCSS**: Apple-likeデザイン（backdrop-filter, 控えめなshadow）

## 開発履歴

- **2026-03-22**: プロトタイプ初版作成
  - トップページ、商品ページ（りんごティー）、アプリページ実装
  - LAVA記事作成（aff-hunterデータベース活用）
  - DESIGN.md更新（詳細な仕様追加）

## 関連リポジトリ

- **aff-hunter**: アフィリエイト自動化プラットフォーム（データソース・スキル提供元）
  - パス: `/Users/rin5uron/github-local/personal/aff-hunter/`

## ライセンス

© 2026 Studio Jinsei. All rights reserved.
