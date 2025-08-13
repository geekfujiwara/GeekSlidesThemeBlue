# 🎯 HTMLスライドジェネレーター

このツールは、**入力されたテキストやファイル**に基づいて、クリーンでモダンな印象を持つ**スライドHTML**を自動生成するPower Apps キャンバスアプリです。  

スライドは **目的（objective）** に沿って構成され、ストーリー性のあるスライドを作成することが可能です。

AI Builder にはプロンプト内に **Tailwind CSS** と **カスタムCSS** 、 **カスタムプロンプト** が含まれており、視認性とレイアウトに優れたスライドを構築します。  

>[!Note]
>カスタムCSSやカスタムプロンプトはアプリからユーザーにより変更することができます。設定情報はユーザーごとにDataverseに保存されます。

## 出力されるスライド (HTML) のイメージ

以下のようなスライドを作成することができます。

<img width="1602" height="753" alt="image" src="https://github.com/user-attachments/assets/4a32c5f4-96bb-4dde-b7a1-2e7de48caba1" />

<img width="1603" height="910" alt="image" src="https://github.com/user-attachments/assets/c1b7570f-8247-4edb-9957-531865c94f85" />

<img width="1596" height="758" alt="image" src="https://github.com/user-attachments/assets/73991426-4476-4f24-8eea-d358bdd36113" />

<img width="1596" height="759" alt="image" src="https://github.com/user-attachments/assets/e090ccdd-29d2-4b7f-a26a-d7a34a4bb12f" />

## インストール

[こちらからソリューションファイル](https://github.com/geekfujiwara/HtmlSlideGen/releases/tag/ExpressSlide)を入手できます。

Power Apps ソリューションからインポートしてお使いください。

## 前提条件
以下のライセンスが必要です。

- Power Apps Premium ライセンス
- AI Builder 容量

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
