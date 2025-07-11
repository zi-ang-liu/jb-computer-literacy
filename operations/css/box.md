# CSSボックスモデル

ボックスモデル（box model）は、HTML要素のレイアウトを理解するための基本的な概念です。すべてのHTML要素は、ボックスとして表現され、以下の4つの部分で構成されています。

- **コンテンツ（content）**: 実際の内容が表示される領域。
- **パディング（padding）**: コンテンツとボーダーの間のスペース。
- **ボーダー（border）**: パディングとマージンの間にある線。
- **マージン（margin）**: ボックスの外側のスペース。

:::{figure-md} CSS Box Model
<img src="https://upload.wikimedia.org/wikipedia/commons/7/7a/Boxmodell-detail.png" alt="CSS Box Model" width="500px">

CSSボックスモデル，[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/deed.en)
:::


## ボーダー

`border-style`はボーダーのスタイルを指定するプロパティです。よく使われる値は以下の通りです。

- `none`: ボーダーなし
- `solid`: 実線
- `dashed`: 破線
- `dotted`: 点線

`border-width`はボーダーの太さを指定するプロパティです。

- `thin`: 細いボーダー
- `medium`: 通常のボーダー
- `thick`: 太いボーダー
- `px`: ピクセル単位で指定（例: `2px`）

`border-color`はボーダーの色を指定するプロパティです。色は名前、HEXコード、RGB値などで指定できます。

`border-radius`はボーダーの角を丸くするためのプロパティです。値はピクセル単位で指定します。

以下の例では、ボーダーのスタイル、太さ、色と角の丸みを指定しています。

```css
/* style.css */
#box {
    border-style: solid; /* ボーダーのスタイル */
    border-width: 2px; /* ボーダーの太さ */
    border-color: blue; /* ボーダーの色 */
    border-radius: 10px; /* ボーダーの角を丸くする */
}
```

```html
<!-- index.html -->
<p>The box below has a solid blue border with a width of 2 pixels and rounded corners.</p>
<div id="box" style="width: 200px; height: 100px;">
    This is a box with a solid blue border.
</div>
```

:::{note}

上下左右のボーダーを個別に指定することもできます。例えば、`border-top-style`は上のボーダーのスタイル，`border-bottom-width`は下のボーダーの太さ，`border-left-color`は左のボーダーの色，`border-top-right-radius`は右上の角の丸みを指定します。

また，`border: border-width border-style border-color`のように、ボーダーのスタイル、太さ、色を一度に指定することもできます。

```css
/* style.css */
#box {
    border: 2px solid blue; /* ボーダーのスタイル、太さ、色を一度に指定 */
}
```

:::

## マージン

`margin`は、ボーダーの外側，要素間のスペースを指定するプロパティです。

`margin`は、以下のように指定できます。

```css
/* style.css */
#box {
    /* マージンの指定 */
    margin: 20px;

    /* ボーダーの指定 */
    border-style: solid; 
    border-width: 2px;
}
```

```html
<!-- index.html -->
<p>The box below has a margin of 20 pixels.</p>
<div id="box" style="width: 200px; height: 100px;">
    This is a box with a margin of 20 pixels.
</div>
```

マージンは、個別に指定することもできます。例えば、`margin-top`は上のマージン，`margin-right`は右のマージン，`margin-bottom`は下のマージン，`margin-left`は左のマージンを指定します。

```css
/* style.css */
#box {
    margin-top: 10px; /* 上のマージン */
    margin-right: 20px; /* 右のマージン */
    margin-bottom: 30px; /* 下のマージン */
    margin-left: 40px; /* 左のマージン */
}
```

## パディング

`padding`は、コンテンツとボーダーの間のスペースを指定するプロパティです。

`padding`は、以下のように指定できます。

```css
/* style.css */
#box {
    /* パディングの指定 */
    padding: 20px;

    /* ボーダーの指定 */
    border-style: solid; 
    border-width: 2px;
}
```

```html
<!-- index.html -->
<p>The box below has a padding of 20 pixels.</p>
<div id="box" style="width: 200px; height: 100px;">
    This is a box with a padding of 20 pixels.
</div>
```

パディングも、個別に指定することができます。

- `padding-top`: 上のパディング
- `padding-right`: 右のパディング
- `padding-bottom`: 下のパディング
- `padding-left`: 左のパディング

```css
/* style.css */
#box {
    padding-top: 10px; /* 上のパディング */
    padding-right: 20px; /* 右のパディング */
    padding-bottom: 30px; /* 下のパディング */
    padding-left: 40px; /* 左のパディング */
}
```

## ボックスサイズ

デフォルトでは、要素の`width`と`height`は、コンテンツの幅と高さを指定します。

`box-sizing: border-box;`を指定すると、`width`と`height`にボーダーとパディングのサイズが含まれるようになります。

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Box Model Example</title>
    <style>
        #box1 {
            width: 500px; /* 幅 */
            height: 50px; /* 高さ */
            background-color: lightblue; /* 背景色 */
            border-width: 0px; /* ボーダーの太さ */
            padding: 0px; /* パディング */
            margin: 0px; /* マージン */
        }
        #box2 {
            width: 500px; /* 幅 */
            height: 50px; /* 高さ */
            background-color: lightgreen; /* 背景色 */
            border: 2px solid red; /* ボーダーのスタイル */
            padding: 20px; /* パディング */
            margin: 0px; /* マージン */
        }
        #box3 {
            box-sizing: border-box; /* ボックスサイズをborder-boxに設定 */
            width: 500px; /* 幅 */
            height: 50px; /* 高さ */
            background-color: lightcoral; /* 背景色 */
            border: 2px solid blue; /* ボーダーのスタイル */
            padding: 20px; /* パディング */
            margin: 0px; /* マージン */
        }
    </style>
</head>
<body>
    <p>The boxs below demonstrate the box model.</p>
    <div id="box1">
        This is box 1.
    <div id="box2">
        This is box 2 with a border and padding.
    </div>
    <div id="box3">
        This is box 3 with box-sizing set to border-box.
    </div>
</body>
</html>
```

ボックス全体のサイズは`width + padding + border`で計算されます。

- `box1`
  - 幅: 500
  - 高さ: 50
- `box2`: 
  - 幅: 500 + 20 (左パディング) + 20 (右パディング) + 2 (左ボーダー) + 2 (右ボーダー) = 544
  - 高さ: 50 + 20 (上パディング) + 20 (下パディング) + 2 (上ボーダー) + 2 (下ボーダー) = 94
- `box3`:
  - 幅: 500 
  - 高さ: 50 

`box-sizing: border-box;`を指定すると、要素の全体的なサイズを簡単に制御できるため，下記のようなコードがよく使われます。

```css
* {
    box-sizing: border-box; 
    padding: 0; 
    margin: 0; 
}
```


## ボックスモデルの例

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Box Model Example</title>
    <style>
        #box {
            width: 200px; /* 幅 */
            height: 100px; /* 高さ */
            background-color: lightblue; /* 背景色 */
            border-style: solid; /* ボーダーのスタイル */
            border-width: 2px; /* ボーダーの太さ */
            border-color: blue; /* ボーダーの色 */
            border-radius: 10px; /* ボーダーの角を丸くする */
            padding: 20px; /* パディング */
            margin: 30px; /* マージン */
        }
    </style>
</head>
<body>
    <div id="box">
        This is a box with a solid blue border, padding of 20 pixels, and a margin of 30 pixels.
    </div>
</body>
</html>
```