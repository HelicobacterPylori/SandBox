#

## 文書について

### CSSの調整

さっとメモ的に使うだけならデフォルトで全然問題ないのですが、多少とも仕事で点検に出すような文書とするために、`Markdown Preview Enhanced`のCSSを調整します。

具体的には、`Markdown Preview Enhanced:Customize Css`を実行すると次のように`style.less`が表示されるので、７行目に相当する箇所に、以降の各章で挙げる必要な設定を追加していきます。

````css {.line-numbers}
/* Please visit the URL below for more information: */
/*   https://shd101wyy.github.io/markdown-preview-enhanced/#/customize-css */

.markdown-preview.markdown-preview {
  // modify your style here
  // eg: background-color: blue;

}
````

#### 文書の見た目を整える

私は`h1`を文章タイトルとし、実際の文章は`h2`から書くようにしています。そのため、次の設定により`h1`はセンタリングで下線を付けし、`h2`〜`h6`のフォントサイズは本文と同じフォントサイズに戻しています。

```css {.line-numbers}
  h1 {
    text-align: center;
    text-decoration: underline;
  }

  h2, h3, h4, h5, h6 {
    font-size:initial;
  }
```

また各段落の先頭は必ず1文字字下げするよう、次の設定を行っています。

```css {.line-numbers}
  p {
    text-indent: 1em;
  }
```

#### 見出しに項番を付ける

文書が、ある程度大きく、またある程度の構造を持つ場合、自動で見出しに項番がついてくれると助かります。

VS Codeの機能拡張で可能なものもありましたが、使い勝手がいまいちだったので、勉強も兼ねてCSSで実現。とりあえず`h2`〜`h4`に自動で項番を付けます。

```css {.line-numbers}
  h1 {
    counter-reset: Lv1;
  }

  h2 {
    counter-reset: Lv2;
  }

  h3 {
    counter-reset: Lv3;
  }

  h2::before{
    counter-increment: Lv1;
    content: counter(Lv1) ". ";
  }

  h3::before{
    counter-increment: Lv2;
    content: counter(Lv1) "." counter(Lv2) " ";
  }

  h4::before{
    counter-increment: Lv3;
    content: counter(Lv1) "." counter(Lv2) "."counter(Lv3) " ";
  }
```

#### 文書全体の字下げを設定する

職場などにより文化の違いはあるでしょうが、大抵は見出しによる字下げなどが定義されているでしょう。

とりあえず一般的な、見出しのレベルにしたがって後ろの各要素を1文字ずつ字下げするようにします。

`h3`、`h4`の見出し自身と、`h2`、`h3`、`h4`に続く`p`、`ol`、`nl`、`pre`、`table`を自動で字下げします。

```css {.line-numbers}
  h2~p, h2~ul, h2~ol, h2~pre, h2~table {
    margin-left: 1em;
  }

  h3 {
      margin-left: 1em;
  }
  h3~p, h3~ul, h3~ol, h3~pre, h3~table {
    margin-left: 2em;
  }

  h4 {
    margin-left: 2em;
  }
  h4~p, h4~ul, h4~ol, h4~pre, h4~table {
    margin-left: 3em;
  }
```



### .mdファイルを構造化する

文書サイズが小さいうちは`.mdファイル`1つで作成できますが、ある程度大きくなると`.mdファイル`を章などの単位で分割したくなります。

どうするのが正しいのか分かりませんが、私は次のように書いた`.mdファイル`を`@import`することにしました。

```markdown {.line-numbers}
#

## 章見出し

本文
```

1行目の空の#は書きたくないのですが、これがないと上手くプレビューされない場合が多いので、必ず入れるようにしました。

ただしそうすると、htmlに空の`h1`タグが表示されて不要な空白になってしまうため、次のCSSで空の`h1`タグを非表示にしています。

```css {.line-numbers}
  h1:empty {
    display:none;
  }
```
