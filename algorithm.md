# アルゴリズム

```{epigraph}
Today, computer science has established itself as the science of algorithms.

-- G. Brookshear and D. Brylow, Computer Science: An Overview, 13th ed. Pearson, 2018.
```

:::{important} Objective 
- アルゴリズムの概念を理解する。
- 代入、選択構造、反復構造を理解し、擬似コードで表現できる。
- 簡単な問題に対して、アルゴリズムを設計し、擬似コードで表現できる。
:::



## アルゴリズムとは

**アルゴリズム**（algorithm）とは、問題を解決するための手順を指す。今までは、いくつかのアルゴリズムを紹介してきた。

CPUが実行する命令サイクルは、3つの基本的なステップからなる簡単なアルゴリズムである。

```{prf:algorithm} CPU命令サイクル
:label: cpu-instruction-cycle

1. **命令の取得**（fetch）：メモリから次の命令を取得する。
2. **命令の解読**（decode）：取得した命令を解読する。
3. **命令の実行**（execute）：解読した命令を実行する。
```

10進数から他の記数法への変換は、以下のようなアルゴリズムで行われる。

```{prf:algorithm} 10進数から$n$進数への変換
:label: decimal-to-n-base

1. 与えられた値を$n$で割り、商と余りを求める。
2. 商が0になるまで繰り返す。
3. 商が0になったら、余りを逆順に並べる。
```

正式に定義すると、アルゴリズムは明確な命令を持ち、有限のステップで実行可能な手順である。

- Unambiguous（明確）：アルゴリズムの各ステップは明確で、解釈の余地がない。
- Finite（有限）：アルゴリズムは有限のステップで完了する。

> An algorithm is an ordered set of unambiguous, executable steps that defines a terminating process.
> 
> -- G. Brookshear and D. Brylow, Computer Science: An Overview, 13th ed. Pearson, 2018.

> (An algorithm is a set of) unambiguous instructions for solving a problem or subproblem in a finite amount of time using a finite amount of data.
> 
> -- N. Dale and J. Lewis, Computer science illuminated, 7th ed. Sudbury, MA: Jones and Bartlett, 2024.

  
## アルゴリズムの表現

アルゴリズムは、さまざまな方法で表現できる。代表的な方法には、フローチャート、擬似コードがある。

## 擬似コード

**擬似コード**（Pseudocode）は、アルゴリズムを記述するための表記法である。厳密な構文はないが、自然言語より明確にアルゴリズムを表現できる。

ここでは、曖昧さのない一般的に使われる擬似コードの表記法を紹介する。

### 代入

**代入**（assignment）とは、変数に値を設定する操作である。代入の擬似コードは以下の通りである。

$$
\texttt{variable} \gets \texttt{expression}
$$

例えば、給与とボーナスの合計を計算する場合、擬似コードは以下のようになる。

$$\texttt{sum} \gets \texttt{salary} + \texttt{bonus}$$

さらに、給与とボーナスを入力として、合計を出力するアルゴリズムは以下のように表現できる。

```{prf:algorithm} 収入計算
:label: income-calculation
**Input**: salary, bonus   
**Output**: sum

1. $\texttt{sum} \gets \texttt{salary} + \texttt{bonus}$
```

以下は、PythonとC言語での実装例である。

```{code} python
:label: income-python
:caption: Calculating income in Python
salary = 400
bonus = 100
sum = salary + bonus
print(sum)
```

```{code} c
:label: income-c
:caption: Calculating income in C
#include <stdio.h>
int main() {
    int salary = 400;
    int bonus = 100;
    int sum = salary + bonus;
    printf("%d\n", sum);
    return 0;
}
```

### 選択構造

選択構造（selection structure）は、条件に基づいて異なる処理を実行するための構造である。擬似コードでは、以下のように表現される。

```{prf:algorithm} selection structure
:label: selection-structure

1. **if** condition **then**
   1. activity
2. **else**
   1. activity
```

例えば、

```{prf:algorithm} 成績判定
:label: score-evaluation

**Input**: $\texttt{score}$

1. **if** $\texttt{score} \geq 60$ **then**
   1. print "Pass"
2. **else**
   1. print "Fail"
```

以下は、PythonとC言語での実装例である。

```{code} python
:label: score-python
:caption: Evaluating score in Python
score = 75
if score >= 60:
    print("Pass")
else:
    print("Fail")
```

```{code} c
:label: score-c
:caption: Evaluating score in C
#include <stdio.h>
int main() {
    int score = 75;
    if (score >= 60) {
        printf("Pass\n");
    } else {
        printf("Fail\n");
    }
    return 0;
}
```

### 反復構造

