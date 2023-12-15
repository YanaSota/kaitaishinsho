[](ファイル名はコマンド名.md)
# pwconv
etc/passwdをシャドウパスワードファイルへ変換するコマンド

  実行例 [](変更しない)
  
  ```
  pwconv
  ```


  実行結果　[](変更しない)


  ```
  $ sudo cat passwd | grep user　/実行前のパスワードファイル確認

  user:$6$tR・・・/n1YlV6$・・・/jFasYC.GEvPyJLEi8HlPl7mg9m5d3P70:1000:1000:user:/home/user:/bin/bash
  //ユーザアカウントの横に文字列が並んでいる。

  $ pwconv  //実行

  $ cat passwd | grep user
  user:x:1000:1000:user:/home/user:/bin/bash

  ```

