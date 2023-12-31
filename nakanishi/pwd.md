[](ファイル名はコマンド名.md)
# pwd
自分が現在自分がいるディレクトリを表示するコマンド

  実行例 [](変更しない)
  
  ```
  pwd
  ```


  実行結果　[](変更しない)


  ```
  /home/user 　//現在自分がいるディレクトリを表示
  ```

### オプション一覧


- **-L**
  
  オプション無しと同じ挙動をします。オプションをつけても付けなくてもいい。

  実行例 [](変更しない)
  
  ```
  pwd -L
  ```


  実行結果　[](変更しない)


  ```
  /home/user  //現在自分がいるディレクトリを表示
  ```
- **-P** 


  このオプションは、カレントディレクトリの物理的なパスを表示する。シンボリックリンクが含まれる場合でも、シンボリックリンクが解決され、実際のディレクトリのパスが表示される。別のファイルやディレクトリへの参照を作成するための特殊なファイル。
  <br>
  
  実行例　[](変更しない)
  
  ```
  pwd -P
  ```


  実行結果　[](変更しない)


  ```
  $ ln -s /tmp tmp  /現在のディレクトリにシンボリックリンクを貼る

  $ ls
  tmp //現在のディレクトリで/（ルート）直下のtmpを参照できる
  $ cd tmp
  $ pwd    //オプション無し
  home/user/Prmn/pwd

  $ pwd -P //オプションあり
  /tmp
  ```
