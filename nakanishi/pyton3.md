[](ファイル名はコマンド名.md)
# python3
pythonのプログラムを動かすためのコマンド

  実行例 [](変更しない)
  
  ```
  python3 hero.py
  ```


  実行結果　[](変更しない)


  ```
  $ cat hero.py
  print("Hello World")
  $ python3 hero.py
  Hello World
  ```

### オプション一覧


- **-c**
  
  コマンドラインからpythonのスクリプトを直接実効するためのオプション

  実行例.1 [](変更しない)
  
  ```
  python3 -c "result = 2 + 3; print(result)"
  
  ```


  実行結果.1　[](変更しない)


  ```
  5
  ```
  実行例.2　[](変更しない)
  
  ```
  python3 -c "import math; result = math.sqrt(25); print(result)"
  ```


  実行結果.2　[](変更しない)


  ```
  5.0
  ```
  実行例2では、モジュールをインポートしている。
- **-i** 
    
  pythonの実行後に対話モードに入る。対話モードに入ると、式の演算や変数の定義を操作などを行うことができる。
  
  実行例　[](変更しない)
  
  ```
  python3 -i hero.py 
  ```


  実行結果　[](変更しない)


  ```
  $ cat hero.py
  print("Hello World")
  $ python3 -i hero.py 
  Hello World
  >>>
  対話モードに入ると「>>>」が表示されるようになり、
  ここから入力ができる。

  $ python3 -i hero.py 
  Hello World
  >>> 2 + 3                // 2+3の計算
  5
  >>> "Hello, " + "World!" //Hello World!の表示
  'Hello, World!'
  >>> 10 > 5               //10>5が正しいかどうかを判断する
  True
  >>> len([1, 2, 3])　　　　//配列の長さを表示
  3
  ```
- **-m** 
    
  Pythonのモジュールを直接実効するためのオプション
  
  実行例.1　[](変更しない)
  
  ```
  python3 -m mymodule
  ```


  実行結果.1　[](変更しない)


  ```
  $ cat mymodule.py
  # mymodule.py

  def main():
    print("This is the main function.")

  if __name__ == '__main__':
    main()
  $ python3 -m mymodule
  This is the main function.
  ```
  
  実行例.2　[](変更しない)
  
  ```
  python3 -m http.server
  ```


  実行結果.2　[](変更しない)


  ```
  Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
  ```
  "http://0.0.0.0:8000/"にアクセスすると、ウェブサイトがブラウザで開かれる。このサイトには、現在いるディレクトリのファイル情報が記載されている。



- **-O** 
    
  Pythonの最適化モードを有効するためのオプション。最適化モードにすることで、実効速度が向上する。
  
  実行例　[](変更しない)
  
  ```
  python3  -O time.py 
  ```


  実行結果　[](変更しない)


  ```
  $ cat time.py
  import time

  def calculate_sum(n):
      start_time = time.time()
      total = 0
      for i in range(1, n+1):
          total += i
      end_time = time.time()
      execution_time = end_time - start_time
      print(f"Sum of numbers from 1 to {n} is: {total}")
      print(f"Execution Time: {execution_time} seconds")

  if __name__ == "__main__":
      calculate_sum(10000000)

  このコードは、calculate_sum関数が与えられた範囲の数値の総和を計算する。
  計算が終わると、プロセスの実行時間が表示される。


  $ python3 time.py  //最適化モードなし
  Sum of numbers from 1 to 10000000 is: 50000005000000
  Execution Time: 0.5327153205871582 seconds
  $ python3 -O time.py //最適化モードを適用
  Sum of numbers from 1 to 10000000 is: 50000005000000
  Execution Time: 0.5239436626434326 seconds

  ```
  オプション無しで実行した場合、時間が0.532sであるのに対し、
  -Oオプションありで実行すると時間が0.523sとなり、実行時間が短くなっていることが確認できる。

  
- **-B** 
    
  Python実行時に.pycファイルを生成しないようにするためのオプション。
  
  実行例　[](変更しない)
  
  ```
  python3 -Bc "import mymodule"
  ```


  実行結果　[](変更しない)


  ```
  $ cat mymodule.py //使用するモジュールの表示
  # mymodule.py

  def main():
      print("This is the main function.")

  if __name__ == '__main__':
      main()


  $ ls //ディレクトリにあるファイルを確認
  mymodule.py
  $ python3 -c "import mymodule" //-Bオプション無しで実行
  $ ls
  mymodule.py  __pycache__

  __pycache__ディレクトリが作成されており、その中には.pycファイルが存在する。


  $ rm -r  __pycache__ // __pycache__の削除
  $ python3 -Bc "import mymodule"  //-Bオプションありで実行
  $ ls 
  mymodule.py  //__pycache__が作成されていない
  ```

