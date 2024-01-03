[](ファイル名はコマンド名.md)
# gst-discoverer-1.0
gst → GStreamer  
GStreamerは、マルチメディアデータの処理やストリーミングを行うためのフレームワークであり、様々なメディア関連のタスクに使用される。  
指定したファイルやURIに関するメタデータやプロパティ、ストリームの構造などを取得する。

  実行例 [](変更しない)
  
  ```
  $ gst-discoverer-1.0 video.mp4
  ```


  実行結果　[](変更しない)


  ```
  Analyzing file:///home/user/video/video.mp4
  Done discovering file:file:///home/user/video/video.mp4
  Missing plugins
   (gstreamer|1.0|gst-discoverer-1.0|H.264 (Main Profile) デコーダー|decoder-video/x=h264, level=(string)3.1, profile=(string)main)
   (gstreamer|1.0|gst-discoverer-1.0|MPEG-4 AAC デコーダー|decoder-audio/mpeg, mpegversion=(int)4, level=(string)2, base-profile=(string)lc, profile=(string)lc)
  ```

### オプション一覧




- **-v、--verbose**
  
  入手可能な情報を全て出力する。

  実行例 [](変更しない)
  
  ```
  $ gst-discoverer-1.0 -v video.mp4
  ```


  実行結果　[](変更しない)


  ```
  実行例と同様のため省略
  ```
- **-t, --timeout=\<T>** 
    
  タイムアウトを秒単位で指定する。 (デフォルトは10 秒)
  実行後指定した秒数でタイムアウトする。
  
  実行例　[](変更しない)
  
  ```
  $ gst-discoverer-1.0 -t 20 video.mp4
  ```


  実行結果　[](変更しない)


  ```
  実行例と同様のため省略
  ```
  

- **-c, --toc**
  
  可能な場合は目次 (章やチャプター) を出力する。

  実行例 [](変更しない)
  
  ```
  $ gst-discoverer-1.0 -c video.mp4
  ```


  実行結果　[](変更しない)


  ```
  実行例と同様のため省略
  ```
- **-a, --async** 
    
  非同期コードパスを使用する。
  プログラムが非同期的に動作するようになる。
  
  実行例　[](変更しない)
  
  ```
  $ gst-discoverer-1.0 -a video.mp4
  ```


  実行結果　[](変更しない)


  ```
  実行例と同様のため省略
  ```