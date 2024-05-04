[](ファイル名はコマンド名.md)
# < HEAD > < /HEAD >
HTML のヘッド部は < HEAD > 要素の内容である。ヘッド部の内容はページには表示されない。その代わり、ヘッド部の仕事は文書のメタデータを含んでいる。メタデータとはデータを説明するためのデータである。
構造を意味するタグ。

  記述例 [](変更しない)
  
  ```
   <HEAD>
    <META charset="utf-8">　<!--日本語と認識できるように指定-->
    <TITLE>解体新書</title>
   </HEAD>
  ```


### タグ一覧


- **< TITLE >**
  
  この文書のタイトルを指定する。
  HTML文書のヘッダ部に<b>一度だけ</b>記述する。タイトルは、ブラウザのツールバー、履歴、検索エンジンの検索結果などの表示で反映される。
  HTMLタグ、HEADタグ、BODYタグは省略可能だが、TITLEタグだけは省略することができない。
  タイトルに日本語を用いる場合は、先にMETAタグで文字コードの指定を行っておくことが推奨されている。
  <br>
  
  記述例 [](変更しない)
  
  ```
   <HEAD>
    <META charset="utf-8">　<!--日本語と認識できるように指定-->
    <TITLE>解体新書</title>
   </HEAD>
   <BODY>
    ここが本文新書
   </BODY>
  ```
  <br>
  <br>

  <b>実行結果</b>
  ![](https://raw.githubusercontent.com/YanaSota/kaitaishinsho/main/goto/%E3%83%96%E3%83%83%E3%82%AF%E3%83%9E%E3%83%BC%E3%82%AF%20gead.png "今回用いる処理グラフ")

  <br>
  
- **< META >**
  
  HTML文書内で使用される特殊なタグであり、メタデータ（文書に関する情報）を指定するため用いる。
  
  
  #### 属性一覧

  
  - **文字セットcharset**
    
    HTML文書の文字エンコーディングを指定する。一般的な値はUTF-8である。
    前述にもあるようにTITLEに非ASCII文字(日本語等)を用いている場合はTITLEタグの前に記述する必要がある。
    
    記述例 [](変更しない)
    
    ```
    <META CHARSET="UTF-8"> ※ASCII+日本語
    <META CHARSET="Shift_JIS"> ※日本語
    <META CHARSET="ISO-8859-1"> ※ラテン文字
    ```
  - **アプリケーション名 name="application-name"**
    
    Webアプリケーション名を指定するが、Webアプリケーションではない通常ページの場合には指定してはいけない。
    
    記述例 [](変更しない)
    
    ```
    <meta name="application-name" content="KaitaiSinsho">
    ```
  - **筆者名 author="author"**
    
    HTML文書の著者を明記する。画面上では表示の変化はない。
    
    記述例 [](変更しない)
    
    ```
    <meta name="author" content="Fukachan">
    ```
