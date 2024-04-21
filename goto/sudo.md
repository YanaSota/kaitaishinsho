[](sudo.md)
# sudo
sudoは、許可されたユーザーが、スーパーユーザーまたは他のユーザーとしてコマンドを実行することができる。つまり一時的にpcの特権レベルを利用することが可能となる。

実行例 [](変更しない)

```
$python3 www.py
 python3: can't open file '/home/admin/www.py': [Errno 13] Permission denied. (権限が無いのでpython3で指定しているファイルを開けないよ)
$sudo python3 www.py
 (debug) serving at port 8080
```

実行結果 [](変更しない)

```
※コマンドによって結果は異なる。
```
### オプション一覧
- **-b, --background**

  バックグラウンドでコマンドを実行

  実行例 [](変更しない)

  ```
  $sudo -b python3 www.py
  ```

  実行結果 [](変更しない)

  ```
  (debug) serving at port 8080 ※Enterを押したらバックグラウンド処理に移る
  ```

- **-l, --list**

  ユーザーの権限をリストアップしたり、特定のコマンドがどこにあるかをチェックできる。

  実行例 [](変更しない)

  ```
  $ sudo -l python3 www.py
  ```

  実行結果 [](変更しない)

  ```
  /usr/bin/python3 www.py
  ```

- **-u, --user**

  デフォルトではrootになるが、指定されたコマンドを root 以外のユーザとして実行する。ユーザ名の代わりに uid を指定するときは、#uid という書き方をする。

  実行例 [](変更しない)

  ```
  $ sudo -u hoge cat 1.txt
  ```

  実行結果 [](変更しない)

  ```
  Hi※実行するコマンドによって異なる
  ```
