[](ファイル名はコマンド名.md)
## pstree
現在実行されているプロセスをツリー表示するコマンド

 実行例 [](変更しない)
  
  ```
  pstree
  ```


  実行結果　[](変更しない)


  ```
  systemd─┬─ModemManager───2*[{ModemManager}]
        ├─agetty
        ├─containerd───8*[{containerd}]
        ├─cron
        ├─dbus-daemon
        ├─dockerd───9*[{dockerd}]
        ├─irqbalance───{irqbalance}
        ├─multipathd───6*[{multipathd}]
        ├─networkd-dispat
        ├─packagekitd───2*[{packagekitd}]
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd───3*[{rsyslogd}]
        ├─snapd───10*[{snapd}]
        ├─sshd───sshd───sshd───bash───pstree
        ├─systemd───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-network
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        ├─tailscaled───10*[{tailscaled}]
        ├─thermald───{thermald}
        ├─udisksd───4*[{udisksd}]
        ├─unattended-upgr───{unattended-upgr}
        └─upowerd───2*[{upowerd}]
  ```


オプション一覧


  
  

  
- **-a** 
    
  各プロセスのコマンドライン引数を表示する
  
  実行例　[](変更しない)
  
  ```
  pstree -a
  ```


  実行結果　[](変更しない)


  ```
  systemd --system --deserialize 36
  ├─ModemManager
  │   └─2*[{ModemManager}]
  ├─agetty -o -p -- \\u --noclear tty1 linux
  ├─containerd
  │   └─8*[{containerd}]
  ├─cron -f -P
  ├─dbus-daemon --system --address=systemd: --nofork --nopidfile...
  ├─dockerd -H fd:// --containerd=/run/containerd/containerd.sock
  │   └─9*[{dockerd}]
  ├─irqbalance --foreground
  │   └─{irqbalance}
  ├─multipathd -d -s
  │   └─6*[{multipathd}]
  ├─networkd-dispat /usr/bin/networkd-dispatcher --run-startup-triggers
  ├─packagekitd
  │   └─2*[{packagekitd}]
  ├─polkitd --no-debug
  │   └─2*[{polkitd}]
  ├─rsyslogd -n -iNONE
  │   └─3*[{rsyslogd}]
  ├─snapd
  │   └─10*[{snapd}]
  ├─sshd
  │   └─sshd
  │       └─sshd
  │           └─bash
  │               └─pstree -a
  ├─systemd --user
  │   └─(sd-pam)
  ├─systemd-journal
  ├─systemd-logind
  ├─systemd-network
  ├─systemd-resolve
  ├─systemd-timesyn
  │   └─{systemd-timesyn}
  ├─systemd-udevd
  ├─tailscaled --state=/var/lib/tailscale/tailscaled.state--socket=/run/ta
  │   └─10*[{tailscaled}]
  ├─thermald --systemd --dbus-enable --adaptive
  │   └─{thermald}
  ├─udisksd
  │   └─4*[{udisksd}]
  ├─unattended-upgr ...
  │   └─{unattended-upgr}
  └─upowerd
      └─2*[{upowerd}]
  ```

- **-c** 
    
  -cオプションを使用すると、各プロセスの実行可能ファイル(コマンド)の名前を表示する。
  
  実行例　[](変更しない)
  
  ```
  pstree -c
  ```


  実行結果　[](変更しない)


  ```
  systemd─┬─ModemManager─┬─{ModemManager}
        │              └─{ModemManager}
        ├─agetty
        ├─containerd─┬─{containerd}
        │            ├─{containerd}
        │            ├─{containerd}
        │            ├─{containerd}
        │            ├─{containerd}
        │            ├─{containerd}
        │            ├─{containerd}
        │            └─{containerd}
        ├─cron
        ├─dbus-daemon
        ├─dockerd─┬─{dockerd}
        │         ├─{dockerd}
        │         ├─{dockerd}
        │         ├─{dockerd}
        │         ├─{dockerd}
        │         ├─{dockerd}
        │         ├─{dockerd}
        │         ├─{dockerd}
        │         └─{dockerd}
        ├─irqbalance───{irqbalance}
        ├─multipathd─┬─{multipathd}
        │            ├─{multipathd}
        │            ├─{multipathd}
        │            ├─{multipathd}
        │            ├─{multipathd}
        │            └─{multipathd}
        ├─networkd-dispat
        ├─packagekitd─┬─{packagekitd}
        │             └─{packagekitd}
        ├─polkitd─┬─{polkitd}
        │         └─{polkitd}
        ├─rsyslogd─┬─{rsyslogd}
        │          ├─{rsyslogd}
        │          └─{rsyslogd}
        ├─snapd─┬─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       └─{snapd}
        ├─sshd───sshd───sshd───bash───pstree
        ├─systemd───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-network
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        ├─tailscaled─┬─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            ├─{tailscaled}
        │            └─{tailscaled}
        ├─thermald───{thermald}
        ├─udisksd─┬─{udisksd}
        │         ├─{udisksd}
        │         ├─{udisksd}
        │         └─{udisksd}
        ├─unattended-upgr───{unattended-upgr}
        └─upowerd─┬─{upowerd}
                  └─{upowerd}
  ```

  - **-h** 
    
  文章説明
  
  実行例　[](変更しない)
  
  ```
  pstree -h
  ```


  実行結果　[](変更しない)


  ```
  systemd─┬─ModemManager───2*[{ModemManager}]
        ├─agetty
        ├─containerd───8*[{containerd}]
        ├─cron
        ├─dbus-daemon
        ├─dockerd───9*[{dockerd}]
        ├─irqbalance───{irqbalance}
        ├─multipathd───6*[{multipathd}]
        ├─networkd-dispat
        ├─packagekitd───2*[{packagekitd}]
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd───3*[{rsyslogd}]
        ├─sh───node─┬─node─┬─bash───pstree
        │           │      └─11*[{node}]
        │           ├─node─┬─node───6*[{node}]
        │           │      └─15*[{node}]
        │           ├─node───12*[{node}]
        │           └─10*[{node}]
        ├─snapd───10*[{snapd}]
        ├─sshd─┬─sshd───sshd───bash
        │      └─sshd───sshd
        ├─systemd───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-network
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        ├─tailscaled───10*[{tailscaled}]
        ├─thermald───{thermald}
        ├─udisksd───4*[{udisksd}]
        ├─unattended-upgr───{unattended-upgr}
        └─upowerd───2*[{upowerd}]
  ```

- **-l** 
    
  長い行を表示。デフォルトでは、長い行はディスプレイの幅で切られる。
  
  実行例　[](変更しない)
  
  ```
  pstree -l
  ```


  実行結果　[](変更しない)


  ```
  systemd─┬─ModemManager───2*[{ModemManager}]
        ├─agetty
        ├─containerd───8*[{containerd}]
        ├─cron
        ├─dbus-daemon
        ├─dockerd───9*[{dockerd}]
        ├─irqbalance───{irqbalance}
        ├─multipathd───6*[{multipathd}]
        ├─networkd-dispat
        ├─packagekitd───2*[{packagekitd}]
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd───3*[{rsyslogd}]
        ├─sh───node─┬─node─┬─bash───pstree
        │           │      └─11*[{node}]
        │           ├─node───12*[{node}]
        │           ├─node───15*[{node}]
        │           └─10*[{node}]
        ├─snapd───10*[{snapd}]
        ├─sshd─┬─sshd───sshd───bash
        │      └─sshd───sshd
        ├─systemd───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-network
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        ├─tailscaled───10*[{tailscaled}]
        ├─thermald───{thermald}
        ├─udisksd───4*[{udisksd}]
        ├─unattended-upgr───{unattended-upgr}
        └─upowerd───2*[{upowerd}]
  ```


- **-n**
  
  同じ親を持つプロセスを、名前ではなくPIDでソートしる。

  実行例 [](変更しない)
  
  ```
  pstree -n
  ```


  実行結果　[](変更しない)


  ```
  systemd─┬─multipathd───6*[{multipathd}]
        ├─cron
        ├─dbus-daemon
        ├─irqbalance───{irqbalance}
        ├─networkd-dispat
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd───3*[{rsyslogd}]
        ├─systemd-logind
        ├─thermald───{thermald}
        ├─agetty
        ├─ModemManager───2*[{ModemManager}]
        ├─unattended-upgr───{unattended-upgr}
        ├─tailscaled───10*[{tailscaled}]
        ├─snapd───10*[{snapd}]
        ├─containerd───8*[{containerd}]
        ├─dockerd───9*[{dockerd}]
        ├─systemd-timesyn───{systemd-timesyn}
        ├─packagekitd───2*[{packagekitd}]
        ├─upowerd───2*[{upowerd}]
        ├─sshd─┬─sshd───sshd───bash
        │      └─sshd───sshd
        ├─systemd-journal
        ├─udisksd───4*[{udisksd}]
        ├─systemd-udevd
        ├─systemd-network
        ├─systemd-resolve
        ├─systemd───(sd-pam)
        └─sh───node─┬─10*[{node}]
                    ├─node─┬─11*[{node}]
                    │      └─bash───pstree
                    ├─node───12*[{node}]
                    └─node───15*[{node}]
  ```


- **-p**
  
  文章説明

  実行例 [](変更しない)
  
  ```
  pstree -p
  ```


  実行結果　[](変更しない)


  ```
  systemd(1)─┬─ModemManager(743)─┬─{ModemManager}(749)
           │                   └─{ModemManager}(755)
           ├─agetty(702)
           ├─containerd(12189)─┬─{containerd}(12190)
           │                   ├─{containerd}(12191)
           │                   ├─{containerd}(12192)
           │                   ├─{containerd}(12193)
           │                   ├─{containerd}(12194)
           │                   ├─{containerd}(12195)
           │                   ├─{containerd}(12196)
           │                   └─{containerd}(12199)
           ├─cron(665)
           ├─dbus-daemon(666)
           ├─dockerd(12520)─┬─{dockerd}(12521)
           │                ├─{dockerd}(12522)
           │                ├─{dockerd}(12523)
           │                ├─{dockerd}(12524)
           │                ├─{dockerd}(12525)
           │                ├─{dockerd}(12526)
           │                ├─{dockerd}(12527)
           │                ├─{dockerd}(12528)
           │                └─{dockerd}(12531)
           ├─irqbalance(673)───{irqbalance}(688)
           ├─multipathd(457)─┬─{multipathd}(462)
           │                 ├─{multipathd}(463)
           │                 ├─{multipathd}(464)
           │                 ├─{multipathd}(465)
           │                 ├─{multipathd}(466)
           │                 └─{multipathd}(467)
           ├─networkd-dispat(674)
           ├─packagekitd(240910)─┬─{packagekitd}(240915)
           │                     └─{packagekitd}(240916)
           ├─polkitd(675)─┬─{polkitd}(689)
           │              └─{polkitd}(729)
           ├─rsyslogd(676)─┬─{rsyslogd}(703)
           │               ├─{rsyslogd}(704)
           │               └─{rsyslogd}(705)
           ├─sh(250384)───node(250393)─┬─node(250456)─┬─bash(2+
           │                           │              ├─sh(253+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              └─{node}+
           │                           ├─node(250588)─┬─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              └─{node}+
           │                           ├─node(250601)─┬─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              ├─{node}+
           │                           │              └─{node}+
           │                           ├─{node}(250396)
           │                           ├─{node}(250398)
           │                           ├─{node}(250399)
           │                           ├─{node}(250400)
           │                           ├─{node}(250402)
           │                           ├─{node}(250404)
           │                           ├─{node}(250405)
           │                           ├─{node}(250406)
           │                           ├─{node}(250407)
           │                           └─{node}(250408)
           ├─snapd(7523)─┬─{snapd}(7542)
           │             ├─{snapd}(7553)
           │             ├─{snapd}(7554)
           │             ├─{snapd}(7555)
           │             ├─{snapd}(7556)
           │             ├─{snapd}(7560)
           │             ├─{snapd}(7563)
           │             ├─{snapd}(7564)
           │             ├─{snapd}(7604)
           │             └─{snapd}(8387)
           ├─sshd(240914)─┬─sshd(241403)───sshd(241510)───bash+
           │              ├─sshd(250501)───sshd(250558)
           │              └─sshd(253237)───sshd(253294)
           ├─systemd(241406)───(sd-pam)(241407)
           ├─systemd-journal(240920)
           ├─systemd-logind(681)
           ├─systemd-network(240946)
           ├─systemd-resolve(240948)
           ├─systemd-timesyn(240909)───{systemd-timesyn}(24094+
           ├─systemd-udevd(240939)
           ├─tailscaled(793)─┬─{tailscaled}(794)
           │                 ├─{tailscaled}(795)
           │                 ├─{tailscaled}(796)
           │                 ├─{tailscaled}(797)
           │                 ├─{tailscaled}(798)
           │                 ├─{tailscaled}(799)
           │                 ├─{tailscaled}(800)
           │                 ├─{tailscaled}(802)
           │                 ├─{tailscaled}(803)
           │                 └─{tailscaled}(811)
           ├─thermald(684)───{thermald}(746)
           ├─udisksd(240921)─┬─{udisksd}(240924)
           │                 ├─{udisksd}(240926)
           │                 ├─{udisksd}(240932)
           │                 └─{udisksd}(240943)
           ├─unattended-upgr(744)───{unattended-upgr}(765)
           └─upowerd(240913)─┬─{upowerd}(240930)
                             └─{upowerd}(240931)
  ```

- **-u**
  
  文章説明

  実行例 [](変更しない)
  
  ```
  pstree -u
  ```


  実行結果　[](変更しない)


  ```
  systemd─┬─ModemManager───2*[{ModemManager}]
        ├─agetty
        ├─containerd───8*[{containerd}]
        ├─cron
        ├─dbus-daemon(messagebus)
        ├─dockerd───9*[{dockerd}]
        ├─irqbalance───{irqbalance}
        ├─multipathd───6*[{multipathd}]
        ├─networkd-dispat
        ├─packagekitd───2*[{packagekitd}]
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd(syslog)───3*[{rsyslogd}]
        ├─sh(tomo)───node─┬─node─┬─bash───pstree
        │                 │      ├─sh───cpuUsage.sh───sleep
        │                 │      └─11*[{node}]
        │                 ├─node───12*[{node}]
        │                 ├─node───15*[{node}]
        │                 └─10*[{node}]
        ├─snapd───10*[{snapd}]
        ├─sshd─┬─sshd───sshd(tomo)───bash
        │      └─2*[sshd───sshd(tomo)]
        ├─systemd(tomo)───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-network(systemd-network)
        ├─systemd-resolve(systemd-resolve)
        ├─systemd-timesyn(systemd-timesync)───{systemd-timesyn+
        ├─systemd-udevd
        ├─tailscaled───10*[{tailscaled}]
        ├─thermald───{thermald}
        ├─udisksd───4*[{udisksd}]
        ├─unattended-upgr───{unattended-upgr}
        └─upowerd───2*[{upowerd}]
  ```