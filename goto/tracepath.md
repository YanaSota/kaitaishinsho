
[](tracepath.md)
# tracepath
宛先までのネットワークパスをトレースし、そのパスに沿ったMTUを発見する。MTUはネットワークで一回に送信できる最大のデータサイズのこと。
tracerouteに似ているが、sudo権限を必要とせず、複雑なオプションも存在しない。
出力はの形式は以下の通りである。
__(ホップ番号):ホップのIPアドレス------任意のホップまでの応答時間__
######※ホップとは送信元と送信先の間の経路の部分を指す用語のことである。
<!-- tracepath6は、traceroute6の代替であり、Linuxエラー・キューの典型的な応用例である。
商用のIPルーターはICMPエラーメッセージに十分な情報を返さないためtracepath4は現在状況としては良くない。それらがアップデートされれば、状況は変わるが今のところVan Jacobsonのトリックを使い、一連のUDPポートを掃引してトレース履歴を維持している。 -->

実行例 [](変更しない)

```
tracepath example.com
```

実行結果 [](変更しない)

```
 1?: [LOCALHOST]                      pmtu 1500 (今回のMTUは1500byte)
 1:  _gateway                                              0.865ms
 1:  _gateway                                              0.823ms
 2:  _gateway                                              0.836ms pmtu 1454
 2:  118.23.89.226                                         3.505ms
 3:  118.23.89.13                                          5.038ms
 4:  221.184.5.201                                         5.474ms
 5:  125.170.97.97                                        21.937ms
 6:  125.170.97.130                                       25.727ms
 7:  122.28.104.118                                       23.620ms
 8:  210.173.176.198                                      24.569ms asymm  9
 9:  150.222.90.123                                       24.075ms asymm 13
10:  no reply
11:  54.239.52.97                                         41.056ms
12:  150.222.90.61                                        24.866ms asymm 10
13:  52.93.66.34                                          28.730ms asymm 10
14:  52.93.66.140                                         25.184ms asymm 10
15:  no reply
~~(省略)~~
     Too many hops: pmtu 1454
     Resume: pmtu 1454
```
### オプション一覧
    
- **-4**

  IPv4を使用する。

  実行例 [](変更しない)

  ```
  tracepath example.com -4
  ```

  実行結果 [](変更しない)

  ```
   1?: [LOCALHOST]                      pmtu 1500
   1:  _gateway                                              0.869ms
   1:  _gateway                                              0.910ms
   2:  _gateway                                              0.824ms pmtu 1454
   2:  118.23.89.226                                         3.387ms
   3:  118.23.89.9                                           5.079ms
   4:  221.184.5.193                                         4.727ms
   5:  125.170.97.97                                        20.378ms
   6:  125.170.97.130                                       26.821ms
   7:  ae-8.a03.tokyjp05.jp.bb.gin.ntt.net                  24.022ms
   8:  ae-5.r32.tokyjp05.jp.bb.gin.ntt.net                  34.216ms asymm  9
   9:  ae-4.r25.lsanca07.us.bb.gin.ntt.net                 127.998ms asymm 10
  10:  ae-1.a04.lsanca07.us.bb.gin.ntt.net                 136.814ms asymm 16
  11:  ae-0.r25.snjsca04.us.bb.gin.ntt.net                 130.185ms asymm  9
  12:  po-65.core1.sac.edgecastcdn.net                     130.509ms asymm 16
  13:  no reply
  14:  ae-0.edgecast-networks.snjsca04.us.bb.gin.ntt.net   151.358ms asymm 15
  15:  no reply
     ~~(省略)~~
        Too many hops: pmtu 1454
        Resume: pmtu 1454
  ```

- **-6**

  IPv6を使用する。そのためIPアドレスの形式が128bitの16進数で表される。

  実行例 [](変更しない)

  ```
  tracepath example.com -6
  ```

  実行結果 [](変更しない)

  ```
  1?: [LOCALHOST]
  1: 2001:db8:85a3::1 0.109ms
  2: 2001:db8:85a3::2 0.208ms
  3: 2001:db8:85a3::3 0.312ms
  4: 2001:db8:85a3::4 0.415ms
  5: 2001:4860::1:0:1234 10.123ms
  6: 2001:4860:0:1::abcd 20.345ms
  7: 2001:4860:0:2::efgh 30.678ms
  8: 2001:4860:0:3::ijkl 40.987ms
  9: 2001:4860:0:4::mnop 50.876ms
  10: 2001:4860:0:5::qrst 60.789ms
  11: 2001:4860:0:6::uvwxyz 70.987ms
  ~~(省略)~~
  ```

- **-b**

  名前とIPの両方を表示する。

  実行例 [](変更しない)

  ```
  tracepath example.com -b
  ```

  実行結果 [](変更しない)

  ```
   1?: [LOCALHOST]                      pmtu 1454
   1:  _gateway (10.252.0.1)                                 0.831ms
   1:  _gateway (10.252.0.1)                                 0.781ms
   2:  118.23.89.226 (118.23.89.226)                         3.152ms
   3:  118.23.89.9 (118.23.89.9)                             5.045ms
   4:  221.184.5.193 (221.184.5.193)                         6.528ms
   5:  125.170.97.97 (125.170.97.97)                        20.463ms
   6:  125.170.97.130 (125.170.97.130)                      23.322ms
   7:  ae-7.a04.tokyjp05.jp.bb.gin.ntt.net (120.88.53.25)   21.848ms
   8:  ae-6.r32.tokyjp05.jp.bb.gin.ntt.net (129.250.5.109)  24.183ms asymm  9
   ~~(省略)~~
     Too many hops: pmtu 1454
     Resume: pmtu 1454
  ```

- **-l <length>**

  初期パケット長をpklen(packet length)に指定する。指定しない場合デフォルトは65536である。tracepath6は128000となっている。

  実行例 [](変更しない)

  ```
  tracepath example.com -l 29
  ```

  実行結果 [](変更しない)

  ```
   1:  _gateway                                              0.497ms
   2:  118.23.89.226                                         3.176ms
   3:  118.23.89.9                                           4.186ms
   4:  221.184.5.193                                         3.938ms
   5:  125.170.97.97                                        21.849ms (This broken router returned corrupted payload)
   6:  125.170.97.130                                       24.840ms
   7:  ae-8.a03.tokyjp05.jp.bb.gin.ntt.net                  23.500ms
   8:  ae-5.r32.tokyjp05.jp.bb.gin.ntt.net                  34.172ms asymm  9
  4194313:  ae-1.r33.tokyjp05.jp.bb.gin.ntt.net                 -202710115721828681.740ms asymm  8
  4194314:  ae-4.r25.lsanca07.us.bb.gin.ntt.net                 -202710115721828533.614ms asymm  9
  11:  ce-3-2-1.a04.lsanca07.us.ce.gin.ntt.net             131.014ms asymm 12
  ~~(省略)~~
    Too many hops: pmtu 29
    Resume: pmtu 29
  ```

- **-m <hops>**

  最大ホップ数を指定する。

  実行例 [](変更しない)

  ```
  tracepath example.com -m 10
  ```

  実行結果 [](変更しない)

  ```
   1?: [LOCALHOST]                      pmtu 1454
   1:  _gateway                                              0.794ms
   1:  _gateway                                              0.866ms
   2:  118.23.89.226                                         3.374ms
   3:  118.23.89.9                                           4.969ms
   4:  221.184.5.193                                         5.626ms
   5:  125.170.97.97                                        21.899ms
       Too many hops: pmtu 1454
       Resume: pmtu 1454
  ```

- **-n**

  出力においてアドレス名を使用する。ホスト名では記載されない。

  実行例 [](変更しない)

  ```
  tracepath example.com -n
  ```

  実行結果 [](変更しない)

  ```
   1?: [LOCALHOST]                      pmtu 1454
   1:  10.252.0.1                                            0.805ms
   1:  10.252.0.1                                            0.823ms
   2:  118.23.89.226                                         3.159ms
   3:  118.23.89.9                                           5.143ms
   4:  221.184.5.193                                         4.214ms
   5:  125.170.97.97                                        21.240ms
    ~~(省略)~~
    Too many hops: pmtu 1454
    Resume: pmtu 1454
  ```

- **-p <port>**

  特定のポート番号を使用して経路確認を行う。

  実行例 [](変更しない)

  ```
  tracepath example.com -p 25565 (因みにこのポートはマイクラのjava版の鯖でよく使われる場所)
  ```

  実行結果 [](変更しない)

  ```
   1?: [LOCALHOST]                      pmtu 1454
   1:  _gateway                                              0.867ms
   1:  _gateway                                              0.848ms
   2:  118.23.89.226                                         3.271ms
   3:  118.23.89.9                                           4.940ms
   4:  221.184.5.193                                         9.435ms
   5:  125.170.97.97                                        23.881ms
   ~~(省略)~~
    Too many hops: pmtu 1454
    Resume: pmtu 1454
  ```
