[](ファイル名はコマンド名.md)
# find
指定されたPATHを始点とするディレクトリツリーを探索し、与えられた式を、優先規則に従いつつ、左から右へ評価することによって検索を行う。結果が確定すると(例えば、and演算なら左辺が偽になった時点で、or演算なら左辺が真になった時点で)、findは検査の対象を次のファイル名に移す。
後述するオプションのうち、整数を引数として指定するオプションにおいて、nを整数とすると、"+n"とするとnを超える数であることを意味し、"-n"とするとn未満であることを意味する。"n"とするとぴったりnであることを意味する。

  実行例 [](変更しない)
  
  ```
  なし
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```

### オプション一覧


- **-name**
  
  ファイルやディレクトリのベースネーム(パスから最後の要素だけを残し、先行するディレクトリを取り去ったもの)が、マッチすれば出力する。

  実行例 [](変更しない)
  
  ```
  find /home/user/ -name a.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/a.txt
  ```
- **-iname** 
    
  -nameと同じだが、大文字小文字を区別しない。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -iname a.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/A.txt
  /home/user/a.txt
  ```
- **-type f** 
    
  タイプがファイルであれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -type f
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/upload_and_run.py
  /home/user/project/index.html
  /home/user/.wget-hsts
  /home/user/.profile
  ```
- **-type d** 
    
  タイプがディレクトリであれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -type d
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/docker
  /home/user/project/upload
  /home/user/.vnc
  ```
- **-size** 
    
  ファイルの容量が指定した値であれば出力する。次の接尾辞を使用できる。
  "b" ブロック。1ブロックは512バイトである。接尾辞を使用しない場合のデフォルトである。
  "c" バイト。
  "w" ワード。1ワードは2バイト。
  "k" キロバイト。1キロバイトは1024バイト。
  "M" メガバイト。1メガバイトは1048576バイト。
  "G" ギガバイト。1ギガバイトは1073741824バイト。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -size 10c
  ```


  実行結果　[](変更しない)


  ```
  /home/user/snap/firefox/common/.mozilla/firefox/Crash Reports/InstallTime20230512012512
  /home/user/snap/firefox/common/.mozilla/firefox/Crash Reports/InstallTime20230414190624
  /home/user/snap/firefox/common/.mozilla/firefox/Crash Reports/InstallTime20230710222611
  ~略~
  ```
- **-newer** 
    
  指定したファイルの内容更新日時よりも、内容更新日時が最近であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -newer a.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/
  /home/user/A.txt
  /home/user/.cache/tracker3/files
  ~略~
  ```
- **-anewer** 
    
  指定したファイルの内容更新日時よりも、最終アクセス日時が最近であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -anewer a.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/
  /home/user/A.txt
  /home/user/a.txt
  ~略~
  ```
- **-cnewer** 
    
  指定したファイルの内容更新日時よりも、最終ステータス変更日時が最近であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -cnewer a.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/
  /home/user/test
  /home/user/test/t.txt
  ~略~
  ```
- **-maxdepth** 
    
  指定されたパスから最大何段階下のディレクトリまで探索するかを指定する。実行例では、/home/user/test/test1というディレクトリ構造になっており、testディレクトリにt.txt、test1ディレクトリにT.txtというファイルを配置したマシンを想定し、引数を変えて実行した。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -maxdepth 2 -iname t.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t.txt
  ```

  実行例　[](変更しない)
  
  ```
  find /home/user/ -maxdepth 3 -iname t.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t.txt
  /home/user/test/test1/T.txt
  ```
- **-mindepth** 
    
  指定されたパスから少なくとも何段階下のディレクトリまで探索しないかを指定する。実行例では、/home/user/test/test1というディレクトリ構造になっており、testディレクトリにt.txt、test1ディレクトリにT.txtというファイルを配置したマシンを想定し、引数を変えて実行した。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -mindepth 3 -iname t.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/test1/T.txt
  ```

  実行例　[](変更しない)
  
  ```
  find /home/user/ -mindepth 2 -iname t.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t.txt
  /home/user/test/test1/T.txt
  ```
- **-daystart** 
    
  後述する-mtime、-mmin、-atime、-amin、-ctime、-cminにおいて、デフォルトでは時間を計算する際の基準をコマンド実行時ピッタリの日時となるが、このオプションを先に指定することで、時間を計算する際の基準をコマンド実行時当日の0時とする。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -daystart -ctime -1
  ```


  実行結果　[](変更しない)


  ```
  /home/user/
  /home/user/test
  /home/user/test/t.txt
  ~略~
  ```
- **-mtime** 
    
  ファイルの最終内容更新日時が、指定した数字"日"であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -mtime 0
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/.cache/tracker3/files/meta.db-wal
  /home/user/.cache/tracker3/files/http%3A%2F%2Ftracker.api.gnome.org%2Fontology%2Fv3%2Ftracker%23Documents.db-shm
  /home/user/.cache/update-manager-core/meta-release-lts
  ```
- **-mmin** 
    
  ファイルの最終内容更新日時が、指定した数字"分"であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -mmin -30
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/.cache/tracker3/files/last-crawl.txt
  /home/user/.cache/tracker3/files/http%3A%2F%2Ftracker.api.gnome.org%2Fontology%2Fv3%2Ftracker%23FileSystem.db-wal
  /home/user/.cache/tracker3/files/meta.db-wal
  ```
- **-atime** 
    
  ファイルの最終アクセス日時が、指定した数字"日"であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -atime 0
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/upload
  /home/user/.profile
  /home/user/.vnc
  ```
- **-amin** 
    
  ファイルの最終アクセス日時が、指定した数字"分"であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -amin -30
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/.cache/tracker3/files/last-crawl.txt
  /home/user/.cache/tracker3/files/http%3A%2F%2Ftracker.api.gnome.org%2Fontology%2Fv3%2Ftracker%23FileSystem.db-wal
  /home/user/.cache/tracker3/files/meta.db-wal
  ```
- **-ctime** 
    
  ファイルの最終ステータス変更日時が、指定した数字"日"であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -ctime 0
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/.cache/tracker3/files/meta.db-wal
  /home/user/.cache/tracker3/files/http%3A%2F%2Ftracker.api.gnome.org%2Fontology%2Fv3%2Ftracker%23Documents.db-shm
  /home/user/.cache/update-manager-core/meta-release-lts
  ```
- **-cmin** 
    
  ファイルの最終ステータス変更日時が、指定した数字"分"であれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -cmin -30
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/.cache/tracker3/files/last-crawl.txt
  /home/user/.cache/tracker3/files/http%3A%2F%2Ftracker.api.gnome.org%2Fontology%2Fv3%2Ftracker%23FileSystem.db-wal
  /home/user/.cache/tracker3/files/http%3A%2F%2Ftracker.api.gnome.org%2Fontology%2Fv3%2Ftracker%23Documents.db-shm
  ```
- **-empty** 
    
  空のファイルかディレクトリであれば出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -empty
  ```


  実行結果　[](変更しない)


  ```
  /home/user/.cache/sessions
  /home/user/.cache/motd.legal-displayed
  /home/user/project/upload
  ~略~
  ```
- **-regex** 
    
  指定した正規表現と一致した場合に出力する。この場合の一致とは、PATHも含めたファイル名全体に対する一致である。例えば、./fubar3という名前のファイルに一致させるために、正規表現".*bar."や".*b.*3"は使用できるが、"f.*r3"は使用できない。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -regex .*t2.txt
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/ダウンロード/go1.20.2.linux-amd64/go/src/go/doc/comment/testdata/text2.txt
  /home/user/ダウンロード/go1.20.2.linux-amd64/go/src/go/doc/comment/testdata/list2.txt
  /home/user/output2.txt
  ```
- **-iregex** 
    
  -regexと同じだが、大文字小文字を区別しない。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -iregex .*T2.txt
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/ダウンロード/go1.20.2.linux-amd64/go/src/go/doc/comment/testdata/text2.txt
  /home/user/ダウンロード/go1.20.2.linux-amd64/go/src/go/doc/comment/testdata/list2.txt
  /home/user/output2.txt
  ```
- **-perm** 
    
  ファイルの権限が一致した場合に出力する。権限の前に"-"を付けると、0以外の権限が全て与えられているファイルを出力する。権限の前に"/"を付けると、0以外の権限のどれかが与えられているファイルを出力する。

  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -maxdepth 1 -perm 777
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t1.txt
  ```
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -maxdepth 1 -perm -707
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t1.txt
  ```

  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -maxdepth 1 -perm /706
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t.txt
  /home/user/test/t1.txt
  /home/user/test/test1
  ```
  
- **-user** 
    
  ファイルの所有者が指定したユーザ名と一致した場合に出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -user root
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/docker/Dockerfile
  /home/user/project/upload_and_run.py
  /home/user/project/index.html
  ```
- **-uid** 
    
  ファイルの所有者が指定したユーザIDと一致した場合に出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -uid 0
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/docker/Dockerfile
  /home/user/project/upload_and_run.py
  /home/user/project/index.html
  ```
- **-group** 
    
  ファイルの属するグループが指定したグループ名と一致した場合に出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -group root
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/docker/Dockerfile
  /home/user/project/upload_and_run.py
  /home/user/project/index.html
  ```
- **-gid** 
    
  ファイルの属するグループIDが指定したグループIDと一致した場合に出力する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/ -group 0
  ```


  実行結果　[](変更しない)


  ```
  ~略~
  /home/user/project/docker/Dockerfile
  /home/user/project/upload_and_run.py
  /home/user/project/index.html
  ```
- **-delete** 
    
  探索したファイルを消去する。実行結果では、実行前と実行後に"ls -la"を実行した出力を記述する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -maxdepth 1 -perm 777 -delete
  ```


  実行結果　[](変更しない)


  ```
  実行前
  drwxrwxr-x  3 user user 4096  1月 30 04:11 .
  drwxr-x--- 29 user user 4096  1月 30 02:28 ..
  -rw-rw-rw-  1 user user    0  1月 30 02:28 t.txt
  drwxrwxr-x  2 user user 4096  1月 30 02:29 test1
  -rwxrwxrwx  1 root  root     0  1月 30 04:11 test1.txt

  実行後
  drwxrwxr-x  3 user user 4096  1月 30 04:12 .
  drwxr-x--- 29 user user 4096  1月 30 02:28 ..
  -rw-rw-rw-  1 user user    0  1月 30 02:28 t.txt
  drwxrwxr-x  2 user user 4096  1月 30 02:29 test1
  ```
- **-exec** 
    
  探索したファイルに対して、指定したコマンドを実行する。"-exec コマンド {} \;"のように記述する。{}は探索した全てのファイル名に置き換えられる。コマンドの終わりには\;が必要。実行結果では、実行前と実行後に"ls -la"を実行した出力を記述する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -perm 777 -exec sudo chmod 666 {} \;
  ```


  実行結果　[](変更しない)


  ```
  実行前
  drwxrwxr-x  3 user user 4096  1月 30 04:23 .
  drwxr-x--- 29 user user 4096  1月 30 04:21 ..
  -rwxrwxrwx  1 user user    0  1月 30 02:28 t.txt
  -rwxrwxrwx  1 root  root    15  1月 30 04:14 test.py
  drwxrwxr-x  2 user user 4096  1月 30 02:29 test1
  -rwxrwxrwx  1 root  root    22  1月 30 04:23 test1.py

  実行後
  drwxrwxr-x  3 user user 4096  1月 30 04:23 .
  drwxr-x--- 29 user user 4096  1月 30 04:21 ..
  -rw-rw-rw-  1 user user    0  1月 30 02:28 t.txt
  -rw-rw-rw-  1 root  root    15  1月 30 04:14 test.py
  drwxrwxr-x  2 user user 4096  1月 30 02:29 test1
  -rw-rw-rw-  1 root  root    22  1月 30 04:23 test1.py
  ```
- **-ok** 
    
  -exec と似ているが、まずユーザに問い合わせを行う。ユーザーが同意すれば、 コマンドを実行する。同意しなければ、何もしない。helloと標準出力に出力するtest.pyと、good morningと標準出力に出力するtest1.pyを作り、実行した。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.py -ok python3 {} \;
  ```


  実行結果　[](変更しない)


  ```
  < python3 ... /home/user/test/test.py > ? yes
  hello
  < python3 ... /home/user/test/test1.py > ? yes
  good morning
  ```
- **-print** 
    
  探索したファイルのPATH付きのファイル名を標準出力に表示し、各ファイル名の後ろに改行文字を付ける。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.py -print
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/test.py
  /home/user/test/test1.py
  ```
- **-print0** 
    
  探索したファイルのPATH付きのファイル名を標準出力に表示し、各ファイル名の後ろにヌル文字を付ける。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.py -print0
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/test.py/home/user/test/test1.py
  ```
- **-fprint** 
    
  探索したファイルのPATH付きのファイル名を指定したファイルに出力し、各ファイル名の後ろに改行文字を付ける。実行結果では出力したファイルの内容を記述する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.py -fprint output.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/test.py
  /home/user/test/test1.py
  ```
- **-fprint0** 
    
  探索したファイルのPATH付きのファイル名を指定したファイルに出力し、各ファイル名の後ろにヌル文字を付ける。実行結果では出力したファイルの内容を記述する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.py -fprint0 output1.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/test.py^@/home/user/test/test1.py^@
  ```
- **-a,-and** 
    
  これで結合された条件式は、and結合と解釈される。条件式の間に単にスペースを開けただけの場合も、and結合と解釈される。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.txt -and -perm 666
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/t.txt
  ```
- **-o,-or** 
    
  これで結合された条件式は、or結合と解釈される。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -regex .*.txt -or -perm 666
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/test.py
  /home/user/test/output1.txt
  /home/user/test/t.txt
  /home/user/test/output.txt
  /home/user/test/test1/T.txt
  /home/user/test/test1.py
  ```
- **-not** 
    
  これの後に記述された条件式が一致しない、という条件で探索する。
  
  実行例　[](変更しない)
  
  ```
  find /home/user/test/ -not -type f
  ```


  実行結果　[](変更しない)


  ```
  /home/user/test/
  /home/user/test/test1
  ```
