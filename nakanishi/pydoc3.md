[](ファイル名はコマンド名.md)
# pydoc3
Pythonのモジュール、クラス、メソッド等のドキュメントを生成するためのツール。ドキュメントを作成することで、モジュールに含まれる関数やクラスを確認できる。
  実行例 [](変更しない)
  
  ```
  pydoc3 math
  ```


  実行結果　[](変更しない)


  ```
  Help on built-in module math:

    NAME
        math

    DESCRIPTION
        This module provides access to the mathematical functions
        defined by the C standard.

    FUNCTIONS
    acos(x, /)
        Return the arc cosine (measured in radians) of x.

        The result is between 0 and pi.

    acosh(x, /)
        Return the inverse hyperbolic cosine of x.

    asin(x, /)
        Return the arc sine (measured in radians) of x.

        The result is between -pi/2 and pi/2.

    asinh(x, /)
        Return the inverse hyperbolic sine of x.

    atan(x, /)
        Return the arc tangent (measured in radians) of x.

        The result is between -pi/2 and pi/2.

    atan2(y, x, /)
        Return the arc tangent (measured in radians) of y/x.

        Unlike atan(y/x), the signs of both x and y are considered.

    atanh(x, /)
        Return the inverse hyperbolic tangent of x.

    ceil(x, /)
        Return the ceiling of x as an Integral.

        This is the smallest integer >= x.
        ・
        ・
        ・

  DATA
    e = 2.718281828459045
    inf = inf
    nan = nan
    pi = 3.141592653589793
    tau = 6.283185307179586

  ```
ドキュメントには、「DESCRIPTION」、「FUNCTIONS」、「DATA」の3つのタグがある。
DESCRIPTION：モジュールの説明文
FUNCTIONS：モジュールに含まれている関数を表示
DATA：モジュール内で使用されている定数の表示

上の例では、mathモジュールのドキュメントを表示している。
実行結果からmathモジュールには、acos()やasin()などの関数が含まれていることが確認できる。また、自然対数（e）や演習率などの定数も確認できる。


### オプション一覧


- **-w**
  
  指定したモジュールのドキュメントを、HTMLドキュメントとして現在にいるディレクトリに作成する。

  実行例 [](変更しない)
  
  ```
  pydoc3 -w math
  ```


  実行結果　[](変更しない)


  ```
  $ ls //現在のディレクトリにあるファイルを確認
  file.txt
  $ pydoc3 -w math //コマンドの実効
  wrote math.html 
  $ ls　//実効後のファイルを確認
  file.txt math.html
  ```
- **-b** 
    
  pydocを使用して任意の未使用ポート上でHTTPサーバーをローカルホストで起動し、ウェブブラウザにウェブサイトが自動的に開かれる。このサイトでは、モジュールを検索しドキュメントを表示することができる。
  
  実行例　[](変更しない)
  
  ```
  $ pydoc3 -b
  ```


  実行結果　[](変更しない)


  ```
  Server ready at http://localhost:44161/
  Server commands: [b]rowser, [q]uit
  server>
  ```
  実行すると、サーバが起動して表示されたURLからアクセスできる。また、[b]を押すことでもサイトにアクセスできる。
  [q]を押すことでサーバを停止できる。

- **-n** 
    
  指定されたホスト名でHTTPサーバを起動して、ドキュメントを表示するウェブサイトを表示する。
  
  実行例　[](変更しない)
  
  ```
  pydoc3 -n 10.20.30.40
  ```


  実行結果　[](変更しない)


  ```
  Server ready at http://10.20.30.40:41009/
  Server commands: [b]rowser, [q]uit
  server> 
  ```

- **-p** 
    
  指定したポート番号でHTTPサーバを起動して、ドキュメントを表示するウェブサイトを表示する。
  
  実行例　[](変更しない)
  
  ```
  pydoc3 -p 5000
  ```


  実行結果　[](変更しない)


  ```
  Server ready at http://localhost:5000/
  Server commands: [b]rowser, [q]uit
  server>
  ```
- **-k**
  
  キーワードを指定して、それに関するモジュールを検索する

  実行例 [](変更しない)
  
  ```
  pydoc3 -k math
  ```


  実行結果　[](変更しない)


  ```
  cmath - This module provides access to mathematical functions for complex
  math - This module provides access to the mathematical functions
  numpy._core._multiarray_umath
  numpy._core.umath
  numpy.core._multiarray_umath
  numpy.core._umath_tests
  numpy.core.tests.test_scalarmath
  numpy.core.tests.test_umath
  numpy.core.tests.test_umath_accuracy
  numpy.core.tests.test_umath_complex
  numpy.core.umath - Create the numpy.core.umath namespace for backward compatibility. In v1.16
  numpy.core.umath_tests - Shim for _umath_tests to allow a deprecation period for the new name.
  numpy.lib.scimath - Wrapper functions to more user-friendly calling of certain math functions
  numpy.linalg._umath_linalg
  ```
  上の例では、キーワード「math」に関するモジュールの検索結果である。
  "cmath"、"math"、"numpy"などのモジュールが表示されている。
