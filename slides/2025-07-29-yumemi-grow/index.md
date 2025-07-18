---
marp: true
paginate: true
math: mathjax

title: yumemi_grow用スライド
description: 2025-07-29 | yumemi_grow用プレゼンテーション
author: ムツミックス / Mutsumix
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
    background: linear-gradient(180deg, #3498db 0%, #667eea 100%);
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
    margin: 0.5rem 0;
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
    background-image:
      url("./images/header.png"),
      url("./images/smclogo-trance-full.png");
    background-position:
      center center,
      center center;
    background-size:
      cover,
      cover;
    background-position:
      top right,
      bottom right;
    background-size:
      1280px,
      500px;
  }

    /* グラデーション背景の大項目スライド */
  section.section-title {
    background: radial-gradient(circle at 20% 80%,
      #1a252f 0%,
      #2c3e50 15%,
      #34495e 30%,
      #4a6fa5 50%,
      #667eea 70%,
      #3b82f6 100%);
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
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5), -1px -1px 2px rgba(0,0,0,0.3);
    -webkit-text-stroke: 1px rgba(0,0,0,0.2);
    /* 下線デザイン */
    border-bottom: 3px solid rgba(255,255,255,0.8);
    padding-bottom: 0.5rem;
    display: inline-block;
    width: fit-content;
    position: static; /* 縦棒の::beforeを無効化 */
    padding-left: 0; /* 縦棒用の左paddingを削除 */
  }

  section.section-title h1::before {
    display: none; /* 縦棒を非表示 */
  }

  section.section-title h2 {
    color: white;
    font-weight: 500;
    letter-spacing: 0.05em;
    line-height: 1.3;
    margin-top: 2rem;
    text-shadow: 1px 1px 3px rgba(0,0,0,0.4);
  }
---

<!-- _class: cover -->

# yumemi_grow用スライド

### ムツミックス / Mutsumix

<br />

2025-07-29 | yumemi_grow用プレゼンテーション

---

<!--
footer: yumemi_grow用スライド | Mutsumix
-->

# タイトルスライド

## サブタイトル

- 項目1
- 項目2
- 項目3

---

<!-- _class: section-title -->

# セクションタイトル

---

# 通常のスライド

## 見出し

内容をここに記載します。

---

<!-- _class: section-title -->

# ありがとうございました 🙏