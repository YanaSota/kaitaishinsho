[](ファイル名はコマンド名.md)
# pzstd
ファイルの圧縮を目的としたコマンド。写真や動画などを圧縮することができる。

  実行例 [](変更しない)
  
  ```
  pzstd file.txt

  pzstd -9 file.txt //圧縮レベルの指定

  $ pzstd --ultra -22 file1.txt  //より高い圧縮レベルを指定できる
  ```


  実行結果　[](変更しない)


  ```
 $ ls  //ディレクトリにあるファイルを確認
 file1.txt  
 $ pzstd file1.txt
 
 file1.txt            :2500.00%   (     0 =>     25 bytes, file1.txt.zst)
 $ ls  //実行後のディレクトリにあるファイルの確認
 file1.txt file1.txt.zst
  ```
  上の例では、1つのファイルを指定して圧縮ファイルを作成しているが、
  複数のファイルを指定して圧縮ファイルを作成できる。例えば、「file1.txt」、「file2.txt」を指定すると、「file1.txt.zst」、「file2.txt.zst」の2種類圧縮ファイルが作成される。
  ハイフン(-)の後に数字を入れることで、圧縮レベルを指定できる。圧縮レベルは1から19まである。また、「--ultra」を付けることで圧縮レベルを22まで指定できる

### オプション一覧


- **-d**
  
  .zst形式の圧縮ファイルを解凍する

  実行例 [](変更しない)
  
  ```
  pzstd -d file1.txt.zst
  ```


  実行結果　[](変更しない)


  ```
  $ ls  //ディレクトリにあるファイルの確認
  file1.txt.zst
  $ pzstd -d file1.txt.zst　//実行
  
  file1.txt.zst       : 0 bytes
  $ ls　//実行後のディレクトリにあるファイルの確認
  file1.txt file1.txt.zst
  ```
- **-p** 
    
  圧縮および解凍に使用するスレッド数を指定する。スレッドとは、プロセス内で実行される個々のタスクや処理の単位である。
  
  実行例　[](変更しない)
  
  ```
  pzstd -p 4 file1.txt
  ```


  実行結果　[](変更しない)


  ```
  $ ls //ディレクトリ内のファイルを確認
  file1.txt
  $ pzstd -p 4 file1.txt
  file1.txt            :2500.00%   (     0 =>     25 bytes, file1.txt.zst)
  $ ls　//実行後のディレクトリ内のファイルを確認
  file1.txt  file1.txt.zst  man.txt
  ```
- **-o** 
    
  出力ファイルの名前を指定する。
  
  実行例　[](変更しない)
  
  ```
  pzstd -o test.zst file1.txt
  ```


  実行結果　[](変更しない)


  ```
  $ ls
  file1.txt  file1.txt.zst  
  $ pzstd -o test.zst file1.txt  // 出力ファイルの名前を"test.zst"に指定
  file1.txt            :2500.00%   (     0 =>     25 bytes, test.zst)
  $ pzstd -o output.zst file1.txt　// 出力ファイルの名前を"output.zst"に指定
  file1.txt            :2500.00%   (     0 =>     25 bytes, output.zst)
  $ ls
  file1.txt  file1.txt.zst output.zst  test.zst
  ```

- **-f** 
    
  圧縮されたファイルを強制的に上書きする。通常、出力ファイルと同名のファイルが存在する場合、上書きするかどうかユーザに確認するメッセージが表示されるが、このオプションを使用するとメッセージが表示されなくなる。
  
  実行例　[](変更しない)
  
  ```
  pzstd -f file1.txt
  ```


  実行結果　[](変更しない)


  ```
  $ ls　//ディレクトリ内のファイルを確認
  file1.txt file1.txt.zst
  $ pzstd file1.txt　//オプション無しで実行
  pzstd: file1.txt.zst already exists; do you wish to overwrite (y/n) ? y 
  //上書きするかどうかの確認メッセージが表示される
  file1.txt            :2500.00%   (     0 =>     25 bytes, file1.txt.zst)

  $ pzstd -f file1.txt  //-fオプションで実行
  file1.txt            :2500.00%   (     0 =>     25 bytes, file1.txt.zst)
  //上書きするかどうかの確認メッセージが表示されない
  ```


- **オプション** 
    
  処理の詳細を表示する
  
  実行例　[](変更しない)
  
  ```
  pzstd -v file1.txt
  ```


  実行結果　[](変更しない)


  ```
  $ pzstd -v file1.txt
  Chosen frame size: 8388608
  file1.txt            :2500.00%   (     0 =>     25 bytes, file1.txt.zst)

  ```
  "Chosen frame size" は圧縮に使用されるフレームサイズである。上の例では、フレームサイズが8388608バイト(8メガバイト)であることがわかる。


- **-r** 
    
  ディレクトリを指定して、そのディレクトリ内のファイルを圧縮する。圧縮されたファイルは指定したディレクトリ内にある
  
  実行例　[](変更しない)
  
  ```
  pzstd -r test
  ```


  実行結果　[](変更しない)


  ```
  $ ls //現在いるディレクトリ(/test)内のファイルを確認 
  file1.txt      file2.txt      file3.txt
  $ cd ..
  $ pzstd -r test
  $ cd test
  $ ls //実行後のtestディレクトリ内のファイル確認
  file1.txt      file2.txt      file3.txt     
  file1.txt.zst  file2.txt.zst  file3.txt.zst 
  ```

