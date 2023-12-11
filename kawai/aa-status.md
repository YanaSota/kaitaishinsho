[](ファイル名はコマンド名.md)
# aa-status
AppArmor(Linuxのセキュリティプロファイルを結びつけることで、ネットワークアクセスやRaw socketアクセス、ファイルへの読み書き実行などの機能に制限をかけることができるプログラム。例えば、あるプログラムに対して、参照しかしないファイルへの書き込み、利用するはずがないファイルへのアクセス、関係がない別のプログラムの呼び出しを禁止できる。"/etc/apparmor/parser.conf"に記述された通りに制限がかけられる。)の状態を表示するコマンド。デフォルトでは、--verboseオプションと同じ情報が表示される。実行にはroot権限が必要。

  実行例 [](変更しない)
  
  ```
  sudo aa-status
  ```


  実行結果　[](変更しない)


  ```
  apparmor module is loaded.
  49 profiles are loaded.
  47 profiles are in enforce mode.
   /snap/snapd/19993/usr/lib/snapd/snap-confine
   /snap/snapd/19993/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /snap/snapd/20092/usr/lib/snapd/snap-confine
   /snap/snapd/20092/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /snap/snapd/20290/usr/lib/snapd/snap-confine
   /snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /usr/bin/evince
   /usr/bin/evince-previewer
   /usr/bin/evince-previewer//sanitized_helper
   /usr/bin/evince-thumbnailer
   /usr/bin/evince//sanitized_helper
   /usr/bin/man
   /usr/lib/NetworkManager/nm-dhcp-client.action
   /usr/lib/NetworkManager/nm-dhcp-helper
   /usr/lib/connman/scripts/dhclient-script
   /usr/lib/cups/backend/cups-pdf
   /usr/lib/snapd/snap-confine
   /usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /usr/sbin/cups-browsed
   /usr/sbin/cupsd
   /usr/sbin/cupsd//third_party
   /{,usr/}sbin/dhclient
   docker-default
   libreoffice-senddoc
   libreoffice-soffice//gpg
   libreoffice-xpdfimport
   lsb_release
   man_filter
   man_groff
   nvidia_modprobe
   nvidia_modprobe//kmod
   snap-update-ns.firefox
   snap-update-ns.snap-store
   snap-update-ns.snapd-desktop-integration
   snap.firefox.firefox
   snap.firefox.geckodriver
   snap.firefox.hook.configure
   snap.firefox.hook.connect-plug-host-hunspell
   snap.firefox.hook.disconnect-plug-host-hunspell
   snap.firefox.hook.post-refresh
   snap.snap-store.hook.configure
   snap.snap-store.snap-store
   snap.snap-store.ubuntu-software
   snap.snap-store.ubuntu-software-local-file
   snap.snapd-desktop-integration.hook.configure
   snap.snapd-desktop-integration.snapd-desktop-integration
   tcpdump
  2 profiles are in complain mode.
   libreoffice-oosplash
   libreoffice-soffice
  0 profiles are in kill mode.
  0 profiles are in unconfined mode.
  7 processes have profiles defined.
  7 processes are in enforce mode.
   /usr/bin/man (93992)
   /usr/bin/less (94000) /usr/bin/man
   /usr/sbin/cups-browsed (94258)
   /usr/sbin/cupsd (94221)
   /bin/snap-store (1413) snap.snap-store.ubuntu-software
   /bin/snapd-desktop-integration (872) snap.snapd-desktop-integration.snapd-desktop-integration
   /bin/snapd-desktop-integration (1216) snap.snapd-desktop-integration.snapd-desktop-integration
  0 processes are in complain mode.
  0 processes are unconfined but have a profile defined.
  0 processes are in mixed mode.
  0 processes are in kill mode.
  ```

### オプション一覧


- **--enabled**
  
  AppArmorが利用不可の場合にエラーコードを表示する。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --enabled
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--profiled** 
    
  読み込まれたAppArmorプロファイル(AppArmorを利用して設定された権限の情報が書かれたファイル)の数を表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo aa-status --profiled
  ```


  実行結果　[](変更しない)


  ```
  49
  ```
- **--enforced**
  
  読み込まれた強制AppArmorプロファイルの数を表示する。強制AppArmorプロファイルは受けている制限が強制されるとともに、違反の試行が記録される。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --enforced
  ```


  実行結果　[](変更しない)


  ```
  47
  ```
- **--complaining**
  
  読み込まれた苦情AppArmorプロファイルの数を表示する。苦情AppArmorプロファイルは受けている制限が強制されないが、違反の試行は記録される。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --complaining
  ```


  実行結果　[](変更しない)


  ```
  2
  ```
- **--kill**
  
  違反時にタスクを強制終了する強制AppArmorプロファイルを読み込み、数を表示する。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --kill
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--special-unconfined**
  
  制限を受けていないモードである、非強制AppArmorプロファイルを読み込み、数を表示する。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --special-unconfined
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--process-mixed**
  
  異なるモードのプロファイルを持つプロファイルスタックによって制限されたプロセスの数を表示する。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --process-mixed
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--verbose**
  
  AppArmorプロファイルの状態を表示する

  実行例 [](変更しない)
  
  ```
  sudo aa-status --verbose
  ```


  実行結果　[](変更しない)


  ```
  apparmor module is loaded.
  49 profiles are loaded.
  47 profiles are in enforce mode.
   /snap/snapd/19993/usr/lib/snapd/snap-confine
   /snap/snapd/19993/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /snap/snapd/20092/usr/lib/snapd/snap-confine
   /snap/snapd/20092/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /snap/snapd/20290/usr/lib/snapd/snap-confine
   /snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /usr/bin/evince
   /usr/bin/evince-previewer
   /usr/bin/evince-previewer//sanitized_helper
   /usr/bin/evince-thumbnailer
   /usr/bin/evince//sanitized_helper
   /usr/bin/man
   /usr/lib/NetworkManager/nm-dhcp-client.action
   /usr/lib/NetworkManager/nm-dhcp-helper
   /usr/lib/connman/scripts/dhclient-script
   /usr/lib/cups/backend/cups-pdf
   /usr/lib/snapd/snap-confine
   /usr/lib/snapd/snap-confine//mount-namespace-capture-helper
   /usr/sbin/cups-browsed
   /usr/sbin/cupsd
   /usr/sbin/cupsd//third_party
   /{,usr/}sbin/dhclient
   docker-default
   libreoffice-senddoc
   libreoffice-soffice//gpg
   libreoffice-xpdfimport
   lsb_release
   man_filter
   man_groff
   nvidia_modprobe
   nvidia_modprobe//kmod
   snap-update-ns.firefox
   snap-update-ns.snap-store
   snap-update-ns.snapd-desktop-integration
   snap.firefox.firefox
   snap.firefox.geckodriver
   snap.firefox.hook.configure
   snap.firefox.hook.connect-plug-host-hunspell
   snap.firefox.hook.disconnect-plug-host-hunspell
   snap.firefox.hook.post-refresh
   snap.snap-store.hook.configure
   snap.snap-store.snap-store
   snap.snap-store.ubuntu-software
   snap.snap-store.ubuntu-software-local-file
   snap.snapd-desktop-integration.hook.configure
   snap.snapd-desktop-integration.snapd-desktop-integration
   tcpdump
  2 profiles are in complain mode.
   libreoffice-oosplash
   libreoffice-soffice
  0 profiles are in kill mode.
  0 profiles are in unconfined mode.
  7 processes have profiles defined.
  7 processes are in enforce mode.
   /usr/bin/man (93992)
   /usr/bin/less (94000) /usr/bin/man
   /usr/sbin/cups-browsed (94258)
   /usr/sbin/cupsd (94221)
   /bin/snap-store (1413) snap.snap-store.ubuntu-software
   /bin/snapd-desktop-integration (872) snap.snapd-desktop-integration.snapd-desktop-integration
   /bin/snapd-desktop-integration (1216) snap.snapd-desktop-integration.snapd-desktop-integration
  0 processes are in complain mode.
  0 processes are unconfined but have a profile defined.
  0 processes are in mixed mode.
  0 processes are in kill mode.
  ```
- **--json**
  
  AppArmorプロファイルの状態を、JSON形式で表示する。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --json
  ```


  実行結果　[](変更しない)


  ```
  {"version": "2", "profiles": {"/snap/snapd/19993/usr/lib/snapd/snap-confine": "enforce", "/snap/snapd/19993/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce", "/snap/snapd/20092/usr/lib/snapd/snap-confine": "enforce", "/snap/snapd/20092/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce", "/snap/snapd/20290/usr/lib/snapd/snap-confine": "enforce", "/snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce", "/usr/bin/evince": "enforce", "/usr/bin/evince-previewer": "enforce", "/usr/bin/evince-previewer//sanitized_helper": "enforce", "/usr/bin/evince-thumbnailer": "enforce", "/usr/bin/evince//sanitized_helper": "enforce", "/usr/bin/man": "enforce", "/usr/lib/NetworkManager/nm-dhcp-client.action": "enforce", "/usr/lib/NetworkManager/nm-dhcp-helper": "enforce", "/usr/lib/connman/scripts/dhclient-script": "enforce", "/usr/lib/cups/backend/cups-pdf": "enforce", "/usr/lib/snapd/snap-confine": "enforce", "/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce", "/usr/sbin/cups-browsed": "enforce", "/usr/sbin/cupsd": "enforce", "/usr/sbin/cupsd//third_party": "enforce", "/{,usr/}sbin/dhclient": "enforce", "docker-default": "enforce", "libreoffice-senddoc": "enforce", "libreoffice-soffice//gpg": "enforce", "libreoffice-xpdfimport": "enforce", "lsb_release": "enforce", "man_filter": "enforce", "man_groff": "enforce", "nvidia_modprobe": "enforce", "nvidia_modprobe//kmod": "enforce", "snap-update-ns.firefox": "enforce", "snap-update-ns.snap-store": "enforce", "snap-update-ns.snapd-desktop-integration": "enforce", "snap.firefox.firefox": "enforce", "snap.firefox.geckodriver": "enforce", "snap.firefox.hook.configure": "enforce", "snap.firefox.hook.connect-plug-host-hunspell": "enforce", "snap.firefox.hook.disconnect-plug-host-hunspell": "enforce", "snap.firefox.hook.post-refresh": "enforce", "snap.snap-store.hook.configure": "enforce", "snap.snap-store.snap-store": "enforce", "snap.snap-store.ubuntu-software": "enforce", "snap.snap-store.ubuntu-software-local-file": "enforce", "snap.snapd-desktop-integration.hook.configure": "enforce", "snap.snapd-desktop-integration.snapd-desktop-integration": "enforce", "tcpdump": "enforce", "libreoffice-oosplash": "complain", "libreoffice-soffice": "complain"}, "processes": {"/bin/snap-store": [{"profile": "snap.snap-store.ubuntu-software", "pid": "1413", "status": "enforce"}], "/bin/snapd-desktop-integration": [{"profile": "snap.snapd-desktop-integration.snapd-desktop-integration", "pid": "872", "status": "enforce"}, {"profile": "snap.snapd-desktop-integration.snapd-desktop-integration", "pid": "1216", "status": "enforce"}], "/usr/bin/less": [{"profile": "/usr/bin/man", "pid": "94000", "status": "enforce"}], "/usr/bin/man": [{"profile": "/usr/bin/man", "pid": "93992", "status": "enforce"}], "/usr/sbin/cups-browsed": [{"profile": "/usr/sbin/cups-browsed", "pid": "94258", "status": "enforce"}], "/usr/sbin/cupsd": [{"profile": "/usr/sbin/cupsd", "pid": "94221", "status": "enforce"}]}}
  ```
- **--pretty-json**
  
  AppArmorプロファイルの状態を、人間にも読みやすい形式で表示する。

  実行例 [](変更しない)
  
  ```
  sudo aa-status --pretty-json
  ```


  実行結果　[](変更しない)


  ```
  {
        "version":      "2",
        "profiles":     {
                "/snap/snapd/19993/usr/lib/snapd/snap-confine": "enforce",
                "/snap/snapd/19993/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce",
                "/snap/snapd/20092/usr/lib/snapd/snap-confine": "enforce",
                "/snap/snapd/20092/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce",
                "/snap/snapd/20290/usr/lib/snapd/snap-confine": "enforce",
                "/snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce",
                "/usr/bin/evince":      "enforce",
                "/usr/bin/evince-previewer":    "enforce",
                "/usr/bin/evince-previewer//sanitized_helper":  "enforce",
                "/usr/bin/evince-thumbnailer":  "enforce",
                "/usr/bin/evince//sanitized_helper":    "enforce",
                "/usr/bin/man": "enforce",
                "/usr/lib/NetworkManager/nm-dhcp-client.action":        "enforce",
                "/usr/lib/NetworkManager/nm-dhcp-helper":       "enforce",
                "/usr/lib/connman/scripts/dhclient-script":     "enforce",
                "/usr/lib/cups/backend/cups-pdf":       "enforce",
                "/usr/lib/snapd/snap-confine":  "enforce",
                "/usr/lib/snapd/snap-confine//mount-namespace-capture-helper":  "enforce",
                "/usr/sbin/cups-browsed":       "enforce",
                "/usr/sbin/cupsd":      "enforce",
                "/usr/sbin/cupsd//third_party": "enforce",
                "/{,usr/}sbin/dhclient":        "enforce",
                "docker-default":       "enforce",
                "libreoffice-senddoc":  "enforce",
                "libreoffice-soffice//gpg":     "enforce",
                "libreoffice-xpdfimport":       "enforce",
                "lsb_release":  "enforce",
                "man_filter":   "enforce",
                "man_groff":    "enforce",
                "nvidia_modprobe":      "enforce",
                "nvidia_modprobe//kmod":        "enforce",
                "snap-update-ns.firefox":       "enforce",
                "snap-update-ns.snap-store":    "enforce",
                "snap-update-ns.snapd-desktop-integration":     "enforce",
                "snap.firefox.firefox": "enforce",
                "snap.firefox.geckodriver":     "enforce",
                "snap.firefox.hook.configure":  "enforce",
                "snap.firefox.hook.connect-plug-host-hunspell": "enforce",
                "snap.firefox.hook.disconnect-plug-host-hunspell":      "enforce",
                "snap.firefox.hook.post-refresh":       "enforce",
                "snap.snap-store.hook.configure":       "enforce",
                "snap.snap-store.snap-store":   "enforce",
                "snap.snap-store.ubuntu-software":      "enforce",
                "snap.snap-store.ubuntu-software-local-file":   "enforce",
                "snap.snapd-desktop-integration.hook.configure":        "enforce",
                "snap.snapd-desktop-integration.snapd-desktop-integration":     "enforce",
                "tcpdump":      "enforce",
                "libreoffice-oosplash": "complain",
                "libreoffice-soffice":  "complain"
        },
        "processes":    {
                "/bin/snap-store":      [{
                                "profile":      "snap.snap-store.ubuntu-software",
                                "pid":  "1413",
                                "status":       "enforce"
                        }],
                "/bin/snapd-desktop-integration":       [{
                                "profile":      "snap.snapd-desktop-integration.snapd-desktop-integration",
                                "pid":  "872",
                                "status":       "enforce"
                        }, {
                                "profile":      "snap.snapd-desktop-integration.snapd-desktop-integration",
                                "pid":  "1216",
                                "status":       "enforce"
                        }],
                "/usr/bin/less":        [{
                                "profile":      "/usr/bin/man",
                                "pid":  "94000",
                                "status":       "enforce"
                        }],
                "/usr/bin/man": [{
                                "profile":      "/usr/bin/man",
                                "pid":  "93992",
                                "status":       "enforce"
                        }],
                "/usr/sbin/cups-browsed":       [{
                                "profile":      "/usr/sbin/cups-browsed",
                                "pid":  "94258",
                                "status":       "enforce"
                        }],
                "/usr/sbin/cupsd":      [{
                                "profile":      "/usr/sbin/cupsd",
                                "pid":  "94221",
                                "status":       "enforce"
                        }]
        }
}
  ```
