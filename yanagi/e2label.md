[](ファイル名はコマンド名.md)
# e2label
e2label は、デバイス上の ext2, ext3, ext4 ファイルシステムのボリュームラベルを表示または変更する。

引数 volume-label が存在しない場合、 e2label は単に現在のボリュームラベルを表示する。


引数 volume-label が存在する場合、 e2label はボリュームラベルを volume-label に設定する。もし volume-label が 16文字より長い場合は、 e2label はそれを切り捨てて警告メッセージを表示する。


tune2fs(8) の -L オプションを使用してボリュームラベルを設定することも可能である。

e2labelはe2fsprogsパッケージの一部であり、http://e2fsprogs. sourceforge.netから入手できる。
  実行例 [](変更しない)
  
  ```
  sudo e2label /dev/sda1
  sudo e2label /dev/sda1 label_test
  sudo e2label /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  表示なし
  label_test
  ```

### オプションなし