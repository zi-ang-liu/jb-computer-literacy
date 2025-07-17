# 擬似クラス

擬似クラス（pseudo-class）は、特定の状態にある要素を選択するためのCSSの機能です。

`<a>`要素の擬似クラスを例にとって説明します。

```css
/* styles.css */

a:link {
    color: blue; /* リンクの色 */
}
a:visited {
    color: purple; /* 訪問済みリンクの色 */
}
a:hover {
    color: red; /* ホバー時のリンクの色 */
    text-decoration: underline; /* ホバー時に下線を引く */
}
a:active {
    color: green; /* アクティブ状態のリンクの色（クリックした瞬間） */
}
```

## 例

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
<style>
a:link {
    color: blue; /* リンクの色 */
}
a:visited {
    color: purple; /* 訪問済みリンクの色 */
}
a:hover {
    color: red; /* ホバー時のリンクの色 */
    text-decoration: underline; /* ホバー時に下線を引く */
}
a:active {
    color: green; /* アクティブ状態のリンクの色（クリックした瞬間） */
}
</style>
</head>
<body>

<a href="https://www.wikipedia.org">wikipedia</a>
<a href="https://www.google.com">google</a>

</body>
</html>
```