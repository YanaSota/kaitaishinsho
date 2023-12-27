[](ls.md)
# ls
デフォルトでは現在のディレクトリの中にあるファイルに関する情報をリストアップする。
`-cftuvSUX` または `--sort` のいずれも指定されていない場合は、検索結果をアルファベット順にソートして出力する。

実行例 []()

```
ls
```

実行結果 []()

```
auto_create_md.py  ls.md  man.md  ping.md
```
### オプション一覧
    
- **-a, --all**

  . から始まるファイル（ドットファイル）も表示する。

  実行例 []()

  ```
  ls -a
  ```

  実行結果 []()

  ```
  .  ..  .git  auto_create_md.py  ls.md  man.md  ping.md
  ```

- **-A, --almost-all**

  どこのディレクトリにもあるドットファイルである、「.」および「..」をリストに含めないようにする。

  実行例 []()

  ```
  ls -A
  ```

  実行結果 []()

  ```
  .git  auto_create_md.py  ls.md  man.md  ping.md
  ```

- **--author**

  `-l` と併用することで各ファイルの作者を表示できる。

  実行例 []()

  ```
  ls -l --author
  ```

  実行結果 []()

  ```
  total 36
  -rw-r--r-- 1 author user user  4519 Dec 23 15:10 auto_create_md.py
  -rw-rw-r-- 1 author user user 11692 Dec 23 15:10 ls.md
  -rw-rw-r-- 1 author user user 10558 Dec 10 03:49 man.md
  -rw-rw-r-- 1 author user user  1024 Dec 9 04:23 ping.md
  ```
  上の例でわかりやすく `author` としているところに作者のアカウント名が表示される。

- **--color[=WHEN]**

  ファイルの種類を区別するための出力の色をつけるかどうかを変更できるオプション。
  オプションを付与した場合にのみ作用され、常に変更できるわけではない。常に変更する場合は `LS_COLORS` という環境変数により設定を変更できる。その設定には `dircolors` コマンドを使用する必要がある。（ここでは記載しない。）
  
  デフォルトの `ls` では引数 (`=WHEN`) に `always` が渡された時と同じく、色がついている状態。以下の値を引数に取ることができる。
  - `always` : デフォルトの挙動。色がつく。
  - `auto` : 標準出力がターミナルに接続できている場合にのみ、色がつく。ssh などにより色がつかなくなっているのはこのオプションによるもの。
  - `never` : 色がつかない。


  実行例 []()

  ```
  ls --colors=never
  ```

  実行結果 [ls --colors=never]()

  ```
  auto_create_md.py  ls.md  man.md  ping.md
  ```

  この書式上、色が区別できる状態の実行結果を見せることはできないが、上記の実行例ではかならず何も着色されていない状態で出力される。

- **-f**

  ソートせず、`-aU` オプションを有効にし、`-ls` `--color` オプションを無効にした出力をするオプション。つまり、詳細情報ではない隠しファイルをふくむすべてのファイルを見つけた順で色なしで表示するオプション。

  実行例 []()

  ```
  ls -f
  ```

  実行結果 [ls -f]()

  ```
  ..  .  man.md  create_hoge_files.sh  ls.md  auto_create_md.py  ping.md
  ```




- **--format=WORD**

  引数( `WORD` ) に以下の単語を渡すことで指定できる出力形式で、出力できるオプション。

  - `across`(=`-x`オプション) : 行で出力する。
  - `commas`(=`-m`オプション) : カンマ区切りで出力する。
  - `horizontal`(=`-x`オプション) : 行で出力する。
  - `long`(=`-l`オプション) : 詳細情報まで出力する。
  - `single-column`(=`-1`オプション) : 1行につき1ファイルずつ出力する。
  - `verbose`(=`-l`オプション) : 詳細情報まで出力する。
  - `vertical`(=`-C`オプション) : 詳細情報まで出力する。

  実行例 []()

  ```
  ls --format=across
  ```

  実行結果 []()

  ```
  各コマンドの出力先を参照。
  ```





- **--group-directories-first**

  ディレクトリをファイルより先に表示するオプション。
  `--sort` オプションと組み合わせて使用することもできるが、`--sort=none` もしくは `-U` と併用してしまうと先にディレクトリが表示されないようになってしまう。

  実行例 []()

  ```
  ls --group-directories-first
  ```

  実行結果 [ls]()

  ```
  // dir = ディレクトリ
  auto_create_md.py  create_hoge_files.sh  dir  ls.md  man.md  ping.md
  ```

  実行結果 [ls --group-directories-first]()

  ```
  // dir = ディレクトリ
  dir  auto_create_md.py  create_hoge_files.sh  ls.md  man.md  ping.md
  ```

- **--hide=PATTERN**

  シェルで利用できる正規表現を引数( `=PATTERN` )に渡すことで指定した正規表現にマッチするファイル名を表示しないで出力するオプション。`-a` オプションなどとの併用ではマッチしたものも表示されてしまう。

  実行例 []()

  ```
  ls --hide='*.md'
  ```

  実行結果 [ls]()

  ```
  auto_create_md.py  create_hoge_files.sh  dir  ls.md  man.md  ping.md
  ```

  実行結果 [ls --hide='*.md']()

  ```
  auto_create_md.py  create_hoge_files.sh  dir
  ```

- **-l**

  ファイル(ディレクトリ)の詳細情報を表示するオプション。

  `total` にはディレクトリ内のすべてのファイルの \**ブロック* 数の合計が出力される。
  
  （\* ブロック : ディスク上の容量のひとまとまりの単位のこと。通常1ブロックは 512 もしくは 1024バイト）
  
  左から、ファイル(ディレクトリ)のパーミッション、そのファイルに対する \**ハードリンク* の数、ファイルの所有者、所属グループ、ファイルサイズ、最終変更時刻、ファイル(ディレクトリ)名が表示される。
  
  (\* ハードリンク : 同一のファイルに対する別名のこと。ハードリンク同士で同じデータブロックを共有するため、どちらかの変更が他方にも反映される。)

  実行例 []()

  ```
  ls -l
  ```

  実行結果 []()

  ```
  total 44
  -rw-r--r-- 1 user user  4519 Dec 25 15:10 auto_create_md.py
  -rwxrwxr-x 1 user user    63 Dec 26 01:27 create_hoge_files.sh
  drwxrwxr-x 2 user user  4096 Dec 28 00:20 dir
  -rw-rw-r-- 1 user user 11692 Dec 25 15:10 ls.md
  -rw-rw-r-- 1 user user 10558 Dec 11 03:49 man.md
  -rw-rw-r-- 1 user user  1024 Dec 11 04:23 ping.md
  ```

- **-p, --indicator-style=slash**

  ディレクトリ名の末尾に `/` が追加されて表示されるオプション。

  実行例 []()

  ```
  ls -p
  ```

  実行結果 []()

  ```
  // dir は ディレクトリ
  auto_create_md.py  create_hoge_files.sh  dir/  ls.md  man.md  ping.md
  ```

- **-Q, --quote-name**

  表示されるファイル(ディレクトリ)名がダブルクォーテーションで囲まれて出力されるオプション。
  ファイル(ディレクトリ)名にスペースや特殊文字が含まれているときに使用することが多い。

  実行例 []()

  ```
  ls -Q
  ```

  実行結果 [ls]()

  ```
   auto_create_md.py      dir     man.md               ping.md
  create_hoge_files.sh   ls.md  'one'$'\n''two.txt'
  ```

  実行結果 [ls -Q]()

  ```
  "auto_create_md.py"     "dir"    "man.md"        "ping.md"
  "create_hoge_files.sh"  "ls.md"  "one\ntwo.txt"
  ```

- **-r, --reverse**

  ファイル(ディレクトリ)のソートの順番を逆にするオプション。

  実行例 []()

  ```
  ls -r
  ```

  実行結果 [ls]()

  ```
   auto_create_md.py      dir     man.md               ping.mdcreate_hoge_files.sh   ls.md  'one'$'\n''two.txt'
  ```

  実行結果 [ls -r]()

  ```
  ping.md              man.md   dir                    auto_create_md.py
  'one'$'\n''two.txt'   ls.md    create_hoge_files.sh
  ```

- **-R, --recursive**

  \**サブディレクトリ* の中身まで再帰的に表示するオプション。

  (\* サブディレクトリ : 現在のディレクトリの下に存在するディレクトリのこと)

  実行例 []()

  ```
  ls -R
  ```

  実行結果 []()

  ```
  // dir ディレクトリの中
  user@localhost:~/dir$ ls
  hoge-hoge.txt
  ```

  実行結果 []()

  ```
  // dirディレクトリの上の階層のディレクトリの中
  user@localhost:~$ ls -R
  .:
  auto_create_md.py      dir     man.md               ping.md
  create_hoge_files.sh   ls.md  'one'$'\n''two.txt'

  ./dir:
  hoge-hoge.txt
  ```

  上記例では \**カレントディレクトリ* は `.` として表示されている。

  (\* カレントディレクトリ : 現在のディレクトリのこと)

- **-S**

  ファイルサイズの大きい順にソートして表示されるオプション。

  実行例 []()

  ```
  ls -S
  ```

  実行結果 [ls -l]()

  ```
  total 52
  drwxrwxr-x  3 user user  4096 Dec 28 01:52  ./
  drwxr-x--- 15 user user  4096 Dec 26 03:48  ../
  -rw-r--r--  1 user user  4519 Dec 25 15:10  auto_create_md.py
  -rwxrwxr-x  1 user user    63 Dec 26 01:27  create_hoge_files.sh*
  drwxrwxr-x  2 user user  4096 Dec 28 02:11  dir/
  -rw-rw-r--  1 user user 11692 Dec 25 15:10  ls.md
  -rw-rw-r--  1 user user 10558 Dec 11 03:49  man.md
  -rw-rw-r--  1 user user     0 Dec 28 01:52 'one'$'\n''two.txt'
  -rw-rw-r--  1 user user  1024 Dec 11 04:23  ping.md
  ```

  実行結果 [ls -Sx]()

  ```
  // 横でソートされているのを確認するために
  // ls -Sx としている

  ls.md                  man.md               auto_create_md.py   dir   ping.md
  create_hoge_files.sh  'one'$'\n''two.txt'
  ```

  上記の `ls -l` の例から `ls.md`, `man.md`, `auto_create_md.py`, ... の順にファイルサイズが大きいことが確認でき、`ls -Sx` の例からその順でソートされて出力されていることが確認できる。

- **--sort=WORD**

  出力を引数( `=WORD` )にて指定した方法でソートするオプション。`WORD` には以下の単語を指定できる。

  - `none` (= `-U`オプション) : ソートしない。ファイルが見つかった順。
  - `size` (= `-S`オプション) : ファイルサイズが大きい順。
  - `time` (= `-t`オプション) : 更新時刻順。
  - `versino` (= `-v`オプション) : バージョン番号順。
  - `extension` (= `-X`オプション) : 拡張子順。

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```

- **--time=WORD**

  修正時間を使うデフォルトを変更する；
                               アクセス時間（-u）：atime、access、use；
                               変更時間 (-c): ctime, status；
                               誕生時間：誕生、作成；
                             lで、WORDが表示する時間を決定する；
                             -sort=timeで、WORDでソート（新しいものから）。

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```

- **--time-style=TIME_STYLE**

  lを使った時間／日付フォーマット。

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```

- **-T, --tabsize=COLS**

  各COLSでタブストップが8つではなく、8つとする。

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```

- **-w, --width=COLS**

  出力幅を COLS に設定する。  0は制限なし

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```

- **-Z, --context**

  各ファイルのセキュリティコンテキストを表示する

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```



  バージョン情報を出力して終了する

  実行例 []()

  ```
  実行例
  ```

  実行結果 []()

  ```
  実行結果
  ```
