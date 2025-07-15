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