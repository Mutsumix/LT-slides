# Modern Japanese Slide Template

モダンな日本語スライド用のテンプレートです。

## 🎨 特徴

- **美しい日本語フォント**の最適化
- **縦棒デザイン**の通常スライド
- **グラデーション背景**の大項目スライド
- **白抜き文字**で視認性向上
- **コードブロック**のグラデーション背景
- **吹き出しコンポーネント**でインタラクティブな表現

## 📁 ファイル構成

```
templates/
├── .marprc                    # Marp設定ファイル
├── themes/
│   └── modern-japanese.css    # テーマファイル
├── template.md                # ベーステンプレート
└── README.md                  # このファイル
```

## 🚀 使い方

### 1. テンプレートをコピー

```bash
# 新しいスライド用フォルダを作成
mkdir my-new-slide
cd my-new-slide

# テンプレートファイルをコピー
cp ../templates/template.md ./index.md
cp ../templates/.marprc ./
cp -r ../templates/themes ./
```

### 2. 内容を編集

`index.md`を編集してスライドを作成：

- **表紙**: title, author, description を変更
- **大項目**: `<!-- _class: section-title -->`でセクション区切り
- **通常スライド**: そのまま記述
- **画像**: `images/`フォルダに配置

### 3. プレビュー・出力

Marp CLI または VS Code の Marp 拡張機能を使用してプレビュー・出力できます。

## 🎯 スライドクラス

### `cover`

表紙ページ用。背景はデフォルトで薄いグレー。

```markdown
<!-- _class: cover -->

# スライドタイトル
```

### `section-title`

大項目・セクション区切り用。美しいグラデーション背景。

```markdown
<!-- _class: section-title -->

# 大項目タイトル
```

## 🛠 コンポーネント

### 吹き出し

```markdown
<div class="balloon-left">左側の吹き出し</div>
<div class="balloon-right">右側の吹き出し</div>
```

### プロフィール画像

```markdown
<style scoped>
  .profile-icon {
    width: 90px;
    float: left;
    margin-right: 16px;
  }
</style>

<img src="./images/profile.jpg" class="profile-icon" />
```

## 🎨 カラーパレット

- **メインブルー**: `#3498db`
- **グラデーション**: `#667eea` → `#764ba2`
- **テキスト**: `#2c3e50` (濃いグレー)
- **サブテキスト**: `#34495e`, `#7f8c8d`
- **アクセント**: `#e74c3c` (赤)
- **背景**: `#fafafa` (薄いグレー)

## 📝 カスタマイズ

`themes/modern-japanese.css`を編集することで、色やレイアウトをカスタマイズできます。

---

このテンプレートを使って、美しいスライドを作成してください！🎉
