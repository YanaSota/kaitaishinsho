[](ファイル名はコマンド名.md)
# gs
gs → ghostscript  
PostScriptおよびPDFファイルを表示および印刷するためのオープンソースのプログラム

  実行例 [](変更しない)
  
  ```
  gs -q -sPAPERSIZE=a4 -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -sOutputFile=test.pdf
  ```


  実行結果　[](変更しない)
　

  ```
  なし
  ```
  単一のページからなる無地のPDFファイルtest.pdfが作成される。

  ------

  実行例 [](変更しない)
  
  ```
  gs -sDEVICE=pngalpha -o test.png -r300 -dNOPAUSE -q test.pdf -c quit
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```
  test.pdfをDPI300でtest.pngに変換する。

### オプション一覧




- **-sDEVICE=\<device>**
  
  出力デバイスを指定する。

  以下はdeviceに指定できる項目である。

  - PDFデバイス:  
    - pdfwrite: PDFファイルを生成する。  
    - pdfmark: PDFマークファイルを生成する。  
    - pdfdraw: PDF描画オブジェクトを生成する。
  
  - 画像デバイス:  
    - pngalpha: PNG形式で透明な背景を持つ画像を生成する。  
    - jpeg: JPEG形式の画像を生成する。  
    - tiffg4: TIFF形式の画像を生成する。

  - プリンターデバイス:  
    - ljet4: HP LaserJet 4プリンターのエミュレーションを行う。  
    - cups: CUPS (Common UNIX Printing System) 用のデバイス。

  - 表示デバイス:  
    - x11: X Window System上に画像を表示する。  
    - display: ディスプレイに表示する。

  - SVGデバイス:  
    - svg: SVG (Scalable Vector Graphics) ファイルを生成する。

  - PostScriptデバイス:  
    - ps2write: Level2のPostScriptファイルを生成する。  
    - psmono: モノクロのPostScriptファイルを生成する。

- **-sOutputFile=\<file>** 
    
  出力ファイルの名前を指定する。

- **-r\<res>** 
    
  解像度を指定する。

  実行例　[](変更しない)
  
  ```
  -r300
  ```
  300 DPIに設定

- **\<file>** 
    
  入力ファイルの名前を指定する。

- **-o \<file>**

  出力ファイルの名前をしていする。

- **-dBATCH** 
    
  PostScript コマンドを読み取る対話型ループに入るのではなく、コマンド ラインで指定されたすべてのファイルを処理した後に Ghostscript を終了するようになる。コマンドラインの最後に -c quit を入力するのと同じである。

- **-dNOPAUSE** 
    
  プロンプトを無効にし、各ページの終わりで一時停止します。通常ファイルに出力を生成する場合は-dBATCHと共に使用する必要がある。

- **-q,-dQUIET** 
    
  標準出力上のルーチン情報コメントを抑制する。

- **-dFirstPage=\<n>** 
    
  変換する最初のページを指定する。

- **-dLastPage=\<n>** 
    
  変換する最後のページを指定する。

- **-sPAPERSIZE=\<size>** 
    
  用紙サイズを指定する。デフォルトはa4。

  以下はsizeに指定できる項目である。

  - a0~a6、b0~b6、c0~c6  
  - letter、legal、ledger、tabloid、executive、comm10

- **-c \<command>** 
    
  PostScriptコマンドを実行する。

  実行例　[](変更しない)
  
  ```
  -c "showpage"
  ```

- **-dPDFSETTINGS=\<value>** 
    
  PDF変換の品質を調整する。

  以下がvalueに指定できる項目である。

  - /screen:  
  画面表示用の低品質設定。低い解像度で生成される。ファイルサイズは小さくなり、画質も低下する。

  - /ebook:  
  電子書籍用の中程度の品質設定。モノクロ画像は高品質、カラー画像は中程度の品質で生成される。

  - /printer:  
  プリンター用の高品質設定。高解像度で生成される。ファイルサイズは大きくなるが、印刷時に高品質な結果が得られる。

  - /prepress:
  印刷用の最高品質設定。非常に高い解像度で生成され、印刷物としての品質が求められる場合に適している。

  - /default  
  デフォルト設定。通常、中程度の品質とファイルサイズになる。

- **g\<width>x\<height>** 

  生成されるページの幅を指定する。入力する値はポイント（1/72インチ）単位で指定する。

