# ソートアルゴリズム

データを一定の順序にそろえて並べ換えることをソートという。例えば、データをアルファベット順、数値を大小順に並べることがソートにあたる。

**ソートアルゴリズム**（sorting algorithm）は、データをソートするためのアルゴリズムのことを指す。整列アルゴリズムとも呼ばれる。

ここでは、いくつかの代表的なソートアルゴリズムを紹介する。

## 選択ソート（Selection Sort）

数値をソートする場合は、最も単純な方法として、最小の要素を見つけてリストの先頭に移動し、次に最小の要素を見つけて2番目の位置に移動するという手順を繰り返すことが考えられる。

例えば、`[3, 5, 2, 4, 1]`というリストがあるとする。このリストを選択ソートでソートする場合、次のように進める。

1. リストの中から最小の要素`1`を見つけて、リストの先頭に移動する。結果は`[1, 5, 2, 4, 3]`。
2. 残りのリスト`[5, 2, 4, 3]`から最小の要素`2`を見つけて、2番目の位置に移動する。結果は`[1, 2, 5, 4, 3]`。
3. 残りのリスト`[5, 4, 3]`から最小の要素`3`を見つけて、3番目の位置に移動する。結果は`[1, 2, 3, 4, 5]`。
4. 残りのリスト`[4, 5]`から最小の要素`4`を見つけて、4番目の位置に移動する。結果は`[1, 2, 3, 4, 5]`。
5. これでリストはソートされ、結果は`[1, 2, 3, 4, 5]`となる。

このアルゴリズムの擬似コードは次のようになる。

```{prf:algorithm} selection sort
:label: selection-sort  
:caption: Selection Sort Algorithm

**Input**: リスト $l = [l_1, l_2, \ldots, l_n]$
**Output**: ソートされたリスト $l　= [l_1, l_2, \ldots, l_n]$

1. $i \gets 1$
2. **while** $i < n$ **do**
    1. $j \gets i$
    2. **for** $k \gets i + 1$ **to** $n$ **do**
        1. **if** $l_k < l_j$ **then**
            1. $j \gets k$
    2. **if** $j \neq i$ **then**
        1. swap $l_i$ and $l_j$
    3. $i \gets i + 1$
```

これをPythonとC言語で実装すると、次のようになる。

```{code} python
:label: selection-sort-python
:caption: Selection Sort in Python

def selection_sort(l):
    n = len(l)
    for i in range(n):
        j = i
        for k in range(i + 1, n):
            if l[k] < l[j]:
                j = k
        if j != i:  
            l[i], l[j] = l[j], l[i]
    return l

if __name__ == "__main__":
    l = [3, 5, 2, 4, 1]
    print(selection_sort(l))  # [1, 2, 3, 4, 5]

```

```{code} c
:label: selection-sort-c
:caption: Selection Sort in C
#include <stdio.h>

void selection_sort(int l[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int j = i;
        for (int k = i + 1; k < n; k++) {
            if (l[k] < l[j]) {
                j = k;
            }
        }
        if (j != i) {
            int temp = l[i];
            l[i] = l[j];
            l[j] = temp;
        }
    }
}
int main() {
    int l[] = {3, 5, 2, 4, 1};
    int n = sizeof(l) / sizeof(l[0]);
    selection_sort(l, n);
    for (int i = 0; i < n; i++) {
        printf("%d ", l[i]);
    }
    // 1 2 3 4 5
    return 0;
}