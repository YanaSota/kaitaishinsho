[](ファイル名はコマンド名.md)
# basename
ファイルのパスからファイル名の前についたディレクトリ構造を削除し、ファイル名を表示する。

  実行例 [](変更しない)
  
  ```
  basename /home/kawai/testdir/testdir1/test.txt
  ```


  実行結果　[](変更しない)


  ```
  test.txt
  ```

### オプション一覧


- **-a**
  
  複数のパスを引数として渡し、複数のファイル名を順に表示する。

  実行例 [](変更しない)
  
  ```
  basename -a /home/kawai/testdir/testdir1/test /home/kawai/testdir/testdir1/test.txt
  ```


  実行結果　[](変更しない)


  ```
  test
  test.txt
  ```
- **-s** 
    
  ファイル名の接尾辞を指定し、削除する。
  
  実行例　[](変更しない)
  
  ```
  basename -s .txt /home/kawai/testdir/testdir1/test.txt
  ```


  実行結果　[](変更しない)


  ```
  test
  ```
- **-z** 
    
  出力の区切り文字を改行でなくNULLにする。
  
  実行例　[](変更しない)
  
  ```
  basename -z -a /home/kawai/testdir/testdir1/test /home/kawai/testdir/testdir1/test.txt
  ```


  実行結果　[](変更しない)


  ```
  testtest.txt
  ```
