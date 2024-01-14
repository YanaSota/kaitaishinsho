[](mkdir.md)
# mkdir
ディレクトリを作成するコマンド。指定されたディレクトリが存在しない場合に作成する。

make directory の略だと言われている。

実行例 []()
```
mkdir hoge
```

実行結果 []()
```
// 実行前
user@localhost:~/mkdir$ ls

// 実行後
user@localhost:~/mkdir$ ls
hoge

// cd コマンドで移動できる
user@localhost:~/mkdir$ cd hoge
user@localhost:~/mkdir/hoge$ 
```

### オプション一覧
    
- **-m, --mode=MODE**

  ファイルモードを設定（chmodと同様）するオプション。`a=rwx` のような形式で指定する。umask ではなく、実際のモードを指定する。

  実行例 []()
  ```
  mkdir -m a=w fuga
  ```

  実行結果 []()
  ```
  // 実行前
  user@localhost:~/mkdir$ ls

  // 実行後
  user@localhost:~/mkdir$ ls
  hoge  fuga

  // cd コマンドで移動できる
  user@localhost:~/mkdir$ cd hoge
  user@localhost:~/mkdir/fuga$

  // 権限を確認する
  user@localhost:~/mkdir$ ls -l
  total 16
  drwxrwxr-x 4 user user 4096 Jan 12 01:15 ./
  drwxrwxr-x 9 user user 4096 Jan 12 01:14 ../
  d-w--w--w- 2 user user 4096 Jan 12 01:15 fuga/
  drwxrwxr-x 2 user user 4096 Jan 12 01:14 hoge/
  ```

- **-p, --parents**

  既にディレクトリが存在していてもエラーを発せず、必要に応じて親ディレクトリを作成するオプション。

  実行例 [エラー避け]()
  ```
  mkdir -p hoge
  ```

  実行結果 [エラー避け]()
  ```
  // 実行前
  user@localhost:~/mkdir$ ls
  hoge

  // -p なし
  user@localhost:~/mkdir$ mkdir hoge
  mkdir: cannot create directory ‘hoge’: File exists

  // -p あり
  user@localhost:~/mkdir$ mkdir hoge
  user@localhost:~/mkdir$ ls
  hoge
  ```

  次に親ディレクトリまで作成してくれる例を示す。

  実行例 [親ディレクトリ作成]()
  ```
  mkdir -p fuga/funga/fungaa
  ```

  実行結果 [親ディレクトリ作成]()
  ```
  // 実行前
  user@localhost:~/mkdir$ ls
  hoge

  // 実行後
  user@localhost:~/mkdir$ ls -R
  .:
  fuga  hoge

  ./fuga:
  funga

  ./fuga/funga:
  fungaa

  ./fuga/funga/fungaa:

  ./hoge:
  ```

  上は `ls` コマンドの `-R` オプションを利用してディレクトリ構造を再起的に表示させたものである。現在のディレクトリが `.` であるから全て相対パスとして考えると階層的にディレクトリが作成できたことが読み取れるはずである。


- **-v, --verbose**

  作成されたディレクトリごとにメッセージを表示するオプション。

  実行例 []()
  ```
  mkdir -vp fuga/fugafuga/fugafugafuga
  ```

  実行結果 []()
  ```
  mkdir: created directory 'fuga'
  mkdir: created directory 'fuga/fugafuga'
  mkdir: created directory 'fuga/fugafuga/fugafugafuga'
  ```
