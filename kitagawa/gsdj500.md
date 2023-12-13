[](ファイル名はコマンド名.md)
# gsdj500
Ghostscriptを使用してDeskJet 500 BubbleJet向けにテキストをフォーマットおよび印刷する。  
ヘッダーやフッターの文字列内の% # はpage #で置き換えられる。
デフォルトのデバイス（-sDEVICE=）と解像度（-r）は次のとおりである。
  gsdj500  djet500  300
  

  実行例 [](変更しない)
  
  ```
  gsdj500 test.pdf
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```
  test.pdfを印刷する。

### オプション一覧




- **-12BclqRr, -b\<header>,-f\<font>, -F\<hfont>, -L\<lines>, -p\<outfile>**
  
  基本のフォーマットを設定する。

- **-T\<n>** 
    
  tabの幅を指定する。
  
- **--add-to-space \<units>**
  
  各スペースの幅に指定された1/72インチ単位の数を追加する（負の値も可能）。

- **--add-to-width \<units>** 
    
  各文字の幅に指定された1/72インチ単位の数を追加する（負の値も可能）。
  
- **--columns \<n>**
  
  <n>列で印刷する。

- **--detect** 
    
  ファイルが%!で始まる場合、PostScriptファイルとして扱う。

- **--first-page \<n>**
  
  ページ<n>から印刷を開始する。

- **--kern \<file.afm>** 
    
  指定された.AFMファイルの情報を使用してカーニングを行う。

- **--last-page \<n>**
  
  ページ<n>で印刷を停止する。

- **--(heading|footing)-(left|center|right) \<string>** 
    
  ヘッダー/フッターのフィールドを設定する。

- **--margin-(top|bottom|left|right) <inches>** 
    
  余白を設定する。

- **--no-eject-(file|formfeed)** 
    
  end-of-file（EOF）が検出された場合、新しい列は始まるが、新しいページは始まらなくなる。

- **--spacing <n>** 
    
  行間の幅を2倍（n=2）,3倍（n=3）などで指定する。    