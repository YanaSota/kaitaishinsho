[](ファイル名はコマンド名.md)
## timeout
timeoutコマンドは、指定された時間内にコマンドやプロセスを実行し、制限時間が経過すると実行を中断する。  
※timeoutコマンドは、コマンドがタイムアウトした場合にはステータスコード124で終了し、--preserve-statusオプションが設定されている場合には実行中のコマンドの終了ステータスを保持する。タイムアウト時にはTERMシグナルが送信され、キャッチできない場合にはKILL（9）シグナルが使用される。これにより、timeoutコマンドはタイムアウト制御とプロセス終了の管理を行う。

  実行例 [](変更しない)
  
  ```
  timeout 1 ping localhost
  ```


  実行結果　[](変更しない)


  ```
  PING localhost (127.0.0.1) 56(84) bytes of data.
  64 bytes from localhost (127.0.0.1): icmp_seq=1 ttl=128 time=0.136 ms
  ```
オプション一覧

- **-s/--signal=SIGNAL**
  
  タイムアウト時に送信するシグナルを指定。デフォルトではTERMシグナルを使用。

  実行例 [](変更しない)
  
  ```
  timeout -s USR1 -k 2 3 ./test-u.sh
  ```


  実行結果　[](変更しない)


  ```
  test
  test
  test
  User defined signal 1
  USER1 signal
  test
  test
  Killed
  ```
- **-k/--kill-after=DURATION** 
    
  初期のシグナルが送信されてから指定した時間が経過してもコマンドが実行中の場合には、KILLシグナルも送信することで確実にコマンドのキルをする。
  
  実行例　[](変更しない)
  
  ```
  timeout -k 2 3 ./test-u.sh
  ```


  実行結果　[](変更しない)
 
  ```
  test
  test
  test
  Terminated
  TERM signal
  test
  test
  Killed
  ```