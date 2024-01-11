[](ファイル名はコマンド名.md)
# apparmor_status
AppArmor(Linuxのセキュリティプロファイルを結びつけることで、ネットワークアクセスやRaw socketアクセス、ファイルへの読み書き実行などの機能に制限をかけることができるプログラム。例えば、あるプログラムに対して、参照しかしないファイルへの書き込み、利用するはずがないファイルへのアクセス、関係がない別のプログラムの呼び出しを禁止できる。"/etc/apparmor/parser.conf"に記述された通りに制限がかけられる。)の状態を表示するコマンド。デフォルトでは、--verboseオプションと同じ情報が表示される。実行にはroot権限が必要。

  実行例 [](変更しない)
  
  ```
  sudo apparmor_status
  ```


  実行結果　[](変更しない)


  ```
  apparmor module is loaded.
  19 profiles are loaded.
  19 profiles are in enforce mode.
    /snap/snapd/20290/usr/lib/snapd/snap-confine
    /snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
    /snap/snapd/20671/usr/lib/snapd/snap-confine
    /snap/snapd/20671/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
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
  0 profiles are in complain mode.
  0 profiles are in kill mode.
  0 profiles are in unconfined mode.
  0 processes have profiles defined.
  0 processes are in enforce mode.
  0 processes are in complain mode.
  0 processes are unconfined but have a profile defined.
  0 processes are in mixed mode.
  0 processes are in kill mode.
  ```

### オプション一覧


- **--profiled**
  
  読み込まれたAppArmorプロファイル(AppArmorを利用して設定された権限の情報が書かれたファイル)の数を表示する。

  実行例 [](変更しない)
  
  ```
  sudo apparmor_status --profiled
  ```


  実行結果　[](変更しない)


  ```
  19
  ```
- **--enforced** 
    
  読み込まれた強制AppArmorプロファイルの数を表示する。強制AppArmorプロファイルは受けている制限が強制されるとともに、違反の試行が記録される。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --enforced
  ```


  実行結果　[](変更しない)


  ```
  19
  ```
- **--complaining** 
    
  読み込まれた苦情AppArmorプロファイルの数を表示する。苦情AppArmorプロファイルは受けている制限が強制されないが、違反の試行は記録される。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --complaining
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--kill** 
    
  違反時にタスクを強制終了する強制AppArmorプロファイルを読み込み、数を表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --kill
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--special-unconfined** 
    
  制限を受けていないモードである、非強制AppArmorプロファイルを読み込み、数を表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --special-unconfined
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--process-mixed** 
    
  異なるモードのプロファイルを持つプロファイルスタックによって制限されたプロセスの数を表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --process-mixed
  ```


  実行結果　[](変更しない)


  ```
  0
  ```
- **--verbose** 
    
  AppArmorプロファイルの状態を表示する
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --verbose
  ```


  実行結果　[](変更しない)


  ```
  apparmor module is loaded.
  19 profiles are loaded.
  19 profiles are in enforce mode.
     /snap/snapd/20290/usr/lib/snapd/snap-confine
     /snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
     /snap/snapd/20671/usr/lib/snapd/snap-confine
     /snap/snapd/20671/usr/lib/snapd/snap-confine//mount-namespace-capture-helper
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
  0 profiles are in complain mode.
  0 profiles are in kill mode.
  0 profiles are in unconfined mode.
  0 processes have profiles defined.
  0 processes are in enforce mode.
  0 processes are in complain mode.
  0 processes are unconfined but have a profile defined.
  0 processes are in mixed mode.
  0 processes are in kill mode.
  ```
- **--json** 
    
  AppArmorプロファイルの状態を、JSON形式で表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --json
  ```


  実行結果　[](変更しない)


  ```
  {"version": "2", "profiles": {"/snap/snapd/20290/usr/lib/snapd/snap-confine": "enforce", "/snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce", "/snap/snapd/20671/usr/lib/snapd/snap-confine": "enforce", "/snap/snapd/20671/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce", "snap-update-ns.firefox": "enforce", "snap-update-ns.snap-store": "enforce", "snap-update-ns.snapd-desktop-integration": "enforce", "snap.firefox.firefox": "enforce", "snap.firefox.geckodriver": "enforce", "snap.firefox.hook.configure": "enforce", "snap.firefox.hook.connect-plug-host-hunspell": "enforce", "snap.firefox.hook.disconnect-plug-host-hunspell": "enforce", "snap.firefox.hook.post-refresh": "enforce", "snap.snap-store.hook.configure": "enforce", "snap.snap-store.snap-store": "enforce", "snap.snap-store.ubuntu-software": "enforce", "snap.snap-store.ubuntu-software-local-file": "enforce", "snap.snapd-desktop-integration.hook.configure": "enforce", "snap.snapd-desktop-integration.snapd-desktop-integration": "enforce"}, "processes": {}}
  ```
- **--pretty-json** 
    
  AppArmorプロファイルの状態を、人間にも読みやすい形式で表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo apparmor_status --pretty-json
  ```


  実行結果　[](変更しない)


  ```
  {
          "version":      "2",
          "profiles":     {
                  "/snap/snapd/20290/usr/lib/snapd/snap-confine": "enforce",
                  "/snap/snapd/20290/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce",
                  "/snap/snapd/20671/usr/lib/snapd/snap-confine": "enforce",
                  "/snap/snapd/20671/usr/lib/snapd/snap-confine//mount-namespace-capture-helper": "enforce",
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
                  "snap.snapd-desktop-integration.snapd-desktop-integration":     "enforce"
          },
          "processes":    {
          }
  }
  ```