# 機械語

## 学習目標

- 機械語の概念を理解する。
- RISCとCISCの違いを理解する。
- 簡単なPep/9の機械語プログラムを作成できる。
- Pep/9のシミュレータを使って、機械語プログラムを実行できる。

## 機械語とは

コンピューターが直接理解し、処理できる言語は**機械語**（Machine Language）という。プログラム内蔵方式を実現するため、機械語は0と1のビット列で表現される。

CPUでは、事前に定義された**命令セットアーキテクチャ**（ISA）に基づいて、機械語の命令を解釈し、実行する。各命令は、特定の操作を指示するビットパターンで構成されている。

コンピューターで処理するすべてのプログラムは、最終的には機械語に変換され、事前に定義された命令セットに従って実行される。

## ISAの種類

- **RISC**（Reduced Instruction Set Computer）：単純な命令を持つ。TV、スマートフォンなどでよく使用されるARMのプロセッサがその代表例。
- **CISC**（Complex Instruction Set Computer）：複雑な命令を持つ。消費電力が高い。PCでよく使用されるIntelやAMDのプロセッサがその代表例。

|            | RISC   | CISC |
| ---------- | ------ | ---- |
| 命令数     | 少ない | 多い |
| 生産コスト | 低い   | 高い |
| 消費電力   | 低い   | 高い |
| 応用       | TVなど | PC   |

## Pep/9

CPUの種類によって、処理する命令セットは異なる。ここでは、Pep/9という仮想コンピューターを使って、機械語を体験する。

<!-- Pep/9のワードは、16ビット（2バイト）で構成される。
**ワード**（Word）とは、コンピューターの内部で一度に処理される情報量の単位である。1ワードを構成するビット数でその大きさを表す。ワードはコンピューターによって異なり、一般的には8・16・32・64ビットなどがある。 -->

Pep/9の記憶装置は、65536バイトで構成され、アドレスは`0000`から`FFFF`までの範囲で指定される。**アドレス**(Address)は、記憶装置中の位置を識別するための数字である。Pep/9では、一つのアドレスに1バイトのデータが格納される。

下記の表は、Pep/9の記憶装置でのアドレスと格納されるビットパターンの例である。

| アドレス | データ      |
| -------- | ----------- |
| `0000`   | `0000 1010` |
| `0001`   | `0000 0010` |
| ...      | ...         |
| `FFFF`   | `1001 1011` |

Pep/9では、7つのレジスタを持つ。以下は三つの主要なレジスタの説明である。

- The Accumulator（A）：演算の結果を一時的に保存するレジスタ。
- The Program Counter（PC）：次に実行する命令のアドレスを指すレジスタ。
- The Instruction Register（IR）：現在実行中の命令を保持するレジスタ。

### 命令

Pep/9の命令セットには40種類の命令がある。

命令は、**命令部**（Instruction Specifier）と**オペランド部**（Operand Specifier）の2つの部分で構成される。命令部は、命令の種類を示す8ビットのビットパターンである。オペランド部は、命令が操作するデータのアドレスや値を示す16ビットのビットパターンである。そのため、Pep/9の命令は、合計24ビット（3バイト）で表現される。

:::{figure} image/program-instruction.drawio.svg
:label: pep9_instruction_format
:alt: Pep/9 Instruction Format
:width: 700px
:align: center

Pep/9の命令
:::

また、命令部だけで構成される命令もある。これらの命令は、オペランド部を持たないため、8ビットで表現される。

命令部は以下の3つの部分で構成される。

- **オペコード**（Opcode, Operation Code）：命令の種類を示すビットパターン。
- **レジスタ指定子**（Register Specifier）：操作対象のレジスタを指定するビット。
- **アドレス指定方式**（Addressing Mode）：オペランドの指定方法を示すビット。

下では、Pep/9の命令セットの一部を紹介する。

| 命令        | 説明                         |
| ----------- | ---------------------------- |
| `0000 0000` | 実行を停止する               |
| `1100 raaa` | メモリからワードをロードする |
| `1101 raaa` | メモリからバイトをロードする |
| `1110 raaa` | メモリにワードを格納する     |
| `1111 raaa` | メモリにバイトを格納する     |
| `0110 raaa` | オペランドを加算する         |
| `0111 raaa` | オペランドを減算する         |


`0000 0000`は、実行を停止する命令であり、オペコードだけで構成される。

`1100 raaa`は、メモリからワードをレジスタにロードする命令である。ここで、`1100`はオペコードで、`r`はレジスタ指定子、`aaa`はアドレス指定方式を示す。このような命令は、4ビットのオペコードと、1ビットのレジスタ指定子、3ビットのアドレス指定方式を持つ。

:::{figure} image/program-pep9_ins.drawio.svg
:label: pep9_instruction_specifier
:alt: Pep/9 Instruction Specifier
:width: 500px
:align: center

Pep/9のinstruction specifier
:::

:::{note}
ここで紹介するオペコードは、4や8ビットのビットパターンで表現される。Pep/9では、5ビット、7ビットのオペコードも存在する。
:::

レジスタ指定子は、1ビットのビットパターンで、操作対象のレジスタを指定する。Pep/9では、以下の2つのレジスタが使用される。これ以降の例では、レジスタ指定子を`0`とし、レジスタA（Accumulator）を操作対象とする。Accumulatorは、演算の結果を一時的に保存するレジスタである。

| r   | レジスタ          |
| --- | ----------------- |
| 0   | Accumulator, A    |
| 1   | Index register, X |

アドレス指定方式（addressing mode）は、データを指定する方法を示す。アドレス指定方式には、以下の二つを紹介する。

- **即値アドレス指定**（Immediate Addressing）：オペランドの値を直接指定する。Pep/9では、`000`で即値アドレス指定を示す。
- **直接アドレス指定**（Direct Addressing）：オペランドのアドレスを直接指定する。Pep/9では、`001`で直接アドレス指定を示す。

:::{note}
Pep/9では、**メモリマップドI/O**（Memory-mapped I/O）という方式を使用して、キーボードから入力を受け取り、ターミナルに出力する。

Pep/9の入力アドレスは`FC15`、出力アドレスは`FC16`である。命令部では、直接アドレス指定を使用して、オペランド部では入出力アドレスを指定すれば、キーボードからの入力やターミナルへの出力が可能になる。
:::

````{prf:example}
:label: instruction_example_machine_language
:nonumber:

下の命令を考えてみよう。

```
1100 0000 0000 0001 1100 0111
```

この命令部の`1100 0000`は、以下のように分解できる。

- オペコード：`1100`
- レジスタ指定子：`0`
- アドレス指定方式：`000`

この命令は、メモリから2バイトのワードをレジスタAにロードする命令である。アドレス指定方式が`000`であるため、即値アドレス指定を示す。

オペランド部の値は`0000 0001 1100 0111`であり、これは16進数で`01C7`に相当する。この命令は、即値アドレス指定であるため、`01c7`を値としてレジスタAにロードする。

まとめると、この命令は「レジスタAに`01C7`をロードする」という意味になる。
````

## 「Hi」を出力するPep/9の機械語プログラム

「Hi」と出力するPep/9の機械語プログラムを紹介する。

即値アドレス指定を使用する場合は、以下のステップでプログラムを作成する。

1. 「H」のASCIIコードをレジスタAにロードする。
2. レジスタAの値をターミナルに出力する。
3. 「i」のASCIIコードをレジスタAにロードする。
4. レジスタAの値をターミナルに出力する。
5. 実行を停止する。

以上のことを機械語で表現すると、以下のようになる。

1. `1101 0000 0000 0000 0100 1000`
2. `1111 0001 1111 1100 0001 0110`
3. `1101 0000 0000 0000 0110 1001`
4. `1111 0001 1111 1100 0001 0110`
5. `0000 0000`

オペコード`1101 0000`はメモリからレジストAに1バイトの値をロードする命令で、オペランド部は2バイトで構成されるが、最初の1バイトは機能しないため、任意の値を指定できる。ここでは、`0000 0000`を指定している。

さらに、見やすくするために、16進数で表現すると、以下のようになる。

1. `D0 00 48`
2. `F1 FC 16`
3. `D0 00 69`
4. `F1 FC 16`
5. `00`

このプログラム`D0 00 48 F1 FC 16 D0 00 69 F1 FC 16 00 zz`をPep/9で実行すると、ターミナルに「Hi」と出力される。`zz`は、プログラム終了を示すためのコードである。

Pep/9のシミュレータは以下の手順でダウンロードできる。

1. [こちら](https://computersystemsbook.com/5th-edition/pep9/)にアクセスする。
2. 「Download Windows」をクリックして、Pep/9のシミュレータをダウンロードする。
3. ダウンロードした「Pep9-Installer-941.exe」を実行する。
4. 「次へ」をクリックして、インストールを進める。
5. 「インストール」をクリックして、Pep/9のシミュレータをインストールする。
6. インストールが完了したら、「完了」をクリックして、Pep/9のシミュレータを起動する。

機械語で「Hi」を出力するPep/9のプログラムを実行するには、以下の手順を進む。

1. シミュレータを起動し、ソースコードを「Object Code」に入力する。
2. Build > Load Object Codeを選択し、プログラムをロードする。
3. Build > Executeを選択し、プログラムを実行する。
4. Outputに「Hi」と出力されることを確認する。

## 文字列を処理するPep/9の機械語プログラム

二つの文字を受け取り、位置を入れ替え、ターミナルに出力するPep/9の機械語プログラムを紹介する。

このプログラムは、以下のステップで実行される。

1. キーボードから入力した1文字目をレジスタAにロードする。
2. レジスタAの値をメモリの任意のアドレスに格納する。
3. キーボードから入力した2文字目をレジスタAにロードする。
4. レジスタAの値をターミナルに出力する。
5. メモリに格納した1文字目をレジスタAにロードする。
6. レジスタAの値をターミナルに出力する。
7. 実行を停止する。

以下の機械語プログラムは、上記のステップを実行する。

1. `1101 0001 1111 1100 0001 0101`
2. `1111 0001 0000 0000 0001 0110`
3. `1101 0001 1111 1100 0001 0101`
4. `1111 0001 1111 1100 0001 0110`
5. `1101 0001 0000 0000 0001 0110`
6. `1111 0001 1111 1100 0001 0110`
7. `0000 0000`

16進数で表現すると、以下のようになる。

1. `D1 FC 15`
2. `F1 00 16`
3. `D1 FC 15`
4. `F1 FC 16`
5. `D1 00 16`
6. `F1 FC 16`
7. `00`

このプログラム`D1 FC 15 F1 00 16 D1 FC 15 F1 FC 16 D1 00 16 F1 FC 16 00 zz`をPep/9で実行すると、キーボードから入力した2文字の位置が入れ替わり、ターミナルに出力される。

1. プログラムをObject Codeに入力する。
2. 「ab」をInputに入力する。
3. Build > Load Object Codeを選択し、プログラムをロードする。
4. Build > Executeを選択し、プログラムを実行する。
5. Outputに「ba」と出力されることを確認する。

## 練習問題

1. 即値アドレス指定を使用し、「Hosei」と出力するPep/9の機械語プログラムを作成せよ。ただし、オペランド部の最初のバイトは16進数の`00`とすること。プログラムの最後に`zz`を追加すること。
2. 3文字の文字列を受け取り、位置を入れ替え、ターミナルに出力するPep/9の機械語プログラムを作成せよ。例えば、入力が「abc」の場合、出力は「cba」となること。