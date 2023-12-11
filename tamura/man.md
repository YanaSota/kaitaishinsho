[](man.md)
# man
各種コマンド（厳密にはディレクトリやユーティリティと呼ばれるものも含む）の manページ(マニュアルページ) を表示するコマンド。
マニュアルページとはほとんどの UNIXライクなOSで初めからインストールされているドキュメントのことで、慣習として各種コマンドの使用例や書式、オプション、戻り値などが記載されている。マニュアルページは標準では環境変数 `$MANPATH` で指定されている場所に保存されている。
マニュアルページは標準では `less`コマンドを使って表示されており、`less`コマンド以外の表示コマンド（ページャーと呼ぶ）を使用することもできる。ここの例は ページャーを `less` としているため、上下キーで表示を移動させ、`q` キーを押すことでマニュアルページから抜けられる。

  実行例 [](変更しない)
  
  ```
  man ls
  ```

  実行結果 (マニュアルページ)[](変更しない)

  ```
  LS(1)           BSD General Commands Manual           LS(1)

  NAME
       ls -- list directory contents

  SYNOPSIS
       ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]
  
  DESCRIPTION
       For each operand that names a file of a type other than directory, ls
       displays its name as well as any requested, associated information. For
       each operand that names a file of type directory, ls displays the names of files cotained within that directory, as well as any requested, asso-ciated information.

  以下、まだまだ続く
  ```

### オプション一覧

- **-C [file], --config-file=[file]**
  
  デフォルトの `~/.manpath` ではなく指定したユーザ指定ファイルを使用する。

  実行例 [](変更しない)
  
  ```
  man -C ~/my_man_config
  ```

  実行結果　[](変更しない)

  ```
  What manual page do you want?
  For example, try 'man man'.
  ```
- **-d, --debug** 
  
  デバッグ情報を表示する。
  
  実行例　[](変更しない)
  
  ```
  man -d
  ```
  
  実行結果　[](変更しない)
  
  ```
  ruid=1000, euid=1000
  rgid=1000, egid=1000
  ++priv_drop_count = 1
  From the config file /etc/manpath.config:
    Mandatory mandir `/usr/man'.
    Mandatory mandir `/usr/share/man`.
    Mandatory mandir `/usr/local/share/man'.
    Path `/bin' mapped to mandir `/usr/share/man'.
    Path `/usr/bin' mapped to mandir `/usr/share/man'.
    Path `/sbin' mapped to mandir `/usr/share/man'.
    Path `/usr/sbin' mapped to mandir `/usr/share/man'.
    Path `/usr/local/bin' mapped to mandir `/usr/local/man'.
    Path `/usr/local/bin' mapped to mandir `/usr/local/share/man'.
    Path `/usr/local/sbin' mapped to mandir `/usr/local/man'.
    Path `/usr/local/sbin' mapped to mandir `/usr/local/share/man'.
    Path `/usr/X11R6/bin' mapped to mandir `/usr/X11R6/man'.
    Path `/usr/bin/X11' mapped to mandir `/usr/X11R6/man'.
    Path `/usr/games' mapped to mandir `/usr/share/man'.
    Path `/opt/bin' mapped to mandir `/opt/man'.
    Path `/opt/sbin' mapped to mandir `/opt/man'.
    Global mandir `/usr/man', catdir `/var/cache/man/fsstnd'.
    Global mandir `/usr/share/man', catdir `/var/cache/man'.
    Global mandir `/usr/local/man', catdir `/var/cache/man/oldlocal'.
    Global mandir `/usr/local/share/man', catdir `/var/cache/man/local'.
    Global mandir `/usr/X11R6/man', catdir `/var/cache/man/X11R6'.
    Global mandir `/opt/man', catdir `/var/cache/man/opt'.
    Global mandir `/snap/man', catdir `/var/cache/man/snap'.
    Added sections: `1', `n', `l', `8', `3', `0', `2', `3posix', `3pm', `3perl', `3am', `5', `4', `9', `6', `7'.
  is a tty
  using pager as pager
  What manual page do you want?
  For example, try 'man man'.
  ```
- **-D, --default** 
  
  manの動作をデフォルトにリセットする。これは、$MANOPTで設定されている可能性があるオプションをリセットするために使用される。-Dの後に続く任意のオプションは通常の効果がある。
  
  実行例　[](変更しない)
  
  ```
  man -D ls
  ```
  
  実行結果 (マニュアルページの表示)[](変更しない)
  
  ```
  LS(1)           BSD General Commands Manual           LS(1)

  NAME
       ls -- list directory contents

  SYNOPSIS
       ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]
  
  DESCRIPTION
       For each operand that names a file of a type other than directory, ls
       displays its name as well as any requested, associated information. For
       each operand that names a file of type directory, ls displays the names of files cotained within that directory, as well as any requested, asso-ciated information.

  以下、まだまだ続く
  ```
- **--warnings[=warnings]** 
  
  groffからの警告を有効にする。warningsにはコンマで区切られた警告名のリストを指定する。指定されていない場合はデフォルトで "mac" になる。
  
  実行例　[](変更しない)
  
  ```
  man --warnings ls
  ```
  
  実行結果 (マニュアルページの表示)[](変更しない)
  
  ```
  LS(1)              User Commands              LS(1)
  NAME
       ls - list directory contents
  
  SYNOPSIS
       ls [OPTION]... [FILE]...
  
  DESCRIPTION
       List  information about the FILEs (the current directory by default).  Sort entries
       alphabetically if none of -cftuvSUX nor --sort is specified.

       Mandatory arguments to long options are mandatory for short options too.

       -a, --all
              do not ignore entries starting with .

       -A, --almost-all
              do not list implied . and ..

       --author
              with -l, print the author of each file

       -b, --escape
              print C-style escapes for nongraphic characters

       --block-size=SIZE
              with -l, scale sizes by SIZE when printing them; e.g., '--block-size=M'; see
              SIZE format below

       -B, --ignore-backups
              do not list implied entries ending with ~
  
  以下、まだまだ続く
  ```
- **-f, --whatis** 
  
  whatisコマンドと全く同じ。可能であれば、マニュアルページから短い説明を表示する。
  
  実行例　[](変更しない)
  
  ```
  man -f ls
  ```
  
  実行結果　[](変更しない)
  
  ```
  ls (1)               - list directory contents
  LS (6)               - display animations aimed to correct users who accidentally enter LS instead of ls .
  ```

  オマケ

  実行例　[](変更しない)
  
  ```
  whatis ls
  ```
  
  実行結果　[](変更しない)
  
  ```
  ls (1)               - list directory contents
  LS (6)               - display animations aimed to correct users who accidentally enter LS instead of ls .
  ```
- **-k, --apropos** 
  
  aproposと全く同じ。マニュアルのタイトルやインデックス文章内でキーワードを検索し、マッチする場合は短いマニュアルページの説明を表示する。
  
  実行例　[](変更しない)
  
  ```
  man -k lists
  ```
  
  実行結果　[](変更しない)
  
  ```
  Algorithm::Diff (3pm) - Compute `intelligent' differences between two files / lists
  Algorithm::DiffOld (3pm) - Compute `intelligent' differences between two files / lists but use the old (<=0.59) interface.
  column (1)           - columnate lists
  figlist (6)          - lists figlet fonts and control files
  git-rev-list (1)     - Lists commit objects in reverse chronological order
  Mail::Field::AddrList (3pm) - object representation of e-mail address lists
  queue (3)            - implementations of linked lists and queues
  queue (7)            - implementations of linked lists and queues
  stdarg (3)           - variable argument lists
  va_arg (3)           - variable argument lists
  va_copy (3)          - variable argument lists
  va_end (3)           - variable argument lists
  va_start (3)         - variable argument lists
  ```

  オマケ

  実行例　[](変更しない)
  
  ```
  apropos lists
  ```
  
  実行結果　[](変更しない)
  
    ```
  Algorithm::Diff (3pm) - Compute `intelligent' differences between two files / lists
  Algorithm::DiffOld (3pm) - Compute `intelligent' differences between two files / lists but use the old (<=0.59) interface.
  column (1)           - columnate lists
  figlist (6)          - lists figlet fonts and control files
  git-rev-list (1)     - Lists commit objects in reverse chronological order
  Mail::Field::AddrList (3pm) - object representation of e-mail address lists
  queue (3)            - implementations of linked lists and queues
  queue (7)            - implementations of linked lists and queues
  stdarg (3)           - variable argument lists
  va_arg (3)           - variable argument lists
  va_copy (3)          - variable argument lists
  va_end (3)           - variable argument lists
  va_start (3)         - variable argument lists
  ```
- **-K, --global-apropos** 
  
  すべてのマニュアルページでテキストを検索する。ソースコード内のコメントアウトも検索範囲内となる。総当たりの検索のため時間がかかる可能性がある。検索語は単純な文字列（デフォルト）または、--regexオプションにより正規表現も使用可。

  
  実行例　[](変更しない)
  
  ```
  man -K cist
  ```
  
  実行結果 (マニュアルページ)[](変更しない)
  
  ```
  GPROF(1)                                                      GNU                                                     GPROF(1)

  NAME
       gprof - display call graph profile data

  SYNOPSIS
       gprof [ -[abcDhilLrsTvwxyz] ] [ -[ACeEfFJnNOpPqQRStZ][name] ]
        [ -I dirs ] [ -d[num] ] [ -k from/to ]
        [ -m min-count ] [ -R map_file ] [ -t table-length ]
        [ --[no-]annotated-source[=name] ]
        [ --[no-]exec-counts[=name] ]
        [ --[no-]flat-profile[=name] ] [ --[no-]graph[=name] ]
        [ --[no-]time=name] [ --all-lines ] [ --brief ]
        [ --debug[=level] ] [ --function-ordering ]
        [ --file-ordering map_file ] [ --directory-path=dirs ]
        [ --display-unused-functions ] [ --file-format=name ]
        [ --file-info ] [ --help ] [ --line ] [ --inline-file-names ]
        [ --min-count=n ] [ --no-static ] [ --print-path ]
        [ --separate-files ] [ --static-call-graph ] [ --sum ]

  以下、まだまだ続く
  ```
  "q"を入力してマニュアルページを抜けると、次のようになる

  ```
  user@localhost:~$ man -K cist
  --Man-- next: gprof(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

  --Man-- next: lastb(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]
  ```
  enter もしくは return を入力することで検索にヒットした次のコマンドである lastbコマンドのマニュアルページを見ることができる。Ctrl-D でスキップできる。
  以下同様に続く。
  ```
  user@localhost:~$ man -K cist
  --Man-- next: gprof(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

  --Man-- next: lastb(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

  --Man-- next: last(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

  --Man-- next: killall5(8) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

  --Man-- next: pidof(8) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]
  ```
- **-l, --local-file** 
  
  "local"モードを有効にする。システムのマニュアルコレクションを検索する代わりに、ローカルなマニュアルファイルをフォーマットして表示する。catファイルは生成されません。引数の中に '-' が指定されている場合、stdinから入力を受け付けます。このオプションを使用しない場合、manが必要なページを見つけられない場合、エラーメッセージを表示する前に、このオプションが指定されたかのように振る舞い、名前をファイル名として使用して完全一致を検索します。
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```
  
  実行結果　[](変更しない)
  
  ```
  実行結果
  ```
- **オプション** 
  
  文章説明
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```
  
  実行結果　[](変更しない)
  
  ```
  実行結果
  ```
- **オプション** 
  
  文章説明
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```
  
  実行結果　[](変更しない)
  
  ```
  実行結果
  ```
- **オプション** 
  
  文章説明
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```
  
  実行結果　[](変更しない)
  
  ```
  実行結果
  ```
- **オプション** 
  
  文章説明
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```
  
  実行結果　[](変更しない)
  
  ```
  実行結果
  ```