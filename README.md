# Game Development Skills Collection

ゲーム開発向けのAgent Skillsコレクション。React + CSS Gridを使ったゲームレンダリングと、Avalanche風の高品質フロントエンドデザインを提供します。

## スキル一覧

### 1. React CSS Grid Game Rendering Skill

React と CSS Grid を使用したグリッドベースのゲームレンダリングパターンを提供します。Canvas や WebGL を使わずに、DOM ベースでゲームボードを実装するための知識とベストプラクティスをまとめています。

#### 主な機能

- **グリッドレイアウトの設定**: CSS 変数を使った柔軟なグリッドサイズ管理
- **タイルレンダリング**: 2D配列から効率的にタイルを生成するパターン
- **動的オブジェクト配置**: グリッド位置への正確なオブジェクト配置（0ベース/1ベース変換の考慮）
- **パフォーマンス最適化**: 最適化手法とベストプラクティス
- **トラブルシューティング**: よくある問題と解決方法

#### 使用シーン

- グリッドベースのゲームUI実装
- CSS Grid を使ったレイアウト設計
- 動的なオブジェクト配置が必要なゲーム
- ゲームUIのスタイリングとアニメーション

#### 技術スタック

| 技術 | 用途 |
|------|------|
| **React** | UIコンポーネントのレンダリング |
| **CSS Grid** | グリッドレイアウト |
| **CSS Variables** | サイズと色の一元管理 |
| **Inline Styles** | 動的な位置指定 |
| **CSS Animations** | ビジュアルエフェクト |

#### 特徴

- ✅ Canvas/WebGL 不要でシンプルな実装
- ✅ CSS 変数による柔軟なサイズ管理
- ✅ 0ベース/1ベースインデックスの自動変換パターン
- ✅ TypeScript 対応の型安全性ガイドライン

---

### 2. Avalanche-like Frontend Design Skill

Avalanche（アバランチ）ブロックチェーンプラットフォームにインスパイアされた、高品質なフロントエンドデザインスキル。シャープで高性能な視覚的アイデンティティを持つ、プロダクショングレードのインターフェースを作成します。

#### 主な機能

- **デザイン思考**: 明確な美学方向性の設定と意図的なデザイン
- **Avalanche美学の統合**: シャープさ、スピード、構造的な確信を20-30%程度取り入れたデザイン言語
- **タイポグラフィ**: 特徴的で個性的なフォント選択、エンタープライズ級の可読性
- **カラーとテーマ**: ダーク基調（`#0B0B0B`〜`#111`）+ 深紅のアクセント、高コントラスト
- **モーション**: 速く、シャープなトランジション、スナッピーなフェード
- **空間構成**: 予想外のレイアウト、非対称、カードベースUI

#### 使用シーン

- Webコンポーネント、ページ、アーティファクトの作成
- ウェブサイト、ランディングページ、ダッシュボードの構築
- Reactコンポーネント、HTML/CSSレイアウトのスタイリング
- 汎用的なAI美学を避けた、独自性のあるUIデザイン

#### デザイン特徴

- ✅ Avalanche DNA（20-30%）を構造的な骨格として統合
- ✅ 意図的なデザイン思考プロセス
- ✅ プロダクショングレードのコード実装
- ✅ 汎用的なAI美学を避けた差別化されたデザイン
- ✅ エンタープライズ級のタイポグラフィとレイアウト

#### Avalanche美学の要素

- **カラーパレット**: 深紅/クリムゾン、レッド→ブラックグラデーション
- **テクスチャとトーン**: ハード、高速、シャープ、プロフェッショナル
- **レイアウト**: カードベースUI、ダッシュボードパターン、情報階層重視
- **モーション**: 速いトランジション、フェード+軽いスライド

詳細なAvalanche美学リファレンスは `avax-like-frontend-design/references/avax-aesthetics.md` を参照してください。

---

## Installation

### For Claude Code

```bash
# Clone this repository
git clone <your-repo-url>
cd game-skill

# Install React CSS Grid Game Rendering Skill
cp -r react-css-grid-game-rendering ~/.claude/skills/

# Install Avalanche-like Frontend Design Skill
cp -r avax-like-frontend-design ~/.claude/skills/
```

### For Gemini

```bash
# Install React CSS Grid Game Rendering Skill
gemini skills install ./react-css-grid-game-rendering.skill --scope workspace

# Install Avalanche-like Frontend Design Skill
gemini skills install ./avax-like-frontend-design.skill --scope workspace
```

## Publishing to SkillsMP.com

SkillsMP.com に配布するには、以下の手順に従ってください：

### 1. GitHub リポジトリに公開

1. このリポジトリを GitHub にプッシュ
2. リポジトリが公開されていることを確認
3. 最低2スター以上を取得（SkillsMP の要件）

### 2. リポジトリ構造

現在の構造は SkillsMP の要件を満たしています：
```
game-skill/
├── react-css-grid-game-rendering/
│   ├── SKILL.md
│   └── references/
│       └── react-css-grid-rendering.md
├── avax-like-frontend-design/
│   ├── SKILL.md
│   └── references/
│       └── avax-aesthetics.md
├── .claude-plugin/
│   └── marketplace.json
├── .claude/
│   └── skills/
│       └── game-frontend-design/
│           ├── react-css-grid-game-rendering/
│           └── avax-like-frontend-design/
├── .gemini/
│   └── skills/
│       ├── react-css-grid-game-rendering/
│       └── avax-like-frontend-design/
└── README.md
```

### 3. SkillsMP での自動検出

SkillsMP は GitHub を定期的にクロールしてスキルを検出します：
- SKILL.md ファイルを含むリポジトリを自動検出
- 最低2スター以上のリポジトリをフィルタリング
- カテゴリや説明から自動分類

### 4. 手動での確認

SkillsMP に表示されるまで数時間かかる場合があります。以下の方法で確認できます：

1. [SkillsMP.com](https://skillsmp.com/) にアクセス
2. 検索バーでリポジトリ名やスキル名を検索
3. カテゴリ「Development」または「Tools」で確認
