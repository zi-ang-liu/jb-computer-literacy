# 擬似コード

:::{important} Objective 
- 代入、選択構造、反復構造を理解する。
- 簡単なアルゴリズムを擬似コードで表現できる。
:::

アルゴリズムは、さまざまな方法で表現できる。代表的な方法には、フローチャート、擬似コードがある。

**擬似コード**（Pseudocode）は、アルゴリズムを記述するための表記法である。厳密な構文はないが、自然言語より明確にアルゴリズムを表現できる。ここでは、曖昧さのない一般的に使われる擬似コードの表記法を紹介する。

## 代入

**代入**（assignment）とは、変数に値を設定する操作である。代入の擬似コードは以下の通りである。

$$
\texttt{variable} \gets \texttt{expression}
$$

$\texttt{variable}$は変数、$\texttt{expression}$は値や式を表す。記号$\gets$は「代入」を意味する。プログラミング言語では、代入は通常`=`記号で表現される。

例えば、利益は収入からコストを引いた値と定義される。これを擬似コードで表現すると以下のようになる。

$$\texttt{profit} \gets \texttt{revenue} - \texttt{cost}$$

さらに、収入とコストを入力として、利益を出力するアルゴリズムは以下のように表現できる。

```{prf:algorithm} 利益計算
:label: profit-calculation
**Input**: revenue, cost   
**Output**: profit

1. $\texttt{profit} \gets \texttt{revenue} - \texttt{cost}$
```

以下は、PythonとC言語での実装例である。

<!-- :::{note}
PythonはGoogle Colabの環境で簡単に実行できる。以下の手順で試してみよう。

1. [Google Colab](https://colab.research.google.com/)にアクセスする。
2. 「新しいノートブック」をクリックする。
3. 上記のコードをコピーして、セルに貼り付ける。
4. セルを実行する。
::: -->

```{code} python
:label: profit-python
:caption: Calculating profit in Python
revenue = 1000
cost = 600
profit = revenue - cost
print(profit)
```

```{code} c
:label: profit-c
:caption: Calculating profit in C
#include <stdio.h>
int main() {
    int revenue = 1000;
    int cost = 600;
    int profit = revenue - cost;
    printf("%d\n", profit);
    return 0;
}
```

## 選択構造

選択構造（selection structure）は、条件に基づいて異なる処理を実行するための構造である。擬似コードでは、以下のように表現される。

```{prf:algorithm} selection structure
:label: selection-structure

1. **if** condition **then**
   1. activity
2. **else**
   1. activity
```

読みやすくするために、擬似コードでは、字下げを用いて制御範囲を示す。Pythonでは、字下げが構文の一部であるため、特に重要である。

`condition`は条件式で、結果は`True`または`False`である。条件が`True`の場合、`then`以下の処理が実行され、`False`の場合は`else`以下の処理が実行される。

例えば、成績を判定するアルゴリズムは以下のように表現できる。

```{prf:algorithm} 成績判定
:label: score-evaluation

**Input**: $\texttt{score}$   
**Output**: $\texttt{result}$

1. **if** $\texttt{score} \geq 60$ **then**
   1. $\texttt{result} \gets \texttt{"Pass"}$
2. **else**
   1. $\texttt{result} \gets \texttt{"Fail"}$
```

以下は、PythonとC言語での実装例である。

```{code} python
:label: score-python
:caption: Evaluating score in Python
score = 75
if score >= 60:
    result = "Pass"
else:
    result = "Fail"
print(result)
```

```{code} c
:label: score-c
:caption: Evaluating score in C
#include <stdio.h>
int main() {
    int score = 75;
    char result[10];
    if (score >= 60) {
        sprintf(result, "Pass");
    } else {
        sprintf(result, "Fail");
    }
    printf("%s\n", result);
    return 0;
}
```

## 反復構造

反復構造（repetition structure）は、特定の条件が満たされるまで同じ処理を繰り返すための構造である。擬似コードでは、以下のように表現される。

```{prf:algorithm} repetition structure
:label: repetition-structure
1. **while** condition **do**
   1. activity
```

例えば、1からnまでの整数の合計、$\sum_{i=1}^{n} i$を計算するアルゴリズムは以下のように表現できる。

```{prf:algorithm} 合計計算
:label: sum-calculation
**Input**: $\texttt{n}$   
**Output**: $\texttt{sum}$

1. $\texttt{sum} \gets 0$
2. $\texttt{i} \gets 1$
3. **while** $\texttt{i} \leq \texttt{n}$ **do**
   1. $\texttt{sum} \gets \texttt{sum} + \texttt{i}$
   2. $\texttt{i} \gets \texttt{i} + 1$
```

以下は、PythonとC言語での実装例である。

```{code} python
:label: sum-python
:caption: Calculating sum in Python
n = 10
sum = 0
i = 1
while i <= n:
    sum += i
    i += 1
print(sum)
```

```{code} c
:label: sum-c
:caption: Calculating sum in C
#include <stdio.h>
int main() {
    int n = 10;
    int sum = 0;
    int i = 1;
    while (i <= n) {
        sum += i;
        i++;
    }
    printf("%d\n", sum);
    return 0;
}
```

反復構造は、よく一連のデータを順番に処理する場合に使用される。このような処理に対し、for-eachという構造を用いることもある。擬似コードでは、以下のように表現される。

```{prf:algorithm} for-each structure
:label: for-each-structure
1. **for each** item in collection **do**
   1. activity
```

例えば、`[1, 2, 3, 4, 5]`というリストの各要素の2乗を計算するpythonのコードは以下のようになる。

```{code} python
:label: for-each-python
:caption: For-each structure in Python
numbers = [1, 2, 3, 4, 5]

for number in numbers:
    square = number ** 2
    print(square)
```


## 練習問題

```{exercise}
:label: maximum-value

3つの整数を入力として受け取り、その中で最大の値を出力するアルゴリズムを擬似コードで表現し、任意のプログラミング言語で実装しなさい。
```

````{solution} maximum-value
:label: maximum-value-solution
:class: dropdown

擬似コードの解答例は省略。

```{code} python
:label: maximum-value-python
:caption: Finding maximum value in Python
def find_maximum(x1, x2, x3):
    x_max = x1
    if x2 > x_max:
        x_max = x2
    if x3 > x_max:
        x_max = x3
    return x_max
```

```{code} c
:label: maximum-value-c
:caption: Finding maximum value in C
#include <stdio.h>
int find_maximum(int x1, int x2, int x3) {
    int x_max = x1;
    if (x2 > x_max) {
        x_max = x2;
    }
    if (x3 > x_max) {
        x_max = x3;
    }
    return x_max;
}
```
````


