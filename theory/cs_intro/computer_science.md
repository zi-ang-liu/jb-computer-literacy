# コンピューターサイエンス

<!-- research has shown that students understand concrete examples more easily than abstract ones, even when the students themselves are abstract thinkers.  -->

## 抽象化

**抽象化**（abstraction）とは、事物や表象を，ある性質・共通性・本質に着目し，それを抽き出す方法である。抽象化により、不要な性質を排除し、複雑なシステムを簡単に利用できるようにする。

現代生活では、自動車、スマートフォン、コンピューターなど、抽象化されたシステムが数多く存在する。これらのシステムは、複雑な内部構造を持ちながらも、ユーザーにとっては簡単に操作できるようになっている。

:::{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/2/24/Dacia_Logan_MCV_Model_2009_05.JPG/330px-Dacia_Logan_MCV_Model_2009_05.JPG
:label: car_engine
:alt: 自動車エンジン
:width: 300px
:align: center

自動車エンジンの原理がわからなくても、自動車の運転はできる。
:::

例えば、スマートフォンを使って、動画をみるときに、スマートフォン・インターネット・動画に関する技術について考える必要はない。ユーザーは、タッチスクリーンを操作するだけで、動画を楽しむことができる。

**考えてみよう**: 普段の生活で、三つの抽象化されたシステムを挙げてみよう。

## コンピューターシステム

**コンピューター**（computer）とは，電子回路を用い，指示された通り自動的にデータの貯蔵・検索・加工を行う装置であり，**電子計算機**とも呼ばれる．**計算機**という言葉は，狭義では電子計算機を指すが，広義では計算を行う装置全般を指す．

コンピューターには，日常生活で使われるパーソナルコンピュータをはじめ，スーパーコンピューター，スマートフォン，タブレットなどがある．個人が利用するために設計されたコンピューターを**パーソナルコンピュータ**（パソコン，PC）と呼ぶ．パソコンは，**デスクトップパソコン**と**ノートパソコン**に分けられる．

下の図は，日本のスーパーコンピューター「富岳」を示している．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/1/15/Fugaku_20200809_3.jpg
:label: Fugaku
:alt: 富岳
:width: 300px
:align: center

兵庫県神戸市に設置されている「富岳」 © [Barsaka2](https://commons.wikimedia.org/wiki/File:RIKEN_R-CCS_Fugaku.jpg), [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/deed.en)
:::

コンピューターは，**ハードウェア**（hardware）と**ソフトウェア**（software）から構成されている．

ハードウェアは，コンピューターを構成する物理的な装置である。
一般的に，ハードウェアは、演算装置、制御装置、記憶装置、入力装置、出力装置から構成される．

ソフトウェアは，コンピューターを利用するためのプログラムの総称である．ソフトウェアは，システムソフトウェアとアプリケーションソフトウェアに分類される．

特定の仕事をするために作成されたソフトウェアを**アプリケーションソフトウェア**（application software）と呼ぶ．ワードプロセッサ，表計算ソフト，電子ゲームなどがアプリケーションソフトウェアの例である．

**システムソフトウェア**（system software）は，コンピューターのハードウェアを制御や管理するためのソフトウェアである．また，アプリケーションソフトウェアが動作するための環境を提供する．よく知られているシステムソフトウェアとして，**オペレーティングシステム**（operating system, OS）がある．Microsoft Windows，macOS，Linux，Androidなどがオペレーティングシステムの例である．

:::{figure} image/hardware_software.svg
:label: hardware_software
:alt: ハードウェアとソフトウェア
:width: 150px
:align: center

ハードウェアとソフトウェア
:::

## コンピューターサイエンスとは

```{epigraph}
A computer system is like an onion, made up of many layers.

-- N. Dale and J. Lewis, Computer science illuminated, 7th ed. Sudbury, MA: Jones and Bartlett, 2024.
```

:::{figure} image/cs.drawio.svg
:label: cs_intro
:alt: コンピューターサイエンス
:width: 150px
:align: center

コンピューターサイエンス
:::

抽象化という概念は、コンピューターサイエンスにおいて重要な役割を果たす。コンピューターサイエンスで、ハードウェア、プログラミングなどは抽象化されたシステムとして扱われる。それらを理解した上で、他の層との関係を学ぶことで、コンピューターシステム全体を理解することができる。

### 情報の表現

- 二進数
- 文字コード
- 画像の表現
- 音声の表現
- 動画の表現

### ハードウェア

- ゲート
- 論理回路
- アーキテクチャ

### プログラミング

- 機械語、アセンブリ言語、高水準言語
- アルゴリズム
- データ構造

### オペレーティングシステム

- Windows, macOS, Linuxなど
- プロセス管理、メモリ管理
- ファイルシステム

### アプリケーション

- Word, Excel, PowerPointなど
- データベース
- 人工知能
- シミュレーション
- 最適化

### ネットワーク

- OSI参照モデル、TCP/IPモデル
- HTMLとCSS
- セキュリティ

## CSと経営システム工学

コンピューターサイエンスは、経営システム工学と密接に関連している。

経営システム工学は、科学的・工学的方法論に基づく、コンピュータを用いて、企業経営を含む社会システムの設計・運用・改善を行う学問である。

経営システム工学においては、主な研究手法として

- システム最適化
- シミュレーション
- データ分析
- モデリング

が用いられる。

経営システム工学の研究対象は，生産システム、物流システム、社会システムなど多岐にわたる。これらのシステムは、多数の要素が相互に作用し、複雑なシステムになっているため，分析や最適化を行うためには、大規模な計算が必要となる。

以下では、いくつかの経営工学において有名な問題と手法を紹介し、なぜコンピューターサイエンスの知識が必要なのかを説明する。

- [巡回セールスマン問題](https://ja.wikipedia.org/wiki/%E5%B7%A1%E5%9B%9E%E3%82%BB%E3%83%BC%E3%83%AB%E3%82%B9%E3%83%9E%E3%83%B3%E5%95%8F%E9%A1%8C)
<!-- - [ナップサック問題](https://ja.wikipedia.org/wiki/%E3%83%8A%E3%83%83%E3%83%97%E3%82%B5%E3%83%83%E3%82%AF%E5%95%8F%E9%A1%8C)
- [最短経路問題](https://ja.wikipedia.org/wiki/最短経路問題) -->
- [モンテカルロ法](https://ja.wikipedia.org/wiki/%E3%83%A2%E3%83%B3%E3%83%86%E3%82%AB%E3%83%AB%E3%83%AD%E6%B3%95)
- [モンテカルロ木探索](https://ja.wikipedia.org/wiki/モンテカルロ木探索)
- [回帰分析](https://ja.wikipedia.org/wiki/%E5%9B%9E%E5%B8%B0%E5%88%86%E6%9E%90)
- [安定結婚問題](https://ja.wikipedia.org/wiki/%E5%AE%89%E5%AE%9A%E7%B5%90%E5%A9%9A%E5%95%8F%E9%A1%8C)
<!-- - [数値解析](https://ja.wikipedia.org/wiki/%E6%95%B0%E5%80%A4%E8%A7%A3%E6%9E%90) -->

**調べてみよう**: 経営システム工学科の[カリキュラム](https://ise-hp.ws.hosei.ac.jp/study/)を調べ、コンピューターサイエンスのどの分野が特に経営システム工学において重要であるかを考えてみよう。

