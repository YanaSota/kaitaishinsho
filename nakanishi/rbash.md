[](ファイル名はコマンド名.md)
# rbash
Bashを制限付きモードで起動する。制限付きモードで使用すると、cdコマンドでのディレクトリ移動や、シェルスクリプトの実効などの行動が制限される。「rbash」とターミナルに入力すれば制限モードでBashが起動する。また、「exit」か「bash」をターミナルで入力することで制限モードを解除することができる。

  実行例 [](変更しない)
  
  ```
  rbash

  または

  rbash -r
  ```


  実行結果.1　[](変更しない)


  ```
  $ rbash
  $ cd
  rbash: cd: restricted
  ```
  cdコマンドが制限されている。
  <br>

  実行結果.2　[](変更しない)


  ```
  $ rbash
  $ cat test.sh //シェルスクリプトの内容を表示
  #!/bin/bash

  # 引数が与えられているかチェック
  if [ $# -eq 0 ]; then
  echo "Usage: $0 [name]"
  exit 1
  fi

  # 引数の取得とメッセージの表示
  name=$1
  echo "Hello, $name!"

  $ ./test.sh　//シェルスクリプトの実効 
  rbash: ./test.sh: restricted: cannot specify `/' in command names
  ```
  シェルスクリプトの実効が制限されている。
  <br>

  実行結果.3　[](変更しない)


  ```
  $ rbash
  $ man rbash > output.txt
  rbash: output.txt: restricted: cannot redirect output
  ```
  ">、>|、<>、>&、>>`などのリダイレクション演算子を使用して出力をリダイレクトすることが制限されている。


