[](man.md)
# man
各種コマンドの manページ(マニュアルページ) を表示するコマンド。
manページとはほとんどの UNIXライクなOSで初めからインストールされているドキュメントのことで、慣習として各種コマンドの使用例や書式、オプション、戻り値などが記載されている。

  実行例 [](変更しない)
  
  ```
  man ls
  ```

  実行結果 (manページ )[](変更しない)

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
  
  実行結果 (manページの表示)[](変更しない)
  
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
  
  実行結果 (manページの表示)[](変更しない)
  
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