[](ファイル名はコマンド名.md)
# dosfslabel

FATファイルシステムのラベルを設定、表示する
ボリューム名を変更、確認する必要がある場合に使用されるため使用頻度はあまり高くない
ボリューム名はリムーバブルメディアを他のデバイスと区別するために使用されることがある

  実行例 [](変更しない)
  
  ```
  sudo dosfslabel /dev/sda
  ```


  実行結果　[](変更しない)


  ```
  Logical sector size is zero.
  ```


オプション一覧


- **-i**
  
  ラベルの代わりにシリアルナンバーを使い実行する

  実行例 [](変更しない)
  
  ```
  sudo dosfslabel -i /dev/sda
  ```


  実行結果　[](変更しない)


  ```
  Logical sector size is zero.
  ```
- **-r** 
    
  ラベルを取り除くかシリアルナンバーを新しく生成する
  
  実行例　[](変更しない)
  
  ```
  sudo dosfslabel -r /dev/sda
  ```


  実行結果　[](変更しない)


  ```
  Logical sector size is zero.
  ```
- **-c** 
    
  ラベルのエンコード/デコードにDOSコードページを使用する
  
  実行例　[](変更しない)
  
  ```
  sudo dosfslabel -c 800 /dev/sda
  ```


  実行結果　[](変更しない)


  ```
  Cannot initialize conversion from codepage 800 to UTF-8: Invalid argument
  Cannot initialize conversion from UTF-8 to codepage 800: Invalid argument
  ```