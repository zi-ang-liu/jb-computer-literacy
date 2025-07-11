# 生成AIの活用

## 生成AIとは

**生成AI**（generative artificial intelligence）とは，生成モデルを用いて，テキスト，画像，音声などのコンテンツを自動生成する人工知能の一種である．**生成モデル**（generative model）は，大量のデータを学習し，与えられた入力に対して新しいデータを生成する．

2022年11月にChatGPTが公開されたことで，生成AIは急速に普及し，個人や企業，研究機関などで広く利用されるようになった．これに続き，Microsoft Copilot，Claude，Geminiなど多くの生成AIが登場している．

| チャットボット    | 開発元    | 初版       |
| ----------------- | --------- | ---------- |
| ChatGPT           | OpenAI    | 2022年11月 |
| Microsoft Copilot | Microsoft | 2023年2月  |
| Claude            | Anthropic | 2023年3月  |
| Gemini            | Google AI | 2023年3月  |

:::{note}
**GPT**（Generative Pre-trained Transformer）は，OpenAIが開発した大規模言語モデルのシリーズである．GPT-1は，2018年に発表された論文「[Improving Language Understanding by Generative Pre-Training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf)」で紹介された．ChatGPTの公開当初はGPT-3（Generative Pre-trained Transformer 3）という大規模言語モデルを用いていた．
:::

## 生成AIの分類

生成AIは、出力の形式に基づいて以下のように分類できる。

- テキスト生成
- 画像生成
- 音声生成
- 動画生成

また，入力と出力の形式によって以下のように分類できる。

- text-to-text
- text-to-image
- image-to-image
- image-to-text
- image-to-video
- video-to-video

さらに，**マルチモーダルモデル**（multimodal model）は，テキスト，画像，音声，動画などの複数の形式のデータを入力として受け取り，多様な形式のデータを出力する生成AIである．

生成AIを活用することで，日常生活，ビジネス，研究，教育などの様々な場面で業務の効率化が可能となる．

## テキストを生成してみよう

テキスト生成は，生成AIの中でもよく利用されている分野である．テキスト生成の応用例としては，以下のようなものが挙げられる．

- 要約生成
- 文章生成
- 質問応答
- 翻訳
- データ分析
- プログラム生成   

:::{note}
**テキスト生成の難しさ**

英語アルファベットの26文字と空白文字からなる$n$文字の文章を生成する場合，$27^{n}$通りの組み合わせが考えられる．例えば，100文字の文章を生成する場合，$27^{100}$通りの組み合わせが存在し，このうち意味のある文章は極めて少ない．
:::

**練習問題**
- [ChatGPT](https://chatgpt.com/)にアクセスし，チャットボットと会話してみよう．
- `Hello, world!`と出力するC言語のプログラムをChatGPTに生成させ，[OnlineGDB](https://www.onlinegdb.com/)で実行してみよう．
- 本日の東京の天気をChatGPTに尋ねてみよう．


## プロンプトエンジニアリング

生成AIの分野において，**プロンプト**（prompt）とは，生成AIに与える入力データのことを指す．生成AIの回答は，プロンプトによって大きく異なるため，プロンプトの設定が重要である．**プロンプトエンジニアリング**（prompt engineering）とは，適切なプロンプトを設定する技術であり，言語モデルの性能を向上させるための重要な手法である．

:::{note}
プロンプトエンジニアリングに関するサイト

- [Prompt Engineering Guide](https://www.promptingguide.ai/jp)
- [Prompt Engineering (OpenAI)](https://platform.openai.com/docs/guides/prompt-engineering)

:::

ここでは，大規模言語モデルからより良い出力を得るためのプロンプトエンジニアリングの手法を紹介する．

### 具体的な指示を書く

生成AIに与えるプロンプトは，明確で具体的な指示を含むことが重要である．指示が曖昧だと，望ましい出力を得ることが難しくなる．

「プロンプトエンジニアリングについて説明してください。」と聞くと，生成AIは一般的な説明を行うが，どのレベルの説明を求めているのかが不明確である．

- **悪い例**：「プロンプトエンジニアリングについて説明してください。」
- **良い例**：「大学一年生向けにプロンプトエンジニアリングの概念を2~3文で説明してください。」

「アメリカ合衆国財務長官の名前は何ですか？」と聞くと，どの時代の財務長官の名前を求めているのかが不明確である．

- **悪い例**：「アメリカ合衆国財務長官の名前は何ですか？」
- **良い例**：「第１代アメリカ合衆国財務長官の名前は何ですか？在任期間も教えてください。」

### 生成AIに役割を与える

生成AIには，特定の役割を与えることで，その役割に応じた出力を得ることができる．

- **例**：「あなたは現代詩人です。どのような質問にも、現代詩のスタイルで回答してください。説明や補足は不要です。口語表現ではなく、美しい日本語を用いてください。プログラミングの再帰の概念について説明してください。」
- **例**：「あなたはお笑い芸人です。どのような質問にも、お笑いのスタイルで回答してください。大学一年生向けにプロンプトエンジニアリングの概念を2~3文で説明してください。」

### 例文を使用する

的確なプロンプトを設定することが難しい場合，例文を使用することで，生成AIに適切な出力を生成させることができる．この手法を**Few-shot prompting**と呼ぶ．

以下の例では，文を肯定的，中立的，否定的に分類するプロンプトを示している．

```markdown
これはすごい．//肯定的
休暇はまずまずでした．//中立的
昨日の会議はつまらなかった．//否定的
今日の講義は面白かった．//
```

### 記号を使用する

ChatGPTなどの生成AIは，Markdown，LaTeXの書式を理解することができる．これらの記号を使用することで，生成AIがプロンプトを理解しやすくなる．特に，LaTexの書式を使用することで，数式を含むプロンプトを生成AIに与えることができる．

:::{note}
このページはMarkdownの記法を用いて作成されている．Markdownは，講義ノート，Webページ，プログラムのドキュメントなど，様々な場面で利用される軽量マークアップ言語である．興味のある方は，[Markdown記法](https://www.markdownguide.org/basic-syntax/)を学習してみると良い．
:::

まず，よく使用されるMarkdownの記号を紹介する．

| 記号 | 説明              |
| ---- | ----------------- |
| `#`  | 見出し（レベル1） |
| `##` | 見出し（レベル2） |
| `-`  | 箇条書き          |
| `1.` | 番号付き箇条書き  |
| `**` | 太字              |
| `*`  | 斜体              |

LaTeXの書式を用いて，数式をプロンプトに含めることもできる．大学の数学の講義では，難解な数式を生成AIに説明させることができる．

LaTeXの書式では，`$`で囲むことで**インライン数式**（inline equation）を記述することができる．例えば，`$y = ax + b$`は，$y = ax + b$と表示される．

`$$`で囲むことで**ディスプレイ数式**（display equation）を記述することができる．例えば，`$$y = ax + b$$`は，

$$y = ax + b$$

と表示される．

下の例では，数学問題を解決するPythonプログラムを生成AIに作成させるプロンプトを示している．

```markdown
# 問題文

円の面積$A$は，次の式で与えられる：

$$A = \pi r^2$$

ここで：
- $A$は面積である．
- $r$は円の半径である．

## 指示

1. 半径が与えられたときに円の面積を計算するPythonプログラムを書いてください．
2. 半径が5単位の円でプログラムをテストしてください．
```

## 様々な生成AI

- 画像生成
  - [DALL-E 3](https://openai.com/index/dall-e-3/)
- 音声生成
  - [Suno](https://suno.ai/)
  - [SOUNDRAW](https://soundraw.io/)
- 動画生成
  - [Sora](https://openai.com/sora/)
- Coding Assistant
  - [GitHub Copilot](https://github.com/features/copilot)
  - [Cursor](https://www.cursor.com/)

## 参考情報

- [大学・高専における生成AIの教学面の取扱いについて](https://www.mext.go.jp/b_menu/houdou/2023/mext_01260.html)，文部科学省
- [AIに関する暫定的な論点整理](https://www8.cao.go.jp/cstp/ai/ronten_honbun.pdf)，内閣府AI戦略会議
- [生成AIツールに対する基本的考え方](https://www.hoseikyoiku.jp/lf/back_news/view.php?c=topics_view&pk=1687401621)，法政大学
- [生成AIに関する注意点](https://www.tlsc.osaka-u.ac.jp/project/generative_ai/important_point.html)，大阪大学
- [生成AIの利用ガイドライン](https://www.jdla.org/document/#ai-guideline)，日本デイープラーニング協会
- [What are the best AI tools for research? Nature’s guide](https://www.nature.com/articles/d41586-025-00437-0?utm_medium=organic_social&utm_source=wechat&utm_campaign=CONR_NAJRN_ATT1_AP_CNCM_002EB_weeklybrf)
- [DeepSeek-V3](https://github.com/deepseek-ai/DeepSeek-V3)
- [lerobot](https://github.com/huggingface/lerobot)
- [高等学校情報科「情報Ⅱ」教員研修用教材(本編)](https://www.mext.go.jp/a_menu/shotou/zyouhou/detail/mext_00742.html)

## 実習

プロンプトエンジニアリングの基本的な知識を活かしながら、生成AIを実際に使ってみましょう。そのうえで、学習にどう役立つかを体験的に考え、自分の意見や感想をまとめてみてください。

1. 生成AIを活用することで、どのように勉強の効率を上げたり、理解を深めたりできると思いますか？具体的な使い方の例や、あなた自身の学びにどのように応用できそうかもあわせて書いてみましょう。
2. 大学の課題、レポート、論文の作成に生成AIを使うことについて、あなたはどう考えますか？
   - 道徳的な観点にはどんなものがあるでしょうか？
   - 自分自身の学習や成長にどのような影響があると思いますか？