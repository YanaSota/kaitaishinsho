[](man.md)
# man
各種コマンド（厳密にはディレクトリやユーティリティと呼ばれるものも含む）の manページ(マニュアルページ) を表示するコマンド。
マニュアルページとはほとんどの UNIXライクなOSで初めからインストールされているドキュメントのことで、慣習として各種コマンドの使用例や書式、オプション、戻り値などが記載されている。マニュアルページは標準では環境変数 `$MANPATH` で指定されている場所に保存されている。
マニュアルページは標準では `less` コマンドを使って表示されており、`less` コマンド以外の表示コマンド（ページャーと呼ぶ）を使用することもできる。ここの例は ページャーを `less` としているため、上下キーで表示を移動させ、`q` キーを押すことでマニュアルページから抜けられる。

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
  
  実行例 [](変更しない)
  
  ```
  man -d
  ```
  
  実行結果 [](変更しない)
  
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
  
  実行例 [](変更しない)
  
  ```
  man -D ls
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

- **--warnings[=warnings]** 
  
  groffからの警告を有効にする。warningsにはコンマで区切られた警告名のリストを指定する。指定されていない場合はデフォルトで "mac" になる。
  
  実行例 [](変更しない)
  
  ```
  man --warnings ls
  ```
  
  実行結果 (マニュアルページ)[](変更しない)
  
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
  
  `whatis` コマンドと全く同じ。可能であれば、マニュアルページから短い説明を表示する。
  
  実行例 [](変更しない)
  
  ```
  man -f ls
  ```
  
  実行結果 [](変更しない)
  
  ```
  ls (1)               - list directory contents
  LS (6)               - display animations aimed to correct users who accidentally enter LS instead of ls .
  ```

  オマケ

  実行例 [](変更しない)
  
  ```
  whatis ls
  ```
  
  実行結果 [](変更しない)
  
  ```
  ls (1)               - list directory contents
  LS (6)               - display animations aimed to correct users who accidentally enter LS instead of ls .
  ```

- **-k, --apropos** 
  
  `apropos` コマンドと全く同じ。マニュアルのタイトルやインデックス文章内でキーワードを検索し、マッチする場合は短いマニュアルページの説明を表示する。
  
  実行例 [](変更しない)
  
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

  実行例 [](変更しない)
  
  ```
  apropos lists
  ```
  
  実行結果 [](変更しない)
  
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

  
  実行例 [](変更しない)
  
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

  `q` キーを入力してマニュアルページを抜けると、次のようになる

  ```
  user@localhost:~$ man -K cist
  --Man-- next: gprof(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]

  --Man-- next: lastb(1) [ view (return) | skip (Ctrl-D) | quit (Ctrl-C) ]
  ```

  enter もしくは return を入力することで検索にヒットした次のコマンドである `lastb` コマンドのマニュアルページを見ることができる。`Ctrl-D` でスキップできる。
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
  
  "local"モードを有効にする。引数に指定したファイルをマニュアルページとして表示する。
  
  実行例　[](変更しない)
  
  ```
  man -l man.md
  ```
  
  実行結果　(マニュアルページ)[](変更しない)
  
  ```
  [](man.md)                          #                         man
  各種コマンド（厳密にはディレクトリやユーティリティと呼ばれるものも含む）の
  manページ(マニュアルページ)                  を表示するコマンド。
  マニュアルページとはほとんどの
  UNIXライクなOSで初めからインストールされているドキュメントのことで、慣習として各種コマンドの使用例や書式、オプション、戻り値などが記載されている。マニュアルページは標準では環境変数
  ‘$MANPATH‘                 で指定されている場所に保存されている。
  マニュアルページは標準では
  ‘less‘コマンドを使って表示されており、‘less‘コマンド以外の表示コマンド（ページャーと呼ぶ）を使用することもできる。ここの例は
  ページャーを ‘less‘ としているため、上下キーで表示を移動させ、‘q‘
  キーを押すことでマニュアルページから抜けられる。

    実行例 [](変更しない)

    ‘‘‘
    man ls
    ‘‘‘

    実行結果 (マニュアルページ)[](変更しない)

    ‘‘‘
  Manual page man.md line 1 (press h for help or q to quit)

  以下、まだまだ続く
  ```

- **-w, --where, --path, --location**

  指定されたコマンドやファイルがマニュアルページを持っているかどうかを確認するオプション。マニュアルページが存在する場合はその `PATH` が表示され、存在しない場合は何も表示されない。`-a` オプションを同時に使用することで全てのソースファイル（マニュアルページ）の場所が表示される。

  実行例 ( `-w` のみ)[](変更しない)

  ```
  man -w ls
  ```

  実行結果 [](変更しない)

  ```
  /usr/share/man/man1/ls.1.gz
  ```

  実行例 ( `-a` の併用)[](変更しない)

  ```
  man -wa ls
  ```

  実行結果 [](変更しない)

  ```
  /usr/share/man/man1/ls.1.gz
  /usr/share/man/man6/LS.6.gz
  ```

- **-W, --where-cat, --location-cat**

  プリフォーマットされた catファイルの場所を表示する。 `-a` オプションを同時に使用することで条件に完全一致する全てのプリフォーマットされた catファイルの場所を表示する。
  `-w` と `-W` が同時に使用された場合は、ソースファイル（マニュアルページ）と catファイルの両方の場所がスペース区切りで表示する。

  実行例 ()[](変更しない)

  ```
  man -W ls
  ```

  実行結果 [](変更しない)

  ```
  ごめんなさい、catファイルが保存されているはずのディレクトリが無く、実行結果をお見せすることができません。
  ```

- **-c, --catman**

  `catman` コマンドと全く同じ。基本的には通常ユーザやシステム管理者でさえ使用すべきでないオプション。
  `catman` コマンドはマニュアルページをプリフォーマットされた catファイル に変換するプログラム。
  `man -c` はどうにも動かなかったので一応 `catman` の実行を示す。

  実行例 [](変更しない)

  ```
  sudo catman
  ```

  実行結果 [](変更しない)

  ```
  Updating cat files for section 1 of man hierarchy /usr/share/man
  man: can't chown (null): Bad address
  man: can't unlink (null): Bad address
  aa-enabled, man: can't chown (null): Bad address
  man: can't unlink (null): Bad address
  aa-exec, man: can't chown (null): Bad address
  man: can't unlink (null): Bad address
  aa-features-abi, man: can't chown (null): Bad address
  man: can't unlink (null): Bad address
  add-apt-repository, man: can't chown (null): Bad address
  man: can't unlink (null): Bad address
  addr2line, man: can't chown (null): Bad address
  man: can't unlink (null): Bad address
  apport-bug, man: can't chown (null): Bad address
  man: can't unlink (null): Bad address

  以降、全てのマニュアルページが存在するコマンドについて更新が行われるが、sudo権限でもアップデートすることができない
  ```

- **-R, --recode=ENCODING**

  指定されたエンコーディング形式に変換されたソースを出力するためのオプション。

  実行例 [](変更しない)

  ```
  man -R UTF-8 ls
  ```

  実行結果 [](変更しない)

  ```
  .\" DO NOT MODIFY THIS FILE!  It was generated by help2man 1.47.3.
  .TH LS "1" "February 2022" "GNU coreutils 8.32" "User Commands"
  .SH NAME
  ls \- list directory contents
  .SH SYNOPSIS
  .B ls
  [\fI\,OPTION\/\fR]... [\fI\,FILE\/\fR]...
  .SH DESCRIPTION
  .\" Add any additional description here
  .PP
  List information about the FILEs (the current directory by default).
  Sort entries alphabetically if none of \fB\-cftuvSUX\fR nor \fB\-\-sort\fR is specified.
  .PP
  Mandatory arguments to long options are mandatory for short options too.
  .TP
  \fB\-a\fR, \fB\-\-all\fR
  do not ignore entries starting with .
  .TP
  \fB\-A\fR, \fB\-\-almost\-all\fR
  do not list implied . and ..
  .TP
  \fB\-\-author\fR
  with \fB\-l\fR, print the author of each file
  .TP
  \fB\-b\fR, \fB\-\-escape\fR
  print C\-style escapes for nongraphic characters
  .TP
  \fB\-\-block\-size\fR=\fI\,SIZE\/\fR
  with \fB\-l\fR, scale sizes by SIZE when printing them;
  e.g., '\-\-block\-size=M'; see SIZE format below
  .TP
  \fB\-B\fR, \fB\-\-ignore\-backups\fR
  do not list implied entries ending with ~
  .TP
  \fB\-c\fR
  with \fB\-lt\fR: sort by, and show, ctime (time of last
  modification of file status information);
  with \fB\-l\fR: show ctime and sort by name;
  otherwise: sort by ctime, newest first
  .TP
  \fB\-C\fR
  list entries by columns
  .TP
  \fB\-\-color\fR[=\fI\,WHEN\/\fR]
  colorize the output; WHEN can be 'always' (default
  if omitted), 'auto', or 'never'; more info below
  .TP
  \fB\-d\fR, \fB\-\-directory\fR
  list directories themselves, not their contents
  .TP
  \fB\-D\fR, \fB\-\-dired\fR
  generate output designed for Emacs' dired mode
  .TP
  \fB\-f\fR
  do not sort, enable \fB\-aU\fR, disable \fB\-ls\fR \fB\-\-color\fR
  .TP
  \fB\-F\fR, \fB\-\-classify\fR
  append indicator (one of */=>@|) to entries
  .TP
  \fB\-\-file\-type\fR
  likewise, except do not append '*'
  .TP
  \fB\-\-format\fR=\fI\,WORD\/\fR
  across \fB\-x\fR, commas \fB\-m\fR, horizontal \fB\-x\fR, long \fB\-l\fR,
  single\-column \fB\-1\fR, verbose \fB\-l\fR, vertical \fB\-C\fR
  .TP
  \fB\-\-full\-time\fR
  like \fB\-l\fR \fB\-\-time\-style\fR=\fI\,full\-iso\/\fR
  .TP
  \fB\-g\fR
  like \fB\-l\fR, but do not list owner
  .TP
  \fB\-\-group\-directories\-first\fR
  group directories before files;
  .IP
  can be augmented with a \fB\-\-sort\fR option, but any
  use of \fB\-\-sort\fR=\fI\,none\/\fR (\fB\-U\fR) disables grouping
  .TP
  \fB\-G\fR, \fB\-\-no\-group\fR
  in a long listing, don't print group names
  .TP
  \fB\-h\fR, \fB\-\-human\-readable\fR
  with \fB\-l\fR and \fB\-s\fR, print sizes like 1K 234M 2G etc.
  .TP
  \fB\-\-si\fR
  likewise, but use powers of 1000 not 1024
  .TP
  \fB\-H\fR, \fB\-\-dereference\-command\-line\fR
  follow symbolic links listed on the command line
  .TP
  \fB\-\-dereference\-command\-line\-symlink\-to\-dir\fR
  follow each command line symbolic link
  .IP
  that points to a directory
  .TP
  \fB\-\-hide\fR=\fI\,PATTERN\/\fR
  do not list implied entries matching shell PATTERN
  (overridden by \fB\-a\fR or \fB\-A\fR)
  .TP
  \fB\-\-hyperlink\fR[=\fI\,WHEN\/\fR]
  hyperlink file names; WHEN can be 'always'
  (default if omitted), 'auto', or 'never'
  .TP
  \fB\-\-indicator\-style\fR=\fI\,WORD\/\fR
  append indicator with style WORD to entry names:
  none (default), slash (\fB\-p\fR),
  file\-type (\fB\-\-file\-type\fR), classify (\fB\-F\fR)
  .TP
  \fB\-i\fR, \fB\-\-inode\fR
  print the index number of each file
  .TP
  \fB\-I\fR, \fB\-\-ignore\fR=\fI\,PATTERN\/\fR
  do not list implied entries matching shell PATTERN
  .TP
  \fB\-k\fR, \fB\-\-kibibytes\fR
  default to 1024\-byte blocks for disk usage;
  used only with \fB\-s\fR and per directory totals
  .TP
  \fB\-l\fR
  use a long listing format
  .TP
  \fB\-L\fR, \fB\-\-dereference\fR
  when showing file information for a symbolic
  link, show information for the file the link
  references rather than for the link itself
  .TP
  \fB\-m\fR
  fill width with a comma separated list of entries
  .TP
  \fB\-n\fR, \fB\-\-numeric\-uid\-gid\fR
  like \fB\-l\fR, but list numeric user and group IDs
  .TP
  \fB\-N\fR, \fB\-\-literal\fR
  print entry names without quoting
  .TP
  \fB\-o\fR
  like \fB\-l\fR, but do not list group information
  .TP
  \fB\-p\fR, \fB\-\-indicator\-style\fR=\fI\,slash\/\fR
  append / indicator to directories
  .TP
  \fB\-q\fR, \fB\-\-hide\-control\-chars\fR
  print ? instead of nongraphic characters
  .TP
  \fB\-\-show\-control\-chars\fR
  show nongraphic characters as\-is (the default,
  unless program is 'ls' and output is a terminal)
  .TP
  \fB\-Q\fR, \fB\-\-quote\-name\fR
  enclose entry names in double quotes
  .TP
  \fB\-\-quoting\-style\fR=\fI\,WORD\/\fR
  use quoting style WORD for entry names:
  literal, locale, shell, shell\-always,
  shell\-escape, shell\-escape\-always, c, escape
  (overrides QUOTING_STYLE environment variable)
  .TP
  \fB\-r\fR, \fB\-\-reverse\fR
  reverse order while sorting
  .TP
  \fB\-R\fR, \fB\-\-recursive\fR
  list subdirectories recursively
  .TP
  \fB\-s\fR, \fB\-\-size\fR
  print the allocated size of each file, in blocks
  .TP
  \fB\-S\fR
  sort by file size, largest first
  .TP
  \fB\-\-sort\fR=\fI\,WORD\/\fR
  sort by WORD instead of name: none (\fB\-U\fR), size (\fB\-S\fR),
  time (\fB\-t\fR), version (\fB\-v\fR), extension (\fB\-X\fR)
  .TP
  \fB\-\-time\fR=\fI\,WORD\/\fR
  change the default of using modification times;
  access time (\fB\-u\fR): atime, access, use;
  change time (\fB\-c\fR): ctime, status;
  birth time: birth, creation;
  .IP
  with \fB\-l\fR, WORD determines which time to show;
  with \fB\-\-sort\fR=\fI\,time\/\fR, sort by WORD (newest first)
  .TP
  \fB\-\-time\-style\fR=\fI\,TIME_STYLE\/\fR
  time/date format with \fB\-l\fR; see TIME_STYLE below
  .TP
  \fB\-t\fR
  sort by time, newest first; see \fB\-\-time\fR
  .TP
  \fB\-T\fR, \fB\-\-tabsize\fR=\fI\,COLS\/\fR
  assume tab stops at each COLS instead of 8
  .TP
  \fB\-u\fR
  with \fB\-lt\fR: sort by, and show, access time;
  with \fB\-l\fR: show access time and sort by name;
  otherwise: sort by access time, newest first
  .TP
  \fB\-U\fR
  do not sort; list entries in directory order
  .TP
  \fB\-v\fR
  natural sort of (version) numbers within text
  .TP
  \fB\-w\fR, \fB\-\-width\fR=\fI\,COLS\/\fR
  set output width to COLS.  0 means no limit
  .TP
  \fB\-x\fR
  list entries by lines instead of by columns
  .TP
  \fB\-X\fR
  sort alphabetically by entry extension
  .TP
  \fB\-Z\fR, \fB\-\-context\fR
  print any security context of each file
  .TP
  \fB\-1\fR
  list one file per line.  Avoid '\en' with \fB\-q\fR or \fB\-b\fR
  .TP
  \fB\-\-help\fR
  display this help and exit
  .TP
  \fB\-\-version\fR
  output version information and exit
  .PP
  The SIZE argument is an integer and optional unit (example: 10K is 10*1024).
  Units are K,M,G,T,P,E,Z,Y (powers of 1024) or KB,MB,... (powers of 1000).
  Binary prefixes can be used, too: KiB=K, MiB=M, and so on.
  .PP
  The TIME_STYLE argument can be full\-iso, long\-iso, iso, locale, or +FORMAT.
  FORMAT is interpreted like in date(1).  If FORMAT is FORMAT1<newline>FORMAT2,
  then FORMAT1 applies to non\-recent files and FORMAT2 to recent files.
  TIME_STYLE prefixed with 'posix\-' takes effect only outside the POSIX locale.
  Also the TIME_STYLE environment variable sets the default style to use.
  .PP
  Using color to distinguish file types is disabled both by default and
  with \fB\-\-color\fR=\fI\,never\/\fR.  With \fB\-\-color\fR=\fI\,auto\/\fR, ls emits color codes only when
  standard output is connected to a terminal.  The LS_COLORS environment
  variable can change the settings.  Use the dircolors command to set it.
  .SS "Exit status:"
  .TP
  0
  if OK,
  .TP
  1
  if minor problems (e.g., cannot access subdirectory),
  .TP
  2
  if serious trouble (e.g., cannot access command\-line argument).
  .SH AUTHOR
  Written by Richard M. Stallman and David MacKenzie.
  .SH "REPORTING BUGS"
  GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
  .br
  Report any translation bugs to <https://translationproject.org/team/>
  .SH COPYRIGHT
  Copyright \(co 2020 Free Software Foundation, Inc.
  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
  .br
  This is free software: you are free to change and redistribute it.
  There is NO WARRANTY, to the extent permitted by law.
  .SH "SEE ALSO"
  Full documentation <https://www.gnu.org/software/coreutils/ls>
  .br
  or available locally via: info \(aq(coreutils) ls invocation\(aq
  ```

- **-L, --locale=LOCALE**

  引数にロケール文字列を指定することで一時的に locale (Linux上の言語や知識の設定のこと) をオーバーライドするオプション。
  通常は locale は `setlocale` コマンドにて環境変数を上書きすることで設定するが、このオプションでは出力を一時的に locale を変更することができる。

  実行例 [](変更しない)

  ```
  man -L ja_JP.UTF-8 ls
  ```

  実行結果 [](変更しない)

  ```
  LS(1)                           ユーザーコマンド                           LS(1)

  名前
        ls - ディレクトリの内容をリスト表示する

  書式
        ls [オプション]... [ファイル]...

  説明
        FILE    (デフォルトは現在のディレクトリ)   に関する情報を一覧表示します。
        -cftuvSUX のいずれも指定されず、 --sort も指定されていない場合、 要素はア
        ルファベット順でソートされます。

        長いオプションで必須となっている引数は短いオプションでも必須です。

        -a, --all
                . で始まる要素を無視しない

        -A, --almost-all
                . および .. を一覧表示しない

        --author                -l と合わせて使用した時、各ファイルの作成者を表示
                する

        -b, --escape
                表示不可能な文字の場合に C 形式のエスケープ文字を表示する

        --block-size=SIZE
                SIZE の倍数として表示する。例:  '--block-size=M'  は  表示する時に
                1,048,576 バイトを単位としてサイズを 表示する。SIZE の形式は以下を
                参照

  Manual page ls(1) line 1 (press h for help or q to quit)
  ```

- **-m, --systems=SYSTEM**

  他のシステムからマニュアルページを使用する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-M, --manpath=PATH**

  マニュアルページの検索パスをPATHに設定する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-e, --extension=EXTENSION**

  検索を拡張子タイプに限定する EXTENSION

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-i, --ignore-case**

  大文字小文字を区別せずにページを探す (デフォルト)

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-I, --match-case**

  ケース・センシティブにページを探す

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--regex**

  正規表現にマッチするすべてのページを表示する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--wildcard**

  ワイルドカードに一致するすべてのページを表示する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--names-only**

  regexと--wildcardはページ名のみにマッチします、
                             説明文ではなく

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-a, --all**

  一致するマニュアルのページをすべて見つける

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-u, --update**

  キャッシュ一貫性チェックの強制

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--no-subpages**

  例えば、'man foo bar' => 'man
                             foo-bar'

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-P, --pager=PAGER**

  プログラムPAGERを使って出力を表示する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-r, --prompt=STRING**

  レス'ページャーにプロンプトを出す

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-7, --ascii**

  特定の latin1 文字の ASCII 変換を表示する。

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-E, --encoding=ENCODING**

  選択した出力エンコーディングを使用する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--no-hyphenation, --nh turn off hyphenation**

  --nj 正当化機能をオフにする

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--no-justification,**

  STRINGは実行するプリプロセッサを示す：
                             e - [n]eqn, p - pic, t - tbl、
g - grap, r - refer, v - vgrind

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-p, --preprocessor=STRING**

  groffを使用してページをフォーマットする

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-t, --troff**

  選択したデバイスでgroffを使用する

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-T, --troff-device[=DEVICE]**

  使用
                             /home/shuuto/.vscode-server/bin/1a5daa3a0231a0fbba4f14db7ec463cf99d7768e/bin/helpers/browser.shを使用してください。
                             またはHTML出力を表示するBROWSER

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-H, --html[=BROWSER]**

  groff を使って gxditview で表示する
                             (X11):

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-X, --gxditview[=RESOLUTION]**

  グロフを使い、ディトロフを作らせる

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **-Z, --ditroff**

  短い使用メッセージを伝える

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```

- **--usage**

  印刷プログラムバージョン

  実行例 [](変更しない)

  ```
  実行例
  ```

  実行結果 [](変更しない)

  ```
  実行結果
  ```