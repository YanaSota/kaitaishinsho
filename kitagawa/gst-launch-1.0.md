[](ファイル名はコマンド名.md)
# gst-launch-1.0
gst → GStreamer  
GStreamerは、マルチメディアデータの処理やストリーミングを行うためのフレームワークであり、様々なメディア関連のタスクに使用される。  
gst-launch-1.0は、コマンドラインからGStreamerパイプラインを簡単に構築および実行するためのコマンド。  
GStreamerでは Shell のパイプ "|" ではなく "!" を用いる。 

  実行例 [](変更しない)
  
  ```
  $ gst-launch-1.0 audiotestsrc ! autoaudiosink
  ```


  実行結果　[](変更しない)

  ```
  パイプラインを一時停止 (PAUSED) にしています...
  Pipeline is PREROLLING ...
  Pipeline is PREROLLED ...
  パイプラインを再生中 (PLAYING) にしています...
  New clock: GstPulseSinkClock
  Redistribute latency...
  ```
  テスト音源の440Hzが出力される。

### オプション一覧




- **-t, --tags**
  
  タグ (メタデータ) を出力する。

  実行例 [](変更しない)
  
  ```
  $ gst-launch-1.0 -t audiotestsrc ! autoaudiosink
  ```


  実行結果　[](変更しない)


  ```
  パイプラインを一時停止 (PAUSED) にしています...
  Pipeline is PREROLLING ...
  FOUND TAG     : found by element "autoaudiosink0-actual-sink-pilse".
            詳細: audiotest wave
  Pipeline is PREROLLED ...
  パイプラインを再生中 (PLAYING) にしています...
  New clock: GstPulseSinkClock
  Redistribute latency...
  ```
- **-c, --toc** 
    
  可能な場合は目次 (章やチャプター) を出力する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-launch-1.0 -c audiotestsrc ! autoaudiosink
  ```


  実行結果　[](変更しない)


  ```
  実行例と同様のため省略
  ```
- **-v, --verbose** 
    
  ステータス情報とプロパティ通知を出力する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-launch-1.0 -v audiotestsrc ! autoaudiosink
  ```


  実行結果　[](変更しない)


  ```
  パイプラインを一時停止 (PAUSED) にしています...
  Pipeline is PREROLLING ...
  /GstPipeline:pipeline0/GstAudioTestSrc:audiotestsrc0.GstPad:src: caps = audio/x-raw, format=(string)S16LE, layout=(string)interleaved, rate=(int)44100, channels=(int)1
  /GstPipeline:pipeline0/GstAutoAudioSink:autoaudiosink0.GstGhostPad:sink.GstProxyPad:proxypad0: caps = audio/x-raw, format=(string)S16LE, layout=(string)interleaved, rate=(int)44100, channels=(int)1
  Redistribute latency...
  ~~~~以下省略~~~~
  ```
- **-q, --quiet** 
    
  出力データの詳細などは表示せず、再生時間のみを表示する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-launch-1.0 -q audiotestsrc ! autoaudiosink
  ```


  実行結果　[](変更しない)


  ```
  0:00:00.0 / 99:99:99.
  ```
- **-m, --messages** 
    
  パイプラインのバスに提示される出力メッセージを表示する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-launch-1.0 -q audiotestsrc ! autoaudiosink
  ```


  実行結果　[](変更しない)


  ```
  パイプラインを一時停止 (PAUSED) にしています...
  Pipeline is PREROLLING ...
  Got message #9 from element "autoaudiosink0-actual-sink-pulse" (state-changed): GstMessageStateChanged, old-state=(GstState)null, new-state=(GstState)ready, pending-state=(GstState)void-pending;
  Got message #10 from element "autoaudiosink0" (state-changed): GstMessageStateChanged, old-state=(GstState)null, new-state=(GstState)ready, pending-state=(GstState)void-pending;
  ~~~~以下省略~~~~
  ```