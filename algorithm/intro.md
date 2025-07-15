# アルゴリズム

:::{important} Objective 
- アルゴリズムの概念を理解する。
- 代入、選択構造、反復構造を理解し、擬似コードで表現できる。
:::

## アルゴリズムとは

```{epigraph}
Today, computer science has established itself as the science of algorithms.

-- G. Brookshear and D. Brylow, Computer Science: An Overview, 13th ed. Pearson, 2018.
```

**アルゴリズム**（algorithm）とは、問題を解決するための手順を指す。今までは、いくつかのアルゴリズムを紹介してきた。

CPUの命令サイクルは以下のようなアルゴリズムである。

```{prf:algorithm} 命令サイクル
:label: instruction-cycle

1. 命令の取得（fetch）
2. 命令の解読（decode）
3. 命令の実行（execute）
```

10進数から$n$進数への変換もアルゴリズムの一例である。

```{prf:algorithm} 10進数から$n$進数への変換
:label: decimal-to-n-base

1. 与えられた値を$n$で割り、商と余りを求める。
2. 商が0になるまで繰り返す。
3. 商が0になったら、余りを逆順に並べる。
```

正式に、アルゴリズムは明確な命令を持ち、有限のステップで実行可能な手順である。

- Unambiguous（明確）：アルゴリズムの各ステップは明確で、解釈の余地がない。
- Finite（有限）：アルゴリズムは有限のステップで完了する。

> An algorithm is an ordered set of unambiguous, executable steps that defines a terminating process.
> 
> -- G. Brookshear and D. Brylow, Computer Science: An Overview, 13th ed. Pearson, 2018.

> (An algorithm is a set of) unambiguous instructions for solving a problem or subproblem in a finite amount of time using a finite amount of data.
> 
> -- N. Dale and J. Lewis, Computer science illuminated, 7th ed. Sudbury, MA: Jones and Bartlett, 2024.