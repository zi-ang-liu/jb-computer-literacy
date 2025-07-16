# 属性

HTMLの要素は、属性（attribute）を指定することで，その要素の振る舞いや外観を制御できます．

属性は，開始タグに記述され，次の形式で表現されます．

```html
<要素名 属性名="値">内容</要素名>
```

ここでは，`<a>`要素を例に、属性の使い方を説明します．

## a要素とhref属性

`<a>`要素は、リンクを作成するための要素です。「a」はanchorの略で、アンカー要素とも呼ばれます。

書式は以下の通りです。

```html
<a href="リンク先のURL">リンクテキスト</a>
```

### ウェブサイトへのリンク

下記は、「Google」というテキストをクリックすると、Googleのウェブサイトに移動するリンクです。

```html
<a href="https://www.google.com">Google</a>
```

### メールアドレスへのリンク

メールを送信するリンクを作成するには、`mailto:`を使用します。

```html
<a href="mailto:someone@example.com">Send Email</a>
```

「Send Email」のリンクをクリックすると、メールアプリケーションが起動し、指定されたメールアドレスにメールを送信できます。

## 練習

以下の条件を満たす自己紹介用Webページを作成してみましょう。

- `<a>`要素を使用して、メールアドレスへのリンクを作成する。
- `<a>`要素を使用して、法政大学のウェブサイトへのリンクを作成する。

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
  <p>Hello! My name is Hosei Hanako. I am a student at <a href="https://www.hosei.ac.jp">Hosei University</a>.</p>
  <p>I love programming and web development.</p>

  <h2>My Hobbies</h2>
  <p>In my free time, I enjoy reading books, playing video games, and exploring new technologies.</p>

  <p>Author: Hosei Hanako</p>
  <p>Email: <a href="mailto:hanako@example.com">hanako@example.com</a></p>
</body>

</html>
```