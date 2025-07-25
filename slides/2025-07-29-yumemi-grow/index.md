---
marp: true
paginate: true
theme: blue-standard
title: AIコードチェックが面倒すぎるのでテスト駆動開発で解決しようとして読んだら、根本的に俺の勘違いだった
description: 2025-07-29 | 読書シェア会 vol.7
author: 梶原睦
---

<!-- _class: title -->

# AI コードチェックが面倒すぎるのでテスト駆動開発で解決しようとして読んだら、根本的に俺の勘違いだった

## 読書シェア会 vol.7

---

<!-- _class: section-title -->

# 1. AI コーディング、やってますか？

---

<!--
footer: 読書シェア会 vol.7 | AI コードチェックが面倒すぎるのでテスト駆動開発で解決しようとして読んだら、根本的に俺の勘違いだった（ムツミックス）
-->

# AI コーディング、やってますか？

- AI（ChatGPT、Claude 等）にコード書かせる
- 一部のコーディング補助から完全実装まで
- 結果だけチェック
- めちゃくちゃ楽だけど...

---

# AI コーディングの現実

<!-- ![bg right:40% 90%](https://via.placeholder.com/400x300/ff6b6b/ffffff?text=AI+Code) -->

- **最初は順調**
- **だんだん方向性がずれてくる**
- **気づいたら修正不可能な状態**
- 「AI のコードを目 Grep は面倒だし...」

---

# 何か良い方法はないものか？

- 「テストを都度挟めば、ずれを修正できるのでは？」
- 「よし、AI にテストを書かせよう」

### プロンプト：

```
まずテストを書いて、それを突破するように実装して
```

---

# 結果

```javascript
// AIが生成したテスト
describe("UserService", () => {
  it("should create user", () => {
    const mockDb = jest.fn();
    const mockValidator = jest.fn();
    // TODO: implement this test
    expect(true).toBe(true); // とりあえず通る
  });
});
```

- 結果：モックだらけ、重要な部分がコメントアウト、何をテストしているか不明
  **こんなの受け入れていいのか？**

---

# ケント・ベック『テスト駆動開発』

![bg right:25% 80%](./image/tdd.png)

**3 部構成：**

- 第 1 部：貨幣の例（多通貨対応の金額計算）
- 第 2 部：xUnit の例
  - テスティングフレームワーク構築
- 第 3 部：パターンとリファクタリング

## 「テストについてちゃんと学んで、効果的なテストの書き方を学ぶぞ」

<!-- **レッド・グリーン・リファクタサイクル** -->

---

# 読んでみた結果

## 「あれ、これテストの書き方の本じゃない...？」

### TDD の本質：

- ❌ テスト設計手法
- ⭕ **プログラミング中の不安を取り除く思考法**

---

# TDD の真の価値

<!-- ![bg right:35% 85%](https://via.placeholder.com/350x250/95e1d3/ffffff?text=Small+Steps) -->

## 核心は **心理的安全性**

- 小さなステップで確実に前進
- 常に動作するコードを維持
- 複雑さをコントロール
- **開発者の不安を軽減**

---

# 根本的な勘違いに気づく

## Before (勘違い)

- **問題：** AI コードのチェックが面倒
- **最初の試み：** AI にテストを書かせる → **失敗**
- **期待した解決策：** テストで品質担保

## After (理解)

- **実際の TDD：** 開発プロセス自体の改善

---

# TDD を AI コーディングに応用するなら

## ❌ 間違ったアプローチ

```
「テストを最初に設定しろ」とAIに指示
```

## ⭕ 正しいアプローチ

```
「小さな実装→TODOリスト→逐次消化」をAIに指示
```

- 方向性のずれを小さなうちに修正
- ゴールに向けた確実な前進

---

# 実際のプロンプト例

```
以下の手順で実装してください：

1. 最終ゴールを明確にする
2. 現在の状態から次の小さなステップを定義
3. そのステップだけを実装
4. 動作確認
5. 次のTODOを提示
6. 2-5を繰り返し

各ステップは15分以内で完了できるサイズにしてください。
実装前に必ず「今から何をするか」を説明してください。
```

---

# 学んだこと + 次のアクション

## 学んだこと

- **本を読む前の思い込みの危険性**
- **TDD は「テスト手法」ではなく「開発哲学」**
- **AI にも人間の優れた開発プロセスを適用できる可能性**

## 次のアクション

- この手法で実際にプロジェクトを試す
- AI + TDD 的アプローチの効果を検証
- **xUnit の実装を書籍に従って写経**

---

<!-- _class: title -->

おまけ
今回のスライドの作成自体も、AI の支援を受けた
書籍を読もうとしたきっかけ
書籍を読んで何を得たか
これから何をしたいか
一番重要なところを AI に任せてはいけない。

# ありがとうございました！

**質問・ディスカッションをお待ちしています**

Twitter や GitHub でも気軽にお声かけください
[@your_handle]

書籍の引用候補

候補 1: TDD の本質を表す引用（スライド 8「TDD の真の価値」）

「恐怖は開発を麻痺させる。恐怖があると、明確に考えることができず、他の人とのコミュニケーションもうまくいかず、フィードバックも避けてしまう。」
— ケント・ベック『テスト駆動開発』

効果: TDD が単なるテスト手法ではなく、開発者の心理的状態を改善する手法だと明確に示せる
候補 2: 小さなステップの重要性（スライド 10「TDD を AI コーディングに応用するなら」）

「小さなステップでいこう。テストからコードへ、そしてリファクタリングへ。実装から抽象化へ。」
— ケント・ベック『テスト駆動開発』

効果: AI への指示として「小さなステップ」が重要だという主張を権威づけできる
候補 3: TDD の目的（スライド 9「根本的な勘違いに気づく」）

「TDD の目的は完璧なテストを書くことではない。恐怖を管理することだ。」
— ケント・ベック『テスト駆動開発』

効果: 「テスト設計手法」という勘違いを明確に否定し、真の目的を示せる
候補 4: 動作するコードの価値（スライド 8「TDD の真の価値」）

「動作するきれいなコード。Ron Jeffries のこの簡潔な表現が、TDD の目標である。」
— ケント・ベック『テスト駆動開発』

効果: 常に動作するコードを維持するという価値観を強調できる
私の推奨
候補 3 が最も効果的だと思います。理由：

聴衆の「あるある」体験（テスト＝品質担保という思い込み）を直接否定
TDD の真の価値を簡潔に表現
AI コーディングでの「不安」（方向性のずれ）との関連性が明確
スライドの転換点（勘違いから理解へ）で使うことで印象に残る
