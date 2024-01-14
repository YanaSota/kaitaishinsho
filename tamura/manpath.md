[](manpath.md)
# manpath
マニュアルページの検索パス（ manpath ）を決定、表示するための \**ユーティリティ* 。

（\* ユーティリティ : コンピュータの分析、構成、最適化、保守のためのソフトウェアの総称。ユーティリティソフトウェアとも呼ばれる。）

環境変数 `$MANPATH` が設定されている場合、`manpath` はその内容を表示して警告を発する。
もし設定されていなければ、 `manpath` は適切なマニュアルページの階層検索パスを決定し、その結果を表示する。

パスはコロンで区切られ、`/etc/manpath.config`（ man-dbの設定ファイル ）およびユーザーの環境から取得された情報を使用して決定される。

実行例 []()
```
manpath
```

実行結果 []()
```
/usr/local/man:/usr/local/share/man:/usr/share/man/cat1:/usr/share/man
```

### オプション一覧
    
- **-c, --catpath**

  manpath が決定された後、各パス要素を相対的な catpath に変換するオプション。

  実行例 []()
  ```
  manpath -c
  ```

  実行結果 []()
  ```
  /var/cache/man/oldlocal:/var/cache/man/local:/usr/share/man/cat1:/var/cache/man
  ```

  余談だが、`/etc/manpath.config` という設定ファイルの中に次のような記述がある。

  [/etc/manpath.config]()
  ```
  #         *MANPATH*      ->	    *CATPATH*
  #
  MANDB_MAP	/usr/man		          /var/cache/man/fsstnd
  MANDB_MAP	/usr/share/man		    /var/cache/man
  MANDB_MAP	/usr/local/man		    /var/cache/man/oldlocal
  MANDB_MAP	/usr/local/share/man	/var/cache/man/local
  MANDB_MAP	/usr/X11R6/man		    /var/cache/man/X11R6
  MANDB_MAP	/opt/man		          /var/cache/man/opt
  MANDB_MAP	/snap/man		          /var/cache/man/snap
  ```

  ここのコンフィグファイルに書かれているマッピングをもとに変換されることが最初に例示した実行例と上記の実行例からわかる。

- **-C FILE, --config-file=FILE**

  このユーザー設定ファイルを使用し、デフォルトの `~/.manpath` ではない manpath を決定するオプション。

  実行例 []()
  ```
  manpath -C hoge.conf
  ```

  実行結果 [~/manpath]()
  ```
  // hoge.conf というコンフィグファイルを用意
  user@localhost:~/manpath$ ls
  hoge.conf

  // 内容は次のとおり
  MANDATORY_MANPATH  /etc

  // 実行結果
  /usr/local/man:/usr/local/share/man:/usr/share/man/cat1:/usr/share/man:/etc
  ```

  `/etc` ディレクトリが追加されていることがわかる。

- **-d, --debug**

  デバッグ情報を表示するオプション。

  実行例 []()
  ```
  manpath -d
  ```

  実行結果 [~/manpath]()
  ```
  From the config file /etc/manpath.config:
  Mandatory mandir `/usr/man'.
  Mandatory mandir `/usr/share/man'.
  Mandatory mandir `/usr/local/share/man'.
  Path `/bin' mapped to mandir `/usr/share/man'.
  Path `/usr/bin' mapped to mandir `/usr/share/man'.
  Path `/sbin' mapped to mandir `/usr/share/man'.
  Path `/usr/sbin' mapped to mandir `/usr/share/man'.
  Path `/usr/local/bin' mapped to mandir `/usr/local/man'.
  Path `/usr/local/bin' mapped to mandir `/usr/local/share/man'.
  Path `/usr/local/bin' mapped to mandir `/usr/share/man/cat1'.
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
  path directory /home/shuuto/.local/bin is not in the config file
  path directory /usr/local/sbin is in the config file
    adding /usr/local/man to manpath
    adding /usr/local/share/man to manpath
  path directory /usr/local/bin is in the config file
    adding /usr/share/man/cat1 to manpath
  path directory /usr/sbin is in the config file
    adding /usr/share/man to manpath
  path directory /usr/bin is in the config file
  path directory /sbin is in the config file
  path directory /bin is in the config file
  path directory /usr/games is in the config file
  path directory /usr/local/games is not in the config file
  path directory /snap/bin is not in the config file
  adding mandatory man directories
  warning: /usr/man: No such file or directory
  /usr/local/man:/usr/local/share/man:/usr/share/man/cat1:/usr/share/man
  ```

- **-g, --global**

   man-db設定ファイルで「global」として指定されたすべてのパスから構成される manpath を生成するオプション。

  実行例 []()
  ```
  manpath -g
  ```

  実行結果 []()
  ```
  /usr/man:/usr/share/man:/usr/local/man:/usr/local/share/man:/usr/X11R6/man:/opt/man:/snap/man
  ```
