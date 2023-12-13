[](ファイル名はコマンド名.md)
# ptx 
ptxコマンドは、与えられたテキストファイルを処理し、単語の順列索引を生成する。順列索引は、単語をアルファベット順にソートし、単語ごとにその出現箇所や参照情報を提供する。順列索引は、単語を検索したり、単語の出現パターンを分析したりするのに役立つ。

  実行例 [](変更しない)
  
  ```
  ptx file.txt
  ```


  実行結果　[](変更しない)



  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx file.txt　/実行後

   with various words.                 It contains multiple lines of text
   permuted index of these/            The ptx command will generate a
   the ptx command.                    This is a sample file for testing
   command.                  This is   a sample file for testing the ptx
       The ptx command will generate   a permuted index of these words.
     sample file for testing the ptx   command.                   This is a
   index of these words/     The ptx   command will generate a permuted
   with various words.            It   contains multiple lines of text
                    This is a sample   file for testing the ptx command.
               This is a sample file   for testing the ptx command.
   words.       The ptx command will   generate a permuted index of these
            will generate a permuted   index of these words.       /command
   ptx command.                 This   is a sample file for testing the
                It contains multiple   lines of text with various words.
   various words.        It contains   multiple lines of text with
          It contains multiple lines   of text with various words.
      will generate a permuted index   of these words.         /ptx command
     The ptx command will generate a   permuted index of these words.
       a sample file for testing the   ptx command.                 This is
   permuted index of these/      The   ptx command will generate a
   command.                This is a   sample file for testing the ptx
           This is a sample file for   testing the ptx command.
       It contains multiple lines of   text with various words.
        is a sample file for testing   the ptx command.                This
        generate a permuted index of   these words.           /command will
         multiple lines of text with   various words.           It contains
   these words.      The ptx command   will generate a permuted index of
     contains multiple lines of text   with various words.               It
          lines of text with various   words.                     /multiple
           a permuted index of these   words.                /will generate

  
  
  ```
  実行結果の中央を見ると、上から「It」,「The」,「This」～のようにアルファベット順でキーワードの順列索引が生成されます。キーワードの両サイドには前後の文脈が表示される。




### オプション一覧
このオプションを用いると、左の列にファイル名とキーワードが含まれている行番号を表示することができる。ただし、標準入力の場合ファイル名は表示されない。

- **-A**
  
  

  実行例.1 [](変更しない)
  
  ```
  ptx file.txt -A

 
  ```


  実行結果.1　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx file.txt -A /実行後
  file.txt:2:  of text with various/        It contains multiple lines
  file.txt:3:  generate a permuted/         The ptx command will
  file.txt:1:  testing the ptx/             This is a sample file for
  file.txt:1:  the ptx/           This is   a sample file for testing
  file.txt:3:      /command will generate   a permuted index of these/
  file.txt:1:    file for testing the ptx   command.            /a sample
  file.txt:3:  permuted/          The ptx   command will generate a
  file.txt:2:  text with various/      It   contains multiple lines of
  file.txt:1:            This is a sample   file for testing the ptx/
  file.txt:1:       This is a sample file   for testing the ptx command/
  file.txt:3:        The ptx command will   generate a permuted index/
  file.txt:3:   /will generate a permuted   index of these words.
  file.txt:1:  testing the ptx/      This   is a sample file for
  file.txt:2:        It contains multiple   lines of text with various/
  file.txt:2:  various/       It contains   multiple lines of 

  ```
  実行例.2 [](変更しない)
  
  ```
   cat file.txt | ptx -A
  //catでfile.txtの中身を標準出力し、それをpxtで順列索引する。
  ```


  実行結果.2　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.


  $ cat file.txt | ptx -A /実行後


  :2:  text with various words.         It contains multiple lines of
  :3:  permuted index of these/         The ptx command will generate a
  :1:  testing the ptx command.         This is a sample file for
  :1:  ptx command.           This is   a sample file for testing the
  :3:      /ptx command will generate   a permuted index of these words/
  :1:        file for testing the ptx   command.             /is a sample
  :3:  permuted index of/     The ptx   command will generate a
  :2:  with various words.         It   contains multiple lines of text
  :1:  command.      This is a sample   file for testing the ptx
  :1:           This is a sample file   for testing the ptx command.
  :3:            The ptx command will   generate a permuted index of/
  :3:        will generate a permuted   index of these words.    /command
  :1:  the ptx command.          This   is a sample file for testing
  :2:            It contains multiple   lines of text with various/
  :2:  various words/     It contains   multiple lines of text with
  :2:      It contains multiple lines   of text with various words.
  :3:       generate a permuted index   of these words.     /command will
  :3:    /ptx command will generate a   permuted index of these words.
  :1:     sample file for testing the   ptx command.            This is a
  :3:  permuted index of/         The   ptx command will generate a
  :1:  command.             This is a   sample file for testing the ptx
  :1:       This is a sample file for   testing the ptx command.
  :2:      contains multiple lines of   text with various words.       It
  :1:    is a sample file for testing   the ptx command.             This
  :3:    generate a permuted index of   these words.                /will
  :2:     multiple lines of text with   various words.        It contains
  :3:  of these/      The ptx command   will generate a permuted index
  :2:          multiple lines of text   with various words.     /contains
  :2:      lines of text with various   words.                  /multiple
  :3:       a permuted index of these   words.             /will generate
  ```



- **-W**
  
  正規表現を用いて、順列索引するキーワードを設定できる。

  実行例 [](変更しない)
  
  ```
  ptx file.txt -W 'It'
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx file.txt -W 'It' /実行後
  with various words.                 It contains multiple lines of text
  ```
- **-f** 
    
  索引のソートや正規表現の大文字と小文字を区別する動作を変更する。索引のソートは大文字と小文字を区別しなくなり、正規表現の大文字と小文字の区別もなくなる
  
  実行例　[](変更しない)
  
  ```
  ptx file.txt -f
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.


  $ ptx file.txt -f /実行後
      This is   　　　　　　　　　　　   a sample file for testing the ptx
       The ptx command will generate   a permuted index of these words.
     sample file for testing the ptx   command.                   This is a
   index of these words/     The ptx   command will generate a permuted
   with various words.            It   contains multiple lines of text
                    This is a sample   file for testing the ptx command.
               This is a sample file   for testing the ptx command.
   words.       The ptx command will   generate a permuted index of these
            will generate a permuted   index of these words.       /command
   ptx command.                 This   is a sample file for testing the
   with various words.                 It contains multiple lines of text
                It contains multiple   lines of text with various words.
   various words.        It contains   multiple lines of text with
          It contains multiple lines   of text with various words.
      will generate a permuted index   of these words.         /ptx command
     The ptx command will generate a   permuted index of these words.
       a sample file for testing the   ptx command.                 This is
   permuted index of these/      The   ptx command will generate a
   command.                This is a   sample file for testing the ptx
           This is a sample file for   testing the ptx command.
       It contains multiple lines of   text with various words.
        is a sample file for testing   the ptx command.                This
   permuted index of these/            The ptx command will generate a
        generate a permuted index of   these words.           /command will
   the ptx command.                    This is a sample file for testing
         multiple lines of text with   various words.           It contains
   these words.      The ptx command   will generate a permuted index of
     contains multiple lines of text   with various words.               It
          lines of text with various   words.                     /multiple
           a permuted index of these   words.                /will generate
  ```
  オプション無しの場合では大文字から小文字の順にソートされるが、fオプションを使うと、大文字小文字の区別なしにアルファベット順にソートされる。
　　
- **-g** 
    
  実行結果の中央部分にあるスペースを変更するオプション。gの後に数字を指定して幅を変える。デフォルトでは3になっている。
  
  実行例　[](変更しない)
  
  ```
  ptx -g 7 file.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.



  $ ptx -g 7 file.txt /実行後
       with various words.                 It contains multiple lines of text
       permuted index of/                  The ptx command will generate a
       the ptx command.                    This is a sample file for testing
       command.              This is       a sample file for testing the ptx
          /ptx command will generate       a permuted index of these words.
            file for testing the ptx       command.            This is a sample
       index of/             The ptx       command will generate a permuted
       with various/              It       contains multiple lines of text
                    This is a sample       file for testing the ptx command.
               This is a sample file       for testing the ptx command.
                The ptx command will       generate a permuted index of these/
           /will generate a permuted       index of these words.
       ptx command.             This       is a sample file for testing the
                It contains multiple       lines of text with various words.
       various/          It contains       multiple lines of text with
          It contains multiple lines       of text with various words.
           generate a permuted index       of these words.        /command will
        /ptx command will generate a       permuted index of these words.
         sample file for testing the       ptx command.               This is a
       permuted index/           The       ptx command will generate a
       command.            This is a       sample file for testing the ptx
           This is a sample file for       testing the ptx command.
          contains multiple lines of       text with various words.          It
           a sample file for testing       the ptx command.             This is
                 a permuted index of       these words.          /will generate
         multiple lines of text with       various words.           It contains
                     The ptx command       will generate a permuted index of/
              multiple lines of text       with various words.        /contains
          lines of text with various       words.                     /multiple
           a permuted index of these       words.                /will generate
  ```

- **-T** 
    
  出力をTeXディレクティブとして生成します。TeXディレクティブは、ptxコマンドによって生成される出力形式の1つ。TeXは、文書作成システムであり、特に科学技術文書や数式を含む文書の作成に広く使用される。
  
  実行例　[](変更しない)
  
  ```
  ptx file.txt -T
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx file.txt -T /実行後
  \xx {with various words.}{}{It}{ contains multiple lines of text}{}
  \xx {permuted index of these}{}{The}{ ptx command will generate a}{}
  \xx {the ptx command.}{}{This}{ is a sample file for testing}{}
  \xx {command.}{This is}{a}{ sample file for testing the ptx}{}
  \xx {}{The ptx command will generate}{a}{ permuted index of these words.}{}
  \xx {}{sample file for testing the ptx}{command}{.}{This is a}
  \xx {index of these words}{The ptx}{command}{ will generate a permuted}{}
  \xx {with various words.}{It}{contains}{ multiple lines of text}{}
  \xx {}{This is a sample}{file}{ for testing the ptx command.}{}
  \xx {}{This is a sample file}{for}{ testing the ptx command.}{}
  \xx {words.}{The ptx command will}{generate}{ a permuted index of these}{}
  \xx {}{will generate a permuted}{index}{ of these words.}{command}
  \xx {ptx command.}{This}{is}{ a sample file for testing the}{}
  \xx {}{It contains multiple}{lines}{ of text with various words.}{}
  \xx {various words.}{It contains}{multiple}{ lines of text with}{}
  \xx {}{It contains multiple lines}{of}{ text with various words.}{}
  \xx {}{will generate a permuted index}{of}{ these words.}{ptx command}
  \xx {}{The ptx command will generate a}{permuted}{ index of these words.}{}
  \xx {}{a sample file for testing the}{ptx}{ command.}{This is}
  \xx {permuted index of these}{The}{ptx}{ command will generate a}{}
  \xx {command.}{This is a}{sample}{ file for testing the ptx}{}
  \xx {}{This is a sample file for}{testing}{ the ptx command.}{}
  \xx {}{It contains multiple lines of}{text}{ with various words.}{}
  \xx {}{is a sample file for testing}{the}{ ptx command.}{This}
  \xx {}{generate a permuted index of}{these}{ words.}{command will}
  \xx {}{multiple lines of text with}{various}{ words.}{It contains}
  \xx {these words.}{The ptx command}{will}{ generate a permuted index of}{}
  \xx {}{contains multiple lines of text}{with}{ various words.}{It}
  \xx {}{lines of text with various}{words}{.}{multiple}
  \xx {}{a permuted index of these}{words}{.}{will generate}
  ```


- **-S** 
    
  行の終わりまたは文の終わりを指定するために使用される。具体的な正規表現を指定する必要がある。
  
  実行例　[](変更しない)
  
  ```
  ptx -S '\.|\?|!' file.txt
  //文の終わりを .(ピリオド),?,!に設定。
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.


  $ ptx -S '\.|\?|!' file.txt
  　   /for testing the ptx command.   It contains multiple lines of text/
        /of text with various words.   The ptx command will generate a/
   the ptx command. It/                This is a sample file for testing
   command. It contains/     This is   a sample file for testing the ptx
    /. The ptx command will generate   a permuted index of these words.
     sample file for testing the ptx   command. It contains multiple/    /a
        /with various words. The ptx   command will generate a permuted/
    /for testing the ptx command. It   contains multiple lines of text/
   It contains/     This is a sample   file for testing the ptx command.
               This is a sample file   for testing the ptx command. It/
        /words. The ptx command will   generate a permuted index of these/
            will generate a permuted   index of these words.       /command
   ptx command. It/             This   is a sample file for testing the
      /command. It contains multiple   lines of text with various words./
       /the ptx command. It contains   multiple lines of text with/
       /. It contains multiple lines   of text with various words. The/
      will generate a permuted index   of these words.         /ptx command
     The ptx command will generate a   permuted index of these words.    /.
      /a sample file for testing the   ptx command. It contains multiple/
    /of text with various words. The   ptx command will generate a/
   command. It/            This is a   sample file for testing the ptx
           This is a sample file for   testing the ptx command. It/
    /. It contains multiple lines of   text with various words. The ptx/
       /is a sample file for testing   the ptx command. It contains/
        generate a permuted index of   these words.           /command will
        /multiple lines of text with   various words. The ptx command/
     /various words. The ptx command   will generate a permuted index of/
     contains multiple lines of text   with various words. The ptx/   /. It
         /lines of text with various   words. The ptx command will/
           a permuted index of these   words.                /will generate
  ```


- **-r** 
    
  各入力行の先頭の非空白文字を参照IDとして扱うために使用される。参照IDは行のテキストとは別に扱われ、インデックス生成時にそれぞれの行に関連付けられる。
  
  実行例　[](変更しない)
  
  ```
  ptx -r file.txt
  ```


  実行結果　[](変更しない)


  ```

  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.


  $ ptx -r file.txt /実行後
  This   ptx command.               is   a sample file for testing the
  The        ptx command will generate   a permuted index of these/
  This        file for testing the ptx   command.             is a sample
  The    permuted index of/        ptx   command will generate a
  It     text with various words/        contains multiple lines of
  This   command.          is a sample   file for testing the ptx
  This                is a sample file   for testing the ptx command.
  The    these/       ptx command will   generate a permuted index of
  The        /will generate a permuted   index of these words.
  This   the ptx command.                is a sample file for testing
  It     words.      contains multiple   lines of text with various
  It     various words.       contains   multiple lines of text with
  It           contains multiple lines   of text with various words.
  The        generate a permuted index   of these words.    /command will
  The      ptx command will generate a   permuted index of these words.
  This     sample file for testing the   ptx command.                is a
  The    permuted index of these/        ptx command will generate a
  This   ptx command.             is a   sample file for testing the
  This            is a sample file for   testing the ptx command.
  It        contains multiple lines of   text with various words.
  This       a sample file for testing   the ptx command.              is
  The              a permuted index of   these words.      /will generate
  It       multiple lines of text with   various words.          contains
  The    of these/         ptx command   will generate a permuted index
  It            multiple lines of text   with various words.     contains
  It        lines of text with various   words.                 /multiple
  The        a permuted index of these   words.                 /generate
  ```
  -Aオプションでは左端にファイル名と行番号が表現されるが、-rオプションでは各行の先頭に来る単語「This」,「The」,「It」が左端に表示される。
  <br>
- **-w** 
    
  出力行の長さを指定した数字によって設定することができるオプション。
  
  実行例.1　[](変更しない)
  
  ```
  ptx -w 20 file.txt
  ```


  実行結果.1　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx -w 20 file.txt /実行後

             It/
             The ptx/
   a/        This is
       /is   a sample/
          /   a/
      /ptx   command.
      /ptx   command/
        It   contains/
          /   file for/
     /file   for/
     /will   generate/
          /   index of/
      This   is a/
          /   lines of/
          /   multiple/
    /lines   of text/
    /index   of these/
        /a   permuted/
      /the   ptx/
       The   ptx/
     /is a   sample/
      /for   testing/
       /of   text/
          /   the ptx/
       /of   these/
     /with   various/
          /   will/
     /text   with/
          /   words.
    /these   words.
  ```  
  実行例.2　[](変更しない)
  
  ```
  ptx -w 100 file.txt
  ```


  実行結果.2　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx -w 100 file.txt /実行後


     words.                                          It contains multiple lines of text with various
   of these words.                                   The ptx command will generate a permuted index
   command.                                          This is a sample file for testing the ptx
                                           This is   a sample file for testing the ptx command.
                     The ptx command will generate   a permuted index of these words.
         This is a sample file for testing the ptx   command.
   words.                                  The ptx   command will generate a permuted index of these
   words.                                       It   contains multiple lines of text with various
                                  This is a sample   file for testing the ptx command.
                             This is a sample file   for testing the ptx command.
                              The ptx command will   generate a permuted index of these words.
          The ptx command will generate a permuted   index of these words.
                                              This   is a sample file for testing the ptx command.
                              It contains multiple   lines of text with various words.
                                       It contains   multiple lines of text with various words.
                        It contains multiple lines   of text with various words.
        ptx command will generate a permuted index   of these words.                                The
                   The ptx command will generate a   permuted index of these words.
             This is a sample file for testing the   ptx command.
   these words.                                The   ptx command will generate a permuted index of
                                         This is a   sample file for testing the ptx command.
                         This is a sample file for   testing the ptx command.
                     It contains multiple lines of   text with various words.
                 This is a sample file for testing   the ptx command.
     ptx command will generate a permuted index of   these words.
                        The
           It contains multiple lines of text with   various words.
                                   The ptx command   will generate a permuted index of these words.
                It contains multiple lines of text   with various words.
      contains multiple lines of text with various   words.




  ```  

- **-b** 
    
  単語の区切りをコンマ(,)やピリオド(.)などの文字で指定することができる。-bオプションを使用しない場合は、タブ文字（\t）、改行文字（\n）、およびスペースが単語の区切りとして扱われる。指定方法は、テキストファイルに記載された文字を参照する。
  
  実行例　[](変更しない)
  
  ```
  ptx -b separators.txt file.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ cat  separators.txt /単語を区切る文字の出力
  .
  ,
  ;


  $ ptx -b separators.txt file.txt /実行後

   .                                   It contains multiple lines of text with various words　
   .                                   The ptx command will generate a permuted index of these words
   .                                   This is a sample file for testing the ptx command



  ``` 
  上の例ではピリオド(.)がヒットし、file.txt内の各1文が単語として区切られている。


- **-o** 
    
  順序索引するワードの指定を、ファイル指定によって行うオプション。
  
  実行例　[](変更しない)
  
  ```
  ptx -o keywords.txt file.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ cat keywords.txt /順序索引するワード表示
  It
  The
  This
  a
  command


  $  ptx -o keywords.txt file.txt /実行後
   with various words.                 It contains multiple lines of text
   permuted index of these/            The ptx command will generate a
   the ptx command.                    This is a sample file for testing
   command.                  This is   a sample file for testing the ptx
       The ptx command will generate   a permuted index of these words.
     sample file for testing the ptx   command.                   This is a
   index of these words/     The ptx   command will generate a permuted
  ```  

- **-i** 
    
  順序索引しないワードをテキストファイルで指定する。
  
  実行例　[](変更しない)
  
  ```
  ptx -i ignore.txt file.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ cat ignore.txt /順序索引しないワードの表示
  It
  The
  This
  a
  command

  $ ptx -i ignore.txt file.txt
  with various words.            It    contains multiple lines of text
                    This is a sample   file for testing the ptx command.
               This is a sample file   for testing the ptx command.
   words.       The ptx command will   generate a permuted index of these
            will generate a permuted   index of these words.       /command
   ptx command.                 This   is a sample file for testing the
                It contains multiple   lines of text with various words.
   various words.        It contains   multiple lines of text with
          It contains multiple lines   of text with various words.
      will generate a permuted index   of these words.         /ptx command
     The ptx command will generate a   permuted index of these words.
       a sample file for testing the   ptx command.                 This is
   permuted index of these/      The   ptx command will generate a
   command.                This is a   sample file for testing the ptx
           This is a sample file for   testing the ptx command.
       It contains multiple lines of   text with various words.
        is a sample file for testing   the ptx command.                This
        generate a permuted index of   these words.           /command will
         multiple lines of text with   various words.           It contains
   these words.      The ptx command   will generate a permuted index of
     contains multiple lines of text   with various words.               It
          lines of text with various   words.                     /multiple
           a permuted index of these   words.                /will generate

  ``` 

- **-R** 
    
  参照行を右に配置する。
  
  実行例　[](変更しない)
  
  ```
  ptx -RA file.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx -RA file.txt
  with various words.                 It contains multiple lines of text     file.txt:2
  permuted index of these/            The ptx command will generate a        file.txt:3
  the ptx command.                    This is a sample file for testing      file.txt:1
  command.                  This is   a sample file for testing the ptx      file.txt:1
      The ptx command will generate   a permuted index of these words.       file.txt:3
    sample file for testing the ptx   command.                   This is a   file.txt:1
  index of these words/     The ptx   command will generate a permuted       file.txt:3
  with various words.            It   contains multiple lines of text        file.txt:2
                   This is a sample   file for testing the ptx command.      file.txt:1
              This is a sample file   for testing the ptx command.           file.txt:1
  words.       The ptx command will   generate a permuted index of these     file.txt:3
           will generate a permuted   index of these words.       /command   file.txt:3
  ptx command.                 This   is a sample file for testing the       file.txt:1
               It contains multiple   lines of text with various words.      file.txt:2
  various words.        It contains   multiple lines of text with            file.txt:2
         It contains multiple lines   of text with various words.            file.txt:2
     will generate a permuted index   of these words.         /ptx command   file.txt:3
    The ptx command will generate a   permuted index of these words.         file.txt:3
      a sample file for testing the   ptx command.                 This is   file.txt:1
  permuted index of these/      The   ptx command will generate a            file.txt:3
  command.                This is a   sample file for testing the ptx        file.txt:1
          This is a sample file for   testing the ptx command.               file.txt:1
      It contains multiple lines of   text with various words.               file.txt:2
      is a sample file for testing   the ptx command.
  This   file.txt:1
       generate a permuted index of   these words.           /command will   file.txt:3
        multiple lines of text with   various words.           It contains   file.txt:2
  these words.      The ptx command   will generate a permuted index of      file.txt:3
    contains multiple lines of text   with various words.
    It   file.txt:2
  
  
  ``` 
  オプション-Aで表示されるファイル名と行番号が右に表示される

- **-O** 
    
  出力をROFFディレクティブとして生成する。ROFFディレクティブは、テキストのフォーマットやスタイルを指定するためのコマンドセットである。
  
  実行例　[](変更しない)
  
  ```
  ptx -O file.txt > output.roff
  ```


  実行結果　[](変更しない)


  ```
  $ cat file.txt /実行前

  This is a sample file for testing the ptx command.
  It contains multiple lines of text with various words.
  The ptx command will generate a permuted index of these words.

  $ ptx -O file.txt > output.roff 

  $ cat output.roff /実行後
  .xx "with various words." "" "It contains multiple lines of text" ""
  .xx "permuted index of these/" "" "The ptx command will generate a" ""
  .xx "the ptx command." "" "This is a sample file for testing" ""
  .xx "command." "This is" "a sample file for testing the ptx" ""
  .xx "" "The ptx command will generate" "a permuted index of these words." ""
  .xx "" "sample file for testing the ptx" "command." "This is a"
  .xx "index of these words/" "The ptx" "command will generate a permuted" ""
  .xx "with various words." "It" "contains multiple lines of text" ""
  .xx "" "This is a sample" "file for testing the ptx command." ""
  .xx "" "This is a sample file" "for testing the ptx command." ""
  .xx "words." "The ptx command will" "generate a permuted index of these" ""
  .xx "" "will generate a permuted" "index of these words." "/command"
  .xx "ptx command." "This" "is a sample file for testing the" ""
  .xx "" "It contains multiple" "lines of text with various words." ""
  .xx "various words." "It contains" "multiple lines of text with" ""
  .xx "" "It contains multiple lines" "of text with various words." ""
  .xx "" "will generate a permuted index" "of these words." "/ptx command"
  .xx "" "The ptx command will generate a" "permuted index of these words." ""
  .xx "" "a sample file for testing the" "ptx command." "This is"
  .xx "permuted index of these/" "The" "ptx command will generate a" ""
  .xx "command." "This is a" "sample file for testing the ptx" ""
  .xx "" "This is a sample file for" "testing the ptx command." ""
  .xx "" "It contains multiple lines of" "text with various words." ""
  .xx "" "is a sample file for testing" "the ptx command." "This"
  .xx "" "generate a permuted index of" "these words." "/command will"
  .xx "" "multiple lines of text with" "various words." "It contains"
  .xx "these words." "The ptx command" "will generate a permuted index of" ""
  .xx "" "contains multiple lines of text" "with various words." "It"
  .xx "" "lines of text with various" "words." "/multiple"
  .xx "" "a permuted index of these" "words." "/will generate"


  
  ``` 



- **-F** 
    
  行の切り詰めを示すためのフラグを指定するために使用さる。行の切り詰めとは、テキストが行の幅に収まらずに途中で切り捨てられた場合に、それを示すための特定のフラグや記号を挿入することを指す。
  
  実行例　[](変更しない)
  
  ```
  ptx -F "/---" input.txt > output.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat input.txt /実行前
  This is a sample text that is too long to fit within a single line. /---

  $ ptx -F "/---" input.txt > output.txt /実行後

  $ $ cat output.txt
     is too long to fit/---            This is a sample text that
   long to fit/---           This is   a sample text that is too
           is too long to fit within   a single line. /---         /---that
        /---text that is too long to   fit within a single line. /-/---
   long to fit/---              This   is a sample text that is too
           /---is a sample text that   is too long to fit within a/---
              to fit within a single   line. /---           /---is too long
       /---a sample text that is too   long to fit within a single/---
   to fit/---              This is a   sample text that is too long
            too long to fit within a   single line. /---        /---that is
                    This is a sample   text that is too long to fit/---
               This is a sample text   that is too long to fit/---
           /---text that is too long   to fit within a single line./---
        /---is a sample text that is   too long to fit within a/---
         /---that is too long to fit   within a single line. /---

  ``` 

- **-G** 
    
  System Vのptxコマンドと同様の動作をするようにptxコマンドを設定する。
  
  実行例　[](変更しない)
  
  ```
  $ ptx -G input.txt > output.txt
  ```


  実行結果　[](変更しない)


  ```
  $ cat input.txt /実行前
  This is line 1.
  This is line 2.
  This is line 3.

  $  ptx -G input.txt > output.txt

  $ cat output.txt
  .xx "" "This is line" "1." ""
  .xx "" "This is line" "2." ""
  .xx "" "This is line" "3." ""
  .xx "" "" "This is line 1." ""
  .xx "" "" "This is line 2." ""
  .xx "" "" "This is line 3." ""
  .xx "" "This" "is line 1." ""
  .xx "" "This" "is line 2." ""
  .xx "" "This" "is line 3." ""
  .xx "" "This is" "line 1." ""
  .xx "" "This is" "line 2." ""
  .xx "" "This is" "line 3." ""
  ```


 


