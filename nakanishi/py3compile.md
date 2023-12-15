[](ファイル名はコマンド名.md)
# py3compile
python3のソースファイルをバイトコンパイルするためのコマンド。

  実行例 [](変更しない)
  
  ```
   py3compile test.py
  ```


  実行結果　[](変更しない)


  ```
  $ ls  //実行前
  test.py

  $ ls  //実行後
  __pycache__  test.py  //__pycache__ディレクトリが作成される

  $ cd __pycache__

  $ ls test.cpython-310.pyc //.pycが作成される。
  ```

### オプション一覧


- **-f**
  
  タイムスタンプに関係なく常にバイトコードファイルを再構築するためのオプション。つまり、ソースファイル（.pyファイル）の最終更新日時とバイトコードファイル（.pycファイル）の最終更新日時を比較し、ソースファイルが変更されていなくてもバイトコードファイルを再構築することを指す。

  実行例 [](変更しない)
  
  ```
  py3compile -f test.py
  ```


  実行結果　[](変更しない)


  ```
  $ pwd
  /home/user/py3compile/__pycache__
  $ ls
  test.cpython-310.pyc //.pycファイルがすでにある状態

  $cd ..
  $pwd
  home/user/py3compile
  $ ls
  __pycache__  test.py

  $ py3compile -f test.py //実行
  $ cd __pycache__
  $ ls 
  test.cpython-310.pyc // 同じ.pyが生成されている。
  ```
- **-O** 
    
  pyoファイルにコンパイル
  
  実行例　[](変更しない)
  
  ```
  py3compile -O test.py
  ```


  実行結果　[](変更しない)


  ```
  $ ls
  test.py

  $ py3compile -O test.py

  $ ls
  __pycache__  test.py

  $ cd __pycache__
  $ ls
  test.cpython-310.opt-1.pyc //.pyoファイルが生成される
  ```
- **-v** 
    
  コンパイルの際に、詳細な実行情報を表示
  
  実行例　[](変更しない)
  
  ```
  $ py3compile -v test.py
  ```


  実行結果　[](変更しない)


  ```
  D: py3compile:253: argv: ['/usr/bin/py3compile', '-vf', 'test.py']
  D: py3compile:254: options: {'verbose': True, 'force': True, 'optimize': False, 'package': None, 'vrange': None, 'regexpr': None}
  D: py3compile:255: args: ['test.py']
  ```

