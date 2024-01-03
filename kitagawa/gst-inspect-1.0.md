[](ファイル名はコマンド名.md)
# gst-inspect-1.0
gst → GStreamer  
GStreamerは、マルチメディアデータの処理やストリーミングを行うためのフレームワークであり、様々なメディア関連のタスクに使用される。  
GStreamerのプラグインに関する情報を取得するためのコマンド。

  実行例 [](変更しない)
  
  ```
  $ gst-inspect-1.0
  ```


  実行結果　[](変更しない)


  ```
  1394: dv1394src: Firewire (1394) DV video source
  1394: hdv1394src: Firewire (1394) HDV video source
  aasink: aasink: ASCII art video sink
  aasink: aatv: aaTV effect
  adder: adder: Adder
  alaw: alawdec: A Law audio decoder
  alaw: alawenc: A Law audio encoder
  alpha: alpha: Alpha filter
  alphacolor: alphacolor: Alphacolor filter
  ~~~~以下省略~~~~
  ```

### オプション一覧



- **\<PLUGIN|ELEMENT>** 
    
  指定したプラグインまたは要素の詳細を表示する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-inspect-1.0 audiotestsrc
  ```


  実行結果　[](変更しない)


  ```
  Factory Details:
      Rank                     none (0)
      Long-name                Audio test source
      Klass                    Source/Audio
      Description              Creates audio test signals of given frequency and volume
      Author                   Stefan Kost <ensonic@users.sf.net>

  ~~~~以下省略~~~~
  ```

- **-a, --print-all**
  
  全てのプラグインと要素を全て出力する。

  実行例 [](変更しない)
  
  ```
  $ gst-inspect-1.0 -a
  ```


  実行結果　[](変更しない)


  ```
  dv1394src: Factory Details:
  dv1394src:  Rank              none (0)
  dv1394src:  Long - name       Firewire (1394) DV video source
  dv1394srv:  Klass             Source/Video
  dv1394src:  Description       Source for DV video data from firewire port
  ~~~~以下省略~~~~
  ```
- **-b, --print-blacklist** 
    
  ブラックリストを表示する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-inspect-1.0 -b
  ```


  実行結果　[](変更しない)


  ```
  Blacklisted files:

  Total count: 0 blacklisted files
  ```
- **--plugin**
  
  プラグインを表示する。

  実行例 [](変更しない)
  
  ```
  $ gst-inspect-1.0 --plugin
  ```


  実行結果　[](変更しない)


  ```
  dv1394src: Factory Details:
  dv1394src:  Rank              none (0)
  dv1394src:  Long - name       Firewire (1394) DV video source
  dv1394srv:  Klass             Source/Video
  dv1394src:  Description       Source for DV video data from firewire port
  ~~~~以下省略~~~~
  ```
- **--print-plugin-auto-install-info** 
    
  指定されたプラグインが提供する機能の機械が可読なリストを表示します。外部の自動プラグインインストールメカニズムと連携する際に役立つ。
  
  実行例　[](変更しない)
  
  ```
  $ gst-inspect-1.0 --print-plugin-auto-install-info
  ```


  実行結果　[](変更しない)


  ```
  element-dv1394src
  urisource-dv
  element-hdv1394src
  urisource-hdv
  element-aasink
  element-aatv
  element-adder
  ~~~~以下省略~~~~
  ```
- **-t, --types**
  
  指定した文字列が含まれるプラグインや要素のみを表示する。

  実行例 [](変更しない)
  
  ```
  $ gst-inspect-1.0　-t bin
  ```


  実行結果　[](変更しない)


  ```
  camerabin:  camerabin: Camera Bin
  cluttergst3:  clutterautovideosink: Generic bin
  encoding:  encodebin: Encoder Bin
  encoding:  encodebin2: Encoder Bin
  multifile:  splitmuxsink: Split Muxing Bin
  multifile:  splitmuxsrc: Split File Demuxing Bin
  ~~~~以下省略~~~~
  ```
- **-u, --uri-handlers** 
    
  サポートされているURIスキームとそれを実装する要素を表示する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-inspect-1.0 -u
  ```


  実行結果　[](変更しない)


  ```
  dv1394src (read, rank 0): dv
  hdv1394src (rad, rank 0): hdv
  appsink (write, rank 0): appsink
  appsrc (read, rank 0): appsrc
  cdparanoasrc (read, rank 128): cdda
  ~~~~以下省略~~~~
  ```
- **--no-colors**
  
  結果を表示する際に単色で表示する。（デフォルトは要素ごとに色分け）

  実行例 [](変更しない)
  
  ```
  $ gst-inspect-1.0 --no-colors
  ```


  実行結果　[](変更しない)


  ```
  1394: dv1394src: Firewire (1394) DV video source
  1394: hdv1394src: Firewire (1394) HDV video source
  aasink: aasink: ASCII art video sink
  aasink: aatv: aaTV effect
  adder: adder: Adder
  alaw: alawdec: A Law audio decoder
  alaw: alawenc: A Law audio encoder
  alpha: alpha: Alpha filter
  alphacolor: alphacolor: Alphacolor filter
  ~~~~以下省略~~~~
  ```

- **-C, --color**
  
  表示される要素ごとに色をつけて表示する。

  実行例 [](変更しない)
  
  ```
  $ gst-inspect-1.0 -C
  ```


  実行結果　[](変更しない)

  ```
  1394: dv1394src: Firewire (1394) DV video source
  1394: hdv1394src: Firewire (1394) HDV video source
  aasink: aasink: ASCII art video sink
  aasink: aatv: aaTV effect
  adder: adder: Adder
  alaw: alawdec: A Law audio decoder
  alaw: alawenc: A Law audio encoder
  alpha: alpha: Alpha filter
  alphacolor: alphacolor: Alphacolor filter
  ~~~~以下省略~~~~
  ```
