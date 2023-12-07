
## dir

指定されたディレクトリ内のファイルとサブディレクトリのリストを一覧表示できる


オプション一部一覧


- **-a,-all**
  
  隠しファイルを含む全てのファイルを表示する

  実行例 [](変更しない)
  
  ```
  dir -a
  dir -all
  ```


  実行結果　[](変更しない)


  ```
  .       ..      file1.txt   .hidden_file   directory1   .hidden_directory
  ```

- **-A,--almost-all,--author**
  
  "."と".."は除く"."で始まる隠しファイルを含む全てのファイルを表示する

  実行例 [](変更しない)
  
  ```
  dir -A
  dir --almost-all
  ```


  実行結果　[](変更しない)


  ```
  file1.txt   .hidden_file   directory1   .hidden_directory
  ```

- **-b,--escape,--block-size=SIZE** 
    
  エスケープ文字を表示する
  
  実行例　[](変更しない)
  
  ```
  dir -b
  dir --escape
  ```


  実行結果　[](変更しない)


  ```
  file1.txt  file2.txt  directory1  directory2
  ```
  
- **-B,--ignore-backups** 
    
  ファイルの最後に「～（チルダ）」がついたバックアップファイルを表示しない
  
  実行例　[](変更しない)
  
  ```
  dir -B
  dir --ignore-backups
  ```


  実行結果　[](変更しない)


  ```
  file1.txt  file2.txt  directory1  directory2
  ```

- **-c**
  
  変更日時(ctime)の新しい順でソートする
  

  実行例 [](変更しない)
  
  ```
  dir -c
  ```


  実行結果　[](変更しない)


  ```
  file3.txt    ctime: Dec 5 2023 12:30
  file1.txt    ctime: Dec 3 2023 09:15
  directory2   ctime: Dec 1 2023 16:45
  directory1   ctime: Nov 30 2023 08:20
  ```


- **-color**
  
  カラー表示にする
  
  ディレクトリは青色

  実行可能なファイルは緑色

  一般的なファイルは白色

  実行例 [](変更しない)
  
  ```
  dir -color
  ```


  実行結果　[](変更しない)


    ```
    directory  file1.txt
    ``` 



- **-d, --directory**
  
  ディレクトリそのものの情報を表示する

  実行例 [](変更しない)
  
  ```
  dir -d
  dir --directory
  ```


  実行結果　[](変更しない)


  ```
  .
  ```

- **-i**
  
  iノード番号を表示

  実行例 [](変更しない)
  
  ```
  dir -i
  ```


  実行結果　[](変更しない)


  ```
  9851624185227536 directory
  7881299348254011 file.txt
  ```

- **-l**
  
  詳細な情報を表示する

  実行例 [](変更しない)
  
  ```
  dir -l
  ```


  実行結果　[](変更しない)


  ```
  drwxr-xr-x 1 name 197609 0 Dec  6 23:55 file.txt
  drwxr-xr-x 1 name 197609 0 Dec  23 11:32 directory
  ```

- **-t**
  
  ファイル更新日時でソートして表示する

  実行例 [](変更しない)
  
  ```
  dir -t
  ```


  実行結果　[](変更しない)


  ```
  file3.txt  file1.txt directory2  directory1
  ```

  - **-S**
  
    ファイルサイズが大きいものからソートする

  実行例 [](変更しない)
  
  ```
  dir -S
  ```


  実行結果　[](変更しない)


  ```
  file1.txt  file2.txt  directory  directory2
  ```

  - **-1**
  
  リストを縦１列で表示する

  実行例 [](変更しない)
  
  ```
  dir -1
  ```


  実行結果　[](変更しない)


  ```
  directory
  directory2
  file1.txt
  file4.txt
  file2.txt
  ```
