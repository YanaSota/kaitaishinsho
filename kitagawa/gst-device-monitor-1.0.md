[](ファイル名はコマンド名.md)
# gst-device-monitor-1.0
gst → GStreamer  
GStreamerは、マルチメディアデータの処理やストリーミングを行うためのフレームワークであり、様々なメディア関連のタスクに使用される。  
gst-device-monitor-1.0 は、GStreamer のデバイス監視機能を利用するためのコマンド。

  実行例 [](変更しない)
  
  ```
  $ gst-device-monitor-1.0
  ```


  実行結果　[](変更しない)


  ```
  Probing devices...

  Device found

      name  : Monitor of 内部オーディオ　アナログステレオ
      class : Audio/Source
      caps  : audio/x-raw, format={ (string)S16LE, (string)S16BE, (string)F32LE, (string)F32BE, (string)S32LE, (string)S32BE, (string)S24LE, (string)S24BE, (string)S24_32LE, (string)S124_32BE, (string)UB }, layout=interleaved, rate=[ 1, 384000 ], channels=[ 1, 32 ]

          audio/x-alaw, rate=[ 1, 384000 ], channels=[ 1, 32 ]
          audio/x-mulaw, rate=[ 1, 384000 ], channels=[ 1, 32 ]
      properties:
          device.description = "Monitor\ of\ \345\206\205\351\203\250\343\202\252\343\203\274\343\203\207\343\202\243\343\202\252\ \343\202\242\343\203\212\343\203\255\343\202\260\343\202\271\343\203\205\343\2-3\254\343\202\252"
          device/class = monitor
          alsa.card = 0
          alse.card_name = "Intel\ 82801AA-ICH"
  ~~~~以下省略~~~~
  ```

### オプション一覧




- **-f, --follow**
  
  デバイス・リストを表示した後は終了せず、デバイスの追加と削除を待つ。

  実行例 [](変更しない)
  
  ```
  $ gst-device-monitor-1.0 -f
  ```


  実行結果　[](変更しない)

  ```
  Probing devices...

  Monitoring devices, waiting for devices to be removed or new devices to be added

  ~~~~以下実行例と同様~~~~
  ```
  実行後はデバイスリストを現在のデバイスリストを表示後、待機する。


- **-i, --include-hidden** 
    
  非表示のデバイスを含めて表示する。
  
  実行例　[](変更しない)
  
  ```
  $ gst-device-monitor-1.0 -i
  ```


  実行結果　[](変更しない)

  ```
  実行例と同様のため省略
  ```
