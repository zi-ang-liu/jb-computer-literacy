# 探索アルゴリズム

## 線形探索

**線形探索**（linear search, sequential search）は、与えられたリストから目的の要素があるかどうかを順番に調べる最も単純なアルゴリズムの一つである。

例えば、`[3, 5, 2, 4, 1]`というリストがあるとする。このリストから`4`を探す場合、次のように進める。

1. `3`を読み取る。`4`ではないので次へ。
2. `5`を読み取る。`4`ではないので次へ。
3. `2`を読み取る。`4`ではないので次へ。
4. `4`を読み取る。これが目的の要素である。
5. 探索を終了。

以上は線形探索の一例である。このアルゴリズムを数学記号を用いて、より一般的に表現すると、次のようになる。

$n$個の要素を持つリスト$l$があるとき、ある目的要素$x$が存在するかどうかを調べる線形探索は、次のように定義される。

```{prf:algorithm} squential search
:label: sequential-search

**Input**: リスト $l = [l_1, l_2, \ldots, l_n]$, 目的要素 $x$   
**Output**: $\texttt{found} \in \{\texttt{True}, \texttt{False}\}$

1. $\texttt{found} \gets \texttt{False}$
2. $i \gets 1$
3. **while** $i \leq n$ and $\texttt{found} = \texttt{False}$ **do**
    1. **if** $l_i = x$ **then**
        1. $\texttt{found} \gets \texttt{True}$
    2. **else**
        1. $i \gets i + 1$
4. **return** $\texttt{found}$
```

以下は、PythonとC言語での実装例である。

```{code} python
:label: linear-search-python
:caption: Linear search in Python
def linear_search(l, x):
    found = False
    i = 0
    while i < len(l) and not found:
        if l[i] == x:
            found = True
        else:
            i += 1
    return found

if __name__ == "__main__":
    l = [3, 5, 2, 4, 1]
    x = 4
    print(linear_search(l, x))  # True
```

```{code} c
:label: linear-search-c
:caption: Linear search in C
#include <stdio.h>

int linear_search(int l[], int n, int x) {
    int found = 0; // 0: False, 1: True
    int i = 0;
    while (i < n && !found) {
        if (l[i] == x) {
            found = 1;
        } else {
            i++;
        }
    }
    return found;
}
int main() {
    int l[] = {3, 5, 2, 4, 1};
    int n = sizeof(l) / sizeof(l[0]);
    int x = 4;
    printf("%d\n", linear_search(l, n, x));  // 1 (True)
    return 0;
}
```

### 整列配列に対する線形探索

ソートされた配列を整列配列（sorted array）と呼ぶ。例えば、`[1, 2, 3, 4, 5]`、`['a', 'c', 'd', 'e']`、`["Alice", "Bob", "Charlie"]`などが整列配列である。

このような整列配列に対して、ある要素が存在するかどうかを調べる場合、線形探索を用いることもできるが、効率的ではない。最悪のケースにおいて、全ての要素を調べる必要となる。

線形探索よりも効率的な方法があるかを考えよう。

## 二分探索

**二分探索**（binary search）は、整列配列に対して効率的に要素を探すアルゴリズムである。整列配列の中央の要素と目的の要素を比較し、等しくなければ、半分の要素を排除し、残りの半分に対して再度同じ操作を繰り返す。これを目的の要素が見つかるまで続ける。

例えば、`[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`という整列配列から`10`を探す場合、次のように進める。

1. 中央の要素は`5`。`10`は`5`より大きいので、`[6, 7, 8, 9, 10]`に絞る。
2. 中央の要素は`8`。`10`は`8`より大きいので、`[9, 10]`に絞る。
3. 中央の要素は`9`。`10`は`9`より大きいので、`[10]`に絞る。
4. 中央の要素は`10`。これが目的の要素である。
5. 探索を終了。

線形探索は10回の要素を調べる必要があるが、二分探索は4回の要素を調べるだけで済む。

:::{note}
要素数が奇数の場合、中央の要素は真ん中の要素を指す。偶数の場合は、中央の2つの要素のうち、どちらを選んでもよい。ここでは左側の要素を選ぶことにする。

$L$と$R$はそれぞれ、探索範囲の左端と右端を指すとし、$\lfloor (L + R) / 2 \rfloor$で中央の要素を求める。ここでは、$\lfloor x \rfloor$は$x$の小数点以下を切り捨てた整数を表し、$x$のfloorと呼ばれる。

例えば、$L = 1$、$R = 10$の場合、中央の要素は$\lfloor (1 + 10) / 2 \rfloor = \lfloor 5.5 \rfloor = 5$となる。また、$L = 6$、$R = 10$の場合、中央の要素は$\lfloor (6 + 10) / 2 \rfloor = \lfloor 8 \rfloor = 8$となる。
:::

$n$個の要素を持つ整列配列$l$があるとき、ある目的要素$x$が存在するかどうかを調べる二分探索は、次のように定義される。

```{prf:algorithm} binary search
:label: binary-search

**Input**: 整列配列 $l = [l_1, l_2, \ldots, l_n]$, 目的要素 $x$   
**Output**: $\texttt{found} \in \{\texttt{True}, \texttt{False}\}$

1. $\texttt{found} \gets \texttt{False}$
2. $L \gets 1$
3. $R \gets n$
4. **while** $L \leq R$ and $\texttt{found} = \texttt{False}$ **do**
   1. $m \gets \lfloor (L + R) / 2 \rfloor$  
   2. **if** $l_m = x$ **then**
      1. $\texttt{found} \gets \texttt{True}$
   3. **else if** $l_m < x$ **then**
      1. $L \gets m + 1$
   4. **else**
      1. $R \gets m - 1$
5. **return** $\texttt{found}$
```

以下は、PythonとC言語での実装例である。

```{code} python
:label: binary-search-python
:caption: Binary search in Python
def binary_search(l, x):
    found = False
    L = 0
    R = len(l) - 1
    while L <= R and not found:
        m = (L + R) // 2
        if l[m] == x:
            found = True
        elif l[m] < x:
            L = m + 1
        else:
            R = m - 1
    return found

if __name__ == "__main__":
    l = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    x = 9
    print(binary_search(l, x))  # True
```

```{code} c
:label: binary-search-c
:caption: Binary search in C
#include <stdio.h>

int binary_search(int l[], int n, int x) {
    int found = 0; // 0: False, 1: True
    int L = 0;
    int R = n - 1;
    while (L <= R && !found) {
        int m = (L + R) / 2;
        if (l[m] == x) {
            found = 1;
        } else if (l[m] < x) {
            L = m + 1;
        } else {
            R = m - 1;
        }
    }
    return found;
}
int main() {
    int l[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int n = sizeof(l) / sizeof(l[0]);
    int x = 9;
    printf("%d\n", binary_search(l, n, x));  // 1 (True)
    return 0;
}
```