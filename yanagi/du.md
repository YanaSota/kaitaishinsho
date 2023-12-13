[](ファイル名はコマンド名.md)
# du
ディスク上のディレクトリやファイルのディスク使用量を表示するために使用する
システム管理者や開発者など、ディスク使用量の監視やトラブルシューティングを行うため高頻度で使用される
一般ユーザではディスク容量が不足している場合や特定のディレクトリやファイルのサイズを確認したい場合に使用されることがある

ディスク使用量を表示するため、大規模なディレクトリやファイルの場合では実行に時間がかかることがあり、正確な計算には適切なオプションが必要である

シンボリックリンクとはファイルシステムにおいて、特定のファイルシステムやディレクトリへの参照を作成するために使用される特殊なファイル
ファイルやディレクトリのパス名を指定し、そのパス名に対する参照を提供する

  実行例 [](変更しない)
  
  ```
  du file.txt
  ```


  実行結果　[](変更しない)


  ```
  4      file.txt
  ```


オプション一覧


- **-0**
  
  各出力を改行ではなくNULLで終了させる

  実行例 [](変更しない)
  
  ```
  du -0
  ```


  実行結果　[](変更しない)


  ```
  4  ./.cache/tracker3/files/errors14244  . /.cache/mesa_shader_cache/388   . /. cacache/1e8   he/mesa_shader_cache/2512   ache/ce8  ache/6312   ·/ピクチャ4   he/tracker3/files14248   he/mesa_shader_cache/cf8  ache/1a8   he/mesa_shader_cache/138. /. cache/mesa_shader_cache/658 . /.cache/mesa_shader_cache/e28./. cac . /.cache/mesa_shader_cache/cc8 ./.cache/mesa_shader_  . cache/mesa_shader_cache/998 ./. cache/mesa_shader_cache/448 ./.cache/mesa_shader_cache/068  he/mesa_shader_cache/2e12 . /.cache/mesa_shader_cache/758   ·/ビデオ4  . /. cache/tracker38  . /.cache/mesa_shader_cache/a48 . /.cache/mesa_shader_c . /. cache/mesa_shader_cache/848 . /.cache/mesa_shader_cache/3f8  . /. cache/mesa_shader_cache/2912 . /. cache/mesa_shader_c  . /.cache/mesa_shader_cache/8d12 . /.cache/mesa_shader_c  . /. cache/mesa_shader_cache/d68 ./.cache/mesa_shader_cache/708   ./. cac   . /. cache/mesa_shader_cache/268 . /.cache/mesa_shader_c   ./.cache/mesa_shader_cache/3c8 ./.cac
  ```
- **-a** 
    
  ディレクトリだけでなく、すべてのファイルのカウントを表示する
  
  実行例　[](変更しない)
  
  ```
  du -a
  ```


  実行結果　[](変更しない)


  ```
  4     . /.config/mozc/ibus_config. textproto
  424   ./.config/mozc
  0     . /.config/ibus-mozc-gnome-initial-setup-done
  4     . /.config/evolution/sources/system-proxy. source
  8     . /.config/evolution/sources
  12    . /.config/evolution
  580   ./. config
  97576 .
  ```
- **--apparent-size** 
    
  ディスク使用量ではなく、表面のサイズを表示する
  表面のサイズは通常は小さいが、ファイルのホール、内部の断片化、関節ブロックのために大きくなることがある
  
  実行例　[](変更しない)
  
  ```
  du --apparent-size
  ```


  実行結果　[](変更しない)


  ```
  73     . /.config/pulse
  4      . /.config/update-notifier
  397    . /.config/mozc
  6      . /.config/evolution/sources
  10     . /.config/evolution
  515    . /.config
  97162  .
  ```
- **-B** 
    
  SIZEの倍率として表示する
  "-BM"は1,048,576バイト単位でサイズを表示する
  
  実行例　[](変更しない)
  
  ```
  du -BM /home/ubuntu/.config
  ```


  実行結果　[](変更しない)

  ```
  1M  /home/ubuntu/.config/gtk-3.0
  1M  /home/ubuntu/.config/goa-1.0
  1M  /home/ubuntu/.config/ibus/bus
  1M  /home/ubuntu/.config/ibus
  1M  /home/ubuntu/.config/nautilus
  1M  /home/ubuntu/.config/dconf
  1M  /home/ubuntu/.config/pulse
  ```
- **-c** 
    
  総合計量を表示する
  
  実行例　[](変更しない)
  
  ```
  du -c file.txt
  ```


  実行結果　[](変更しない)


  ```
  4     file.txt
  4     合計
  ```
- **-D** 
    
  コマンドラインで指定されたシンボリックのみをたどる
  
  実行例　[](変更しない)
  
  ```
  du -D /home/ubuntu/.config/evolution/
  ```


  実行結果　[](変更しない)


  ```
  8     /home/ubuntu/.config/evolution/sources
  12    /home/ubuntu/.config/evolution/
  ```
- **-d** 
    
  コマンド実行場所から,N階層以内のディレクトリの合計を表示する
  
  実行例　[](変更しない)
  
  ```
  du -d 4 /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  8　　　/home/ubuntu/.config/gtk-3.0
  4　　　/home/ubuntu/.config/goa-1.0
  12　　 /home/ubuntu/.config/ibus/bus
  16     /home/ubuntu/.config/ibus
  4      /home/ubuntu/.config/nautilus
  8      /home/ubuntu/.config/dconf
  84     /home/ubuntu/.config/pulse
  4      /home/ubuntu/.config/update-notifier
  424    /home/ubuntu/.config/mozc
  8      /home/ubuntu/.config/evolution/sources
  12     /home/ubuntu/.config/evolution
  580    /home/ubuntu/.config
  ```
- **-H** 
    
  シンボリックを解決し、リンク先のファイルやディレクトリを操作するオプションと同じもの
  
  実行例　[](変更しない)
  
  ```
  du -H /home/ubuntu/file.txt
  ```


  実行結果　[](変更しない)


  ```
  4      /home/ubuntu/file.txt
  ```
- **-h** 
    
  人に読みやすい形でサイズを表示する
  
  実行例　[](変更しない)
  
  ```
  du -h /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  4.0K     /home/ubuntu/.config/nautilus
  8.0K     /home/ubuntu/.config/dconf
  84K      /home/ubuntu/.config/pulse
  4.0K     /home/ubuntu/.config/update-notifier
  424K     /home/ubuntu/. config/mozc
  8.0K     /home/ubuntu/.config/evolution/sources
  12K      /home/ubuntu/.config/evolution
  580K     /home/ubuntu/.config
  ```
- **-k** 
    
  ブロックサイズを1K単位とした時と同じ
  
  実行例　[](変更しない)
  
  ```
  du -k /home/ubuntu/
  ```


  実行結果　[](変更しない)


  ```
  4.0K     /home/ubuntu/.config/nautilus
  8.0K     /home/ubuntu/.config/dconf
  84K      /home/ubuntu/.config/pulse
  4.0K     /home/ubuntu/.config/update-notifier
  424K     /home/ubuntu/. config/mozc
  8.0K     /home/ubuntu/.config/evolution/sources
  12K      /home/ubuntu/.config/evolution
  580K     /home/ubuntu/.config
  ```
- **-L** 
    
  全てのシンボリックリンクをたどらない
  
  実行例　[](変更しない)
  
  ```
  du -L /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  4       /home/ubuntu/.config/nautilus
  8       /home/ubuntu/.config/dconf
  84      /home/ubuntu/.config/pulse
  4       /home/ubuntu/.config/update-notifier
  424     /home/ubuntu/. config/mozc
  8       /home/ubuntu/.config/evolution/sources
  12      /home/ubuntu/.config/evolution
  580     /home/ubuntu/.config
  ```
- **-l** 
    
  ハードリンクされた場合その個数分サイズを数える
  
  実行例　[](変更しない)
  
  ```
  du -l /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  4       /home/ubuntu/.config/nautilus
  8       /home/ubuntu/.config/dconf
  84      /home/ubuntu/.config/pulse
  4       /home/ubuntu/.config/update-notifier
  424     /home/ubuntu/. config/mozc
  8       /home/ubuntu/.config/evolution/sources
  12      /home/ubuntu/.config/evolution
  580     /home/ubuntu/.config
  ```
- **-m** 
    
  ブロックサイズを1M単位とした時と同じ
  
  実行例　[](変更しない)
  
  ```
  du -m /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  1       /home/ubuntu/.config/nautilus
  1       /home/ubuntu/.config/dconf
  1       /home/ubuntu/.config/pulse
  1       /home/ubuntu/.config/update-notifier
  1       /home/ubuntu/. config/mozc
  1       /home/ubuntu/.config/evolution/sources
  1       /home/ubuntu/.config/evolution
  1       /home/ubuntu/.config
  ```
- **-P** 
    
  シンボリックリンクをたどらない
  
  実行例　[](変更しない)
  
  ```
  du -P /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  4       /home/ubuntu/.config/nautilus
  8       /home/ubuntu/.config/dconf
  84      /home/ubuntu/.config/pulse
  4       /home/ubuntu/.config/update-notifier
  424     /home/ubuntu/.config/mozc
  8       /home/ubuntu/.config/evolution/sources
  12      /home/ubuntu/.config/evolution
  580     /home/ubuntu/.config
  ```
- **-S** 
    
  子ディレクトリのサイズを含めない
  
  実行例　[](変更しない)
  
  ```
  du -S /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  4       /home/ubuntu/.config/nautilus
  8       /home/ubuntu/.config/dconf
  84      /home/ubuntu/.config/pulse
  4       /home/ubuntu/.config/update-notifier
  424     /home/ubuntu/. config/mozc
  8       /home/ubuntu/.config/evolution/sources
  4       /home/ubuntu/.config/evolution
  16      /home/ubuntu/.config
  ```
- **-s** 
    
  各引数の合計容量のみを表示する
  
  実行例　[](変更しない)
  
  ```
  du -s /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
  580   /home/ubuntu/.config
  ```
- **-t** 
    
  SIZEを指定して、SIZEが正の場合はSIZEより小さいエントリを無視する
  SIZEが負の場合はSIZEより大きなエントリを無視する
  
  実行例　[](変更しない)
  
  ```
  du -t 10M
  ```


  実行結果　[](変更しない)


  ```
  10676  . /snap/firefox/common/.mozilla/firefox/3q93a0v8.default/storage/permanent
  10820  . /snap/firefox/common/.mozilla/firefox/3q93a0v8.default/storage
  28100  ./snap/firefox/common/.mozilla/firefox/3q93a0v8.default
  28124  . /snap/firefox/common/.mozilla/firefox
  28132  . /snap/firefox/common/.mozilla
  80288  ./snap/firefox/common
  80372  ./snap/firefox
  80564  . /snap
  97576  .
  ```
- **--time** 
    
  ディレクトリとその子ディレクトリに含まれるすべてのファイルでの最終更新時間を表示する
  "atime","access","use","ctime","status"で更新時間の代わりにその時間を表示できる
  
  実行例　[](変更しない)
  
  ```
  du --time=use file.txt
  ```


  実行結果　[](変更しない)


  ```
  4    2023-12-10 13:37    file.txt
  ```
- **--time-style** 
    
  時間をSTYLEの形式で表示する

  STYLEには"full-iso","long-iso","iso","+FORMAT(dateと同様)"を指定できる
  
  実行例　[](変更しない)
  
  ```
  du --time-style=full-iso file.txt
  ```


  実行結果　[](変更しない)


  ```
  4     file.txt
  ```
- **-X** 
    
  FILE内のいずれかのパターンに一致するファイルを除外する
  
  実行例　[](変更しない)
  
  ```
  du -X file.txt
  ```


  実行結果　[](変更しない)


  ```
  4     ./. config/nautilus
  8     ./. config/dconf
  84    ./. config/pulse
  4     ./. config/update-notifier
  424   ./. config/mozc
  8     ./. config/evolution/sources
  12    ./.config/evolution
  580   ./.config
  97576 .
  ```
- **-x** 
    
  異なるファイルシステム上のディレクトリはスキップする
  
  実行例　[](変更しない)
  
  ```
  du -x /home/ubuntu/.config
  ```


  実行結果　[](変更しない)


  ```
    ```
  4       /home/ubuntu/.config/nautilus
  8       /home/ubuntu/.config/dconf
  84      /home/ubuntu/.config/pulse
  4       /home/ubuntu/.config/update-notifier
  424     /home/ubuntu/.config/mozc
  8       /home/ubuntu/.config/evolution/sources
  12      /home/ubuntu/.config/evolution
  580     /home/ubuntu/.config
  ```