[](ファイル名はコマンド名.md)
# aptdcon
ソフトウェアのインストールや削除などのパッケージ管理タスクを実行できる。

  実行例 [](変更しない)
  
  ```
  なし
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```

### オプション一覧


- **-i,--install**
  
  パッケージをインストールする。複数のパッケージをインストールしたい場合は、パッケージ名を""で囲う。

  実行例 [](変更しない)
  
  ```
  sudo aptdcon -i "nano init"
  ```


  実行結果　[](変更しない)


  ```
  [\]   0% 依存関係を解決しています
  [\]   0% ソフトウェアの一覧を読み込んでいます
  [/]   0% 処理の開始を待っています
  The following NEW packages will be installed (2):
    init nano
  Do you want to continue [Y/n]?y
  [-]   0% 認証を待っています
  [-]   0% タスクを実行中です
  [-]  11% タスクを実行中です
  [+] 100%  成功しました
  ```
- **--reinstall** 
    
  パッケージを再インストールする。複数のパッケージを再インストールしたい場合は、パッケージ名を""で囲う。
  
  実行例　[](変更しない)
  
  ```
  sudo aptdcon --reinstall "nano init"
  ```


  実行結果　[](変更しない)


  ```
  [\]   0% 依存関係を解決しています
  [\]   0% ソフトウェアの一覧を読み込んでいます
  [/]   0% 処理の開始を待っています
  The following packages will be reinstalled (2):
    init nano
  Do you want to continue [Y/n]?y
  [-]   0% 認証を待っています
  [-]   0% タスクを実行中です
  [-]  11% タスクを実行中です
  [+] 100%  成功しました
  ```
- **-r,--remove**
  
  パッケージを削除する。複数のパッケージを削除したい場合は、パッケージ名を""で囲う。removeの場合設定ファイルは残るが、purgeの場合は設定ファイルも削除される。

  実行例 [](変更しない)
  
  ```
  sudo aptdcon -r nano
  ```


  実行結果　[](変更しない)


  ```
  [\]   0% 依存関係を解決しています
  [\]   0% ソフトウェアの一覧を読み込んでいます
  [/]   0% 処理の開始を待っています
  The following package will be REMOVED (1):
    nano
  After this operation, -880640.0B of additional disk space will be freed.
  Do you want to continue [Y/n]?y
  [-]   0% 認証を待っています
  [-]   0% タスクを実行中です
  [-]  11% タスクを実行中です
  [-]  11% ダウンロード中です
  [-]  11% ダウンロード中です
  [-]  50% ダウンロード中です
  [-]  50% 変更を適用しています
  (データベースを読み込んでいます ... 現在 253199 個のファイルとディレクトリがインストールされています。)
  nano (6.2-1) を削除しています ...
  update-alternatives: using /usr/bin/vim.tiny to provide /usr/bin/editor (editor) in auto mode
  install-info (6.8-4build1) のトリガを処理しています ...
  man-db (2.10.2-1) のトリガを処理しています ...
  [\]  76% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  /usr/lib/python3/dist-packages/aptdaemon/console.py:337: Warning: Source ID 22 was not found when attempting to remove it
    GLib.source_remove(wid)
  /usr/lib/python3/dist-packages/aptdaemon/console.py:337: Warning: Source ID 23 was not found when attempting to remove it
    GLib.source_remove(wid)
  [+] 100%  成功しました
  ```
- **-p,--purge** 
    
  パッケージを完全に削除する。複数のパッケージを完全に削除したい場合は、パッケージ名を""で囲う。removeの場合設定ファイルは残るが、purgeの場合は設定ファイルも削除される。
  
  実行例　[](変更しない)
  
  ```
  sudo aptdcon -p nano
  ```


  実行結果　[](変更しない)


  ```
  [\]   0% 依存関係を解決しています
  [\]   0% ソフトウェアの一覧を読み込んでいます
  [/]   0% 処理の開始を待っています
  The following packages will be REMOVED (2):
    nano nano
  After this operation, -880640.0B of additional disk space will be freed.
  Do you want to continue [Y/n]?y
  [-]   0% 認証を待っています
  [-]   0% タスクを実行中です
  [-]  11% タスクを実行中です
  [-]  11% ダウンロード中です
  [-]  11% ダウンロード中です
  [-]  50% ダウンロード中です
  [-]  50% 変更を適用しています
  (データベースを読み込んでいます ... 現在 253199 個のファイルとディレクトリがインストールされています。)
  nano (6.2-1) を削除しています ...
  update-alternatives: using /usr/bin/vim.tiny to provide /usr/bin/editor (editor) in auto mode
  install-info (6.8-4build1) のトリガを処理しています ...
  man-db (2.10.2-1) のトリガを処理しています ...
  (データベースを読み込んでいます ... 現在 253127 個のファイルとディレクトリがインストールされています。)
  nano (6.2-1) の設定ファイルを削除しています ...
  [\]  82% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  [\] 100% 終了しました インストール後トリガ dpkg-exec を実行しています
  /usr/lib/python3/dist-packages/aptdaemon/console.py:337: Warning: Source ID 22 was not found when attempting to remove it
    GLib.source_remove(wid)
  /usr/lib/python3/dist-packages/aptdaemon/console.py:337: Warning: Source ID 23 was not found when attempting to remove it
    GLib.source_remove(wid)
  [+] 100%  成功しました
  ```
- **-u,--upgrade**
  
  パッケージをアップグレードする。複数のパッケージをアップグレードしたい場合は、パッケージ名を""で囲う。

  実行例 [](変更しない)
  
  ```
  sudo aptdcon -u "nano init"
  ```


  実行結果　[](変更しない)


  ```
  [\]   0% 依存関係を解決しています
  [\]   0% ソフトウェアの一覧を読み込んでいます
  [/]   0% 処理の開始を待っています
  The following packages will be upgraded (2):
    init nano
  Do you want to continue [Y/n]?y
  [-]   0% 認証を待っています
  [-]   0% タスクを実行中です
  [-]  11% タスクを実行中です
  [+] 100%  成功しました
  ```
- **--upgrade-system** 
    
  システム全体をアップグレードする。
  
  実行例　[](変更しない)
  
  ```
  sudo aptdcon --upgrade-system
  ```


  実行結果　[](変更しない)


  ```
  [\]   0% 依存関係を解決しています
  [\]   0% ソフトウェアの一覧を読み込んでいます
  [/]   0% 依存関係を解決しています
  [-]   0% 処理の開始を待っています
  The following packages will be upgraded (7):
    linux-firmware python3-software-properties python3-update-manager software-properties-common software-properties-gtk update-manager-core update-manager
  The following packages have been kept back (3):
    dnsmasq-base gjs libgjs0g
  Need to get 251.6MB of archives.
  After this operation, 19.9MB of additional disk space will be used.
  Do you want to continue [Y/n]?y
  [\]   0% 認証を待っています
  [\]   0% タスクを実行中です
  [\]  11% タスクを実行中です
  [\]  11% ダウンロード中です
  [\]  11% ダウンロード中です (Downloaded 0.0B of 251.6MB)
  ~略~
  ```
- **--fix-install**
  
  "dpkg --configure -a"を呼び出し、以前にキャンセルされたインストールを実行する。

  実行例 [](変更しない)
  
  ```
  sudo aptdcon --fix-install nano
  ```


  実行結果　[](変更しない)


  ```
  [\]   9% 依存関係を解決しています
  [\]   9% 処理の開始を待っています
  [\]   9% 認証を待っています
  [\]   9% タスクを実行中です
  [\]  11% タスクを実行中です
  [\]  11% クリーンアップ中です
  [\]  11% 変更を適用しています
  [\]  11% ソフトウェアの一覧を読み込んでいます
  [\]   1% ソフトウェアの一覧を読み込んでいます
  /usr/lib/python3/dist-packages/aptdaemon/console.py:337: Warning: Source ID 20 was not found when attempting to remove it
    GLib.source_remove(wid)
  /usr/lib/python3/dist-packages/aptdaemon/console.py:337: Warning: Source ID 21 was not found when attempting to remove it
    GLib.source_remove(wid)
  [+] 100%  成功しました
  ```