[](ファイル名はコマンド名.md)
# pwck
Linuxシステムでユーザやグループのパスワードファイルをチェックするためのコマンド。パスワードファイル内のエントリに関する問題を検出し、修正するのに役立つ。このコマンドを実行するにはrootユーザまたはsudo権限を持つユーザである必要がある。

  実行例 [](変更しない)
  
  ```
  pwck
  ```


  実行結果　[](変更しない)


  ```
    user 'lp': directory '/var/spool/lpd' does not exist
    user 'news': directory '/var/spool/news' does not exist
    user 'uucp': directory '/var/spool/uucp' does not exist
    user 'www-data': directory '/var/www' does not exist
    user 'list': directory '/var/list' does not exist
    user 'irc': directory '/run/ircd' does not exist
    user 'gnats': directory '/var/lib/gnats' does not exist
    user '_apt': directory '/nonexistent' does not exist
    user 'nobody': directory '/nonexistent' does not exist
    pwck: no changes
  ```

### オプション一覧


- **-r**
  
  読み込み専用（書き込みできない）でコマンドを実行する

  実行例 [](変更しない)
  
  ```
  sudo pwck -r
  ```


  実行結果　[](変更しない)


  ```
  user 'john' has an invalid home directory '/home/john'
  user 'jane' has an invalid shell '/bin/false'
  user 'testuser' is missing a password entry
  ```
  この実行結果のから、ユーザー「john」のホームディレクトリが無効であること、ユーザー「jane」のシェルが無効であること、そして「testuser」のパスワードエントリが存在しないことが確認できる。
  <br>
  
- **-q** 
    
  システムやグループ設定に関するエラーや警告を表示するオプション。
  
  実行例　[](変更しない)
  
  ```
  pwck -q
  ```


  実行結果　[](変更しない)


  ```
  user 'john' has an invalid home directory '/home/john'
  user 'jane' has an invalid shell '/bin/false'
  ```
  この実行結果から、ユーザー「john」のホームディレクトリが無効であること、ユーザー「jane」のシェルが無効であることがわかる


- **-R** 
    
  指定されたchrootディレクトリ内の設定ファイルを使用して、pwckコマンドを実行するためのオプション。chrootとは、プロセスが利用できるルートディレクトリを変更することを指す。
  <br>
  実行例　[](変更しない)
  
  ```
  pwck -R /mnt/chroot
  ```


  実行結果　[](変更しない)


  ```
  user 'john': directory '/mnt/chroot/home/john' does not exist
  user 'jane': directory '/mnt/chroot/home/jane' does not exist
  ```

- **-s** 
    
  パスワードファイル (/etc/passwd) と shadow ファイル (/etc/shadow) のエントリを UID (ユーザー識別子) の昇順でソートするオプション。
  
  実行例　[](変更しない)
  
  ```
  pwck -s
  ```


  実行結果　[](変更しない)


  ```
  表示なし
  ```




  
