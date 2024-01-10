[](ファイル名はコマンド名.md)
# ed
edは行指向のテキストエディタである。

対話的に、あるいはシェルスクリプトを使って、 テキストファイルの作成、表示、変更、その他の操作に使われる。

ed の制限付きバージョンである red は、カレントディレクトリのファイルのみを編集でき、 シェルコマンドを実行することはできない。

edは、Unixのオリジナルエディタであり、広く利用できるという意味で、「標準的な」テキストエディタである。

しかし、ほとんどの用途では、GNU EmacsやGNU Moeのようなフルスクリーンエディタが使用されている。

  実行例 [](変更しない)
  
  ```
  user@Ubuntu:~$ ed
  P
  *i
  Hello
  .
  *a
  Good Morining
  Good Night
  .
  *w test
  30
  *q
  ```


  実行結果　[](変更しない)


  ```
  user@Ubuntu:~$ cat test
  Hello
  Good Morning
  Good Night
  ```

### オプション一覧


- **-E,--extended-regexp**
  
  拡張正規表現を使う。

  実行例 [](変更しない)
  
  ```
  1,3p
  1,3s/'o{2}'/o/1
  1,3p
  ```


  実行結果　[](変更しない)


  ```
  Hello
  Good Morning
  Good Night

  Hello
  God Morining
  Good Night
  ```
- **-G,--traditional** 
    
  従来型、互換モードで実行する。
  
  実行例　[](変更しない)
  
  ```
  ed -G test
  ```


  実行結果　[](変更しない)


  ```
  変化なし
  ```

- **-l,--loose-exit-status** 
    
  コマンドに失敗しても0ステータスで終了する。
  
  実行例　[](変更しない)
  
  ```
  ed -l test
  ```


  実行結果　[](変更しない)


  ```
  *aaaa
  強制終了
  ```
- **-p,--prompt=STRING** 
    
  STRINGを対話型プロンプトとして使う。
  
  実行例　[](変更しない)
  
  ```
  ed -p test
  ```


  実行結果　[](変更しない)


  ```
  test P
  test i
  Hello
  .
  test p
  Hello
  test w test
  6
  test Q
  ```
- **-r,--restricted** 
    
  制限モードで実行する。
  
  実行例　[](変更しない)
  
  ```
  ed -r
  ```


  実行結果　[](変更しない)


  ```
  変化なし
  ```
- **-s,--quiet,--silent** 
    
  診断、バイト数、'!'プロンプトを表示しない。
  
  実行例　[](変更しない)
  
  ```
  ed -s test
  ```


  実行結果　[](変更しない)


  ```
  *w
  *q
  ```
- **-v,--verbose** 
    
  H'コマンドと同じ。
  
  実行例　[](変更しない)
  
  ```
  ed -v test
  ```


  実行結果　[](変更しない)


  ```
  変化なし
  ```
- **--strip-trailing-cr** 
    
  テキスト行末のキャリッジ・リターンを除去する。

  一部のテキストファイルで行末に挿入される\rを削除できる。
  
  実行例　[](変更しない)
  
  ```
  ed --strip-trailing-cr test
  cat test
  ```


  実行結果　[](変更しない)


  ```
　Hello
  Good Morning
  Good Night
  ```