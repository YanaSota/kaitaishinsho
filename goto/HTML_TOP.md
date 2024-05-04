[](ファイル名はコマンド名.md)
# HTML
HTML（HyperText Markup Language）は、ウェブページを作成するための標準的なマークアップ言語である。HTMLは、テキストベースの文書を構造化し、コンテンツを表示するための<b>タグ</b>を使用する。
タグは< *** >から< /*** >までを一つのブロックと見なす。
<b>そのため大文字/小文字の区別や空白や改行も無視される</b>。

記述例 [](変更しない)
  
  ```
<!-- saved from url=(0035)http://api.fml.org/dist/lsform.html -->
<html>
    <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"></head>
    <body>
        <p>SHOPPING CART</p>
        <form method="POST" action="http://api.fml.org/api/lsform/v1">
            <p>item-01<input name="item-01" type="text"></p>
            <p>item-02<input name="item-02" type="text"></p>
            <p>item-03<input name="item-03" type="text"></p>
            <p><input type="submit" value="buy"></p>
        </form>
    </body>
</html>
  ```

表示結果　[](変更しない)

![](https://raw.githubusercontent.com/YanaSota/kaitaishinsho/main/goto/%E5%88%9D%E3%83%94%E3%83%B3%E3%82%B0.png)


### タグ一覧 

- **[B](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 太文字
- **[BODY](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 本コンテンツ
- **[FORM](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 情報を送ることができる
- **[H](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 見出し
- **[HEAD](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 ヘッダー情報
- **[HTML](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 HTML文と指定する
- **[P](https://github.com/YanaSota/kaitaishinsho/blob/main/goto/tsort.md)** 　 一つの段落、文章