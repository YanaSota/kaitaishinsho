[](ファイル名はコマンド名.md)
# readkink
シンボリックリンクのリンク先の名前を表示するコマンド。
シンボリックリンクとはファイルやディレクトリを参照である。
readlinkコマンドには、「Readlink mode」と、「Canonicalize mode」の2つのモードがある。
Readlink modeでは、シンボリックリンクファイルを指定すると、そのリンク先を表示する。このモードはreadlinkコマンドのデフォルトになる。
Canonicalize modeでは、ファイルの絶対パスを出力する。

  実行例 [](変更しない)
  
  ```
   readlink /test
  ```


  実行結果　[](変更しない)


  ```
  $ ln -s /tmp/ test 　 //tmpを参照するシンボリックリンクを「test」という名前で作成
  $ ls
  test
  $ readlink /test
  /tmp/ 
  ```
  上の結果から、シンボリックリンク「test」は/tmpを参照していることがわかる。

### オプション一覧


- **-f**
  
  readlinkコマンドをCanonical modeにする。指定したファイルの絶対パスを表示する。
  ファイルパスの最後の部分以外で、そのファイルが見つからない場合や利用できない場合は、何も表示しない。
  例えば、file1の絶対パスを取得する場合、file1が存在するしないに関係せず絶対パスが表示される。しかし、dir1/file1の絶対パスを取得するときにdir1が存在しない場合は何も表示されない。

  実行例 [](変更しない)
  
  ```
  readlink -f file.txt
  ```


  実行結果.1　[](変更しない)


  ```
  $ readlink -f file.txt
  /home/user/Prmn/file.txt
  ```
  実行結果.2　[](変更しない)


  ```
  $ ls //ディレクトリ内のファイルを確認
  $ test
  $ readlink -f test/file.txt
  /home/user/Prmn/test/file.txt
  $ readlink -f dumy/file.txt //存在しないディレクトリを指定
  $       //何も表示されない
  ```
- **-e** 
    
  readlinkコマンドをCanonical modeにする。-fオプションと違い、存在するファイルのみ絶対パスを表示する。
  
  実行例　[](変更しない)
  
  ```
  readlink -e test/test.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cd test
  $ ls       //testディレクトリ内のファイルを確認
  test.txt
  $ cd ..
  $ readlink -e test/test.txt  //存在するファイルを指定
  /home/user/Prmn/test/test.txt
  $ readlink -e test/no_exist_file.txt　//存在しないファイルを指定
  $　　　　　　　　　//何も表示されない
  ```
- **-m** 
    
  readlinkコマンドをCanonical modeにする。
  -fオプションと違いファイルが存在しない場合や利用できない場合は、ディレクトリとして扱い絶対パスを表示する。
  
  実行例　[](変更しない)
  
  ```
  readlink -m aaa/bbb/ccc/ddd.txt
  ```


  実行結果　[](変更しない)


  ```
  $ ls
  test
  $ readlink -m aaa/bbb/ccc/ddd.txt  //存在しないディレクトリやファイルを指定
  /home/tomo/Prmn/aaa/bbb/ccc/ddd.txt  
  ```

- **-v** 
    
  readlinkコマンドでのエラーメッセージを表示する
  
  実行例　[](変更しない)
  
  ```
  readlink -v aaa/bbb/ccc/ddd.txt
  ```


  実行結果　[](変更しない)


  ```
  $ ls
  test
  $ readlink -v aaa/bbb/ccc/ddd.txt  //存在しないディレクトリやファイルを指定
  readlink: aaa/bbb/ccc/ddd.txt: No such file or directory
  ```

