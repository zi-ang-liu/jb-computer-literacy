# CSSの基本

## CSSの構文

```css
selector {
  property_1: value_1;
  property_2: value_2;
  ...
  property_n: value_n;
}
```

- `selector`: HTML要素を指定。
- `property`: スタイルのプロパティを指定（例: `color`, `font-size`）。
- `value`: プロパティに適用する値を指定（例: `red`, `16px`）。

次の例では、`h1`要素の文字色を青に、フォントサイズを24pxに設定し、中央揃えにしています。`color`、`font-size`，`text-align`がそれぞれのプロパティで、`blue`、`24px`，`center`がそれぞれの値です。

```css
h1 {
  color: blue;
  font-size: 24px;
  text-align: center;
}
```

## CSSの使用

CSSは、以下の三つの方法でHTMLに適用できます。

- **Inline**: HTML要素の`style`属性を使用して、直接スタイルを指定します。
- **Internal**: HTML文書内の`<style>`タグを使用して、スタイルを定義します。
- **External**: 別のCSSファイルを作成し、HTML文書の`<link>`タグを使用して読み込みます。

Externalは、一般的に最も推奨される方法です。

## Inline CSS

HTML要素の`style`属性を使用して、直接スタイルを指定します。例えば、以下のように記述します。

```html
<h1 style="color: blue;">A blue heading</h1>
<p style="color: red;">A red paragraph</p>
```

## Internal CSS

HTML文書内の`<style>`タグを使用して、スタイルを定義します。以下のように記述します。

```html
<!DOCTYPE html>
<html>

<head>
  <title>Internal CSS Example</title>
  <style>
    h1 {
      color: blue;
    }

    p {
      color: red;
    }
  </style>
</head>

<body>
  <h1>A blue heading</h1>
  <p>A red paragraph</p>
</body>

</html>
```

## External CSS

別のCSSファイルを作成し、HTML文書の`<link>`タグを使用して読み込みます。

```
my_website/
├── index.html
└── assets/
    └── images/
├── css/
    └── styles.css
```

```html
<!-- index.html -->
<!DOCTYPE html>
<html>

<head>
  <title>Internal CSS Example</title>
  <link rel="stylesheet" href="css/styles.css">
</head>

<body>
  <h1>A blue heading</h1>
  <p>A red paragraph</p>
</body>

</html>
```

```css
/* styles.css */
h1 {
  color: blue;
}
p {
  color: red;
}
```

## 練習

以下の内容を`styles.css`ファイルに入力し、`index.html`ファイルで読み込んで、ブラウザで表示して、結果を確認しましょう。

```css
/* styles.css */
h1 {
  text-align: center;
  color: blue;
  font-size: 24px;
}
p {
  color: red;
  font-size: 16px;
}
```