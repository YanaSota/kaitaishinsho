[](ファイル名はコマンド名.md)
# e2scrub
e2scrub は、マウントされた ext[234] ファイルシステムが LVM 論理ボリューム上にある場合、 そのファイルシステムの全てのメタデータのチェックを試みる (修復はしない)。LVM 論理ボリュームのブロックデバイスを渡すこともできる。

このプログラムはボリュームをスナップショットし、スナップショットに対してファイルシステムチェックを実行して、破損エラーを探します。LVMボリュームグループには、スナップショットに割り当てられる未割り当て領域が少なくとも256MiB必要です。e2scrubとudevはdev/diskの下にシンボリックリンクを作成しない。
e2scrub を実行する前にスナップショットを削除するように努めますが、 悲惨な状況では手動でスナップショットを削除する必要がある。

エラーが見つからず、ファイルシステムがマウントされていれば fstrim を呼び出すことができる。
エラーが見つかった場合は、ファイルシステムにエラーがあるものとしてマークされる。ファイルシステムはできるだけ早くオフラインにして e2fsck を実行すべきである。ファイルシステムが修復されない場合、次のマウントの前に e2fsck が実行される。

  実行例 [](変更しない)
  
  ```
  sudo e2scrub /dev/VG_NAME/LV_NAME
  ```


  実行結果　[](変更しない)


  ```
  端末
  Reducing COW size 256.00 MiB down to maximum usable size 16.00 MiB.
  Logical volume "LV_NAME.e2scrub" created.
  e2fsck 1.46.5 (30-Dec-2021)
  Pass 1: Checking i/ - Is, blocks, and sizes
  Pass 2: Checking ディレクトリ structure
  Checking ディレクトリ connectivity
  Pass 4: Checking reference counts
  Pass 5: Checking グループ summary information
  /dev/VG_NAME/LV_NAME.e2scrub: 11/3072 files (9.1% non-contiguous), 1227/3072 blocks
  /dev/VG_NAME/LV_NAME: Scrub succeeded.
  tune2fs 1.46.5 (30-Dec-2021)
  Setting current mount count to 0
  Setting time filesystem last checked to Thu Jan 4 16:29:28 2024
  
  Logical volume "LV_NAME.e2scrub" successfully removed
  ```

### オプション一覧




- **-n**
  
  ファイルシステムをチェックするために e2scrub が実行するコマンドを表示する。
  コマンドは実際には実行されない。
  
  e2scrub は実行されるコマンドを決定するために いくつかのコマンドを実行してシステムに問い合わせる必要があるので、 root 権限で実行する必要がある。

  実行例 [](変更しない)
  
  ```
  sudo e2scrub -n /dev/VG_NAME/LV_NAME
  ```


  実行結果　[](変更しない)


  ```
  Would execute: lvremove -f VG_NAME/LV_NAME.e2scrub
  Would execute: lvcreate -s -L 256m -n LV_NAME. e2scrub VG_NAME/LV_NAME
  Would execute: udevadm settle
  Would execute: /sbin/e2fsck -E journal_only -p /dev/VG_NAME/LV_NAME. e2scrub
  Would execute: /sbin/e2fsck -f -y /dev/VG_NAME/LV_NAME. e2scrub
  /dev/VG_NAME/LV_NAME: Scrub succeeded.
  Would execute: /sbin/tune2fs -C 0 -T 20240105045737 /dev/VG_NAME/LV_NAME
  Would execute: lvremove -f VG_NAME/LV_NAME. e2scrub
  ```
- **-r** 
    
  e2scrubスナップショットを削除し、何もチェックせずに終了する。
  
  実行例　[](変更しない)
  
  ```
  sudo e2scrub -r /dev/VG_NAME/LV_NAME
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```
- **-t**
  
  エラーが見つからなければ、マウントしたファイルシステムで fstrim(1) を実行する。

  実行例 [](変更しない)
  
  ```
  sudo e2scrub　-t /dev/VG_NAME/LV_NAME
  ```


  実行結果　[](変更しない)


  ```
  Reducing COW size 256.00 MiB down to maximum usable size 16.00 MiB.Logical volume "LV_NAME. e2scrub" created.
  e2fsck 1.46.5 (30-Dec-2021)
  Pass 1: Checking i - N's, blocks, and sizes
  Pass 2: Checking ディレクトリ structure
  Pass 3: Checking ディレクトリ connectivity
  Pass 4: Checking reference counts
  Pass 5: Checking グループ summary information
  /dev/VG_NAME/LV_NAME.e2scrub: 11/3072 files (9.1% non-contiguous), 1227/3072 blocks
  /dev/VG_NAME/LV_NAME: Scrub succeeded.
  tune2fs 1.46.5 (30-Dec-2021)
  Setting current mount count to 0
  Setting time filesystem last checked to Fri Jan 5 05:00:08 2024
  
  Logical volume "LV_NAME.e2scrub" successfully removed
  /dev/VG_NAME/LV_NAME: Trimming free space.
  fstrim: /media/ubuntu/ce2349bf-3052-4214-81a6-3a739a3afdcd: the discard operation is not supported
  ```