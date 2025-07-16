# よく使うタグ

HTMLでWebページを作成する際に頻繁に使うタグを紹介します。

## 見出し

HTMLでは、見出しを作成するためにh1からh6までの要素を使用します。hは"heading"の略で、数字が小さいほど見出しのレベルが高くなります。

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

## 改行

`<br>`要素はテキストの途中で改行したいときに使用します。

```html
<p>This is a line.<br>This is another line.</p>
```

:::{note}

段落を分けたい場合はp要素を使用しましょう。

```html
<p>これは1つ目の段落です。</p>
<p>これは2つ目の段落です。</p>
```
:::

## 文字装飾

| タグ       | 説明 | 見た目 |
| ---------- | ---- | ------ |
| `<b>`      | 太字 | 太字   |
| `<strong>` | 強調 | 太字   |
| `<i>`      | 斜体 | 斜体   |
| `<em>`     | 強調 | 斜体   |


```html
<p>This is <b>bold</b> text.</p>
<p>This is <strong>strong</strong> text.</p>
<p>This is <i>italic</i> text.</p>
<p>This is <em>emphasized</em> text.</p>
```

## リスト

### 番号付きリスト

`<ol>`要素は、番号付きリストを作成するために使用されます。各項目は`<li>`要素で表されます。

```html
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

### 箇条書きリスト

`<ul>`要素は、箇条書きリストを作成するために使用されます。各項目は`<li>`要素で表されます。

```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

## 引用

### blockquote要素

`<blockquote>`要素は、引用を示すために使用されます。

```html
法政大学の目的は、以下のとおりである。

<blockquote cite="https://www.hosei.ac.jp/hosei/daigakugaiyo/rinen/rinen/">
    <ol>
        <li>「自由と進歩」の精神と公正な判断力をもって、主体的、自立的かつ創造的に、新しい時代を構築する市民を育てる。</li>
        <li>学問の自由に基づき、真理の探究と「進取の気象」によって、学術の発展に寄与する。</li>
        <li>多様化する地球規模の課題を解決し、「持続可能な地球社会の構築」に貢献する。</li>
    </ol>
</blockquote>
```

### q要素

`<q>`要素は、短い引用を示すために使用されます。通常、引用符で囲まれます。

```html
<p><q>Anyone who has never made a mistake has never tried anything new.</q> - Albert Einstein</p>
```

### address要素

`<address>`要素は、連絡先情報を示すために使用されます。

```html
<address>
  3-7-2 Kajino-cho<br>
  Koganei-shi, Tokyo 184-8584<br>
  Japan
</address>
```

## Emoji

HTMLでは、Emojiを直接使用することができます。

```html
<p>Here is a grinning face: 😀</p>
<p>Here is a grinning face: &#128512;</p>
```

以下ではいくつかの代表的なEmojiとそのコードを示します。

| Emoji | コード      |
| ----- | ----------- |
| 😀     | `&#128512;` |
| 😂     | `&#128514;` |
| ❤️     | `&#10084;`  |
| 🎉     | `&#127881;` |

## div要素

`<div>`要素は、他のHTML要素をグループ化するために使用されます。`style`属性を使用して、背景色や文字色などを指定することができます。

```html
<div style="background-color:yellow;">
    <h2>Paris</h2>
    <p>Paris is a city in France.</p>
</div>

<div style=" background-color:rebeccapurple; color:white;">
    <h2>New York</h2>
    <p>New York is a city in the United States.</p>
</div>

<div style="background-color:lightblue; color:black;">
    <h2>Tokyo</h2>
    <p>Tokyo is a city in Japan.</p>
</div>
```

## span要素

`<span>`要素は、テキストの一部をスタイル付けするために使用されます。`style`属性を使用して、文字色や背景色などを指定することができます。

:::{note}

`<div>`要素と`<span>`要素はよく似ていますが、`<div>`要素はブロックレベル要素（block-level element）である。一方、`<span>`要素は、インライン要素（inline element）であり、テキストの一部をスタイル付けするために使用されます。

:::

```html
<p>This is a <span style="color: red;">red</span> word.</p>
<p>This is a <span style="background-color: yellow;">highlighted</span> word.</p>
<p>This is a <span style="font-weight: bold;">bold</span> word.</p>
<p>This is a <span style="font-style: italic;">italic</span> word.</p>
```