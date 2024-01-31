[](mkfifo.md)
# mkfifo
与えられた名前で \**名前付きパイプ ( FIFO )* を作成するコマンド。

（\* 名前付きパイプ（ FIFO ）: First In First Out の略。プロセス間通信のための通信手段の一つ。キューのようにデータがストリームされる。`echo hello > hoge | cat` と書かれる時の `|` は パイプ と呼ばれ同じくプロセス間通信をするためのシェルの機能である。）

実行例 []()
```
mkfifo hoge
```

実行結果 []()
```
// 実行前
user@localhost:~/mkfifo$ ls

// 実行後
user@localhost:~/mkfifo$ ls
hoge

// ちゃんとファイルタイプが pipe の p となっている
user@localhost:~/mkfifo$ ll
total 8
drwxrwxr-x  2 user user 4096 Jan 12 02:12 ./
drwxrwxr-x 10 user user 4096 Jan 12 02:11 ../
prw-rw-r--  1 user user    0 Jan 12 02:22 testfifo|
```

### オプション一覧
    
- **-m, --mode=MODE**

  引数（ `MODE` ）にファイルのパーミッションビットを umask 形式で指定することで、権限を設定できるオプション。

  実行例 []()
  ```
  mkfifo -m 644 fuga
  ```

  パーミッションビットの `644` は以下の権限で設定する際の数値である。

  - 所有者 : read(4), write(2)
  - グループ : read(4)
  - その他ユーザ : read(4)

  実行結果 []()
  ```
  // 実行前
  user@localhost:~/mkfifo$ ls

  // 実行後
  user@localhost:~/mkfifo$ ls
  fuga

  // 権限を確認
  user@localhost:~/mkfifo$ ll
  total 8
  drwxrwxr-x  2 user user 4096 Jan 12 02:34 ./
  drwxrwxr-x 10 user user 4096 Jan 12 02:11 ../
  prw-r--r--  1 user user    0 Jan 12 02:34 fuga|
  ```
