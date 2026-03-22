# Claude Code 開発ガイド - QoL Database

このドキュメントは、Claude Codeを使用してqol-database（リンゴラボ）を開発する際のガイドラインです。

## プロジェクト理念

### ブランドコンセプト

**「1日1個のりんご習慣から、整える生活へ」**

管理栄養士の専門性を活かし、科学的根拠に基づいた温活・美容・健康コンテンツを提供します。

### ターゲットオーディエンス

- **年齢層**: 20-40代女性
- **悩み**: 冷え性、むくみ、肌荒れ、生理不順
- **価値観**: 自然派志向、エビデンス重視、ズボラOK

## 重要: aff-hunterとの連携

**このプロジェクトは、aff-hunterリポジトリのデータとスキルを活用します。**

### データベース参照

記事テーマ選定時は、必ず以下のデータベースを参照してください：

```
/Users/rin5uron/github-local/personal/aff-hunter/analysis_data.json
```

- A8.netの149,014件の案件データ
- 報酬単価、承認率、リスティング可否、カテゴリ情報

### スキル活用

コンテンツ制作時は、以下のスキルを適用してください：

#### Copywriting Skill

```
/Users/rin5uron/github-local/personal/aff-hunter/.claude/skills/copywriting/skill.md
```

**適用原則**:
- Clarity over cleverness（明確さ > 創造性）
- Benefits over features（ベネフィット > 機能）
- Specificity over vagueness（具体性 > 曖昧さ）
- Customer language over company language（顧客の言葉 > 企業の言葉）

#### Product Marketing Context

```
/Users/rin5uron/github-local/personal/aff-hunter/.claude/product-marketing-context.md
```

**必須事項**:
- 管理栄養士の専門性を前面に出す
- E-E-A-T（専門性・経験・権威性・信頼性）を重視
- 実体験・エビデンスを盛り込む

## コンテンツ制作ルール

### 記事制作フロー

1. **aff-hunterデータベースを分析**
   - 高報酬 × リスティング可 × 温活/美容/健康関連の案件を抽出
   - スコアリング基準: 報酬単価 × 承認率 × 低競合

2. **Copywritingスキルを適用**
   - ヘッドライン: "{Achieve outcome} without {pain point}"
   - ベネフィット重視: 機能説明より結果を伝える
   - 具体的な数値: "週2回、3ヶ月で体温0.5℃UP"

3. **管理栄養士の専門性を明示**
   - 記事タイトルに「管理栄養士が解説」を含める
   - エビデンス（論文・ガイドライン）を引用
   - 実務経験・資格を活かした独自視点を盛り込む

4. **E-E-A-T対策**
   - **Expertise**: 管理栄養士資格を明記
   - **Experience**: 実体験・保育園勤務経験を語る
   - **Authoritativeness**: 資格番号・所属団体を記載
   - **Trustworthiness**: エビデンスで裏付ける

### 薬機法・景表法コンプライアンス

**絶対にNGな表現**:
- ❌ 「治る」「効く」「改善する」（断定表現）
- ❌ 「No.1」「最安値」（根拠のない最上級表現）
- ❌ 「100%」「必ず」「絶対」（誇大広告）

**推奨される表現**:
- ✅ 「期待できる」「サポートする」「〜に役立つ可能性がある」
- ✅ 「〜と言われています」「〜が報告されています」
- ✅ 「個人の感想です」「効果には個人差があります」

### デザイン原則

#### Apple-like Design System

- **フォント**: -apple-system優先、Noto Sans JPフォールバック
- **シャドウ**: 極めて控えめ（0.04〜0.06 opacity）
- **角丸**: 大きめ（8px〜32px）
- **ホバー効果**: 控えめな移動（-2px程度）

詳細は `prototype/DESIGN.md` を参照

#### レスポンシブ設計

- **モバイルファースト**: 320px〜対応
- **ブレークポイント**: 640px, 768px, 1024px, 1280px
- **タッチターゲット**: 最低44×44px（iOS基準）

## ファイル構成規則

### HTML

- **命名規則**: `kebab-case.html`
- **セマンティックHTML**: `<article>`, `<section>`, `<nav>`を適切に使用
- **アクセシビリティ**: `aria-label`, `alt`属性を必ず設定

### CSS

- **CSS変数**: `--color-primary`等、既存の変数を活用
- **Tailwind優先**: カスタムCSSは最小限に
- **レスポンシブ**: `@media`クエリはモバイルファーストで記述

### 画像

- **形式**: PNG（ロゴ）、JPG（写真）
- **配置**: `prototype/images/`
- **命名**: 小文字、ハイフン区切り（`profile-image.png`）

## Git運用

### ブランチ戦略

- **main**: 本番環境（常に動作する状態を保つ）
- **feature/***: 機能開発ブランチ

### コミットメッセージ

```
[type] 簡潔な変更内容

詳細な説明（必要に応じて）

🤖 Generated with Claude Code
```

**type例**:
- `feat`: 新機能追加
- `fix`: バグ修正
- `docs`: ドキュメント更新
- `style`: デザイン調整
- `refactor`: リファクタリング

### Issue管理

- **ラベル**: `article`, `design`, `bug`, `enhancement`
- **テンプレート**: aff-hunterのissue-rules.mdを参考に

## 開発優先順位

### Phase 1: プロトタイプ完成

- [x] トップページ
- [x] 商品ページ（りんごティー）
- [x] アプリページ
- [ ] 記事ページ（3記事）
  - [x] LAVA記事
  - [ ] よもぎ蒸し記事
  - [ ] 無添加つくりおき記事

### Phase 2: コンテンツ拡充

- [ ] SEO記事10本投稿
- [ ] カテゴリーページ作成
- [ ] 検索機能実装

### Phase 3: 機能追加

- [ ] 体調管理アプリのプロトタイプ実装
- [ ] 問い合わせフォーム
- [ ] SNS連携

## 品質チェックリスト

### 記事公開前

- [ ] 管理栄養士の専門性が明示されているか
- [ ] エビデンス（論文・ガイドライン）が引用されているか
- [ ] 薬機法・景表法に違反する表現がないか
- [ ] モバイル表示が正常か
- [ ] アクセシビリティチェック（aria-label, alt）
- [ ] ページ読み込み速度が3秒以内か

### デザイン品質

- [ ] Apple-likeデザインシステムに準拠しているか
- [ ] カラーパレットは統一されているか
- [ ] フォントサイズ・スペーシングはデザイントークンに準拠しているか
- [ ] ホバー効果は控えめか（-2px程度）

## トラブルシューティング

### よくある問題

#### 1. aff-hunterのデータが読み込めない

→ パスが正しいか確認:
```
/Users/rin5uron/github-local/personal/aff-hunter/analysis_data.json
```

#### 2. Tailwind CSSが反映されない

→ CDN読み込みを確認:
```html
<script src="https://cdn.tailwindcss.com"></script>
```

#### 3. カスタムCSSが効かない

→ 読み込み順序を確認（Tailwind → style.css）:
```html
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="css/style.css">
```

## 参考資料

### 内部ドキュメント

- [DESIGN.md](prototype/DESIGN.md) - デザイン仕様書
- [SITE-SPEC.md](prototype/SITE-SPEC.md) - サイト仕様書
- [aff-hunter/CLAUDE.md](../aff-hunter/CLAUDE.md) - aff-hunter開発ガイド

### 外部リソース

- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [薬機法ルールブック](https://www.mhlw.go.jp/stf/seisakunitsuite/bunya/kenkou_iryou/iyakuhin/)

## 更新履歴

- **2026-03-22**: 初版作成
  - aff-hunter連携ルール明記
  - コンテンツ制作フロー定義
  - 薬機法・景表法コンプライアンス追加
