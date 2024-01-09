
[](truncate.md)
# truncate
指定したファイルのサイズを指定されたサイズに縮小または拡張する。
指定サイズより大きい場合、余分なデータは失われる。指定サイズより短い場合は、NULL文字で拡張される。

実行例 [](変更しない)

```
truncate -s 5 test.txt
```

実行結果 [](変更しない)

```
$ cat test.txt
  hello,world!
$ truncate -s 5 test.txt
$ ls test.txt -l
  -rw-r--r-- 1 user user 5  1月  2 20:58 test.txt
```
### オプション一覧
    
- **-c, --no-create**

  ファイルを作成しない

  実行例 [](変更しない)

  ```
  truncate hoge.txt -c -s 10
  ```

  実行結果 [](変更しない)

  ```
  $ truncate hoge.txt -c -s 10
  $ ls hoge.txt -l
    ls: cannot access 'hoge.txt': No such file or directory
  ```

- **-o, --io-blocks**

  SIZEをバイト数ではなくIOブロック数として扱う

  実行例 [](変更しない)

  ```
  truncate hoge.txt -o -s 10
  ```

  実行結果 [](変更しない)

  ```
  $ truncate hoge.txt -o -s 10
  $ ls hoge.txt -l
    -rw-rw-r-- 1 user user 40960  1月  2 21:03 hoge.txt
  ```

- **-r, --reference=RFILE**

  指定したファイルと同様のファイルサイズに伸長、切り詰める。

  実行例 [](変更しない)

  ```
  truncate hoge.txt -r hoge1.txt
  ```

  実行結果 [](変更しない)

  ```
  $ ls hoge1.txt -l
    ls: cannot access 'hoge1.txt': No such file or directory
  $ truncate hoge.txt -r hoge1.txt
  $ ls hoge1.txt -l
    -rw-rw-r-- 1 user user 12  1月  3 13:48 hoge1.txt
  ```

- **-s, --size=SIZE**

  ファイルサイズをバイト単位で設定または調整する。このオプションがデフォルトで用いられる。

  実行例 [](変更しない)

  ```
  truncate -s 5 test.txt
  ```

  実行結果 [](変更しない)

  ```
  $ truncate -s 5 test.txt
  $ ls test.txt -l
    -rw-r--r-- 1 user user 5  1月  3 13:50 test.txt
  ```
