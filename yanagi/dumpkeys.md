[](ファイル名はコマンド名.md)
# dumpkeys
キーボードドライバの変換ケーブルの現在の内容を指定された形式で標準出力に書き込む。

オプションにより、出力形式の制御やカーネルやプログラムから他の情報を取得することも可能

カーネルから情報を取得しているので管理者権限が必要

  実行例 [](変更しない)
  
  ```
  sudo dumpkeys
  ```


  実行結果(一部)　[](変更しない)


  ```
  keymaps 0-127
  keycode　1 = Escape
         alt    keycode 1 = Meta_Escape
         shift  alt    keycode  1 = Meta_Escape
         altgr  alt    keycode  1 = Meta_Escape
         shift  altgr  alt keycode  1 = Meta_Escape
         control alt    keycode  1 = Meta_Escape
         shift  control alt  keycode  1 = Meta_Escape
         altgr  control alt  keycode  1 = Meta_Escape
         shift  altgr   control alt  keycode  1 = Meta_Escape
  ```

### オプション一覧


- **-i,--short-info**
  
  カーネルのキーボード・ドライバの特徴を表示する。

  表示される項目
  
  Keycode range supported by the kernel(カーネルがサポートするキーコードの範囲):キーコードの後にドの値を使うことができるか指定する。
  詳細はkeymaps(5)を参照

  Number of actions bindable to a key(キーにバインドできるアクションの数):ひとつのキーがさまざまな修飾キーを使っていくつの異なるアクションを出力できるかを示す。例えばこの値が16であれば、修飾キーと組み合わせて1つのキーに最大16種類のアクションを定義することができる。値が16の場合、カーネルはほぼ4つの修飾キーを知っており、キーと異なる組み合わせで押すことで、割り当てられたすべてのアクションにアクセスできる。

  Ranges of action codes supported by kernel(カーネルがサポートするアクションコードの範囲):16進数表記のアクションコード範囲のリストが含まれている。これらはキー定義の右側、行のvvで使用できる値
  
  キーコード xx = VV VV VV VV
  (キー定義行のフォーマットについての詳細は keymaps(5) を参照)。
  
  dumpkeys(1) と loadkeys(1) はシンボリック表記をサポートしており、カーネルごとにアクションコードが異なる可能性がある一方で、シンボリック名は通常同じままであるため、数値表記よりもシンボリック表記を推奨している。アクションコードの範囲のリストは、カーネルが loadkeys(1) が知っているすべてのシンボルを実際にサポートしているかどうか、あるいは、loadkeys(1) プログラムではシンボル名を持たない、カーネルによってサポートされているいくつかのアクションがあるかどうかを決定するために使用することができる。これを見るには、この範囲リストとアクションシンボルリストを比較する。

  Number of function keys supported by kernel(カーネルがサポートするファンクションキーの数):文字列の出力に使用できるアクションコードの数を示す。これらのアクションコードは伝統的にキーボードの様々なファンクションキーや編集キーにバインドされており、標準的なエスケープシーケンスを送信するように定義されている。しかし、一般的なコマンドラインや電子メールアドレスなど、好きなものを送信するようにこれらを再定義することができる。特に、この項目の数がキーボードのファンクションキーや編集キーの数より多い場合は、例えばAltGrと文字の組み合わせにバインドして、便利な文字列を送信できる「予備の」アクションコードがある可能性がある。
  詳細は loadkeys(1) を参照

  Function String(ファンクションの文字列):ファンクションキーの定義は次のコマンドで確認できる

  dumpkeys --funcs-only



  実行例 [](変更しない)
  
  ```
  sudo dumpkeys -i
  ```


  実行結果　[](変更しない)


  ```
  keycode range supported by kernel:        1 - 255
  max number of actions bindable to a key:      256
  number of keymaps in actual use:      128
  of which 121 dynamically allocated ranges of action codes supported by kernel:
        0x0000 - 0x00ff
        0x0100 - 0x01ff
        0x0200 - 0x0213
        0x0300 - 0x0313
        0x0400 - 0x041a
        0x0500 - 0x05ff
        0x0600 - 0x0603
        0x0700 - 0x0708
        0x0800 - 0x08ff
        0x0900 - 0x0919
        0x0a00 - 0x0a08
        0x0b00 - 0x0bff
        0x0c00 - 0x0c08
        0x0doo - 0x0dff
        0x0e00 - 0x0e0a
  number of function keys supported by kernel: 256
  max nr of compose definitions: 256
  nr of compose definitions in actual use: 68
  ```
- **-l,-s,--long-info** 
    
  長い情報リストを表示するようdumpkeysに指示する。
  出力は -- short-info の場合と同じで、 loadkeys(1) と dumpkeys(1) がサポ-トするアクションシンボルのリストと、 シンボルの数値が追加される。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -l
  ```


  実行結果(一部)　[](変更しない)


  ```
  keycode range supported by kernel:        1 - 255
  max number of actions bindable to a key:      256
  number of keymaps in actual use:      128
  of which 121 dynamically allocated ranges of action codes supported by kernel:
        0x0000 - 0x00ff
        0x0100 - 0x01ff
        0x0200 - 0x0213
        0x0300 - 0x0313
        0x0400 - 0x041a
        0x0500 - 0x05ff
        0x0600 - 0x0603
        0x0700 - 0x0708
        0x0800 - 0x08ff
        0x0900 - 0x0919
        0x0a00 - 0x0a08
        0x0b00 - 0x0bff
        0x0c00 - 0x0c08
        0x0doo - 0x0dff
        0x0e00 - 0x0e0a
  number of function keys supported by kernel: 256
  max nr of compose definitions: 256
  nr of compose definitions in actual use: 68
  Symbols recognized by dumpkeys:
  (numeric value, symbol)
  ```
- **-n,--numeric** 
    
  dumpkeysはアクションコードの値をシンボル表記に変換するのをバイパスし、代わりに16進数で表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -n
  ```


  実行結果(一部)　[](変更しない)


  ```
  keymaps 0-127
  keycode　1 = 0x001b
         alt    keycode 1 = 0x081b
         shift  alt    keycode  1 = 0x081b
         altgr  alt    keycode  1 = 0x081b
         shift  altgr  alt keycode  1 = 0x081b
         control alt    keycode  1 = 0x081b
         shift  control alt  keycode  1 = 0x081b
         altgr  control alt  keycode  1 = 0x081b
         shift  altgr   control alt  keycode  1 = 0x081b
  ```
- **-f,--full-table** 
    
 dumpkeys はすべてのショートハンドによるヒューリスティック (keymaps(5) を参照) をスキップし、キーバインドを正規の形式で出力する。
 最初に、現在定義されている修飾子の組み合わせを記述した keymaps 行が出力される。
 次に、各キーに対して、それぞれの修飾子の組み合わせの列を持つ行が出力される。
 例えば、現在使用されているキーマップが7つの修飾子を使用している場合、すべての行は7つのアクションコードの列を持つことになる。
 このフォーマットは、例えばdumpkeysの出力を後処理するプログラムで有用
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -f
  ```


  実行結果(一部)　[](変更しない)


  ```
  keymaps 0-127
  keycode　1 = Escape       Escape      Escape      Escape      Escape      Escape      Escape      Escape      Meta_Escape      Meta_Escape      Meta_Escape      Meta_Escape      Meta_Escape      Meta_Escape      Meta_Escape      Meta_Escape      Escape      Escape      Escape      Escape      Escape      Escape      Escape      Escape      Meta_Escape
  ```
- **-S,--shape** 
    
  コンソールのキーボードレイアウトに関連するキーボードとシンボルの対応が表示される。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -S=8
  ```


  実行結果(一部)　[](変更しない)


  ```
  keymaps 0-127
  keycode　1 = Escape
         alt    keycode 1 = Meta_Escape
         shift  alt    keycode  1 = Meta_Escape
         altgr  alt    keycode  1 = Meta_Escape
         shift  altgr  alt keycode  1 = Meta_Escape
         control alt    keycode  1 = Meta_Escape
         shift  control alt  keycode  1 = Meta_Escape
         altgr  control alt  keycode  1 = Meta_Escape
         shift  altgr   control alt  keycode  1 = Meta_Escape
  ```
- **-t,--funcs-only** 
    
  dumpkeysはファンクションキーの文字列定義のみを表示する。

  通常dumpkeysはキーバインディングと文字列定義の両方を表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -t
  ```


  実行結果　[](変更しない)


  ```
  表示なし
  ```
- **-k,--keys-only** 
    
  dumpkeysはキーバインドだけを表示する。

  通常dumpkeysはキーバインディングと文字列定義の両方を表示する。
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```


  実行結果(一部)　[](変更しない)


  ```
  keymaps 0-127
  keycode　1 = Escape
         alt    keycode 1 = Meta_Escape
         shift  alt    keycode  1 = Meta_Escape
         altgr  alt    keycode  1 = Meta_Escape
         shift  altgr  alt keycode  1 = Meta_Escape
         control alt    keycode  1 = Meta_Escape
         shift  control alt  keycode  1 = Meta_Escape
         altgr  control alt  keycode  1 = Meta_Escape
         shift  altgr   control alt  keycode  1 = Meta_Escape
  ```
- **-d,--compose-only** 
    
  dumpkeysはcomposeキーの組み合わせだけを表示する。

  カーネルがコンポーズ・キーをサポートしている場合にのみ利用できる。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -d
  ```


  実行結果(一部)　[](変更しない)


  ```
  compose '`' 'A' to Agrave
  compose '`' 'a' to agrave
  compose '\' 'A' to Aacute
  compose '\' 'a' to aacute
  compose '^' 'A' to Acircumflex
  compose '^' 'a' to acircumflex
  compose '~' 'A' to Atilde
  compose '~' 'a' to atilde
  compose '"' 'A' to Adiaeresis
  compose '"' 'a' to adiaeresis
  ```
- **-c,--charset=charset** 
    
  指定された文字セットに従って文字コード値を解釈するようにdumpkeysに指示する。
  
  文字コード値からシンボル名への変換にのみ影響する。
  
  現在有効な文字コードの値は iso-8859-Xである。
  
  charsetが指定されていない場合、iso-8859-1がデフォルトとして使用される。
  
  このオプションは出力行`charset "iso-8859-x"'を生成し、loadkeysにキーマップの解釈方法を伝える。
  
  (例えば、"division "はiso-8859-1ではoxf7だが、iso-8859-8ではoxba)。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -c iso-10646-18
  ```


  実行結果　[](変更しない)


  ```
  charset "iso-10646-18"
  keymaps 0-127
  keycode　1 = Escape
         alt    keycode 1 = Meta_Escape
         shift  alt    keycode  1 = Meta_Escape
         altgr  alt    keycode  1 = Meta_Escape
         shift  altgr  alt keycode  1 = Meta_Escape
         control alt    keycode  1 = Meta_Escape
         shift  control alt  keycode  1 = Meta_Escape
         altgr  control alt  keycode  1 = Meta_Escape
         shift  altgr   control alt  keycode  1 = Meta_Escape
  ```
- **-v,--verbose** 
    
  dumpkeysがサポートしている総裁情報が表示される。

  使用用途はキーボードの設定やキーマッピングに関する追加の詳細情報の確認である。
  
  実行例　[](変更しない)
  
  ```
  sudo dumpkeys -v
  ```


  実行結果　[](変更しない)


  ```
  keymaps 0-127
  keycode　1 = Escape
         alt    keycode 1 = Meta_Escape
         shift  alt    keycode  1 = Meta_Escape
         altgr  alt    keycode  1 = Meta_Escape
         shift  altgr  alt keycode  1 = Meta_Escape
         control alt    keycode  1 = Meta_Escape
         shift  control alt  keycode  1 = Meta_Escape
         altgr  control alt  keycode  1 = Meta_Escape
         shift  altgr   control alt  keycode  1 = Meta_Escape
  ```