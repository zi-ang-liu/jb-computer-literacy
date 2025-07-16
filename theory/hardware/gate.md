# ゲート

これまではコンピューターにおいて重要な記数法である2進数について学んだ。そして、0と1のビットを使って、数値や文字などのデータを表現する方法についても触れた。

ここでは、2進数の計算を行うための装置であるゲートについて学ぶ。

学習の目標は次の通りである：

- 真理値表，論理式、記号を使って基本的な論理ゲートを理解する
- AND，OR，NOT，XOR，NAND，NORゲートの動作を理解する

## ブール演算

ビットは一般的に0または1と表現されるが，FalseまたはTrueという**真理値**としての表現もよく使われる．

このような真理値（0と1）を扱うための数学的な体系を**ブール代数**（Boolean algebra）と呼ぶ．ブール代数は，イギリスの数学者**ジョージ・ブール**（George Boole）によって考案された．ブール演算は，AND，OR，NOT，XORなどの論理演算子を使って真偽値を操作する．

## ゲート

コンピューターでは，**ゲート**（gate，論理ゲート，logic gate）と呼ばれる装置を使ってブール演算を実行する．ゲートは，一つまたは複数の入力信号を受け取り，それらの信号を処理して出力信号を生成する．

ここでは，以下の基本的な論理ゲートを紹介する．

- OR
- AND
- NOT
- XOR
- NAND
- NOR

これらのゲートをの紹介には，論理式，真理値表，記号を使う．

- **論理式**（Boolean expressions）は，数学記号を使って，数式で真理値の演算を表現する．
- **真理値表**（truth table）は，ゲートのすべての入力組み合わせに対して，出力の真理値を示す表である．
- **記号**（MIL symbols）は，論理ゲートを図で表現するための記号である．[CircuitVerse](https://circuitverse.org/)という論理回路のシミュレータを使って、ゲートの動作を視覚的に確認することもできる。

### ORゲート

$A$と$B$を真理値とするとき，$A$と$B$の論理和（logical disjunction）は，$A \lor B$と書く．

$A$と$B$の少なくとも一方が$1$のとき，$A \lor B = 1$となる．


論理和の真理値表は以下の通りである．

| $A$ | $B$ | $A \lor B$ |
| --- | --- | ---------- |
| 0   | 0   | 0          |
| 0   | 1   | 1          |
| 1   | 0   | 1          |
| 1   | 1   | 1          |

論理和の演算を行うORゲートは次の記号で表現される．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/1/16/OR_ANSI_Labelled.svg
:label: or_gate
:alt: OR Gate
:width: 200px
:align: center

ORゲート
:::

### ANDゲート

$A$と$B$を真理値とするとき，$A$と$B$の**論理積**（logical conjunction）は，$A \land B$と書く．

$A$と$B$の両方が$1$のとき，$A \land B = 1$となる．

論理積の真理値表は以下の通りである．

| $A$ | $B$ | $A \land B$ |
| --- | --- | ----------- |
| 0   | 0   | 0           |
| 0   | 1   | 0           |
| 1   | 0   | 0           |
| 1   | 1   | 1           |

論理積の演算を行うANDゲートは次の記号で表現される．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/b/b9/AND_ANSI_Labelled.svg
:label: and_gate
:alt: AND Gate
:width: 200px
:align: center

ANDゲート
:::

### NOTゲート

$A$を真理値とするとき，$A$の**否定**（logical negation）は，$\lnot p$と書く．

$A$が$1$のとき，$\lnot A = 0$となり，$A$が$0$のとき，$\lnot A = 1$となる．

否定の真理値表は以下の通りである．

| $A$ | $\lnot p$ |
| --- | --------- |
| 0   | 1         |
| 1   | 0         |

否定の演算を行うNOTゲートは次の記号で表現される．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/6/60/NOT_ANSI_Labelled.svg
:label: not_gate
:alt: NOT Gate
:width: 200px
:align: center

NOTゲート
:::

### XORゲート

$A$と$B$を真理値とするとき，$A$と$B$の**排他的論理和**（exclusive or）は，$A \oplus B$と書く．

$A$と$B$のうち一方だけが$1$のとき，$A \oplus B = 1$となる．

排他的論理和の真理値表は以下の通りである．

| A   | B   | A XOR B |
| --- | --- | ------- |
| 0   | 0   | 0       |
| 0   | 1   | 1       |
| 1   | 0   | 1       |
| 1   | 1   | 0       |

排他的論理和の演算を行うXORゲートは次の記号で表現される．

:::{figure} https://upload.wikimedia.org/wikipedia/commons/1/17/XOR_ANSI_Labelled.svg
:label: xor_gate
:alt: XOR Gate
:width: 200px
:align: center

XORゲート
:::

### NANDゲート

$A$と$B$を真理値とするとき、$A$と$B$の**否定論理積**は、$A \uparrow B$と書書く。NANDはNot ANDの略で、ANDゲートの出力を否定したものである。

$$
A \uparrow B = \lnot (A \land B)
$$

否定論理積の真理値表は以下の通りである。

| $A$ | $B$ | $A \uparrow B$ |
| --- | --- | -------------- |
| 0   | 0   | 1              |
| 0   | 1   | 1              |
| 1   | 0   | 1              |
| 1   | 1   | 0              |

否定論理積の演算を行うNANDゲートは次の記号で表現される。

:::{figure} https://upload.wikimedia.org/wikipedia/commons/e/e6/NAND_ANSI_Labelled.svg
:label: nand_gate
:alt: NAND Gate
:width: 200px
:align: center

NANDゲート
:::

### NORゲート

$A$と$B$を真理値とするとき、$A$と$B$の**否定論理和**は、$A \downarrow B$と書く。NORはNot ORの略で、ORゲートの出力を否定したものである。

$$
A \downarrow B = \lnot (A \lor B)
$$

否定論理和の真理値表は以下の通りである。

| $A$ | $B$ | $A \downarrow B$ |
| --- | --- | ---------------- |
| 0   | 0   | 1                |
| 0   | 1   | 0                |
| 1   | 0   | 0                |
| 1   | 1   | 0                |

否定論理和の演算を行うNORゲートは次の記号で表現される。

:::{figure} https://upload.wikimedia.org/wikipedia/commons/c/c6/NOR_ANSI_Labelled.svg
:label: nor_gate
:alt: NOR Gate
:width: 200px
:align: center

NORゲート
:::

## まとめ

- ANDゲートは、両方の入力が1のときに出力が1になる。
- ORゲートは、少なくとも一方の入力が1のときに出力が1になる。
- NOTゲートは、入力が1のときに出力が0になり、入力が0のときに出力が1になる。
- XORゲートは、入力のうち一方だけが1のときに出力が1になる。
- NANDゲートは、ANDゲートの出力を否定したもので、両方の入力が1のときに出力が0になる。
- NORゲートは、ORゲートの出力を否定したもので、両方の入力が0のときに出力が1になる。

| ゲート |       記号       |
| :----: | :--------------: |
|  AND   |   $A \land B$    |
|   OR   |    $A \lor B$    |
|  NOT   |    $\lnot A$     |
|  XOR   |   $A \oplus B$   |
|  NAND  |  $A \uparrow B$  |
|  NOR   | $A \downarrow B$ |

## プログラミング言語での論理演算

C言語では、真理値は整数型で表現され、`0`は偽（False）、`1`は真（True）として扱われる。

以下のC言語のコードは，`2 > 1`が真であり、`1`を出力する．`2 < 1`が偽であり、`0`を出力する．

```c
#include <stdio.h>

int main() {  
  printf("%d\n", 2 > 1); // 1
  printf("%d\n", 2 < 1); // 0
  return 0;
}
```

Pythonでは，`True`と`False`を使って真理値を表現する．

以下のPythonのコードは、`2 > 1`が真であり、`True`を出力する．`2 < 1`が偽であり、`False`を出力する．

```python
print(2 > 1)  # True
print(2 < 1)  # False
```

C言語では、論理和の演算は`||`演算子を使って表現される．例えば、`A || B`は、$A$または$B$のいずれかが真である場合に真を返す．

```c
#include <stdio.h>
int main() {
    int A = 1; // 真
    int B = 0; // 偽
    printf("A OR B = %d\n", A || B); // 出力: 1
    return 0;
}
```

C言語では、論理積の演算は`&&`演算子を使って表現される．例えば、`A && B`は、$A$と$B$の両方が真である場合に真を返す．

```c
#include <stdio.h>
int main() {
    int A = 1; // 真
    int B = 0; // 偽
    printf("A AND B = %d\n", A && B); // 出力: 0
    return 0;
}
```

C言語では、否定の演算は`!`演算子を使って表現される．例えば、`!A`は、$A$が真である場合に偽を返し、$A$が偽である場合に真を返す．

```c
#include <stdio.h>
int main() {
    int A = 1; // 真
    printf("NOT A = %d\n", !A); // 出力: 0
    return 0;
}
```

### やってみよう

ユーザーから2つの真理値（0または1）を入力として受け取り、AND、OR、NOT、XORの演算結果を表示するC言語のプログラムを作成してみよう。

作成したプログラムを実行すると、次のような出力が得られる。`Enter A`と`Enter B`の後に、0または1を入力することができる。

```plain
Please enter A and B, where A and B are either 0 or 1.
Enter A: __1__
Enter B: __0__
A = 1, B = 0

*** Logical Operations ***
A AND B = 0
A OR B = 1
NOT A = 0
A XOR B = 1
```

#### 解答例

```c
#include <stdio.h>

int main() {
    int A, B;
    printf("Please enter A and B, where A and B are either 0 or 1.\n");
    printf("Enter A: ");
    scanf("%d", &A);
    printf("Enter B: ");
    scanf("%d", &B);
    printf("A = %d, B = %d\n", A, B);

    printf("*** Logical Operations ***\n");
    printf("A AND B = %d\n", A && B);
    printf("A OR B = %d\n", A || B);
    printf("NOT A = %d\n", !A);
    printf("A XOR B = %d\n", A ^ B);
    return 0;
}
```