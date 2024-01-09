[](ファイル名はコマンド名.md)
# apt
パッケージ管理用のコマンド。

  実行例 [](変更しない)
  
  ```
  なし
  ```


  実行結果　[](変更しない)


  ```
  なし
  ```

### オプション一覧


- **update**
  
  パッケージ情報をダウンロードするために使用される。

  実行例 [](変更しない)
  
  ```
  sudo apt update
  ```


  実行結果　[](変更しない)


  ```
  ヒット:1 http://archive.ubuntulinux.jp/ubuntu jammy InRelease
  ヒット:2 http://archive.ubuntulinux.jp/ubuntu-ja-non-free jammy InRelease
  ~中略~
  パッケージリストを読み込んでいます... 完了
  依存関係ツリーを作成しています... 完了
  状態情報を読み取っています... 完了
  アップグレードできるパッケージが 11 個あります。表示するには 'apt list --upgradable' を実行してください。
  ```
- **upgrade** 
    
  システムに現在インストール済みのすべてのパッケージで利用可能なアップグレードをインストールするために使用される。依存関係を満たすために必要な場合は新しいパッケージがインストールされるが、既存のパッケージが削除されることはない。
  
  実行例　[](変更しない)
  
  ```
  sudo apt upgrade
  ```


  実行結果　[](変更しない)


  ```
  パッケージリストを読み込んでいます... 完了
  依存関係ツリーを作成しています... 完了
  状態情報を読み取っています... 完了
  アップグレードパッケージを検出しています... 完了
  ~略~
  ```
- **full-upgrade** 
    
  アップグレードの機能を実行するが、システム全体をアップグレードするために必要とされる場合には、現在インストール済みのパッケージを削除する。
  
  実行例　[](変更しない)
  
  ```
  sudo apt full-upgrade
  ```


  実行結果　[](変更しない)


  ```
  パッケージリストを読み込んでいます... 完了
  依存関係ツリーを作成しています... 完了
  状態情報を読み取っています... 完了
  アップグレードパッケージを検出しています... 完了
  ~略~
  ```
- **install,reinstall,remove,purge** 
    
  指定された 1 つ以上のパッケージに対して要求された処理を実行する。要求された処理は、特定のパッケージに対してパッケージ名にプラス (+) を追加してパッケージのインストールを、マイナス (-) を追加してパッケージの削除を上書きすることができる。パッケージ名にイコール (=) とパッケージのバージョンを続けることで、選択したバージョンのパッケージをインストールすることができる。また、必要な場合には、パッケージの依存関係を満たすリリースからバージョンを選択する。
  パッケージの削除はパッケージの全データを削除するが、削除の事故に備えて、通常は隠れている小さな (修正された) ユーザ設定ファイルを残す。問題が発生した際は、誤って削除したパッケージのインストール要求を発行すると、以前のようにその機能を復元する。一方、purge を呼び出すことで、既に削除したパッケージの残されたデータを削除することができる。
  
  実行例　[](変更しない)
  
  ```
  sudo apt reinstall nano
  ```


  実行結果　[](変更しない)


  ```
  パッケージリストを読み込んでいます... 完了
  依存関係ツリーを作成しています... 完了
  状態情報を読み取っています... 完了
  アップグレード: 0 個、新規インストール: 0 個、再インストール: 1 個、削除: 0 個、保留: 9 個。
  280 kB のアーカイブを取得する必要があります。
  この操作後に追加で 0 B のディスク容量が消費されます。
  取得:1 http://jp.archive.ubuntu.com/ubuntu jammy/main amd64 nano amd64 6.2-1 [280 kB]
  280 kB を 2秒 で取得しました (182 kB/s)
  (データベースを読み込んでいます ... 現在 252595 個のファイルとディレクトリがインストールされています。)
  .../archives/nano_6.2-1_amd64.deb を展開する準備をしています ...
  nano (6.2-1) で (6.2-1 に) 上書き展開しています ...
  nano (6.2-1) を設定しています ...
  man-db (2.10.2-1) のトリガを処理しています ...
  install-info (6.8-4build1) のトリガを処理しています ...
  ```
- **autoremove** 
    
  他のパッケージの依存関係を満たすために自動的にインストールされた後、依存関係の変更あるいは必要としていたパッケージが削除されたことでもう必要なくなったパッケージの削除に使用する。手動でインストールされたパッケージは、自動削除のために提案されない。
  
  実行例　[](変更しない)
  
  ```
  sudo apt autoremove
  ```


  実行結果　[](変更しない)


  ```
  パッケージリストを読み込んでいます... 完了
  依存関係ツリーを作成しています... 完了
  状態情報を読み取っています... 完了
  以下のパッケージは「削除」されます:
    docker-scan-plugin libflashrom1 libftdi1-2 libllvm13
  アップグレード: 0 個、新規インストール: 0 個、削除: 4 個、保留: 9 個。
  この操作後に 113 MB のディスク容量が解放されます。
  続行しますか? [Y/n] y
  (データベースを読み込んでいます ... 現在 252615 個のファイルとディレクトリがインストールされています。)
  docker-scan-plugin (0.23.0~ubuntu-jammy) を削除しています ...
  libflashrom1:amd64 (1.2-5build1) を削除しています ...
  libftdi1-2:amd64 (1.5-5build3) を削除しています ...
  libllvm13:amd64 (1:13.0.1-2ubuntu2.2) を削除しています ...
  libc-bin (2.35-0ubuntu3.5) のトリガを処理しています ...
  ```
- **search** 
    
  指定したパッケージの内容と、その機能を表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo apt search nano
  ```


  実行結果　[](変更しない)


  ```
  ソート中... 完了
  全文検索... 完了
  alpine-pico/jammy 2.25+dfsg1-1build1 amd64
    Simple text editor from Alpine, a text-based email client

  arduino-core-avr/jammy,jammy 1.8.4+dfsg1-1 all
    Arduino Core for AVR microcontroller

  bornagain/jammy 1.19.0-3build2 amd64
    Simulate and fit X-ray and neutron GISAS -- binary

  bornagain-doc/jammy,jammy 1.19.0-3build2 all
    Simulate and fit X-ray and neutron GISAS -- doc
  ```
- **show** 
    
  指定されたパッケージに関する情報を表示する。依存関係、インストールおよびダウンロードサイズ、パッケージが入手可能な取得元、パッケージの内容の説明などを含む。パッケージの削除をさせる前や、インストールする新しいパッケージを検索する際に、この情報を見て参考にすることができる。
  
  実行例　[](変更しない)
  
  ```
  sudo apt show nano 
  ```


  実行結果　[](変更しない)


  ```
  Package: nano
  Version: 6.2-1
  Priority: standard
  Section: editors
  Origin: Ubuntu
  Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
  Original-Maintainer: Jordi Mallach <jordi@debian.org>
  Bugs: https://bugs.launchpad.net/ubuntu/+filebug
  Installed-Size: 881 kB
  Depends: libc6 (>= 2.34), libncursesw6 (>= 6), libtinfo6 (>= 6)
  Suggests: hunspell
  Conflicts: pico
  Breaks: nano-tiny (<< 2.8.6-2)
  Replaces: nano-tiny (<< 2.8.6-2), pico
  Homepage: https://www.nano-editor.org/
  Task: standard
  Download-Size: 280 kB
  APT-Manual-Installed: yes
  APT-Sources: http://jp.archive.ubuntu.com/ubuntu jammy/main amd64 Packages
  Description: Pico にヒントを得て作られた、コンパクトで使いやすいテキストエディタ
   GNU nano は使いやすいテキストエディタで、当初は Pico の代替品として設計され ました。Pico とは、かつて non-free
   だったメーラパッケージ Pine の ncurses ベースのエディタです (現在 Pine 自体は、Apache ライセンスで Alpine
   という名 前で入手できます)。
   .
   However, GNU nano also implements many features missing in Pico, including:
    - undo/redo
    - line numbering
    - syntax coloring
    - soft-wrapping of overlong lines
    - selecting text by holding Shift
    - interactive search and replace (with regular expression support)
    - a go-to line (and column) command
    - support for multiple file buffers
    - auto-indentation
    - tab completion of filenames and search terms
    - toggling features while running
    - and full internationalization support
  ```
- **list** 
    
  一定の基準を満たすパッケージのリストを表示することができる。
  
  実行例　[](変更しない)
  
  ```
  sudo apt list nano
  ```


  実行結果　[](変更しない)


  ```
  一覧表示... 完了
  nano/jammy,now 6.2-1 amd64 [インストール済み]
  ```