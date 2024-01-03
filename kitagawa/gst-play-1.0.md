[](ファイル名はコマンド名.md)
# gst-play-1.0 
gst → GStreamer  
GStreamerは、マルチメディアデータの処理やストリーミングを行うためのフレームワークであり、様々なメディア関連のタスクに使用される。　
gst-play-1.0 を使用すると、コマンドラインから簡単にメディアファイルを再生することができる。

  実行例 [](変更しない)
  
  ```
  $ gst-play-1.0 music.mp3
  ```


  実行結果　[](変更しない)


  ```
  Press 'k' to see a list of keyboard shortcuts.
  Now playing /home/user/music.mp3
  Redistribute latency...
  Redistribute latency...

  Interactive mode - keyboard controls:

    space    : pause/unpause
    q or ESC : quit 
    > or n   : play next
    < or b   : play previous
    →        : seek forward
    ←        : seek backward
    ↑        : volume up
    ↓        : volume down
    m        : toggle audio mute on/off
    +        : increase playback rate
    -        : decrease playback rate
    d        : change playback direction
    t        : enable/disable trick modes
    a        : change audio track
    v        : change video track
    s        : change subtitle track
    0        : seek to beginning
    k        : show keyboard shortcuts
  ```

### オプション一覧




- **-v, --verbose**
  
  ステータス情報とプロパティ通知を出力する。

  実行例 [](変更しない)
  
  ```
  $ gst-play-1.0 -v music.mp3
  ```


  実行結果　[](変更しない)


  ```
  Press 'k' to see a list of keyboard shortcuts.
  Now playing /home/user/music.mp3
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: ring-buffer-max-size = 0
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: buffer-size = -1
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: buffer-duration = -1
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: force-sw-decoders = false
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: use-buffering = false
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: download = false
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: uri = file:///home/user/music.mp3
  /GstPlayBin:playbin/GstURIDecodeBin:uridecodebin0: connection-speed = 0
  ~~~~以下省略~~~~
  ```

- **--audiosink=\<SOMESINK>** 
- 
  autoaudiosinkの代わりに指定したSOMESINKをオーディオ出力として使用する。  
  - 具体的なオーディオ出力の例
    - autoaudiosink: システムのデフォルトのオーディオ出力
    - alsasink: ALSA (Advanced Linux Sound Architecture) を使用したオーディオ出力
    - pulsesink: PulseAudio を使用したオーディオ出力
    - osssink: OSS (Open Sound System) を使用したオーディオ出力
    - openslessink: OpenSL ES を使用したオーディオ出力
  
  実行例　[](変更しない)
  
  ```
  $ gst-play-1.0 --audiosink=alsasink music.mp3
  ```


  実行結果　[](変更しない)


  ```
  Press 'k' to see a list of keyboard shortcuts.
  Now playing /home/user/music.mp3
  Redistribute latency...
  Redistribute latency...
  ```

- **--volume=\<VOLUME>** 
    
  初期再生音量を指定する。  
  1.0がデフォルト。
  
  実行例　[](変更しない)
  
  ```
  $ gst-play-1.0 --volume=0.7 music.mp3
  ```


  実行結果　[](変更しない)


  ```
  Volume: 70%
  Press 'k' to see a list of keyboard shortcuts.
  Now playing /home/user/music.mp3
  Redistribute latency...
  Redistribute latency...
  ```

- **--shuffle**
  
  プレイリストからランダムに並び替えて再生する。

  実行例 [](変更しない)
  
  ```
  $ gst-play-1.0 --shuffle music.mp3
  ```


  実行結果　[](変更しない)


  ```
  最初の実行例と同様のため省略
  ```
- **--no-interactive** 
    
  ターミナルでのキーボード操作による制御を無効にする。
  
  実行例　[](変更しない)
  
  ```
  $ gst-play-1.0 --no-interactive music.mp3
  ```


  実行結果　[](変更しない)


  ```
  Now playing /home/user/music.mp3
  Redistribute latency...
  Redistribute latency...
  ```

- **--gapless**
  
  メディアファイル間の無音部分などを無くして、連続して再生する。  
  このオプションを指定することで、異なるメディアファイルを連続して再生する際に、中断や無音の時間を最小限に抑えることができる。


  実行例 [](変更しない)
  
  ```
  $ gst-play-1.0 --gapless music1.mp3 music2.mp3
  ```


  実行結果　[](変更しない)


  ```
  実行例と同様のため省略
  ```
  1つ目の再生が終了後2つ目の再生が始まる

