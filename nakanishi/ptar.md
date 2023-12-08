[](ファイル名はコマンド名.md)
# patar
Perlで書いたtarに似たコマンド。PerlモジュールであるArchive::Tarを使用してtarアーカイブの抽出、作成、およびリスト表示を行うためのプログラム。

  実行例 [](変更しない)
  
  ```
  オプションなしでは実行できない
  ```


  

### オプション一覧


- **-c**
  
  tarアーカイブを作成する。

  実行例 [](変更しない)
  
  ```
  ptar -c　file1.text file2.txt
  ```


  実行結果　[](変更しない)


  ```
  ls
  file1.text file2.txt //実行前

  ls
  default.tar  file1.text file2.txt/実行後
  ```
- **-f** 
    
  ファイル名の指定ができる。
  
  実行例　[](変更しない)
  
  ```
  ptar -c -f test.tar test_1.txt test_2.txt 
  ```


  実行結果　[](変更しない)


  ```
  ls
  test_1.txt  test_2.txt/実行前
  
  ls
  test_1.txt  test_2.txt  test.tar/実行後
  ```
- **-t** 
    
  tarファイルの中身をリスト表示します。
  
  実行例　[](変更しない)
  
  ```
  ptar -t -f test.tar
  ```


  実行結果　[](変更しない)


  ```
  ./test_1.txt
  ./test_2.txt
  ```

- **-z** 
    
  zlib圧縮されたアーカイブファイルを読み書きするためオプション。zlibは、低レベルのデータ圧縮と解凍のためのライブラリおよびフォーマット。
  
  実行例　[](変更しない)
  
  ```
  ptar -czf test.tar.gz test_1.txt test_2.txt
  ```


  実行結果　[](変更しない)


  ```
  ls
  test_1.txt  test_2.txt  test.tar /実行前

  ls
  test_1.txt  test_2.txt  test.tar  test.tar.gz/実行後
  ```


- **-v** 
    
  ptarコマンドの一部として使用される場合、tarアーカイブに使用されるファイル名が表示される。
  
  実行例　[](変更しない)
  
  ```
  ptar -cvf archive.tar test_1.txt test_2.txt
  ```


  実行結果　[](変更しない)


  ```
  ./test_1.txt
  ./test_2.txt
  ```


- **-T** 
    
  ファイルから作成する名前を取得します。

  実行例　[](変更しない)

  使用するファイル:filelist.txt

  ```
  #filelist.txt
  /home/user/file1.txt
  /home/user/file2.txt
  ```
  
  ```
  ptar -cvf archive.tar -T filelist.txt
  ```


  実行結果　[](変更しない)


  ```
  /home/user/file1.txt
  /home/user/file2.txt
  ```





