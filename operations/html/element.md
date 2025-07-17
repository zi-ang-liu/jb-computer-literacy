# 要素

HTMLは，**タグ**と呼ばれる特別な記号を使って，文書を記述します．タグには，**開始タグ**と**終了タグ**があります．開始タグと終了タグで囲まれた部分を**内容**と呼びます．開始タグ，内容，終了タグで構成される部分を**要素**と呼びます．

タグは，`<`と`>`で囲まれた文字列です．終了タグは，**要素名**の前に`/`を付けて表現します．要素の一般的な書式は次の通りです：

```html
<要素名>内容</要素名>
```

例えば、以下のように書きます：

```html
<p>これは段落です。</p>
```
この例では、`<p>`が開始タグで、`</p>`が終了タグです．`内容`は「これは段落です。」となります．

## HTMLの基本構造

以下はHTML文書の基本的な構造を示す例です．

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


HTMLファイルの最初に書かれている`<!DOCTYPE html>`は，文書型宣言（Document Type Declaration）と呼ばれ、このファイルが「HTML Living Standard」という最新のHTML仕様で書かれていることを示します．

- `<html>`：HTML文書の最上位要素を表し、ルート要素と呼ばれます．`<head>`要素と`<body>`要素が含まれます。
  - `<head>`：メタデータを記述。
    - `<meta charset="UTF-8">`：文字コードをUTF-8に設定．
    - `<title>`：文書のタイトルを指定します．ブラウザのタグに表示されます．
  - `<body>`：文書の内容を記述．
    - `<h1>`：レベル1の見出し．
    - `<p>`：段落．

HTMLは木構造を持ちます．

```
html
├── head
│   └── title
└── body
    ├── h1
    └── p
```

この例では，
- `<html>`要素は文`<head>`要素と`<body>`要素の親要素
- `<head>`要素と`<body>`要素は`<html>`要素の子要素

<!-- また、下の例では、
- `<p>`要素は`<b>`要素の親要素
- `<b>`要素は`<p>`要素の子要素

```html
<p>This is another paragraph with <b>bold</b> text.</p>
``` -->

## 練習

ここまで学んだ内容を使って、自己紹介用のHTMLページを作ってみましょう。

### 参考例1

```html
<!DOCTYPE html>
<html lang="ja">

<head>
  <meta charset="UTF-8">
  <title>Hosei Hanako's Web Page</title>
</head>

<body>
  <h1>Welcome to My Web Page</h1>

  <h2>About Me</h2>
  <p>Hello! My name is Hosei Hanako. I am a student at Hosei University.</p>
  <p>I love programming and web development.</p>

  <h2>My Hobbies</h2>
  <p>In my free time, I enjoy reading books, playing video games, and exploring new technologies.</p>

  <p>Author: Hosei Hanako</p>
</body>

</html>
```

### 参考例2
下の参考例では，文書の構造を明確にするために、`<header>`要素、`<section>`要素、`<footer>`要素を使用しています．

- `<header>`要素は、ページのヘッダー部分を表します。
- `<section>`要素は、ページのセクションを表します。
- `<footer>`要素は、ページのフッター部分を表します。

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Hosei Hanako's Web Page</title>
</head>

<body>
  <header>
    <h1>Welcome to My Web Page</h1>
  </header>

  <section>
    <h2>About Me</h2>
    <p>Hello! My name is Hosei Hanako. I am a student at Hosei University.</p>
    <p>I love programming and web development.</p>
  </section>

  <section>
    <h2>My Hobbies</h2>
    <p>In my free time, I enjoy reading books, playing video games, and exploring new technologies.</p>
  </section>

  <footer>
    <p>Author: Hosei Hanako</p>
  </footer>
</body>

</html>
```