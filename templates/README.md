# Marp カスタムテーマ集

Marpで使用できるカスタムテーマのコレクションです。

## 🎨 利用可能なテーマ

### 1. modern-japanese
モダンな日本語プレゼンテーション向けテーマ
- **青系グラデーション**の縦棒デザイン
- **放射状グラデーション背景**のセクションタイトル
- **吹き出しコンポーネント**付き
- 日本語フォントに最適化

### 2. blue-standard
ビジネスプレゼンテーション向けスタンダードテーマ
- **赤系アクセント**の縦棒デザイン
- **紫系グラデーション**の表紙ページ
- **青系グラデーション**のセクションタイトル
- 数値強調・進捗バー・テーブルスタイルを含む

## 📁 ファイル構成

```
templates/
├── themes/
│   ├── modern-japanese.css    # モダン日本語テーマ
│   └── blue-standard.css      # ブルースタンダードテーマ
└── README.md                  # このファイル
```

## 🚀 使い方

### 1. VS Code の設定でテーマパスを追加

VS Code の設定（`settings.json`）に以下を追加：

```json
{
  "markdown.marp.themes": [
    "./templates/themes/modern-japanese.css",
    "./templates/themes/blue-standard.css"
  ]
}
```

または、VS Code の設定画面から：
1. 設定を開く（`Cmd+,` または `Ctrl+,`）
2. 「marp themes」で検索
3. 「Markdown › Marp: Themes」にCSSファイルのパスを追加

### 2. スライドでテーマを指定

Markdownファイルの冒頭（frontmatter）でテーマを指定：

```yaml
---
marp: true
theme: modern-japanese
---
```

または

```yaml
---
marp: true
theme: blue-standard
---
```

### 3. プレビュー・出力

VS Code の Marp 拡張機能でプレビュー、または Marp CLI で出力できます。

## 🎯 スライドクラス（両テーマ共通）

### `cover`
表紙ページ用クラス
- modern-japanese: 薄いグレー背景
- blue-standard: 紫系グラデーション背景

```markdown
<!-- _class: cover -->

# スライドタイトル
```

### `section-title`
大項目・セクション区切り用クラス
- modern-japanese: 放射状グラデーション背景
- blue-standard: 青系グラデーション背景

```markdown
<!-- _class: section-title -->

# 大項目タイトル
```

## 🛠 特殊コンポーネント

### 吹き出し（modern-japanese テーマのみ）

```markdown
<div class="balloon-left">左側の吹き出し</div>
<div class="balloon-right">右側の吹き出し</div>
```

### 数値強調（blue-standard テーマのみ）

```markdown
<div class="big-number">123</div>
```

### 進捗バー（blue-standard テーマのみ）

```markdown
<div class="progress-bar">
  <div class="progress-fill" style="width: 70%"></div>
</div>
```

## 📝 注意事項

- カスタムテーマを使用する際は、必ず VS Code の設定でテーマパスを追加してください
- テーマファイルへのパスは、ワークスペースのルートからの相対パスで指定します
- Marp CLI を使用する場合は、`--theme` オプションでテーマファイルを指定できます

---

これらのテーマを使って、美しいスライドを作成してください！🎉
