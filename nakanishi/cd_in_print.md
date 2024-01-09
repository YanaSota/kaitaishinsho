[](ファイル名はコマンド名.md)
# cd
cd: cd [-L|[-P [-e]] [-@]] [dir]
作業ディレクトリを変更します。

現在のディレクトリをDIRに変更します。デフォルトのDIRはHOMEシェル変数の値です。

変数CDPATHは、DIRを含むディレクトリの検索パスを定義します。CDPATH内の代替ディレクトリ名はコロン（:）で区切られます。空のディレクトリ名は現在のディレクトリと同じです。DIRがスラッシュ（/）で始まる場合、CDPATHは使用されません。

ディレクトリが見つからない場合、シェルオプション「cdable_vars」が設定されている場合、単語は変数名と見なされます。その変数に値がある場合、その値がDIRとして使用されます。

オプション:
-L シンボリックリンクを強制的にたどる：..'のインスタンスを処理した後、DIR内のシンボリックリンクを解決します。
<br>

-P	シンボリックリンクをたどらずに物理的なディレクトリ構造を使用する：..'のインスタンスを処理する前にDIR内のシンボリックリンクを解決します。
<br>
-e -Pオプションが指定されており、現在の作業ディレクトリを正常に特定できない場合、終了ステータスを非ゼロで終了します。
<br>

-@ サポートされているシステムでは、拡張属性を持つファイルをファイル属性を含むディレクトリとして表示します。
<br>

デフォルトでは、シンボリックリンクをたどります。`..'は、直前のパス名コンポーネントをスラッシュまたはDIRの先頭まで削除して処理されます。

終了ステータス:
ディレクトリが変更されると0を返し、-Pが使用される場合は$PWDが正常に設定された場合に成功します。それ以外の場合は非ゼロを返します。
<br>


  実行例.1 [](変更しない)
  
  cdを単体で使用した場合、ユーザのホームディレクトリへ移動
  ```
  cd
  ```


  実行結果.1　[](変更しない)

  ```
  $ pwd  //実行前の現在地を確認
  home/user/Prmn

  $ cd //実行
  $ pwd //実行後の現在地を確認
  homo/user  //ユーザのホームディレクトリに移動したことがわかる
  ```
<br>

  実行例.2 [](変更しない)
  
  cdの後ろにディレクトリ名を指定するとそのディレクトリへ移動する。
  ```
  cd ディレクトリ名
  ```


  実行結果.2　[](変更しない)


  ```
  $ pwd  //実行前の現在地を確認
  home/user
  $ ls //現在地にあるディレクトリを確認
  Prmn test
  $ cd Prmn // 実行
  $ pwd //実行後の現在地を確認
  home/user/Prmn //Prmnディレクトリに移動したことがわかる
  ```
<br>

  実行例.3 [](変更しない)
   
  1つ前のディレクトリへ戻る
  
  ```
  cd ..
  ```


  実行結果.3　[](変更しない)


  ```
  $ pwd //実行前の現在地を確認
  home/user/Prmn/test
  $ cd ..  //実行
  $ pwd //実行後の現在地を確認
  home/user/Prmn //1つ前のディレクトリへ戻ったことが確認できる
  ```
<br>

  実行例.4 [](変更しない)

  cd単体でコマンドを実行した場合と同じ挙動をする。主に複雑なディレクトリ間を移動する際に使用.。
  ```
  cd ~/Prmm
 ```


  実行結果.4　[](変更しない)


  ```
  $ pwd
  home/user/prac
  $ cd ~/Prmn //一度ユーザのホームディレクトリへ移動してからPrmnへ移動
  $ pwd 
  home/user/Prmn //Prmnディレクトリへ移動していることを確認
  ```
<br>

  実行例.5[](変更しない)
  
  前に居たディレクトリへ移動する。
  ```
  cd -
  ```


  実行結果.5　[](変更しない)


  ```
  $ pwd //移動する前のディレクトリを表示
  home/user/Prmn
  $ cd /etc　// etcへ移動
  $ pwd
  /etc
  $ cd -　// 実行
  $ pwd
  home/user/Prmn //元居た場所へ戻ったことを確認できる
  ```



### オプション一覧


- **-L**
  
  移動先のディレクトリがシンボリックリンクだった場合、シンボリックリンクに移動するオプション。シンボリックリンクとは別のファイルやディレクトリへの参照を作成するための特殊なファイル。
  <br>
  実行例 [](変更しない)
  
  ```
  cd -L tmp
  ```


  実行結果　[](変更しない)


  ```
  $ pwd
  home/user/Prmn //現在地のディレクトリを確認
  $ ln -s tmp/ tmp //現在のディレクトリにシンボリックリンクを作成。
  $ ls
  tmp　//ルート直下のtmpが参照されている
  $ cd -L tmp //参照先のtmpへ移動
  $ pwd 
  home/user/Prmn/tmp　/

  ```
- **-P** 
    
  移動先がシンボリックリンクだったらシンボリックリンクのターゲット飛ぶためのオプション。つまり、参照したディレクトリの元のディレクトリへ移動する。
  <br> 
  実行例 [](変更しない)
  
  ```
  cd -P tmp
  ```
  
  実行結果　[](変更しない)
  
  ```
  $ pwd
  home/user/Prmn //現在地のディレクトリを確認
  $ ln -s tmp/ tmp //現在のディレクトリにシンボリックリンクを作成。
  $ ls
  tmp　//ルート直下のtmpが参照されている
  $ cd -P tmp //参照先のtmpへ移動
  $ pwd 
  /tmp  //ルート直下のtmpディレクトリへ移動していることがわかる。
  ```


  