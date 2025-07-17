# 実習：HTMLとCSSでWebページを作成しよう

HTMLとCSSを使って、個人ホームページまたは自分の興味のあるテーマに関するWebページを作成してください。

作成にあたっては、以下の要件をすべて満たすようにしましょう。

## 作成要件

### ファイル構成

HTMLファイルとCSSファイルは別々に作成し、以下のディレクトリ構成に従って保存してください．

```plain text
my_website/
├── index.html
└── assets/
    └── images/
├── css/
    └── styles.css
```

### HTMLファイルの要件

以下の基本的なHTMLタグを使用してください

- 見出し要素: `<h1>`，`<h2>`
- 段落要素: `<p>`
- リンク要素: `<a>`
- 画像要素: `<img>`
- その他必要な要素

### CSSファイルの要件

CSSファイルでは、以下のセレクタを使用してスタイルを適用してください。

- Universal Selector (`*`)
- Class Selector (`.class-name`)
- その他必要なSelectors

背景色やフォントサイズ、余白などを適宜設定してください。

### 画像の使用

- 1枚以上の画像を使用してください。
- 画像の内容は自由ですが、Webページのテーマに合ったものを選びましょう。

### 生成AIの使用

生成AIを使用しても構いませんが、以下の点に注意してください。
- **Trust but verify**: 生成AIの出力をそのまま信じず、必ず自分で確認してください。
- 生成AIの出力をそのまま使用するのではなく、**必ず理解してから**実装してください。
  - わからない内容が生成された場合は、生成AIに質問したり，google検索を利用して調べてください。

### プライバシーへの配慮

個人情報やプライベートな内容は含めないでください。例えば、実際の住所や電話番号、個人の写真などは避けてください。

## 参考テンプレート

参考テンプレートは，講義で紹介した内容を基に作成されています。このテンプレートをベースにWebページを作成しても構いません．

- `list-style: none;`: リストのデフォルトの箇条書きを削除します。
- `display: inline-block;`: リストアイテムを横並びに表示します。

### 参考例の構成

```plain text
my_website/
├── index.html
└── assets/
    └── images/
        └── profile.jpg
├── css/
    └── styles.css
```

### CSSファイル

```css
/* styles.css */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Arial', sans-serif;
    background: #f0f2f5;
    color: #333;
}

.container {
    width: 800px;
    margin: 50px auto;
    background: #fff;
    padding: 30px;
    border-radius: 12px;
}

.header {
    text-align: center;
    margin-bottom: 30px;
}

.profile-image {
    width: 140px;
    height: 140px;
    border-radius: 50%;
    border: 3px solid #007acc;
    margin-bottom: 16px;
}

h1 {
    font-size: 2.2rem;
    color: #222;
}

.bio {
    font-size: 1rem;
    margin-top: 10px;
    color: #666;
}

.section {
    margin-top: 40px;
}

.section h2 {
    font-size: 1.3rem;
    color: #007acc;
    border-left: 5px solid #007acc;
    padding-left: 10px;
    margin-bottom: 15px;
}

.skills ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.skills li {
    display: inline-block;
    background: #e6f2fb;
    padding: 8px 14px;
    margin: 5px;
    border-radius: 20px;
    font-size: 14px;
}

.social a {
    margin-right: 18px;
    color: #007acc;
    text-decoration: none;
    font-weight: bold;
    font-size: 0.95rem;
}

.social a:hover {
    color: #005f99;
    text-decoration: underline;
}
```

### HTMLファイル

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="ja">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="css/styles.css">
    <title>法政 太郎 | ホームページ</title>
</head>

<body>
    <div class="container">
        <div class="header">
            <img src="assets/images/profile.jpg" alt="法政 太郎のプロフィール画像" class="profile-image" />
            <h1>法政 太郎</h1>
            <p class="bio">1年生...</p>
        </div>

        <div class="section">
            <h2>学歴</h2>
        </div>

        <div class="section">
            <h2>趣味</h2>
        </div>

        <div class="section">
            <h2>スキル</h2>
            <div class="skills">
                <ul>
                    <li>HTML</li>
                    <li>CSS</li>
                    <li>C</li>
                </ul>
            </div>
        </div>

        <div class="section">
            <h2>連絡先</h2>
            <div class="social">
                Email: <a href="#">you@example.com</a>
            </div>
        </div>
    </div>
</body>

</html>
```