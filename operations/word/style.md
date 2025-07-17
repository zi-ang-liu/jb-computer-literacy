# スタイルの設定

「ホーム」タブの「フォント」グループや「段落」グループから、文字と段落の修飾を設定することができますが、より効率的に、一貫性のある文書を作成するためには、スタイルを使用することが重要です。スタイルを使用すると、以下のようなメリットがあります。

- 文書全体の一貫性を保つことができる
- 文書の修飾を簡単に変更できる
- 目次、索引などの自動生成が可能

特に、論文などの長い文書を作成する場合は、スタイルを先に設定しておくと、後で修飾を変更する際に便利です。

## スタイルの適用

以下の図のように、「ホーム」タブの「スタイル」グループには、「標準」、「見出し1」、「表題」、「引用」などのスタイルが用意されています。

:::{figure} images/style/word_style.png
:label: word_style
:alt: Wordのスタイル
:width: 600px
:align: center

Wordのスタイル
:::

:::{figure-md} word_style
<img src="./images/word_style.png" alt="スタイルの設定" width="600px">

Wordのスタイル
:::

ここから、スタイルの適用方法を説明しますので、以下の内容をワードに入力します。

```
タイトル
序論
本論
標準
強調太字
本論（１）
本論（２）
結論
```

上記の内容を入力すると、以下のようになります。「スタイル」グループを確認すると、「標準」が選択されていることがわかります。これは、デフォルトで入力される文字列に適用されるスタイルです。

:::{figure} images/style/word_style_text.png
:label: word_style_text
:alt: スタイルの設定
:width: 600px
:align: center

「標準」スタイルで入力された文字列
:::

:::{figure-md} word_style_text
<img src="./images/word_style_text.png" alt="スタイルの設定" width="600px">

「標準」スタイルで入力された文字列
:::

それぞれのテキストを選択して、スタイルを適用します。
タイトルには「表題」、
序論、本論、結論には「見出し1」、
標準には「標準」、
強調太字には「強調太字」、
本論（１）、本論（２）には「見出し2」を適用します。

下の図では、スタイルが適用された画面を示しています。見出し１と見出し２のスタイルを適用すると、文字も前に点が付きます。この点は、ワードで見出しが適用されていることを示しています。印刷時には、この点は表示されません。

:::{figure} images/style/word_style_apply.png
:label: word_style_apply
:alt: スタイルの適用
:width: 600px
:align: center

スタイルの適用
:::

:::{figure-md} word_style_apply
<img src="./images/word_style_apply.png" alt="スタイルの適用" width="600px">

スタイルの適用
:::

<kbb>Ctrl</kbb> + <kbb>F</kbb>を押すと、ナビゲーションペインが表示されます。ナビゲーションペインの「見出し」を選択すると、文書内の見出しの一覧が表示されます。また、「本論（１）」と「本論（２）」が「本論」に属して、階層構造になっていることがわかります。
ここから、文書内の見出しをクリックすると、その見出しに移動することができます。

:::{figure} images/style/word_navigation.png
:label: word_navigation
:alt: ナビゲーションペイン
:width: 600px
:align: center

ナビゲーションペイン
:::

:::{figure-md} word_navigation
<img src="./images/word_navigation.png" alt="ナビゲーションペイン" width="600px">

ナビゲーションペイン
:::

## スタイルの変更

### 見出し１のスタイル

「見出し１」のスタイルを変更するには、スタイルの「見出し1」を右クリックして、「変更」を選択します。

:::{figure} images/style/word_style_change.png
:label: word_style_change
:alt: 「見出し1」スタイルの変更
:width: 600px
:align: center

「見出し1」スタイルの変更
:::

:::{figure-md} word_style_change
<img src="./images/word_style_change.png" alt="「見出し1」スタイルの変更" width="600px">

「見出し1」スタイルの変更
:::

「変更」を選択すると、「スタイルの変更」が表示されます。ここでは、フォントサイズを「14」に変更して、「**B**」を選択し、「OK」をクリックします。

:::{figure} images/style/word_style_change3.png
:label: word_style_change2
:alt: 「スタイルの変更」ダイアログ
:width: 600px
:align: center

「スタイルの変更」ダイアログ
:::

:::{figure-md} word_style_change3
<img src="./images/word_style_change3.png" alt="「スタイルの変更」ダイアログ" width="600px">

「スタイルの変更」ダイアログ
:::

「序論」、「本論」、「結論」のスタイルが自動的に変更されます。

:::{figure} images/style/word_style_change4.png
:label: word_style_change4
:alt: スタイルを変更した結果
:width: 600px
:align: center

スタイルを変更した結果
:::

:::{figure-md} word_style_change4
<img src="./images/word_style_change4.png" alt="スタイルを変更した結果" width="600px">

スタイルを変更した結果
:::

### 練習
「見出し2」のスタイルを変更してみましょう。
- フォントサイズを「12」に変更
- 「**B**」を選択

## アウトラインの定義

アウトラインの定義を行うと、見出しに番号を自動的に付けることができます。例えば、以下のように「序論」、「本論」、「結論」に「第１章」、「第２章」、「第３章」の番号を付けることができます。

```
第1章 序論
第2章 本論
第3章 結論
```

「アウトラインの定義」をするには、「ホーム」タブの「段落」グループから、「アウトラインの定義」を選択します。

:::{figure} images/style/word_outline.png
:label: word_outline
:alt: 「アウトラインの定義」の選択
:width: 600px
:align: center

「アウトラインの定義」の選択
:::

:::{figure-md} word_outline
<img src="./images/word_outline.png" alt="「アウトラインの定義」の選択" width="600px">

「アウトラインの定義」の選択
:::

「新しいアウトラインの定義」が表示されます。ここで、「オプション」を選択すると、詳細な設定ができます。

:::{figure} images/style/word_outline2.png
:label: new_outline
:alt: 「新しいアウトラインの定義」ダイアログ
:width: 600px
:align: center

「新しいアウトラインの定義」ダイアログ
:::

:::{figure-md} new_outline
<img src="./images/word_outline2.png" alt="「新しいアウトラインの定義」ダイアログ" width="600px">

「新しいアウトラインの定義」ダイアログ
:::

ここでは、「変更するレベルをクリックしてください：」から、「1」を選択します。そして、「レベルと対応つける見出しスタイル」を「見出し1」に設定します。デフォルトでは、「書式番号」が「1」に設定されていますが、ここでは、「第1章」に変更します。「1」の背景が灰色になっていますが、これは「第1章」、「第2章」、「第3章」という形式で番号が付けられることを示しています。設定し終わりましたら、「OK」をクリックして、文書に戻ります。

:::{figure} images/style/word_outline3.png
:label: word_outline3
:alt: 番号書式の設定
:width: 600px
:align: center

番号書式の設定
:::

:::{figure-md} word_outline3
<img src="./images/word_outline3.png" alt="番号書式の設定" width="600px">

番号書式の設定
:::

「序論」、「本論」、「結論」に「第１章」、「第２章」、「第３章」の番号が自動的に付けられます。

:::{figure} images/style/word_outline4.png
:label: word_outline4
:alt: 「見出し1」スタイルが適用された見出しに番号が付けられる
:width: 600px
:align: center  

「見出し1」スタイルが適用された見出しに番号が付けられる
:::

:::{figure-md} word_outline4
<img src="./images/word_outline4.png" alt="「見出し1」スタイルが適用された見出しに番号が付けられる" width="600px">

「見出し1」スタイルが適用された見出しに番号が付けられる
:::

レベル「2」には、「レベルと対応つける見出しスタイル」を「見出し2」に設定します。デフォルトでは、「書式番号」が「1.1」に設定されています。

:::{figure} images/style/word_outline5.png
:label: word_outline5
:alt: 見出し2の設定
:width: 600px
:align: center

見出し2の番号書式の設定
:::

:::{figure-md} word_outline5
<img src="./images/word_outline5.png" alt="見出し2の設定" width="600px">

見出し2の番号書式の設定
:::

「本論（１）」、「本論（２）」が「第２章」に属していることで、「2.1」、「2.2」の番号が付けられます。

:::{figure} images/style/word_outline6.png
:label: word_outline6
:alt: 「見出し2」スタイルが適用された見出しに番号が付けられる
:width: 600px
:align: center  

「見出し2」スタイルが適用された見出しに番号が付けられる
:::

:::{figure-md} word_outline6
<img src="./images/word_outline6.png" alt="「見出し2」スタイルが適用された見出しに番号が付けられる" width="600px">

「見出し2」スタイルが適用された見出しに番号が付けられる
:::