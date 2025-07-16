# 論理回路

複数の論理ゲートを組み合わせれば，より複雑な**論理回路**（logic circuit）を作ることができる．論理回路は，演算や記憶などを行う．

論理回路には，**組み合わせ回路**（combinational circuit）と**順序回路**（sequential circuit）の2種類がある．

## 組み合わせ回路

組み合わせ回路は，入力信号の状態に応じて出力信号が決まる．例えば，加算を行う加算器が該当する．

### 半加算器

コンピューターでは，もっとも基本的な演算は加算である．加算を行う論理回路は**加算器**（adder）と呼ばれる．加算機には，**半加算器**（half adder）と**全加算器**（full adder）がある．ここでは、半加算器について説明する．

半加算器は以下のような加算を行う．

$$
\begin{array}{r}
  0 \\
+ 0 \\
\hline
  00 \\
\end{array}
$$

$$
\begin{array}{r}  
0 \\
+ 1 \\
\hline
  01 \\
\end{array}
$$

$$
\begin{array}{r}
  1 \\
+ 0 \\
\hline
  01 \\
\end{array}
$$

$$
\begin{array}{r}
  1 \\
+ 1 \\
\hline
  10 \\
\end{array}
$$

半加算器は、二つの入力信号$A$と$B$を受け取り、二つの出力信号$S$と$C$を生成する．ここで、$S$はSum（和）を表し、$C$はCarry（桁上がり）を表す．

半加算器は、次のような真理値表で表される．

| $A$ | $B$ | $C$ | $S$ |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 0   |
| 0   | 1   | 0   | 1   |
| 1   | 0   | 0   | 1   |
| 1   | 1   | 1   | 0   |

$A$，$B$，$S$だけを見ると，これはXORゲートで実現できる．$A$，$B$，$C$だけを見ると，これはANDゲートで実現できる．したがって、半加算器は次のように表現できる．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/d/d9/Half_Adder.svg
:label: half_adder
:alt: half adder
:width: 300px
:align: center

半加算器
:::

## 順序回路

順序回路は，入力信号の状態と内部の状態に応じて出力信号が決まる．例えば，記憶ができるSRラッチやが該当する．

### SRラッチ

SRラッチは、1 bitの情報を記憶するための基本的な順序回路である．

ここでは、二つのNORゲートを用いたSRラッチについて説明する．

NORゲートは、入力信号が両方とも0のときに出力が1になるゲートである．

| $A$ | $B$ | 出力 |
| --- | --- | ---- |
| 0   | 0   | 1    |
| 0   | 1   | 0    |
| 1   | 0   | 0    |
| 1   | 1   | 0    |

SRラッチは、$S$（Set）と$R$（Reset）の二つの入力信号を持ち、出力信号は$Q$と$\bar{Q}$で表される．$Q$は記憶されている値を表し、$\bar{Q}$はその否定を表す．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/c/c6/R-S_mk2.gif
:label: sr_latch
:alt: SR Latch
:width: 300px
:align: center

SRラッチ
:::

SRラッチの動作は次の通りである．

1. $S = 1$，$R = 0$のとき、$Q = 1$，$\bar{Q} = 0$となる．「セット」状態になる．
2. 次に$S = 0$，$R = 0$のとき、出力は変化せず、$Q = 1$，$\bar{Q} = 0$のままとなる．「保持」状態になる．
3. $S = 0$，$R = 1$のとき、$Q = 0$，$\bar{Q} = 1$となる．「リセット」状態になる．
4. 次に$S = 0$，$R = 0$のとき、出力は変化せず、$Q = 0$，$\bar{Q} = 1$のままとなる．「保持」状態になる．
5. $S = 1$，$R = 1$のとき、出力は不定となる．
6. 初期状態では、$S = 0$，$R = 0$とする．$Q$と$\bar{Q}$の初期値は不定である．

## 集積回路

集積回路（IC: Integrated Circuit）は、多数の論理ゲートを一つに集約したものである．集積回路は、論理ゲートの数に応じて、次のように分類される．

| 略語 | Full Name                    | Number of Gates   |
| ---- | ---------------------------- | ----------------- |
| SSI  | Small-Scale Integration      | 1-10 gates        |
| MSI  | Medium-Scale Integration     | 10-100 gates      |
| LSI  | Large-Scale Integration      | 100-100,000 gates |
| VLSI | Very Large-Scale Integration | 100,000+ gates    |

（N. Dale and J. Lewis, Computer science illuminated, 7th ed. Sudbury, MA: Jones and Bartlett, 2024.）

## CPU

コンピューターにおいて、最も重要な集積回路は**中央処理装置**（CPU: Central Processing Unit）である．

## 練習問題

1. 以下の図に示す論理回路の真理値表を作成せよ．

:::{figure} image/circuit-1.drawio.svg
:label: logic_circuit
:alt: Logic Circuit 1
:width: 300px
:align: center

問題1
:::

| A    | B   | Output |
| :--- | --- | ------ |
| 0    | 0   | ア     |
| 0    | 1   | イ     |
| 1    | 0   | ウ     |
| 1    | 1   | エ     |

1. 以下の図に示す論理回路の真理値表を作成せよ．

:::{figure} image/circuit-2.drawio.svg
:label: logic_circuit_2
:alt: Logic Circuit 2
:width: 300px
:align: center

問題2
:::

| A    | B   | Output |
| :--- | --- | ------ |
| 0    | 0   | ア     |
| 0    | 1   | イ     |
| 1    | 0   | ウ     |
| 1    | 1   | エ     |

 

<!-- ## 解答例

| A    | B   | Output |
| :--- | --- | ------ |
| 0    | 0   | 1      |
| 0    | 1   | 0      |
| 1    | 0   | 0      |
| 1    | 1   | 1      |


| A    | B   | Output |
| :--- | --- | ------ |
| 0    | 0   | 0      |
| 0    | 1   | 1      |
| 1    | 0   | 1      |
| 1    | 1   | 1      | --> |