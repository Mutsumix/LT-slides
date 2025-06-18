---
marp: true
paginate: true
math: mathjax

title: 地味に効く、ドキュメント作成の AI 活用術
description: 2025-06-19 | 生成AIと働く— エンジニア現場でのリアルな活用方法
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
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
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

  /* 吹き出しのスタイル */
  .balloon-left {
    position: relative;
    display: inline-block;
    margin-left: 64px;
    padding: 32px 64px;
    min-width: 120px;
    max-width: 100%;
    color: #555;
    background: #e0edff;
    border-radius: 20px;
    text-align: center;
  }

  .balloon-left:before {
    content: '';
    position: absolute;
    top: 50%;
    left: -60px;
    margin-top: -15px;
    border: 15px solid transparent;
    border-right: 50px solid #e0edff;
  }

  .balloon-left p {
    margin: 0;
    padding: 0;
  }
  .balloon-right {
    position: relative;
    display: inline-block;
    margin-right: 64px;
    padding: 32px 64px;
    min-width: 120px;
    max-width: 100%;
    color: #555;
    border-radius: 20px;
    background: #e0edff;
  }

  .balloon-right:before {
    content: '';
    position: absolute;
    top: 50%;
    left: 100%;
    margin-top: -15px;
    border: 15px solid transparent;
    border-left: 50px solid #e0edff;
  }

  .balloon-right p {
    margin: 0;
    padding: 0;
  }
---

<!-- _class: cover -->

# 地味に効く、ドキュメント作成の AI 活用術

<style scoped>
  .profile-icon {
    width: 90px;
    float: left;
    margin-right: 16px;
  }
</style>

<img src="./images/mutsumix.jpg" class="profile-icon" width="90px" height="90px" />

### ムツミックス / Mutsumix

<br />

2025-06-19 | 生成 AI と働く— エンジニア現場でのリアルな活用方法

<!-- <img src="./images/smclogo-trance-full.png"  width="500px" height="166px" /> -->

<!-- <https://slides.su8.run/250330-glt06> -->

---

<!--
footer: 地味に効く、ドキュメント作成のAI活用術 | Mutsumix
-->

<style scoped>
  .profile-icon {
    width: 400px;
    float: right;
    margin-right: -20px;
    margin-top: -20px;
  }
</style>

<img src="./images/selfie.png" class="profile-icon"  />

# 自己紹介

## 梶原 睦 / かじはら むつみ

- 株式会社 シスマック
  DX ソリューション事業部 部長

- Twitter: [@Mutsumix_dev](https://x.com/Mutsumix_dev)
- Voicy: [Mutsumix の進捗どう？](https://voicy.jp/channel/818315)
- エンジニア（8 年）
- 最近は受託開発の提案やったり営業やったり研修講師やったり総務やったり

---

<!-- _class: section-title -->

# コードは AI に任せられるようになりました

---

<!-- _class: section-title -->

# 開発ドキュメントは？

---

<div class="balloon-right">WordとExcelで設計書作ってる...
</div>
<img src="./images/mutsumix_mesu.png" width="100px" height="100px" style="float: right; margin-right: 400px;" class="icon">
<br><br>

<img src="./images/mutsumix.jpg" width="100px" height="100px" style="float: left; margin-right: 16px;" class="icon">
<div class="balloon-left">
PowerPointでAWS構成図描いてる...
</div>
<br><br>
<div class="balloon-right">ドキュメント修正のたび、図の修正も...
</div>
<img src="./images/mutsumix_mesu.png" width="100px" height="100px" style="float: right; margin-right: 300px;" class="icon">

---

# 従来ドキュメントの問題点

**バージョン管理不可**（Fix*画面設計書*最終\_本当に最終.docx）

**コードと別の場所にある**（メンテコスト、陳腐化リスク増大）

**コンテキストスイッチ**（VSCode → PowerPoint → Word → VSCode）

## <img src="./images/mutsumix.jpg" width="100px" height="100px" style="float: left; margin-right: -30px;" class="icon"> <div class="balloon-left">図を描くのに 3 時間かかった...</div>

## 仕事した気になってしまうが、ビジネスは何も進んでいない

---

# AI 時代、ドキュメントは Markdown 記法で<br>書くことが一般化する

と勝手に予想。文章を構造化して表現できるので、意図を適切に AI に汲み取らせやすい

## 現状：

README.md、Notion、Slack、Zenn、Qiita、GitHub Issues

## 今後：

設計書、仕様書、議事録、マニュアル、提案書

---

# 特に作図を含むドキュメントは脳への負担が大きい

- **レイアウト**を考える
- **色**を選ぶ
- **アイコン**を探す
- **線を綺麗に整える**
- **文字サイズ**を調整
- **修正が入るたびに微調整**

---

# そこで提案 💡

## **Markdown** + **Cursor** + **Claude** + **draw.io 拡張**

- すべて一つのエディタで完結
- AI が図も文章も生成
- Git でバージョン管理
- コードと同じ場所に保管

---

# 実演 🎬

Terraform コードから構成図を生成

```hcl
resource "aws_vpc" "demo_vpc" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true
}
resource "aws_instance" "web_server" {
  ami                    = data.aws_ami.amazon_linux.id
  instance_type          = "t3.micro"
  subnet_id              = aws_subnet.private_subnet_1.id
  vpc_security_group_ids = [aws_security_group.web_sg.id]
}
# ... 以下、省略（全381行）
```

---

## 指示文

「この Terraform コードを元に、AWS 構成図を.drawio ファイルで作成してください。AWS のアイコンを利用してください。」

---

<!-- ![AWS構成図](./aws.drawio.png) -->

## 結果

<!-- <div style="text-align: center;">
  <img src="./aws.drawio.png"  height="500  px" >
</div> -->

---

## 待っている間に

<div style="text-align: center;">
  <img src="./curry.drawio.png"  height="500  px" >
</div>

---

## さらなるメリット

- **図の修正も一瞬**（AI に再指示するだけ）
- **多言語対応も簡単**（翻訳 AI と連携）
- **検索性抜群**（テキストベース）
- **チーム共有簡単**（GitHub/GitLab）

---

<!-- _class: section-title -->

# ありがとうございました 🙏
