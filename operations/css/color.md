# 色の指定

CSSでは，色名，RGB, HSL, HEXなどの方法で色を指定できます。

## 色名

代表的な色名として，Tomato, Orange, Gray，Black, Whiteなどがあります。

HTML/CSSでは，[140種類の色名](https://www.w3schools.com/colors/colors_names.asp)が定義されています。

以下は、色名を使用して色を指定する例です。

```css
/* style.css */
h1 {
  background-color: Tomato; 
  color: White;
}
p {
  background-color: gray;
  color: white;
}
```

## RGB

`RGB(red, green, blue)`関数を使用して、`red`、`green`、`blue`の値を指定することによって色を指定できます。各値は0から255の範囲で指定します。

以下は、RGBを使用して色を指定する例です。

| Color | RGB                |
| ----- | ------------------ |
| Red   | `rgb(255, 0, 0)`   |
| Green | `rgb(0, 255, 0)`   |
| Blue  | `rgb(0, 0, 255)`   |
| Black | `rgb(0, 0, 0)`     |
| White | `rgb(255,255,255)` |

[RGB Calculator](https://www.w3schools.com/colors/colors_rgb.asp)を使って，色を調整してみましょう。

以下は、RGBを使用して色を指定する例です。
<!-- index.html --><!-- index.html -->
```css
/* style.css */
h1 {
    background-color: rgb(0, 191, 255);
    color: rgb(255, 255, 255);
}
p {
    background-color: rgb(128, 128, 128);
    color: rgb(255, 255, 255);
}
``` 

## HEX

`#RRGGBB`形式で色を指定することもできます。`RR`、`GG`、`BB`はそれぞれ赤、緑、青の値を`00`から`FF`の16進数で表現します。

以下は、HEXを使用して色を指定する例です。
| Color | HEX       |
| ----- | --------- |
| Red   | `#FF0000` |
| Green | `#00FF00` |
| Blue  | `#0000FF` |
| Black | `#000000` |
| White | `#FFFFFF` |

以下は、HEXを使用して色を指定する例です。

```css
/* style.css */
.DIC161 {
    color: #FF710A;
}
.PANTONE280 {
    color: #223A76;
}
```

```html
<h1>法政大学のスクールカラー</h1>
<p>法政大学のスクールカラーは、<span class="DIC161">オレンジ</span>と<span class="PANTONE280">紺（法政ブルー）</span>です。</p>
```