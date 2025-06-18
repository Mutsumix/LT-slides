---
marp: true
paginate: true
math: mathjax
# theme: su8ru

title: 地味に効く、ドキュメント作成の AI 活用術
description: 2025-06-19 | 生成AIと働く— エンジニア現場でのリアルな活用方法
author: ムツミックス / Mutsumix
# image: https://slides.su8.run/250330-glt06/index.jpg
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

<style scoped>
  section {
    background: #ebf8ff;
  }
</style>

![w:600](./images/hupass.png)

## 北大生による、北大生のための時間割アプリ

---

![bg 92%](./images/timetable.png)

---

![bg 80%](images/search.png)

---

## シラバスを検索できる

→ シラバスを取ってくる必要がある

---

![bg 80%](./images/syllabus.png)

---

![bg 80%](./images/decode.png)

---

```python
from collections import deque

from viewstate import ViewState

def parse_viewstate(encoded_viewstate):
    vs = ViewState(encoded_viewstate)
    data = vs.decode()

    # TODO: 本当にひどいのでなんとかしたい。。。
    classinfo = data[0][1][1][1][1][1][1][3][1][1][1][1][1]
    baseinfo = classinfo[3][1][1][1][1][1][1][1]

    for i in range(len(baseinfo) // 2):
        if not (baseinfo[2 * i + 1][0] is None) and False in baseinfo[2 * i + 1][0]:
            continue
        arraylist = baseinfo[2 * i + 1][1]

        (略)

    return data
```

---

## VIEWSTATE があまりに曲者

なんですが、使わないといけない理由もある

---

- Hupass では授業の主キーを自分たちで採番している
- スクレイピングごとにシラバス側を正として上書きしている

→ 判別するためのキーとして**時間割番号が必要**！！！

---

## なんですが

---

普通に検索すると時間割番号が出てこない（なんで？？）

---

なので、どうにかうまく付き合う方法を考えながら

インデックスアクセスを続けています

---

おわり
