# HTMLによるWebページの作成

**HTML**（HyperText Markup Language）は，ハイパーテキストを記述するためのマークアップ言語です．

HTMLファイルは，`*.html`という拡張子を持ちます．

:::{note}
ハイパーテキストとマークアップ言語とは？

**ハイパーテキスト**（HyperText）とは，ハイパーリンク（hyperlink）を通じて，他の文書やファイルへアクセスできるテキストのことです．例えば，「[こちら](https://www.google.com)」というリンクをクリックすると，Googleのウェブページに移動します．

**マークアップ言語**（Markup Language）とは，マークをつけて文書の構造や修飾などを記述する言語のことです．例えば，`<b>Example</b>`は，`Example`というテキストを太字で表示することを指示します．マークアップという言葉は，印刷物の作成時に，赤ペンやハイライトで文書にマークをつけることに由来します．

**Markdown**（マークダウン）は，軽量なマークアップ言語である．Plain Text形式で文書を記述し，HTMLなどのフォーマットに変換することができます．Markdownは，readmeファイル，ドキュメント、ブログ記事などの作成に広く使用されています．この講義資料もMarkdown言語で記述されています．
:::

## VS CodeでのHTMLファイルの作成

Visual Studio Code（VS Code）はMicrosoftが開発している統合開発環境（Integrated Development Environment, IDE）です。C、Python、Javaなどのプログラミング言語をサポートしており、HTML、CSSなどのウェブ開発にも対応しています。

### HTMLファイルを作成する手順

1. 作業フォルダー「my_website」を作成します。
2. VS Codeを起動します。
3. 「ファイル」メニューから「フォルダーを開く」を選択し、「my_website」フォルダーを開きます。
4. 「ファイル」メニューから「新しいファイル」を選択し、`index.html`という名前でファイルを保存します。
5. 作成した`index.html`ファイルに内容を入力します。
6. <kbd>Ctrl</kbd> + <kbd>S</kbd>を押して保存します。
7. エクスプローラーから`index.html`をダブルクリックしてブラウザで開くと、ウェブページが表示されます。

## 練習

以下の内容を`index.html`ファイルに入力して、ブラウザで表示して、結果を確認しましょう。

```html
<!DOCTYPE html>
<html lang="ja">

<head>
  <meta charset="UTF-8">
  <title>Page Title</title>
</head>

<body>
  <h1>This is a heading</h1>
  <p>This is a paragraph.</p>
</body>

</html>
```

## もっと学びたい方へ

以下のリンクからHTMLの基本を体系的に学べます。

- [MDN HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools HTML](https://www.w3schools.com/html)

