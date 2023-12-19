[](ファイル名はコマンド名.md)
# dumpe2fs
dump ext2/ext3/ext4 file system infomation

ext2/ext3/ext4ファイルシステムのスーパーブロックの情報とブロックグループディスクリプタの内容を出力する

スーパーブロックにはファイルシステムの管理用情報が格納されている

オプションなしの実行は不可

### オプション一覧

- **-b**
  
  ファイルシステム内で不良としてマークされたブロックを表示する

  実行例 [](変更しない)
  
  ```
  sudo dumpe2fs -b /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  dumpe2fs 1.46.5 (30-Dec-2021)
  dumpe2fs: Bad magic number in super-block while trying to open /dev/sda1
  Couldn't find valid filesystem superblock.
  ```
- **-o** 
    
  ファイルシステムを調査する際に、ブロックサイズのバイト単位でブロックを使用する

  非常に損傷したファイルシステムの残留物を調査するファイルシステムの専門家以外は必要ないコマンド
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -o superblock=10 /dev/sda2
  ```


  実行結果　[](変更しない)


  ```
  dumpe2fs 1.46.5 (30-Dec-2021)
  dumpe2fs: Bad magic number in super-block while trying to open /dev/sda2
  Couldn't find valid filesystem superblock.
  /dev/sda2 contains a vfat file system
  ```
- **-f** 
    
  dumpe2fsに一部のファイルシステム機能フラグが理解できない可能性がある場合でもファイルシステムを表示するように強制する
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -f -o blocksize=5 /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  dumpe2fs 1.46.5 (30-Dec-2021)
  dumpe2fs: Bad magic number in super-block while trying to open /dev/sda1
  Couldn't find valid filesystem superblock.
  ```
- **-g** 
    
  グループディスクリプタ情報を、機械可読なコロン区切りの値形式で表示する
  グループ番号;グループ内の最初のブロック番号;スーパーブロックの位置;グループディスクリプタが使用するブロックの範囲;ブロックビットマップの位置;iノードビットマップの位置;およびiノードテーブルが使用するブロック
  の形である
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -g -o blocksize=5 /dev/sda3
  ```


  実行結果　[](変更しない)


  ```
  dumpe2fs 1.46.5 (30-Dec-2021)
  dumpe2fs: Filesystem has unexpected block size while trying to open /dev/sda3
  Couldn't find valid filesystem superblock.
  ```
- **-h** 
    
  ブロックグループディスクリプタの詳細情報を表示せずに、スーパーブロック情報のみを表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -h -o blocksize=5 /dev/sda3
  ```


  実行結果　[](変更しない)


  ```
  実行結果
  ```
- **-i** 
    
  e2imageが作成したイメージファイルからファイルシステムデータを表示し、パス名としてデバイスを使用する
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -i -o superblock=3 /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  dempe2fs 1.46.5(30-Dec-2021)
  Couldn't find valid filesystem superblock.
  dumpe2fs: Wrong magic number for Ext2 Image Header while trying to open /dev/sda1 
  ```
- **-m** 
    
  もしファイルシステムでmmp機能が有効になっている場合、デバイスが他のノードで使用されているかどうかを確認する
  
  -iオプションと併用する場合、MMPブロックの情報のみが表示される
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -m -i -o superblock=3 /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  dempe2fs 1.46.5(30-Dec-2021)
  Couldn't find valid filesystem superblock.
  dumpe2fs: Bad magic number in super-block while trying to open /dev/sda1
  ```
- **-x** 
    
  ブロックの詳細なグループ情報を16進数の形式で表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dumpe2fs -x -o superblock=3 /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  dumpe2fs 1.46.5 (30-Dec-2021)
  dumpe2fs: Bad magic number in super-block while trying to open /dev/sda1
  Couldn't find valid filesystem superblock.
  ```