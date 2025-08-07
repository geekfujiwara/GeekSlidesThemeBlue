# 🎯 カスタムCSSスライドジェネレーター

このプロジェクトは、**入力テキスト（input）**に基づいて、クリーンでモダンな印象を持つ**スライドHTML**を自動生成するツールです。  
**Tailwind CSS**と**カスタムCSS**を組み合わせて、視認性とレイアウトに優れたスライドを構築します。  
スライドは**目的（objective）**に沿って構成され、ストーリー性のある説明が可能です。

## 出力されるスライド (HTML) のイメージ

<img width="1912" height="954" alt="image" src="https://github.com/user-attachments/assets/0f8c9a4d-9f4a-424e-a4e9-3e1384cd49b1" />

<img width="1912" height="954" alt="image" src="https://github.com/user-attachments/assets/62a147a1-46f3-46f2-97d2-0411b8761828" />

<img width="1912" height="954" alt="image" src="https://github.com/user-attachments/assets/b80b9eed-3709-4a72-95c3-17f1295aa8f0" />


---

## 📌 特徴

- ✅ Tailwind CSSとカスタムCSSによる美しいデザイン
- ✅ スライド構成は input を解析して自動生成
- ✅ コンテンツの左右分割レイアウト（`container-left` / `container-right`）
- ✅ 以下の要素を活用可能：
  - `info-box`: 強調表示
  - `warning-box`: 注意喚起
  - `keyword`: キーワード表示
- ✅ 重要ポイントはギャラリーカード形式で表示

---

## 応用シナリオ例

* 自律型エージェント の一つのアクションにして、ニュースを自動的にスライドにする
* Copilot Studio とのインタラクティブなチャットから、自動的にスライドにする。
* Power Apps からファイルをアップロードしてスライドにする
* Power Apps からURLを指定してスライドにする
* スケジュールフローからRSSを元にスライドにする
* Power Apps から仕様書を元にスライドにする

## 🧩 スライド構成

### 1. タイトルスライド

- **container-left**
  - `title`: スライドのタイトル
  - `info-box`: サマリ
  - `warning-box`: アクションアイテム
  - `keyword-container`, `keyword`: キーワード表示
- **container-right**
  - `gallery-container`, `gallery-card`: 目次（各ページへのリンク付き）

### 2. 重要ポイントスライド

- **共通要素（左右）**
  - `gallery-container`, `gallery-card`: 重要なポイントをカード形式で表示

### 3. 引用・リンク集スライド

- **container-left**
  - `gallery-card`: 引用リンク集
- **container-right**
  - `warning-box`: 注意点
  - `feature-list`, `feature-item`, `feature-dot`: 補足情報

---

## 🎨 使用CSS

Tailwind CSSをCDNで読み込み、以下のカスタムCSSを使用しています。

## 🚀 利用方法
1. AI Builder にプロンプトを登録します。
`{input}` と `{objective}` の部分は、入力から作成してください。

```
入力テキスト {input} に 基づく、カスタムCSSを利用した、クリーンでモダンな印象とレイアウト、コントラストを考慮した読みやすいテキスト配置のスライドのHTMLコードを作成する。スライドの利用目的は {objective} であり、その目的に沿って構成と説明のストーリーを考える。
## 条件
### 基本デザイン
 - input を解析し、スライドの目次を作成する。目次に基づき、各ページを作成する。
 - ヘッダにて、以下のコードにてCSSを読み込む: 
   `<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">` 
 - すべてのページは、 タイトルはtitle、フッターはfooter, ページサイズは 1280px × 720px で固定する。
 - メインとなる情報はcontainer-leftに表示し、補足する情報をcontainer-rightに表示する。
 - ハイライトしたい箇所はinfo-boxを利用する。
 - 注意点はwarning-boxを利用する。
 - 箇条書きは3点までにまとめ、feature-list, feature-item, feature-dotを利用する。
 - 重要なポイントの説明は gallery-container, gallery-card, card-title, card-description を利用する。
 - container-leftには、feature-list、info-box を利用する。container-rightには、warning-box, feature-list を利用する。

#### 最初のページ
最初のページにはタイトルスライドを作成する。
   タイトルスライドの内容: 
   (1) container-leftには、titleを使用してスライドのタイトルを記載する。また、サマリをinfo-box、アクションアイテムをwarning-box、keyword-container, keyword を利用してキーワードを表示する。
   (2) container-rightには、目次を作成する。目次にはそのページへのリンクが有る。目次はgallery-card, .gallery-containerで1列に表示されるようにする。

#### 2ページ目
スライド全体の重要なポイントの説明を行う。
 - 重要なポイントの説明は gallery-container, gallery-card, card-title, card-description を利用する。

#### 最後のページ
最後のページには引用のリンク集をcontainer-leftにgallery-cardで記載する。container-rightには、warning-box, feature-list, feature-item, feature-dot を利用する。
 
### カスタムCSS
<style>
    .title {
        color: #1a56db;
        font-size: 3rem;
        font-weight: 700;
        margin-bottom: 2rem;
        line-height: 1.2;
    }
    
    /* 丸角カード（ギャラリー用） */
     .gallery-container {
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
    }
   .gallery-card {
        background-color: #ffffff;
        border-radius: 16px;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
        padding: 1rem;
        margin-bottom: 1rem;
    }

.card-title {
    font-size: 1.2rem;
    font-weight: 700;
    color: #1f2937;
    margin-bottom: 0.5rem;
}

.card-description {
    font-size: 0.95rem;
    color: #4b5563;
    line-height: 1.4;
}

    .info-box {
        background-color: #e6f0ff;
        border-left: 4px solid #3b82f6;
        padding: 1rem;
        margin-bottom: 1.5rem;
        border-radius: 12px;
    }
    .info-box-title {
        color: #1d4ed8;
        font-weight: 700;
        margin-bottom: 0.5rem;
    }
    .warning-box {
        background-color: #fff7e6;
        border-left: 4px solid #f59e0b;
        padding: 1rem;
        margin-bottom: 1.5rem;
        border-radius: 12px;
    }

    .warning-title {
        color: #b45309;
        font-weight: 700;
        margin-bottom: 0.5rem;
    }

    body, html {
        margin: 0;
        padding: 0;
        font-family: 'Noto Sans JP', sans-serif;
        background: linear-gradient(135deg, #e0f2fe, #f0f4f8);
        min-height: 100vh;
    }

    .container {
        display: flex;
        width: 100%;
        min-height: 600px;
    }

    .container-left {
        width: 70%;
        padding: 2rem;
        background-color: #ffffff;
        border-radius: 16px 0 0 16px;
    }

    .container-right {
        width: 30%;
        padding: 2rem;
        background-color: #f9fafb;
        border-left: 1px solid #e5e7eb;
        border-radius: 0 16px 16px 0;
    }
        .keyword-container {
        display: flex;
        flex-wrap: wrap;
        gap: 0.75rem;
        margin-top: 1rem;
    }
    .keyword {
        background-color: #dbeafe;
        color: #1e40af;
        font-weight: 500;
        padding: 0.5rem 1rem;
        border-radius: 20px;
        display: flex;
        align-items: center;
    }
    .keyword i {
        margin-right: 0.5rem;
    }
        .feature-list {
        margin-top: 2rem;
    }
    .feature-item {
        display: flex;
        align-items: start;
        margin-bottom: 1rem;
    }
    .feature-dot {
        color: #3b82f6;
        font-weight: bold;
        margin-right: 0.75rem;
        font-size: 1.5rem;
        line-height: 1;
    }
  </style>
```

実際に設定するとこのようなイメージになります。

<img width="1912" height="954" alt="image" src="https://github.com/user-attachments/assets/e17d0cae-3baa-4f68-8687-0ced84974eaa" />

2. AI Builder のインプットには以下を入力します。

* input にスライドの元となるテキストを入力します
* objective にスライドの目的を記述します

> [!Note]
> Power Automate では以下のようなイメージになります。
><img width="1123" height="817" alt="image" src="https://github.com/user-attachments/assets/28f1b3c4-5ed3-4aa6-8559-baa9e8a4f3c8" />


3. HTMLスライドが作成されます。

スライドHTMLが自動生成され、各ページが構成されます

## 🛠️ カスタマイズ
CSSは必要に応じて自由に調整可能です

スライド構成は input の内容に応じて柔軟にカスタマイズ可能です

## 📎 ライセンス
MIT License

👤 作者
[Geek Fujiwara](https://x.com/geekfujiwara)
