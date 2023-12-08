[](ファイル名はコマンド名.md)
# accessdb
Linuxのマニュアルページのデータベース内のデータを人間が読める形式で出力するコマンド。デフォルトでは/var/cache/man/index.<db-type>からデータを出力するが、引数を指定すると上書きできる。

  実行例 [](変更しない)
  
  ```
  accessdb
  ```


  実行結果　[](変更しない)


  ```
  $version$ -> "2.5.0"
  .ldaprc -> "- 5 5 1690841590 0 C ldap.conf - gz "
  /etc/adduser.conf -> "- 5 5 1609913810 0 C adduser.conf - gz "
  /etc/anacrontab -> "- 5 5 1648028411 0 C anacrontab - gz "
  /etc/deluser.conf -> "- 5 5 1609913810 0 C deluser.conf - gz "
  /etc/mailcap.order -> "- 5 5 1639178040 0 C mailcap.order - gz "
  /etc/modules -> "- 5 5 1629191993 0 C modules - gz "
  00-upstream-settings -> "- 5 5 1649592997 0 A - - gz dconf configuration file"

  以下マニュアルの一覧がアルファベット順に表示される。
  ```