
[](uniq.md)
# uniq
ファイル同士を比較し、連続して重複している部分を削るコマンドである。オプションなしだと、指定したファイルに上書きされる。
長いオプションに必須の引数は、短いオプションにも必須である。
基本ファイル内はsort済みであることを想定されているため、Sortは"必須"である。

実行例 [](変更しない)

```
sort File2.txt -o File2.txt　(uniqにはsortが必要なため)
cat File2.txt　(catはそれぞれのtxtを確認するため)
uniq FIle2.txt
```

実行結果 [](変更しない)

```
$cat File2.txt
    Blossom
    blossom
    blooooooooooossom
    Elephant
    Radiant
    Serendipity
    Serendipity
$uniq FIle2.txt
    Blossom
    blossom
    blooooooooooossom
    Elephant
    Radiant
    Serendipity
```
### オプション一覧
    
- **-c, --count**

  出現回数を単語の行ごと先頭に明記する。

  実行例 [](変更しない)

  ```
  uniq -c File2.txt
  ```

  実行結果 [](変更しない)

  ```
    1 Blossom
    1 blossom
    1 blooooooooooossom
    1 Elephant
    1 Radiant
    2 Serendipity
  ```

- **-d, --repeated**

  グループごとに1行ずつ、重複している部分を出力する。

  実行例 [](変更しない)

  ```
  uniq -d File2.txt
  ```

  実行結果 [](変更しない)

  ```
  Serendipity
  ```

- **-D, --all-repeated[=METHOD]**

  重複する行を全て出力する。
  「--all-repeated=none」->重複行のグループに区切りをいれない。(デフォルト)
  「--all-repeated=prepend」->重複行のグループの手前に区切りをいれる。
  「separate」で、グループの間に区切りの空白行をいれる。

  実行例 [](変更しない)

  ```
  uniq -D File2.txt
  ```

  実行結果 [](変更しない)

  ```
  Serendipity
  Serendipity
  ```

- **-f, --skip-fields=N**

  行全体ではなく、スペースやタブ文字で区切られた項目で重複を判断する。指定する際は一番左の項目から0,1の順で指定する。

  実行例 [](変更しない)

  ```
  cat File1.txt
  uniq -f 2 File1.txt
  ```

  実行結果 [](変更しない)

  ```
  $cat File1.txt
    1 Blossom 95
    2 Blossom 20
    3 Harmony 90
    4 Radiant 21
    5 Sunshine 21
    6 Whisper 21
  
  $uniq -f 2 File1.txt
    1 Blossom 95
    2 Blossom 20
    3 Harmony 90
    4 Radiant 21
  ```

- **--group[=METHOD]**

  すべての項目を表示し、グループを空行で区切る。METHODに関してはオプション-Dで記述したものと同様である。
  しかし上記3つに加えて"both"が存在する。これは先頭と最後それぞれに空行を入れる。

  実行例 [](変更しない)

  ```
  cat File2.txt
  uniq --group File2.txt
  ```

  実行結果 [](変更しない)

  ```
  $cat File2.txt
    Blossom
    blossom
    blooooooooooossom
    Elephant
    Radiant
    Serendipity
    Serendipity
  $uniq --group File2.txt
    Blossom

    blossom

    blooooooooooossom

    Elephant

    Radiant

    Serendipity
    Serendipity
  ```

- **-i, --ignore-case**

  比較の際、大文字と小文字の違いは無視する。

  実行例 [](変更しない)

  ```
  uniq -i File2.txt
  ```

  実行結果 [](変更しない)

  ```
  Blossom
  blooooooooooossom
  Elephant
  Radiant
  Serendipity
  ```

- **-s, --skip-chars=N**

  文頭からN文字までを比較対称としない。

  実行例 [](変更しない)

  ```
  uniq -s 1 File2.txt
  ```

  実行結果 [](変更しない)

  ```
  Blossom (Blossomは頭文字以外同じため消えている)
  blooooooooooossom
  Elephant
  Radiant
  Serendipity
  ```

- **-u, --unique**

  重複していない行だけを出力する。

  実行例 [](変更しない)

  ```
  uniq -u  -i File2.txt (今回は小文字、大文字のの違いを無視する)
  ```

  実行結果 [](変更しない)

  ```
  blooooooooooossom
  Elephant
  Radiant
  ```

- **-z, --zero-terminated**

  行の区切り記号は改行ではなくNULLであるゼロバイト文字にする。

  実行例 [](変更しない)

  ```
  uniq -z File2.txt
  ```

  実行結果 [](変更しない)

  ```
  最後に改行されない他に変化しないため記載しない。
  ```

- **-w, --check-chars=N**

  N文字までを比較する。

  実行例 [](変更しない)

  ```
  cat File2.txt
  uniq -w 3 File2.txt
  uniq -w 4 File2.txt
  ```

  実行結果 [](変更しない)

  ```
  $cat File2.txt
    Blossom
    blossom
    blooooooooooossom
    Elephant
    Radiant
    Serendipity
    Serendipity
  $uniq -w 3 File2.txt
    Blossom
    blossom
    Elephant
    Radiant
    Serendipity
  $uniq -w 4 File2.txt
    Blossom
    blossom
    blooooooooooossom
    Elephant
    Radiant
    Serendipity
  ```
