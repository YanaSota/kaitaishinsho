[](ファイル名はコマンド名.md)
# python3
python [ -B ] [ -i ]
[ -m モジュール名 ] [ -O ] [ -s ] 
[ -v ] 
[ --check-hash-based-pycs default | always | never ]
[ -c コマンド | スクリプト | - ] [ 引数 ]

DESCRIPTION
Pythonは、解釈型で、対話的に使えるオブジェクト指向のプログラミング言語です。Pythonは、非常にわかりやすい構文と強力な機能を備えています。
PythonにはPythonチュートリアルがあり、Pythonのプログラミング入門に役立ちます。Pythonライブラリリファレンスでは、組み込みおよび標準の型、定数、関数、およびモジュールについて説明しています。また、Pythonリファレンスマニュアルでは、コア言語の構文と意味論について詳細に説明しています。Pythonの基本的な機能は、CやC++で書かれた独自のモジュールで拡張することもできます。ほとんどのシステムでは、このようなモジュールを動的にロードすることができます。Pythonは既存のアプリケーションの拡張言語としても適応可能です。インストールされたPythonモジュールやパッケージのドキュメントは、pydocプログラムを実行することで表示することができます。
COMMAND LINE OPTIONS
<br>
-B     .pyc ファイルをインポート時に書き込まない。PYTHONDONTWRITEBYTECODE も参照してください。
<br>
-b     str(bytes_instance)、str(bytearray_instance)、および bytes/bytearray と str の比較について警告を表示する（-bb: エラーを発生させる）。
<br>
-c command
        実行するコマンドを指定する（次のセクションを参照）。これにより、オプションリストが終了し、以降のオプションはコマンドの引数として渡されます。
<br>
--check-hash-based-pycs mode
        ハッシュベースの .pyc ファイルの最新情報の評価方法を設定する。

-d     パーサーデバッグ出力を有効にする（専門家向け、コンパイルオプションに依存）。
<br>
-E     PYTHONPATH や PYTHONHOME のような環境変数を無視する。これらはインタプリタの動作を変更するために使用されます。
<br>
-h ,  -? ,  --help
        インタプリタの実行ファイルの使用方法を表示し、終了します。
<br>
-i     スクリプトが最初の引数として渡された場合、または -c オプションが使用された場合、スクリプトまたはコマンドの実行後に対話モードに入る。$PYTHONSTARTUP ファイルは読み込まれません。スクリプトが例外を発生させた場合、グローバル変数やスタックトレースを調査するのに便利です。
<br>
-I     Python を隔離モードで実行する。これには -E と -s も含まれます。隔離モードでは、sys.path にはスクリプトのディレクトリやユーザーの site-packages ディレクトリは含まれません。また、PYTHON* 環境変数も無視されます。さらに、悪意のあるコードの注入を防ぐために追加の制限が課される場合があります。
<br>
-m module-name
        名前付きモジュールを sys.path で検索し、対応する .py ファイルをスクリプトとして実行する。これにより、オプションリストが終了し、以降のオプションはモジュールの引数として渡されます。
<br>
-O     assert 文と __debug__ の値に基づく条件付きコードを削除する；コンパイル（バイトコード）ファイルの拡張子の前に .opt-1 を追加してファイル名を変更する。
<br>
-OO    -O を行い、また docstrings を破棄する；コンパイル（バイトコード）ファイルの拡張子の前に .opt-2 を追加してファイル名を変更する。
<br>
-q バージョンと著作権メッセージを表示しない。これらのメッセージは対話モード以外でも抑制されます。
<br>
-s     ユーザーサイトディレクトリを sys.path に追加しない。
<br>
-S     モジュール site のインポートとそれに関連する sys.path の操作を無効にする。site が後で明示的にインポートされた場合も、これらの操作は無効になります。
<br>
-u     標準出力と標準エラー出力ストリームを非バッファリングにする。このオプションは標準入力ストリームには影響しません。
<br>
-v     モジュールが初期化されるたびにメッセージを表示し、それがロードされる場所（ファイル名または組み込みモジュール）を示す。2回指定すると、モジュールを検索する際にチェックされる各ファイルに対してメッセージを表示します。また、終了時のモジュールのクリーンアップに関する情報も提供します。
<br>
-V , --version
        実行可能ファイルの Python バージョン番号と終了メッセージを表示します。2回指定すると、ビルドに関する詳細情報も表示されます。
<br>

  実行例 [](変更しない)
  
  ```
  python3 hello.py
  ```


  実行結果　[](変更しない)


  ```
  $ cat hello.py
  print("Hello World")
  $ python3 hello.py
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
  python3 -i hello.py 
  ```


  実行結果　[](変更しない)


  ```
  $ cat hello.py
  print("Hello World")
  $ python3 -i hello.py 
  Hello World
  >>>
  対話モードに入ると「>>>」が表示されるようになり、
  ここから入力ができる。

  $ python3 -i hello.py 
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
  "http://0.0.0.0:8000/" にアクセスすると、ウェブサイトがブラウザで開かれる。このサイトには、現在いるディレクトリのファイル情報が記載されている。



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
- **-v** 
    
  Pythonが実行される際に行われる様々な処理や読み込まれるモジュールなどの情報が表示される。
  
  実行例　[](変更しない)
  
  ```
  python3 -v hello.py
  ```


  実行結果　[](変更しない)


  ```
  import _frozen_importlib # frozen
  import _imp # builtin
  import '_thread' # <class '_frozen_importlib.BuiltinImporter'>
  import '_warnings' # <class '_frozen_importlib.BuiltinImporter'>
  import '_weakref' # <class '_frozen_importlib.BuiltinImporter'>
  import '_io' # <class '_frozen_importlib.BuiltinImporter'>
  import 'marshal' # <class '_frozen_importlib.BuiltinImporter'>
  import 'posix' # <class '_frozen_importlib.BuiltinImporter'>
  import '_frozen_importlib_external' # <class '_frozen_importlib.FrozenImporter'>
  # installing zipimport hook
  import 'time' # <class '_frozen_importlib.BuiltinImporter'>
  import 'zipimport' # <class '_frozen_importlib.FrozenImporter'>
  # installed zipimport hook
  # /usr/lib/python3.10/encodings/__pycache__/__init__.cpython-310.pyc matches /usr/lib/python3.10/encodings/__init__.py
  # code object from '/usr/lib/python3.10/encodings/__pycache__/__init__.cpython-310.pyc'
  # /usr/lib/python3.10/__pycache__/codecs.cpython-310.pyc matches /usr/lib/python3.10/codecs.py
  # code object from '/usr/lib/python3.10/__pycache__/codecs.cpython-310.pyc'
  import '_codecs' # <class '_frozen_importlib.BuiltinImporter'>
  import 'codecs' # <_frozen_importlib_external.SourceFileLoader object at 0x7f7e6fdd32e0>

  ・
  ・
  ・
  
  # cleanup[3] wiping builtins
  # destroy _thread
  # destroy posix
  # destroy _frozen_importlib_external
  # destroy _imp
  # destroy io
  # destroy marshal
  # destroy time
  # destroy _warnings
  # destroy os
  # destroy stat
  # destroy genericpath
  # destroy _abc
  # destroy _frozen_importlib
  # destroy codecs
  # destroy sys
  # destroy encodings.aliases
  # destroy encodings.utf_8
  # destroy _codecs
  # destroy builtins
  # clear sys.audit hooks
  ```

