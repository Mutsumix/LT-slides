---
marp: true
paginate: true
math: mathjax

title: JavaScriptフレームワークの必要性と技術者アサインのポイント
description: 2025-07-17 | Web技術の進化とエンジニア配置戦略
author: 梶原睦
style: |
  section {
    font-size: 28px;
    background-repeat: no-repeat /* 共通 */;
    font-family: 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', 'Noto Sans JP', -apple-system, BlinkMacSystemFont, sans-serif;
    background-color: #fafafa;
    line-height: 1.6;
  }

  /* 縦棒デザイン */
  section h1 {
    color: #2c3e50;
    font-weight: 600;
    margin-bottom: 1.5rem;
    position: relative;
    padding-left: 1.5rem;
  }

  section h1::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 6px;
    background: linear-gradient(180deg, #e74c3c 0%, #c0392b 100%);
    border-radius: 3px;
  }

  section h2 {
    color: #34495e;
    font-weight: 500;
    margin-top: 2rem;
    margin-bottom: 1rem;
  }

  section h3 {
    color: #7f8c8d;
    font-weight: 500;
  }

  section strong {
    color: #e74c3c;
    font-weight: 600;
  }

  section li {
    margin: 0.8rem 0;
  }

  section pre {
    background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
    border-radius: 10px;
    padding: 1.5rem;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border: 1px solid #e1e8ed;
    font-size: 0.9em;
  }

  section code {
    background: #f8f9fa;
    padding: 0.2rem 0.4rem;
    border-radius: 4px;
    font-family: 'Fira Code', 'Monaco', 'Consolas', monospace;
    color: #e74c3c;
  }

  /* 表紙ページの背景 */
  section.cover {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }

  section.cover h1 {
    color: white;
    font-size: 3rem;
    margin-bottom: 2rem;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  }

  section.cover h1::before {
    background: rgba(255,255,255,0.8);
  }

  section.cover h2 {
    color: rgba(255,255,255,0.9);
    font-size: 1.5rem;
    margin-top: 1rem;
  }

  /* グラデーション背景の大項目スライド */
  section.section-title {
    background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }

  section.section-title h1 {
    color: white;
    font-weight: 600;
    letter-spacing: 0.02em;
    line-height: 1.2;
    margin: 0;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    border-bottom: 3px solid rgba(255,255,255,0.8);
    padding-bottom: 0.5rem;
    display: inline-block;
    width: fit-content;
    position: static;
    padding-left: 0;
  }

  section.section-title h1::before {
    display: none;
  }

  /* 数値強調スタイル */
  .big-number {
    font-size: 4rem;
    font-weight: 700;
    color: #e74c3c;
    text-align: center;
    margin: 1rem 0;
  }

  /* 進捗バー */
  .progress-bar {
    width: 100%;
    height: 20px;
    background-color: #ecf0f1;
    border-radius: 10px;
    margin: 1rem 0;
  }

  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, #27ae60 0%, #2ecc71 100%);
    border-radius: 10px;
    transition: width 0.3s ease;
  }

  /* テーブルスタイル */
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 1rem 0;
  }

  th, td {
    padding: 0.8rem;
    text-align: left;
    border-bottom: 1px solid #bdc3c7;
  }

  th {
    background-color: #34495e;
    color: white;
    font-weight: 600;
  }

  tr:nth-child(even) {
    background-color: #f8f9fa;
  }
---

<!-- _class: cover -->

# JavaScriptフレームワークについて

## 歴史と技術者提案時のポイント

---

# なぜJavaScriptフレームワークが必要になったのか？

## Web技術は段階的に進化してきた

- **1990年代〜：クライアント・サーバー、静的なWebページの時代**
- **2000年代〜：動的なWebアプリケーションの時代**
- **2010年代〜：リッチなユーザー体験の時代**
- **現在：複雑な業務システムもWebで実現する時代**

---

<!-- _class: section-title -->

# 1. クライアントサーバー時代

---

# クライアントサーバー時代（1990年代）

## 専用ソフトをインストールして使う時代

- **特徴：各PCに専用ソフトをインストール**
- サーバーと通信してデータをやり取り
- 更新が大変（全PCにインストールし直し）

## 課題

**「もっと簡単に使えるようにしたい」**

---

<!-- _class: section-title -->

# 2. 初期WebとエンタープライズJava時代

---

# 初期Web時代（1990年代後半〜2000年代前半）

## ブラウザで見られるように！

- **HTMLで作った静的なページ**（文書を見るだけ）
- サーバー側で全ての処理（Java、PHP等）
- ページ遷移のたびに画面が真っ白に

## 課題

**「もっと動きのある、体験の良いページにしたい」**

---

<!-- _class: section-title -->

# 3. 動的WebとREST APIの台頭期

---

# 動的Web時代（2000年代中盤〜）

## Ajax（エイジャックス）の登場で画面が部分更新できるように

- 画面を更新せずにデータだけ取得
- **JavaScript**が重要な役割を担い始める
- Google Mapsの衝撃（2005年）
- jQueryの登場→JavaScriptでも複雑なUIが作れるようになった

### 課題：開発が複雑に...

**「JavaScriptのコードが増えて管理が大変」**

---

<!-- _class: section-title -->

# 4. モバイル＆クラウド革命期

---

# モバイル時代の到来（2010年代〜）

## スマートフォンの普及で新たな課題

- **様々な画面サイズに対応が必要**
- アプリのような操作感をWebでも実現したい
- 通信環境が不安定でも快適に使いたい

## 解決策として...

**フロントエンドの処理を賢くする必要が出てきた**

---

<!-- _class: section-title -->

# 5. モダンWebフロントエンド期

---

# JavaScriptフレームワークの登場

## 基本フレームワーク

- **React**（Facebook製、2013年〜）
- **Vue**（個人開発から始まり、2014年〜）

### なぜReact・Vueが必要になったか

- **複雑なUI管理を効率化**（データが変わったら画面も自動更新）
- **部品の再利用**（同じボタンを何度も書かない）
- **開発効率の向上**（チームで統一した開発方法）

---

# Next.js・Nuxt.jsの登場

## 拡張版フレームワーク

- **Next.js**（React + 本格Webアプリ機能、2016年〜）
- **Nuxt.js**（Vue + 本格Webアプリ機能、2016年〜）

### なぜNext.js・Nuxt.jsが必要になったか

- **本格的なWebアプリケーション開発**に必要な機能を追加
- **SEO対策**や**パフォーマンス最適化**が組み込み済み
- **企業での大規模開発**に適している



---

<!-- _class: section-title -->

# React/Vue と Next.js/Nuxt.js の関係

---

## React / Vue で「できること」

- 「画面の部品」を作って、組み合わせてWebページを作る
- ボタンや入力欄などを簡単に使い回せる
- データが変わったとき、自動で画面も更新される
- 1つのページの中で色々な動きをつけられる（アプリのような操作感）
- 外部サービスやデータとつなげることも簡単

---

## Next.js / Nuxt.js で「できること」

- ページごとにURLを分けて、Webサイトらしい構成にできる
- Google検索に強いサイト（SEO対策）が作れる
- ページの表示を速くしたり、画像を自動で軽くしたりできる
- ログイン機能や、ちょっとしたサーバーの役割も持たせられる
- 大きなWebサービスや企業向けのサイトも作りやすい

---

> ReactやVueは「画面の部品を作る道具」、Next.jsやNuxt.jsは「本格的なWebサイトやサービスを作るための便利な土台」とイメージしてください。

---
<!-- _class: section-title -->

# 営業的なポイント

### **React経験者はNext.jsも対応可能、Vue経験者はNuxt.jsも対応可能**

---


## React経験者をVue案件にアサインできる？

### **基本的には可能です**

- **共通点：コンポーネント指向、状態管理の概念**
- **学習期間：2〜4週間程度で実務レベルに**
- 両方とも「部品を組み合わせて画面を作る」考え方

### 注意点

- 書き方の違いはあるが、考え方は似ている
- プロジェクトの規模や緊急度によって判断

---

# Next.js・Nuxt.js の技術者アサイン

## React経験者 → Next.js案件、Vue経験者 → Nuxt.js案件

### **順応性：非常に高い**

- **Vueの知識がそのまま活用可能**
- **学習期間：1〜2週間で実務レベル**

## 営業トーク例

**「Next.jsはReactの拡張版、Nuxt.jsはVueの拡張版です。基本技術を知っていれば短期間で習得できます」**

---
<!-- _class: section-title -->

# TypeScriptについて

---

## なぜTypeScriptが登場したか

- Type（タイプ） = 型
- **JavaScriptの弱点：型がない**
（数字か文字か分からない、動かして初めてエラーがわかる）
- 型を定義することでバグを事前に防げる（コードを書いた時点でエラーが分かる）
- 大規模開発で必須になりつつある

---

## JavaScript（エラーが実行時に発生）

```javascript
function addNumbers(a, b) { return a + b; }

let result = addNumbers(5, "10");  // "510"になってしまう
console.log(result * 2);           // ここで不具合に気づくし、気づかないかもしれない
```

## TypeScript（コードを書いた時点でエラー検出）

```typescript
function addNumbers(a: number, b: number): number { return a + b; }

let result = addNumbers(5, "10");  // ← ここでエラー検出！
```
---

<!-- # TypeScriptの技術者アサイン -->
## JavaScript経験者のアサイン

### **学習期間を設ければ対応可能**

- **基本的な学習：1〜2週間**
- **実務レベル：1〜2ヶ月**
- JavaScriptが分かっていれば習得は比較的容易

### 営業トーク例

**「TypeScriptはJavaScriptに型をつけた安全版です。JavaやC#経験者なら馴染みやすい技術です」**

---

# 営業時のポイントまとめ①

<!-- ## 技術者選定の判断基準 -->
1. **フレームワークの互換性**
   - React ↔ Vue：比較的容易（2〜4週間）
   - React → Next.js、Vue → Nuxt.js：非常に容易（1〜2週間）
   - jQuery → React/Vue：時間が必要（1〜2ヶ月）

2. **TypeScript対応**
   - JavaScript経験者なら学習期間で対応可
   - 最初から経験者の方が望ましいが必須ではない

---

# 営業時のポイントまとめ②

## 技術者評価のポイント

- 基礎的なJavaScript力があるか
- React/Vue経験者は Next.js/Nuxt.js も対応可能
- 提案する技術者**新しい技術を学ぶ意欲があるか**要確認

---

<!-- _class: cover -->

# ありがとうございました