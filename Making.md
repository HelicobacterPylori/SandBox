# MarkDown Documentation

Markdownを使用して、仕事に使える文書を作成する方法をメモ。

## 使用した環境

- Windows 10[^winPc]
- Chromebook[^chromebook]
- Visual Studio Code
  - 以後の本文では、VS Codeと表記します。

可能なら、コミットすると自動でPDFが作られる環境を作りたいですが、まだPDF化の環境が充実していない感じなので、手でPDF化します。

[^winPc]: GPD Pocket
[^chromebook]: ASUS Chromebook C223NA

### 使用するソフトウェア

すべて必要な訳ではないので、必要に応じてインストールする。

|名称|用途など|
|:-----------------|:---------------|
|Visual Studio Code|本文書作成時のバージョンは、1.54.3|
|Java              |PlantUMLの実行に必要|
|Graphviz          |PlantUMLで、シーケンス図とアクティビティ図以外を生成する場合必要|
|Google Chrome     |Markdown-PDFで必要|

### Visual Studio Codeの拡張機能

|名称|用途など|
|:-----------------|:---------------|
|Markdown All in One|Markdownの機能拡張|
|Markdown Preview Enhanced|Markdownのプレビュー表示などの機能拡張|
|Draw.io Integration|手で汎用的な図を描く|
|PlantUML|テキストからUMLなどの図を描く|
|PlantUML Previewer|PlantUMLのプレビュー表示|
|Markdown PDF|MarkdownをPDF等に変換|
|markdownlit|Markdownのエラーをハイライト表示|
|テキスト校正くん|Markdown中のテキストなどを校正|

<div style="page-break-before:always"></div>

## 文書について

### 固い見た目にする

>>>フォントとフォントサイズなどの指定

### 見出しに番号を付ける

文書が、ある程度大きく、またある程度の構造を持つ場合、自動で見出しに番号がついてくれると助かります。
VS Codeの機能拡張で可能なものもありましたが、使い勝手がいまいちだったので、勉強も兼ねてCSSで実現。

>>>やり方

### ページフォーマットを使う

>>>やり方

### .mdファイルの構造化

>>>やり方

>>>ページフォーマットをsvgで背景に指定する方法

<div style="page-break-before:always"></div>

## 図について

markdownでは、比較的簡単なUMLなどならPlantUMLで済ませられるでしょうが、実際にはPlantUMLでは描けない図もあります。
今のところそうした図はDraw.ioしかない気がします。
（もしくは、諦めて別に作成した図を張る）

>>>図番号の処理

### MarkDownで作図（UMLなど単純な図）

@import "fig/fig1.plantuml"

### Drow.ioで作図（複雑な図）

>>>やり方

<div style="page-break-before:always"></div>

## PDF化について

<div style="page-break-before:always"></div>

## 参考

- 【VS Code + Marp】Markdownから爆速・自由自在なデザインで、プレゼンスライドを作る
<https://qiita.com/tomo_makes/items/aafae4021986553ae1d8>

- Markdownを印刷しやすいPDFにする時に私がしていること
<https://blog.mmmcorp.co.jp/blog/2018/11/16/markdown-to-pdf-document/>

- Marpで会社のスライドテンプレを作ってみる
<https://future-architect.github.io/articles/20200812/>

- Visual Studio Code＋Markdownでチャート／グラフ／図を描画するには？
<https://blog.masahiko.info/entry/2019/08/16/160422>

- Visual Studio Code - *.drawio.svg や *.drawio.png の衝撃
<https://qiita.com/anfangd/items/4d9b51063ad3fc675cfe>

- [Visual Studio Code][Windows] PlantUMLの環境を設定する
<https://qiita.com/koara-local/items/e7a7a7d68a4f99a91ab1>

- 【仕事効率化】Visual Studio Code で Markdown を使いこなす
<https://cpp-learning.com/vscode_markdown/>

- Markdown の見出しに章番号を振る方法(ついでに目次にも)
<https://qiita.com/UKawamura/items/42f907c88686fb3be4da>

- ChromeBookのVSCodeで日本語入力できるようにする
<https://gotoblog.org/chromebook-vscode-japanese/>
