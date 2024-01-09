[](ファイル名はコマンド名.md)
# e2freefrag
ext2/3/4ファイルシステムの空き領域の断片化を報告するために使われる。

ext2~ext4ファイルシステムとはLinuxで標準的に利用されるファイルシステムの一つで、ext4がよく利用され、オペレーティングシステムをサポートしている。

ブロックビットマップ情報をスキャンして、 どれだけの空きブロックが連続し、整列した空き領域として存在するかを調べる。

ブロックビットマップ情報
ブロック毎に空き/使用中を管理している情報

  実行例 [](変更しない)
  
  ```
  sudo e2freefrag
  ```


  実行結果　[](変更しない)


  ```
  Device: /dev/sda1
  Blocksize: 4096 bytes
  Total blocks: 256
  Free blocks: 238 (93.0%)
  
  
  Min. free extent: 12 KB
  Max. free extent: 856 KB
  Avg. free extent: 236 KB
  Num. free extent: 4
  
  
  HISTOGRAM OF FREE EXTENT SIZES:
  Extent Size Range : Free extents  Free Blocks Percent
      8K ...  16K-  :            1            3   1.26%
     16K ...  32K-  :            1            6   2.52%
     32K ...  64K-  :            1           15   6.30%
    512K ...1024K-  :            1          214  89.92%
  ```

### オプション一覧


- **-c**
  
  チャンクサイズが指定された場合、e2freefragはチャンクサイズの空きチャンクの数をキロバイト単位で表示する

  チャンクとはデータベースサーバのデータ格納専用の物理ディスクの最大単位

  各チャンクの最大サイズは4TBである

  実行例 [](変更しない)
  
  ```
  sudo e2freefrag -c 8 /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  Device: /dev/sda1
  Blocksize: 4096 bytes
  Total blocks: 256
  Free blocks: 238 (93.0%)


  Chunksize: 8192 bytes(2 blocks)
  Total chunks: 129
  Free chunk: 118 (91.5%)
  
  
  Min. free extent: 12 KB
  Max. free extent: 856 KB
  Avg. free extent: 236 KB
  Num. free extent: 4
  
  
  HISTOGRAM OF FREE EXTENT SIZES:
  Extent Size Range : Free extents  Free Blocks Percent
      8K ...  16K-  :            1            3   1.26%
     16K ...  32K-  :            1            6   2.52%
     32K ...  64K-  :            1           15   6.30%
    512K ...1024K-  :            1          214  89.92%
  ```

