[](ファイル名はコマンド名.md)
# < HTML > < /HTML >
構造を意味するタグ。この文書が HTML文書であることを指定する。HTML 文書のルート（最上位要素）を表すので、ルート要素とも呼ばれる。他のすべての要素は、この要素の子孫として基本的には配置しなければならない。

  記述例 [](変更しない)
  
  ```
  <HTML>
    <BODY>
    <p>Hello</p>
    </BODY>
  </HTML>
  ```
### 属性一覧


- **lang**
  
  HTML文書の言語を指定する。
  指定の仕方としては言語コードを指定する。
  windows版のFirefoxではlang="ja"だと、日本語も英語もフォントが"Meiryo"となるが、lang="en"だと英語のみ"TimesNewRoman"で表記されるなどの違いがある。
  またここの言語コードでブラウザ側における自動翻訳の言語識別をしている。 

  記述例.1 [](変更しない)
  
  ```
  <HTML lang="ja">
  <BODY>
  <p>Hello</p>
  </BODY>
  </HTML>
  ```
  実行結果.1　[](変更しない)

  ![](https://raw.githubusercontent.com/YanaSota/kaitaishinsho/main/goto/hello_ja.png)
  <br>
  記述例.2 [](変更しない)
  
  ```
  <HTML lang="en">
  <BODY>
  <p>Hello</p>
  </BODY>
  </HTML>
  ```
  実行結果.2　[](変更しない)

  ![](https://raw.githubusercontent.com/YanaSota/kaitaishinsho/main/goto/Hello_en.png)
