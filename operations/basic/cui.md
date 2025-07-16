# コマンドライン

**CLI**（Command Line Interface）は、コマンドラインを使ってコンピューターを操作するインターフェースのことです。

**コマンドプロンプト**（Command Prompt, also known as cmd.exe）は、Windowsにおける代表的なCLIの一つです。cmd.exeの後継として、**PowerShell**があり、より高度な操作が可能です。ここではPowerShellの基本的な使い方を学びます。

:::{note}
GUIと比べて、CLIの学習コストは高いですが、CLIを使うことで、より高度な操作が可能になります。

CLIと関連する概念として、CUIがあります。**CUI**（Character User Interface）とは、キーボードからコンピューターに文字列を入力して操作する体系・方法のことです。コマンドラインも文字列であるため、CLIはCUIの一種と言えます。

日本では、「CUI」という言葉が一般的に使われていますが、英語圏では「CLI」という言葉が使われることが多いです。
:::

## PowerShellの起動

PowerShellを起動するには、検索ボックスに「PowerShell」と入力し、検索結果から「Windows PowerShell」をクリックします。

## バージョン

PowerShellを起動したら、次のコマンドを入力して、<kbd>Enter</kbd> キーを押すことで、バージョンを確認できます。

```powershell
$PSVersionTable
```

PSVersion の値が5.1以下の場合、以下のサイトの手順に従って、PowerShell 5.1 以上にアップデートしてください。

- [https://aka.ms/PSWindows](https://aka.ms/PSWindows)

:::{note}
PowerShell は、**cmdlet**（コマンドレット）と呼ばれるコマンドを使用します。コマンドレットは、「Verb-Noun」 の形式で構成されます。例えば、`Get-Process` は、「プロセスの情報を取得する」コマンドレットです。

コマンドレットのパラメーターは、`-ParameterName` の形式で指定します。例えば、`Get-Process -Name "explorer"` は、名前が `explorer` のプロセスの情報を取得するコマンドです。

コマンドレットのAlias（エイリアス）とは、コマンドレットの短縮形です。例えば、`Get-Process` のエイリアスは `gps` で、`Get-Process -Name "explorer"` は `gps -Name "explorer"` と書くことができます。

最後に、PowerShell は、基本的に大文字と小文字を区別しません。つまり、`Get-Process` と `get-process` は同じコマンドレットとして扱われます。
:::

:::{note}

PowerShell では、以下の操作ができます。これらの操作を使いこなすことで、PowerShell を効率的に使うことができます。

- <kbd>Tab</kbd> キーを押すと、コマンドの補完ができます。
- <kbd>↑</kbd> キーを押すと、前のコマンドを表示できます。
- <kbd>↓</kbd> キーを押すと、次のコマンドを表示できます。
- <kbd>Ctrl</kbd> + <kbd>C</kbd> キーを押すと、コマンドの実行を中止できます。
:::

## ファイル・ディレクトリ操作

PowerShell でよく使うコマンドを紹介します。

### cd

`cd` コマンドは、カレントディレクトリを変更するコマンドです。**カレントディレクトリ**（Current Directory）とは、現在作業しているディレクトリ、あるいは位置のことです。

以下の例では、カレントディレクトリを `C:\` に変更します。

```powershell
cd C:\
```

次に、`cd Users` コマンドを使用して、`C:\Users` ディレクトリに移動します。

```powershell
cd Users
```

### pwd

`pwd` コマンドは、カレントディレクトリを取得するコマンドです。

```powershell
pwd
```

例えば、カレントディレクトリは 「C:\Users」 の場合、`pwd` コマンドを実行すると、以下のように表示されます。

```
Path
----
C:\Users
```

### dir

`dir` コマンドは、カレントディレクトリにあるファイルとディレクトリの一覧を表示するコマンドです。

カレントディレクトリを `C:\` とし、`dir` コマンドを実行すると、以下のように表示されます。

```
    ディレクトリ: C:\


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       2024/01/01     12:00                PerfLogs
d-r---       2024/01/01     12:00                Program Files
d-r---       2024/01/01     12:00                Program Files (x86)
d-r---       2024/01/01     12:00                Users
d-----       2024/01/01     12:00                Windows
```

### mkdir

`mkdir` コマンドは、新しいディレクトリを作成するコマンドです。

以下の例は、カレントディレクトリが `C:\` の場合、`test` ディレクトリを作成します。

```powershell
mkdir test
```

`dir` コマンドを実行すると、以下のように表示されます。「test」ディレクトリが作成されていることがわかります。

```
    ディレクトリ: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       2024/01/01     12:00                PerfLogs
d-r---       2024/01/01     12:00                Program Files
d-r---       2024/01/01     12:00                Program Files (x86)
d-----       2025/04/01     12:00                test
d-r---       2024/01/01     12:00                Users
d-----       2024/01/01     12:00                Windows
```

### ni

`ni` コマンドは、新しいファイルを作成するコマンドです。

以下の例は、カレントディレクトリが `C:\test` の場合、`test.txt` ファイルを作成します。

```powershell
ni test.txt
```

`dir` コマンドを実行すると、以下のように表示されます。「test.txt」ファイルが作成されていることがわかります。

```
    ディレクトリ: C:\test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       2025/04/01     12:00              0 test.txt
```

### move

`move` コマンドは、ファイルやディレクトリを移動するコマンドです。

まずは、`C:\test` ディレクトリに `test2` ディレクトリを作成します。

```powershell
mkdir test2
```

`dir` コマンドを実行すると、以下のように表示されます。「test2」ディレクトリが作成されていることがわかります。

```
    ディレクトリ: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       2024/01/01     12:00                test2
-a----       2025/04/01     12:00              0 test.txt
```


次に、`test.txt` ファイルを `C:\test\test2` ディレクトリに移動します。

```powershell
move test.txt test2
```

`cd test2` コマンドを使用して、`C:\test\test2` ディレクトリに移動し、`dir` コマンドを実行すると、以下のように表示されます。「test.txt」ファイルが移動されていることがわかります。

```
    ディレクトリ: C:\test\test2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       2025/04/01     12:00              0 test.txt
```

### del

`del` コマンドは、ファイルを削除するコマンドです。

以下の例は、`C:\test\test.txt` ファイルを削除します。

```powershell
del test.txt
```

## 練習

1. カレントディレクトリを `C:\` に変更してみよう。
2. `C:\` に`excercise` ディレクトリを作成してみよう。
3. `excercise` ディレクトリに `sample.txt` ファイルを作成してみよう。
4. `sample.txt` ファイルを削除してみよう。

