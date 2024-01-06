[](ファイル名はコマンド名.md)
# e2mmpstatus
e2mmpstatus は、mmp 機能が有効になっている ext4 ファイルシステムの Multiple-Mount Protection (MMP) ステータスをチェックするために使われる。指定するファイルシステムはデバイス名 (例 /dev/hdc1, /dev/sdb2) か、ext4 ファイルシステムのラベルまたは UUID (例 UUID=8868abf6-88c5-4a83-98b8-bfc24057f7bd または LABEL=root) である。
デフォルトでは、e2mmpstatus プログラムはファイルシステムを複数回マウントする リスクを負わずに、マウントしても安全かどうかをチェックする。

  実行例 [](変更しない)
  
  ```
  sudo e2mmpstatus /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  e2mmpstatus: it is safe to mount '/dev/sda1' , MMP is clean
  MMPがクリーンな状態なのでマウントできるようになっている
  ```

### オプション一覧




- **-i**
  
  MMP情報をチェックするのではなく、出力する。

  実行例 [](変更しない)
  
  ```
  sudo e2mmpstatus -i /dev/sda1
  ```


  実行結果　[](変更しない)


  ```
  MMP_block:
     mmp_magic: 0x4d4d50
     mmp_check_interval: 5
     mmp_sequence: 0xff4d4d50
     mmp_update_date: Wed Jan 3 17:17:21 2024
     mmp_update_time: 1704269841
     mmp_node_name: ubuntu-VirtualBox
     mmp_device_name: /dev/sda1
     mmp block number: 8
  ```