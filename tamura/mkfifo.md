[](mkfifo.md)
# mkfifo
与えられた名前で \**名前付きパイプ ( FIFO )* を作成するコマンド。

（\* 名前付きパイプ（ FIFO ）: First In First Out の略。プロセス間通信のための通信手段の一つ。キューのようにデータがストリームされる。）

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

  ファイルのパーミッションビットをa=rwではなくMODEに設定 - umask

  実行例 []()
  ```
  実行例
  ```

  実行結果 []()
  ```
  実行結果
  ```

- **--context[=CTX]**

  または、CTX が指定されている場合は、SELinux または SMACK のセキュリティコンテキストを CTX に設定する。
  または SMACK セキュリティ・コンテキストを CTX に設定する。

  実行例 []()
  ```
  実行例
  ```

  実行結果 []()
  ```
  実行結果
  ```
