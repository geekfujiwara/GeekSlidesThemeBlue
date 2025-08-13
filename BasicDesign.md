 - input を解析し、5項目程度のスライドの目次を作成する。目次に基づき、各ページを作成する。
 - headにて、以下のコードにてCSSとグラフ表示用のスクリプトを読み込む: 
   `<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">` 
   `<script src="https://cdn.jsdelivr.net/npm/chart.js@3.9.1/dist/chart.min.js"></script>`
 - 全てのページは、タイトルとしてtitle、フッターとしてfooterを表示する。
 - 全てのページのサイズは 1280px × 720px で固定する。このサイズを超えないように、コンテンツの量と、コンテンツの高さを調整する。
 - ページとページの間にはmarginを20px設定する。
 - メインとなる情報はcontainer-leftに表示し、補足する情報をcontainer-rightに表示する。
 - ハイライトしたい箇所はinfo-boxを利用する。
 - 注意点はwarning-boxを利用する。
 - インプットにデータがある場合は、グラフを作成する。グラフの作成にはChart.js のプラグインを利用する。この際、レイアウトが崩れないように高さはページ全体で720pxを超えないように注意する。
 - インプットに画像のURLがある場合は、スライドにも利用して表示する。この際、レイアウトが崩れないように高さはページ全体で720pxを超えないように注意する。
 - 箇条書きは3点程度にまとめ、feature-list, feature-item, feature-dotを利用する。
 - 強調するポイントは gallery-container, gallery-card, card-title, card-description を利用する。
 - container-leftには、gallery-container, gallery-card, card-title, card-description, feature-list, info-box, 必要に応じてグラフを含める。 container-rightには、補足情報や警告情報をwarning-box, feature-list を利用して表示する。gallery-container内には、2列のgallery-cardを含め、gallery-cardは4個程度作成する。グラフがあるページには2列のgallery-cardを含め、gallery-cardは2個作成し、その下にグラフを作成して表示する。

#### 最初のページ
最初のページにはタイトルスライドを作成する。
   タイトルスライドの内容: 
   (1) container-leftには、titleを使用してスライドのタイトルを記載する。また、サマリをinfo-box、アクションアイテムをwarning-box、keyword-container, keyword を利用してキーワードを表示する。
   (2) container-rightには、目次を作成する。目次にはそのページへのリンクが有る。目次はfeature-list, feature-item, feature-dotで1列に表示されるようにする。

#### その他のページ
   (1) container-leftには、titleを使用してページのタイトルを記載する。強調するポイントを説明する。グラフがある場合は、強調するポイントの下に表示する。
   (2) container-rightには、ポイントを内容を箇条書きで説明する。補足する内容はinfo-box、注意点があればwarning-boxを利用する。

#### 最後のページ
最後のページには引用のリンク集をcontainer-leftにgallery-cardで記載する。container-rightには、warning-box, feature-list, feature-item, feature-dot を利用する。
