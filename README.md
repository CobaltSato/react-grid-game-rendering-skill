# React CSS Grid Game Rendering Skill

Grid-based game rendering patterns using React + CSS Grid. Implements game boards with grid layouts instead of Canvas/WebGL.

## スキル概要

このスキルは、React と CSS Grid を使用したグリッドベースのゲームレンダリングパターンを提供します。Canvas や WebGL を使わずに、DOM ベースでゲームボードを実装するための知識とベストプラクティスをまとめています。

### 主な機能

- **グリッドレイアウトの設定**: CSS 変数を使った柔軟なグリッドサイズ管理
- **タイルレンダリング**: 2D配列から効率的にタイルを生成するパターン
- **動的オブジェクト配置**: グリッド位置への正確なオブジェクト配置（0ベース/1ベース変換の考慮）
- **パフォーマンス最適化**: 最適化手法とベストプラクティス
- **トラブルシューティング**: よくある問題と解決方法

### 使用シーン

- グリッドベースのゲームUI実装
- CSS Grid を使ったレイアウト設計
- 動的なオブジェクト配置が必要なゲーム
- ゲームUIのスタイリングとアニメーション

### 技術スタック

| 技術 | 用途 |
|------|------|
| **React** | UIコンポーネントのレンダリング |
| **CSS Grid** | グリッドレイアウト |
| **CSS Variables** | サイズと色の一元管理 |
| **Inline Styles** | 動的な位置指定 |
| **CSS Animations** | ビジュアルエフェクト |

### 特徴

- ✅ Canvas/WebGL 不要でシンプルな実装
- ✅ CSS 変数による柔軟なサイズ管理
- ✅ 0ベース/1ベースインデックスの自動変換パターン
- ✅ TypeScript 対応の型安全性ガイドライン

## Installation

### For Claude Code
```bash
# Clone this repository
git clone <your-repo-url>
cd game-skill

# Copy the skill to your Claude skills directory
cp -r skills/react-css-grid-game-rendering ~/.claude/skills/
```

### For Gemini
```bash
gemini skills install ./react-css-grid-game-rendering.skill --scope workspace
```
