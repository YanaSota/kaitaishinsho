[](ファイル名はコマンド名.md)
# ptargrep
tarアーカイブ内のファイルの内容にパターンマッチングを適用するためのツール

  実行例 [](変更しない)
  
  ```
  オプション無しで実行できない
  ```


  

### オプション一覧



- **--basename**
  
  アーカイブファイル内のファイル名に対して、指定したベース名（パターン）に一致するものを検索するためのコマンド。一致するファイルを抽出する場合、アーカイブからのディレクトリパスを無視し、現在のディレクトリにアーカイブ内のファイルのベース名を使用して書き込む。ただし、アーカイブ内の2つの一致するファイルが同じベース名を持つ場合、2番目のファイルが最初のファイルを上書きする。

  <br>
  

  実行例 [](変更しない)

    使用するアーカイブファイル
  ```
  test.tar
   └─ home
       └── user
             ├──file1.txt
             └──file2.txt
  ```
  
  ```
  $ ptargrep --basename "file" test.tar
  ```


  実行結果　[](変更しない)


  ```
  file1.txt
  file2.txt
  ```
- **--ignore-case** 
    
  --ignore-caseオプションは、大文字と小文字を区別せずに検索を行うためのオプション
  <br>
  
  実行例　[](変更しない)
  
  ```
  $ ptargrep --ignore-case "file" test.tar
  ```


  実行結果　[](変更しない)


  ```
  File.txt
  file.jpg
  ```
- **--list-only** 
    
  文章説明
  
  実行例　[](変更しない)
  
  ```
  $ ptargrep --list-only fruits.tar

  ```


  実行結果　[](変更しない)


  ```
  Apple.txt
  apple.jpg
  Orange.txt
  orange.jpg
  Pineapple.txt
  ```

- **オプション** 
    
  文章説明
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```


  実行結果　[](変更しない)


  ```
  実行結果
  ```

