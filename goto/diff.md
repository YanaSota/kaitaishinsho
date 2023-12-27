
[](diff.md)
# diff
2つのテキストファイルやディレクトリの内容の違いを比較するために使用される。差異部分を出力する。

実行例 [](変更しない)        

```
diff file1.txt file2.txt
```

実行結果 [](変更しない)

```
$ cat file1.txt
    hello,world!!
    I am Linux.
$ cat file2.txt
    hello,world!!
    I am Windows10.
$ diff file1.txt file2.txt
    2c2
    < I am Linux.
    \ No newline at end of file
    ---
    > I am Windows10.
    \ No newline at end of file
```
### オプション一覧
    
- **-r, --recursive**

  ディレクトリに対して比較をしている際、見つかったサブディレクトリも再帰的に比較をする。

  実行例 [](変更しない)

  ```
  diff diff1 diff2 -r
  ```

  実行結果 [](変更しない)

  ```
  $ tree(/test/diff1)
  .
  ├── File1.txt
  └── diff3
      └── File2.txt
  $ tree(/test/diff2)
  .
  ├── File1.txt
  └── diff3
      └── File2.txt
  $diff diff1 diff2 -r
    diff -r diff1/File1.txt diff2/File1.txt
    2c2
    < good night!
    \ No newline at end of file
    ---
    > everyone!
    \ No newline at end of file
    diff -r diff1/diff3/File2.txt diff2/diff3/File2.txt
    1c1
    < I am windows!!
    \ No newline at end of file
    ---
    > I am Linux!!
    \ No newline at end of file
  ```
  
- **-N, --new-file**

  存在しないファイルやディレクトリは空のものとして扱う。この際、差分があるか否かで出力を得れるため、総当たりで差分を見る際などに便利である。

  実行例 [](変更しない)

  ```
   diff diff1 diff4 -q -r -N
  ```

  実行結果 [](変更しない)

  ```
  $ diff diff1 diff4 -q -r -N
      Files diff1/File1.txt and diff4/File1.txt differ
      Files diff1/diff3/File2.txt and diff4/diff3/File2.txt differ
  $ diff diff1 diff4 -q -r
      diff: diff4: No such file or directory
  ```

- **-q, --brief**
  中身を表示せず、２つのファイルが異なるかだけを表示する。

  実行例 [](変更しない)

  ```
  diff file1.txt file2.txt -q
  ```

  実行結果 [](変更しない)

  ```
  $ cat file1.txt
      hello,world!!
      I am Linux.
  $ cat file2.txt
      hello,world!!
      I am Windows10.
  $ diff file1.txt file2.txt -q
      Files file1.txt and file2.txt differ
  ```

- **-i, --ignore-case**

  ファイル名の比較時に大文字と小文字を無視する

  実行例 [](変更しない)

  ```
  diff file1.txt file2.txt -i
  ```

  実行結果 [](変更しない)

  ```
  $ diff file1.txt file2.txt
    2,3c2,3
    < I am Linux.
    < hi!
    \ No newline at end of file
    ---
    > I am Windows10.
    > Hi!
    \ No newline at end of file
  $ diff file1.txt file2.txt -i
    2c2
    < I am Linux.
    ---
    > I am Windows10.
  ```

- **-rq , -rq**

  ディレクトリ同士における差分があるファイルのみ列挙する。これは-rと-qのオプションの重ね技である。

  実行例 [](変更しない)

  ```
  diff -qr diff1 diff2
  ```

  実行結果 [](変更しない)

  ```
  Files diff1/File1.txt and diff2/File1.txt differ
  Files diff1/diff3/File2.txt and diff2/diff3/File2.txt differ
  ```

- **-c, -C NUM, --context[=NUM]**

  比較結果をコンテキスト(!)の形式で表示する。

  実行例 [](変更しない)

  ```
  diff file1.txt file2.txt -c
  ```

  実行結果 [](変更しない)

  ```
  *** file1.txt   2023-12-22 07:14:11.513685033 +0900
  --- file2.txt   2023-12-22 07:14:14.625695524 +0900
  ***************
  *** 1,3 ****
    hello,world!!
  ! I am Linux.
  ! hi!
  \ No newline at end of file
  --- 1,3 ----
    hello,world!!
  ! I am Windows10.
  ! Hi!
  \ No newline at end of file
  ```

- **-s, --report-identical-files**

  ファイルの中身が全く同一の場合、同一であると表示する。そのため改行などやスペースの数なども比較の対象となる。

  実行例 [](変更しない)

  ```
  diff identical1.txt identical2.txt -s
  ```

  実行結果 [](変更しない)

  ```
  $diff identical1.txt identical2.txt -s
    Files identical1.txt and identical2.txt are identical
  $diff identical1.txt identical3.txt -s (identical3.txtは改行のみ追加したもの)
    1c1
    < hello!
    \ No newline at end of file
    ---
    > hello! 
  ```

- **-u, -U NUM, --unified[=NUM]**

  ユニファイド形式で差分を表示する。ユニファイド形式は2つのファイルを合わせた状態で出力する。Gitの差分出力でこの形式が利用されている。

  実行例 [](変更しない)

  ```
  diff file1.txt file2.txt -u
  ```

  実行結果 [](変更しない)

  ```
  --- file1.txt   2023-12-22 07:14:11.513685033 +0900
  +++ file2.txt   2023-12-22 07:14:14.625695524 +0900
  @@ -1,3 +1,3 @@
   hello,world!!
  -I am Linux.
  -hi!
  \ No newline at end of file
  +I am Windows10.
  +Hi!
  \ No newline at end of file
  ```

- **--y, --side-by-side**

  横に並べて差分を見ることができる。

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  hello,world!!              hello,world!!
  I am Linux.              　| I am Windows10.
  ```

- **-b, --ignore-space-change**

  空白の量の変化を無視する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-w, --ignore-all-space**

  空白文字を無視して比較する。

  実行例 [](変更しない)

  ```
  diff diff_sp1.txt diff_sp2.txt -w
  ```

  実行結果 [](変更しない)

  ```
  $ cat diff_sp1.txt
  　　□□□□□□□□□□□hois (※□は空白)
      ora sin. 
  $ cat diff_sp2.txt
  　　ho□□□□□□□□□□i
      ora cos.
  $ diff diff_sp1.txt diff_sp2.txt -w
      2c2
      < ora sin.
      \ No newline at end of file
      ---
      > ora cos.
      \ No newline at end of file
  ```

- **--color[=WHEN]**
  出力をカラー表示する。WHENにあたるものは'never'、'always'、または'auto'のいずれかであるが基本は記述不要である。

  実行例 [](変更しない)

  ```
  diff file1.txt file2.txt --color
  ```

  実行結果 ※色を表現できないため、文末に色を記載する。 [](変更しない)

  ```
  2,3c2,3                     (青)
  < I am Linux.               (赤)
  < hi!                       (赤)
  \ No newline at end of file (白)
  ---                         (白)
  > I am Windows10.           (緑)
  > Hi!                       (緑)
  \ No newline at end of file (白)
  ```