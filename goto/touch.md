[](ファイル名はコマンド名.md)
## touch
  各ファイルのタイムスタンプを変更する。主にファイル内容の変更日時(ctime:Change Time)やファイルへの書き込みや権限などのパラメータ情報の修正日時(mtime:Modify Time)を変更する。
  指定のファイルがない場合は作成される

  実行例 [touch hoge.txt](変更しない)
  
  ```
  touch hoge.txt
  stat hoge.txt(更新日時を確認)
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 0               Blocks: 0          IO Block: 4096   regular empty file
  Device: 802h/2050d      Inode: 5806706     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2023-12-11 00:57:09.763776785 +0900
  Modify: 2023-12-11 00:57:09.763776785 +0900
  Change: 2023-12-11 00:57:09.763776785 +0900
  Birth: 2023-12-11 00:07:45.595626196 +0900
  ```
  <br>
オプション一覧


- **-a**
  アクセス日時(atime)とctimeを変更する。
  

  実行例 [](変更しない)
  
  ```
  touch -a hoge.txt
  stat hoge.txt(更新日時を確認)
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 0               Blocks: 0          IO Block: 4096   regular empty file
  Device: 802h/2050d      Inode: 5806706     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2023-12-11 01:00:24.002451121 +0900
  Modify: 2023-12-11 00:57:09.763776785 +0900
  Change: 2023-12-11 01:00:24.002451121 +0900
  Birth: 2023-12-11 00:07:45.595626196 +0900
  ```
- **-c/--no-create** 
    
  touch実行時、指定ファイルが無い際にファイルを作成しない。
  
  実行例　[](変更しない)
  
  ```
  touch -c hoge1.txt
  ls
  ```


  実行結果　[](変更しない)


  ```
  hoge.txt     snap    　ダウンロード  ドキュメント  ミュージック
  テンプレート  ビデオ     公開         user         デスクトップ  ピクチャ
  ```
- **-d/--date=STRING** 
    
  STRING(日時)を解析して、現在の時刻の代わりに使用する。
  
  実行例　[](変更しない)
  
  ```
  touch -d "2002-05-0210:00:00" hoge.txt　(2002年5月2日は筆者の誕生日)
  stat hoge.txt
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 0               Blocks: 0          IO Block: 4096   regular empty file
  Device: 802h/2050d      Inode: 5806706     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2002-05-02 10:00:00.000000000 +0900
  Modify: 2002-05-02 10:00:00.000000000 +0900
  Change: 2023-12-11 01:15:56.288362108 +0900
  Birth: 2023-12-11 00:07:45.595626196 +0900
  ```
- **-f** 
    
  既存のファイルと同じ名前のファイルが存在していても上書きする。しかし動作的には通常のtouchと変わりはない。
  明示的にファイルを強制的に上書きするという意味合いが込められているのみ。
  
  実行例　[](変更しない)
  
  ```
  同様のため省略
  ```


  実行結果　[](変更しない)


  ```
  同様のため省略
  ```
- **-h / --no-dereference** 
    
  シンボリックリンクの場合、リンク先ではなくシンボリックそのもののタイムスタンプを変更する。シンボリックリンクとはリンクしているファイルのパス自体のこと。
  
  実行例　[](変更しない)
  
  ```
  touch -h link (linkとhoge.txtがつながっている)
  stat link (シンボリックリンク自体のタイムスタンプを確認)
  stat hoge.txt (sourceのタイムスタンプを確認)
  ```


  実行結果　[](変更しない)


  ```
  $touch -h link
  $stat link
    File: hoge.txt
    Size: 9               Blocks: 8          IO Block: 4096   regular file
    Device: 802h/2050d      Inode: 5806905     Links: 1
    Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
    Access: 2023-12-12 02:16:22.142100484 +0900
    Modify: 2023-12-12 02:16:22.142100484 +0900
    Change: 2023-12-12 02:16:22.142100484 +0900
    Birth: 2023-12-12 01:42:56.393351377 +0900

  $stat hoge.txt
    File: link -> /home/shunsuke/hoge.txt
    Size: 23              Blocks: 0          IO Block: 4096   symbolic link
    Device: 802h/2050d      Inode: 5806911     Links: 1
    Access: (0777/lrwxrwxrwx)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
    Access: 2023-12-12 02:16:44.658122212 +0900
    Modify: 2023-12-12 02:16:44.658122212 +0900
    Change: 2023-12-12 02:16:44.658122212 +0900
    Birth: 2023-12-12 02:08:13.509685780 +0900
  ```
  シンボリックリンクと元ファイルのhoge.txtのタイムスタンプを比較すると違う。
  touch linkをすれば元のhoge.txtのタイムスタンプも変更される。

- **-m** 
    
  変更時刻（mtime）のみ変更する。
  
  実行例　[](変更しない)
  
  ```
  touch -m hoge.txt
  stat hoge.txt
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 9               Blocks: 8          IO Block: 4096   regular file
  Device: 802h/2050d      Inode: 5806905     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2023-12-12 02:25:55.299271733 +0900
  Modify: 2023-12-12 02:47:38.463970752 +0900
  Change: 2023-12-12 02:47:38.463970752 +0900
  Birth: 2023-12-12 01:42:56.393351377 +0900
  ```
- **-r, --reference=FILE** 
    
  現在の時刻の代わりに、指定したファイルのタイムスタンプを使用する。
  
  実行例　[](変更しない)
  
  ```
  touch -r hoge_source.txt hoge.txt
  stat hoge.txt
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 9               Blocks: 8          IO Block: 4096   regular file
  Device: 802h/2050d      Inode: 5806905     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2023-12-12 02:25:55.299271733 +0900
  Modify: 2023-12-12 02:47:38.463970752 +0900
  Change: 2023-12-12 02:47:38.463970752 +0900
  Birth: 2023-12-12 01:42:56.393351377 +0900
  ```
- **-r, --reference=FILE** 
    
  タイムスタンプで現在の時刻の代わりに、[[CC]YY]MMDDhhmm[.ss]の形式の時刻（STAMP）を使用する。つまり更新日時などを指定することが可能。-dとの違いは日付指定の形式である。
  
  実行例　[](変更しない)
  
  ```
  touch -t 202312111234.56 hoge.txt
  stat hoge.txt
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 9               Blocks: 8          IO Block: 4096   regular file
  Device: 802h/2050d      Inode: 5806905     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2023-12-11 12:34:56.000000000 +0900
  Modify: 2023-12-11 12:34:56.000000000 +0900
  Change: 2023-12-12 03:13:33.025723661 +0900
  Birth: 2023-12-12 01:42:56.393351377 +0900
  ```
- **--time=WORD** 
    
  タイムスタンプの変更するタイムを指定できる。しかしWORDがacces,atime,useの場合は-aのオプションと同様である。またWORDがmodify,mtimeのときは-mと同様である。
  
  実行例　[](変更しない)
  
  ```
  touch --time=aime
  stat hoge.txt
  ```


  実行結果　[](変更しない)


  ```
  File: hoge.txt
  Size: 9               Blocks: 8          IO Block: 4096   regular file
  Device: 802h/2050d      Inode: 5806905     Links: 1
  Access: (0664/-rw-rw-r--)  Uid: ( 1000/shunsuke)   Gid: ( 1000/shunsuke)
  Access: 2023-12-12 03:19:11.378151886 +0900
  Modify: 2023-12-11 12:34:56.000000000 +0900
  Change: 2023-12-12 03:19:11.378151886 +0900
  Birth: 2023-12-12 01:42:56.393351377 +0900
  ```