[](ファイル名はコマンド名.md)
# pwunconv
pwconvコマンドでシャドウ化したetc/passwdを元に戻すコマンド

  実行例 [](変更しない)
  
  ```
  pwunconv
  ```


  実行結果　[](変更しない)


  ```
  $ cat passwd | grep user //実行前のパスワードファイルを確認
  user:x:1000:1000:user:/home/user:/bin/bash

  $ pwunconv

  user:$6$tR9u4.BHS/n1YlV6$・・・.GEvPy・・・0:1000:1000:user:/home/user:/bin/bash
  ```

