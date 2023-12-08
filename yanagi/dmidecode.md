[](ファイル名はコマンド名.md)
# dmidecode
ハードウェアの情報を表示するコマンド
DMIテーブルに格納されている情報を見やすい形に成型して表示する

詳細を見る場合はルート権限


  実行例 [](変更しない)
  
  ```
  sudo dmidecode
  ```


  実行結果（一部）　[](変更しない)


  ```
  # dmidecode 3.3
Getting SMBIOS data from sysfs.
SMBIOS 2.5 present.
10 structures occupying 456 bytes.
Table at 0x000E1000.
  ```


### オプション一覧




- **-d**
  
  情報元のファイルを指定する
  (デフォルトは/dev/main)

  実行例 [](変更しない)
  
  ```
  sudo dmidecode -d /dev/main
  ```


  実行結果　[](変更しない)


  ```
  上記と同様
  ```
- **-q**
  
  文章説明

  実行例 [](変更しない)
  
  ```
  実行例
  ```


  実行結果　[](変更しない)


  ```
  BIOS Information
     Vendor: innotek GmbH
     Version: VirtualBox
     Release Date: 12/01/2006
     Address: 0xE0000
     Runtime Size: 128 kB
     ROM Size: 128 kB
     Characteristics:
          ISA is supported
          PCI is supported
          Boot from CD is supported
          Selectable boot is supported
          8042 keyboard services are　supported (int 9h)
          CGA/mono video services are supported (int 10h)
          ACPI is supported
  ```
- **-s**
  
  指定したキーワードの情報だけを表示する
  指定できるキーワードの一覧は「dmidecode -s」で確認可能

  実行例 [](変更しない)
  
  ```
  dmidecode -s

  sudo dmidecode -s bios-vendor
  ```


  実行結果　[](変更しない)


  ```
  dmidecode: option requires an argument -- 's'
  String keyword expected
  Valid string keywords are:
  bios-vendor
  bios-version
  bios-release-date
  bios-revision
  firmware-revision
  system-manufacturer
  system-product-name
  system-version
  system-serial-number

  innotek GmbH
  ```
- **-t**
  
  指定したタイプの情報だけを表示する
  指定できるタイプの一覧は「dmidecode -t」で確認可能

  実行例 [](変更しない)
  
  ```
  dmidecode -t

  sudo dmidecode -t chassis
  ```


  実行結果　[](変更しない)


  ```
  dmidecode: option requires an argument -- 't'
  Type number or keyword expected
  Valid type keywords are:
  bios
  system
  baseboard
  chassis
  processor
  memогy
  cache
  connector
  slot


  # dmidecode 3.3
  Getting SMBIOS data from sysfs.
  SMBIOS 2.5 present.
  
  Handle 0x0003, DMI type 3, 13 bytes
  Chassis Information
  Manufacturer: Oracle Corporation
  Type: Other
  Lock: Not Present
  Version: Not Specified
  Serial Number: Not Specified
  Asset Tag: Not Specified
  Boot-up State: Safe
  Power Supply State: Safe
  Thermal State: Safe
  Security Status: None
  ```
- **-H**
  
  指定したCLIハンドルの情報だけを表示する
  実行例 [](変更しない)
  
  ```
  実行例
  ```


  実行結果　[](変更しない)


  ```
  # dmidecode 3.3Getting SMBIOS data from sysfs.
  SMBIOS 2.5 present.
  10 structures occupying 456 bytes.
  Table at 0x000E1000.
  Handle 0x0003, DMI type 3, 13 byte
  Chassis Information
  Manufacturer: Oracle Corporation
  Type: Other
  Lock: Not Present
  Version: Not Specified
  Serial Number: Not Specified
  Asset Tag: Not Specified
  Boot-up State: Safe
  Power Supply State: Safe
  Thermal State: Safe
  Security Status: None
  ```
- **-u**
  
  情報をデコードせず16進数コードのまま表示する

  実行例 [](変更しない)
  
  ```
  sudo dmidecode -u
  ```


  実行結果　[](変更しない)


  ```
  # dmidecode 3.3
  Getting SMBIOS data from sysfs.
  SMBIOS 2.5 present.
  10 structures occupying 456 bytes.
  Table at 0x000E1000.
  Handle 0x0000, DMI type 0, 20 bytes
  Header and Data:
  00 14 00 00 01 02 00 E0 03 01 90 80 01 48 00 00 00 00 01 00
  Strings:
  69 6E 6E 6F 74 65 6B 20 47 6D 62 48 00
  innotek GmbH
  56 69 72 74 75 61 6C 42 6F 78 00
  VirtualBox
  31 32 2F 30 31 2F 32 30 30 36 00 
  12/01/2006
  ```