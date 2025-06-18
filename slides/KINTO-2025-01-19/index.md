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
      cover; /* 例: 全体を覆うように調整 */
    /* 表紙ページ特有の他のスタイルがあればここに追加 */
    /* 例: テキストの色を白にするなど */
    /* color: white; */
    background-position:
      top right,
      bottom right; /* <- メイン背景の基準位置 */
    background-size:
      1280px,
      500px; /* <- メイン背景のサイズ */
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
    border-radius: 20px; /* 角を丸くする */
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
    border-radius: 20px; /* 角を丸くする */
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
header: 地味に効く、ドキュメント作成のAI活用術 | Mutsumix
-->

<!--
footer: 2025-06-19 | 生成 AI と働く— エンジニア現場でのリアルな活用方法
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

# コードは AI に任せられるようになりました

---

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

# AI 時代、ドキュメントは <br>Markdown 記法で書くことが進んでいくと勝手に予想

## 現状：

README.md、Notion、Slack、Zenn、Qiita、GitHub Issues

## 今後：

設計書、仕様書、議事録、マニュアル、提案書

### なぜなら

文章を構造化して表現できるので、意図を適切に AI に汲み取らせやすい

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

# 実演してみます 🎬

## Terraform コードから構成図を生成

```hcl
# VPC
resource "aws_vpc" "demo_vpc" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support   = true
}
# EC2 Instance
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

<style scoped>
  section {
    text-align: center;
    font-size: 48px;
  }
</style>

# ありがとうございました 🙏
