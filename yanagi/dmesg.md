[](ファイル名はコマンド名.md)
# dmesg
Linuxカーネルが起動時に出力したメッセージを表示するコマンド
カーネルの操作のためルート権限が必要



  実行例 [](変更しない)
  
  ```
  sudo dmesg
  ```


  実行結果（以下一部のみ）　[](変更しない)


  ```
  [0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-6.2.0-37-generic root=UUID=b784ca7c-8602-4f1c-8436-8089242f37f3 ro quiet splash
  ```
### オプション一覧


- **-l**
  
  表示レベルを指定する
  
  「emerg(高)」「alert」「crit」「err」「warn」「notice」「info」「debug(低)」から選択、複数指定は","で区切る

  実行例 [](変更しない)
  
  ```
  sudo dmesg -l warn
  ```


  実行結果　[](変更しない)


  ```
  [0.890430] acpi PNPOA03:00: fail to add MMCONFIG information, can't access extended configuration space under this bridge
  [2.420791] device-mapper: core: CONFIG_IMA_DISABLE_HTABLE is disabled. Duplicate IMA measurements will not be recorded in the IMA log.
  [2.420872] platform eisa.0: EISA: Cannot allocate resource for mainboard
  [2.420873] platform eisa.0: Cannot allocate resource for EISA slot 1
  [2.420874] platform eisa.0: Cannot allocate resource for EISA slot 2
  [2.420875] platform eisa.0: Cannot allocate resource for EISA slot 3
  [2.420876] platform eisa.0: Cannot allocate resource for EISA slot 4
  [2.420876] platform eisa.0: Cannot allocate resource for EISA slot 5
  [2.420877] platform eisa.0: Cannot allocate resource for EISA slot 6
  [2.420878] platform eisa. 0: Cannot allocate resource for EISA slot 7
  [2.420879] platform eisa.0: Cannot allocate resource for EISA slot 8
  [20.683554] kauditd_printk_skb: 8 callbacks suppressed
  [25.849810] kauditd_printk_skb: 8 callbacks suppressed
  [61.011374] kauditd_printk_skb: 4 callbacks suppressed
  ```
- **-f** 
    
  表示対象を指定する
  「kern(カーネル)(-kオプション)」「user(-uオプション)」「mail」「daemon」「auth」「syslog」「lpr」「news」から選択、複数指定は","で区切る
  実行例　[](変更しない)
  
  ```
  sudo dmesg -f kern
  ```


  実行結果　[](変更しない)


  ```
  [0.000000] Linux version 6.2.0-37-generic (buildd@bos03-amd64-055) (x86_64-linux-gnu-gcc-11 (Ubuntu 11.4.0-1ubuntu1~22.04) 11.4.0, GNU ld (GNU Binutils forUbuntu) 2.38) #38~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Nov 2 18:01:13 UTC 2 (Ubuntu 6.2.0-37.38~22.04.1-generic 6.2.16)
  [0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-6.2.0-37-generic root=UUID=b784ca7c-8602-4f1c-8436-8089242f37f3 ro quiet splash
  [0.000000] KERNEL supported cpus:
  Intel GenuineIntel
  AMD AuthenticAMD
  Hygon HygonGenuine
  Centaur CentaurHaulszhaoxin
  [0.000000] BIOS-provided physical RAM map:
  ```

- **-x** 
    
  表示レベルと表示対象を表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -x
  ```


  実行結果　[](変更しない)


  ```
  kern :notice: [0.000000] Linux version 6.2.0-37-generic (buildd@bos03-amd64-055) (x86_64-linux-gnu-gcc-11 (Ubuntu 11.4.0-1ubuntu1~22.04) 11.4.0, GNU ld (GNU Binutils for Ubuntu) 2.38) #38~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Nov 2 18:01:13 UTC 2 (Ubuntu 6.2.0-37.38~22.04.1-generic 6.2.16)
  kern :info : [0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-6.2.0-37-generic root=UUID=b784ca7c-8602-4f1c-8436-8089242f37f3 ro quiet splash
  kern:info : [0.000000] KERNEL supported cpus:
  kern:info : [0.000000]Intel GenuineIntel
  kern:info : [0.000000]AMD AuthenticAMD
  kern:info : [0.000000]Hygon HygonGenuine
  kern:info : [0.000000]Centaur CentaurHauls
  kern:info : [0.000000]zhaoxin  Shanghai
  kern:info : [0.000000] BIOS-provided physical RAM map:
  ```
- **-d** 
    
  直前のメッセージからの経過時間を表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -d
  ```


  実行結果　[](変更しない)


  ```
  [  86.241961 <0.000447>] audit: type=1400 audit(1702012655.625:77): apparmor="DENIED" operation="capable" class="cap" profile="/snap/snapd/19457/usr/lib/snapd/snap-confine" pid=1850 comm="snap-confine" capability=38 capname="perfmon"
  ```

- **-e** 
    
  メッセージの表示時刻とメッセージ間の経過時間を表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -e
  ```


  実行結果　[](変更しない)


  ```
  [+0.000447] audit: type=1400 audit(1702012655.625:77): apparmor="DENIED" operati
  on="capable" class="cap" profile="/snap/snapd/19457/usr/lib/snapd/snap-confine" pid=1850 comm="snap-confine" capability=38 capname="perfmon"
  ```

- **-T** 
    
  メッセージが出力された時刻で表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -T
  ```


  実行結果　[](変更しない)


  ```
  [金 12月 8 14:17:35 2023] audit: type=1400 audit(1702012655.625:77): apparmor="DENIED" operation="capable" class="cap" profile="/snap/snapd/19457/usr/lib/snapd/snap-confine" pid=1850 comm="snap-confine" capability=38 capname="perfmon"
  ```
- **-t** 
    
  時間を表示しない
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -t
  ```


  実行結果　[](変更しない)


  ```
  audit: type=1400 audit(1702012655. 625:77): apparmor="DENIED" operation="capable" class="cap" profile="/snap/snapd/19457/usr/lib/snapd/snap-confine" pid=1850 comm="snap-confine" capability=38 capname="perfmon"
  ```

- **-H** 
    
  読みやすいスタイルで表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -H
  ```


  実行結果　[](変更しない)


  ```
  [+0.000002] DMA [mem 0x0000000000001000-0x0000000000ffffff]
  [+0.000003] DMA32 [mem 0x0000000001000000-0x00000000ffffffff]
  [+0.000001] Normal
  [+0.000002] [mem 0x0000000100000000-0x000000011fffffff]
  [+0.000001] Movable zone start for each node
  ```
- **-r** 
    
  メッセージを加工せずに表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -r
  ```


  実行結果　[](変更しない)


  ```
  <5>[86.241961] audit: type=1400 audit(1702012655.625:77) : apparmor="DENIED" operation="capable" class="cap" profile="/snap/snapd/19457/usr/lib/snapd/snap-confine" pid=1850 comm="snap-confine" capability=38 capname="perfmon"
  ```
- **-L** 
    
  色付きで表示する
  出力に変化がないので割愛
  
- **-w** 
    
  新しいメッセージがカーネルから出力されるのを待つ
  [Ctrl]+[C]で終了
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -w
  ```


  実行結果　[](変更しない)


  ```
  [ 2664.473779] audit: type=1326 audit(1702015233.848:78): auid=1000 uid=1000 gid=1000 ses=2 subj=snap.firefox.firefox pid=2429 comm="firefox" exe="/snap/firefox/2987/usr/lib/firefox/firefox" sig=0 arch=c000003e syscall=314 compat=0 ip=0x7f14f03e973d code=0x50000
  ```
- **-F** 
    
  バッファーの代わりに指定したファイルを表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -F file.txt
  ```


  実行結果　[](変更しない)


  ```
  [   0.000000] Hello
  ```
- **-S** 
    
  syslogを使って表示する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -S
  ```


  実行結果　[](変更しない)


  ```
  [86.241961] audit: type=1400 audit(1702012655.625:77): apparmor="DENIED" operation="capable" class="cap" profile="/snap/snapd/19457/usr/lib/snapd/snap-confine" pid=1850 comm="snap-confine" capability=38 capname="perfmon"
  ```
- **-C** 

  バッファーをクリアする
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -C
  sudo dmesg
  ```


  実行結果　[](変更しない)


  ```
  何も表示されなくなる
  ```
- **-c** 

  リンクバッファーを出力してクリアする
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -c
  sudo dmesg 
  ```


  実行結果　[](変更しない)


  ```
  sudo dmesg -c
  [ 3082.092138]audit:type=1326 audit(1702015651.467:79): auid=1000 uid=1000 gid=1000 ses=2 subj=snap.firefox.firefox pid=3081 comm="firefox" exe="/snap/firefox/2987/usr/lib/firefox/firefox" sig=0 arch=c000003e syscall=314 compat=0 ip=0x7efc049f373d code=0x50000
  sudo dmesg 
  何も表示されない
  ```
- **-D** 

  コンソールへの出力を無効にする
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -D
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```
- **-E** 

  コンソールへの出力を有効にする
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -E
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```
- **-n** 

  コンソールに表示するレベルを指定する
  
  実行例　[](変更しない)
  
  ```
  sudo dmesg -n alert
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```