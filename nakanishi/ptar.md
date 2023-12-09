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
  $ ls
  file1.text file2.txt //実行前

  $ ptar -c　file1.text file2.txt

  $ ls
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
  - **-x** 
    
  tarアーカイブは抽出されるを行う。
  
  実行例　[](変更しない)
  
  ```
  ptar -xf archive.tar
  ```
  


  実行結果　[](変更しない)


  ```
  $ ls //実行前
  archive.tar

  ptar -xf archive.tar

  $ ls 
  archive.tar file1.txt file2.txt
  ```

- **-z** 
    
  zlib圧縮されたアーカイブファイルを読み書きするためオプション。zlibは、低レベルのデータ圧縮と解凍のためのライブラリおよびフォーマット。
  
  実行例　[](変更しない)
  
  ```
  ptar -czf test.tar.gz test_1.txt test_2.txt
  ```


  実行結果　[](変更しない)


  ```
  $ ls
  test_1.txt  test_2.txt  test.tar /実行前

  ptar -czf test.tar.gz test_1.txt test_2.txt

  $ ls
  test_1.txt  test_2.txt  test.tar  test.tar.gz/実行後
  ```


- **-v** 
    
  tarアーカイブの作成または抽出されるファイル名が表示される。
  
  実行例　[](変更しない)
  
  ```
  ptar -cvf archive.tar test_1.txt test_2.txt
  ```
  この実行例では、text_1.txtとtext_2.txtを使用してarchive.tarという名前のtarファイルを作成している。vオプションを使用することで、上記のコマンドの実行後にtext_1.txtとtext_2.txtのファイル名が表示される。
  



  実行結果　[](変更しない)


  ```
  ./test_1.txt
  ./test_2.txt
  ```
  


- **-T** 
  
  tarファイルの作成にテキストファイルを使用する。テキストファイルには、tarファイルの作成に使用するファイルのパスが記載されている。あらかじめテキストファイルを作成することで多くのファイルをtarファイルの作成に使用できる。
<br>
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
  $ ls //実行前
  filelist.txt 

  $ ptar -cvf archive.tar -T filelist.txt

  /home/user/file1.txt
  /home/user/file2.txt

  $ ls //実行後
  archive.tar  filelist.txt

  $ tar -xf archive.tar
  //作成されたtarファイルの確認のため、中身を抽出

  $ ls
  archive.tar  filelist.txt  home
  // home/userのディレクトリが抽出される。
  $ cd home/user
  $ ls
  file1.txt file2.txt
  //その中にfile1.txt file2.txtが含まれる。
  ```





