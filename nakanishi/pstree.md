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
    
  文章説明
  
  実行例　[](変更しない)
  
  ```
  実行例
  ```


  実行結果　[](変更しない)


  ```
  実行結果
  ```