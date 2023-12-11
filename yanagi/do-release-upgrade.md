[](ファイル名はコマンド名.md)
# do-release-upgrade
新しいUbuntuがリリースされた際に最新のバージョンにアップグレードするために使用
今回はアップグレードしないためPromptを変更しない

Promptはアップグレード中に表示される質問や確認のことを示す

通常ルート権限で実行する

  実行例 [](変更しない)
  
  ```
  sudo do-release-upgrade
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
入手可能なLTSの開発版はありません。
最新の非LTS開発リリースにアップグレードする
/etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```


### オプション一覧




- **-d**
  
  サポートされている最新のリリースを使用している場合、開発版リリースにアップグレードする

  実行例 [](変更しない)
  
  ```
  sudo do-release-upgrade -d
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  アップグレードの前に入手可能なすべてのアップデートをインストールしてください。
  ```
- **-p** 
    
  アップグレードソフトウェアを使って$distro-proposedから最新のリリースへのアップグレードを試す
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade -p
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```
- **-m** 
    
  特別なアップグレードモードを実行する。現在、デスクトップシステムの標準的なアップグレードを行う
  'desktop'または'server'オプションがある
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade -m desktop
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```
- **-f** 
    
  特定のフロントエンドで実行
  非対話型のアップグレードになり、自動処理されるため、アップグレードがスムーズに進行される場合にのみ、このオプションを使用するべき
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade -f server
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```
- **-c** 
    
  新しいディストリビューション・リリースが利用可能かどうかチェックし、終了コードで結果を通知する
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade -c
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```
- **--data-dir** 
    
  データファイルの含まれるディレクトリ
  
  実行例　[](変更しない)
  
  ```
  sudo -do-release-upgrade --data-dir desktop
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```
- **--allow-third-party** 
    
  サードパーティのミラーとリポジトリをコメントアウトする代わりに有効にしてアップグレードを試す
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade --allow-third-party
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```
- **-q** 
    
  アップグレードプロセスの出力が最小限に抑えられ、進行状況や詳細な情報が表示されない
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade -q
  ```


  実行結果　[](変更しない)


  ```
  表示されない
  ```
- **-e** 
    
  アップグレードプロセスがエクスプレスモードで実行され、エクスプレスモードでは、ユーザの介入なしでアップグレードが進行し、デフォルトの設定がされる
  
  実行例　[](変更しない)
  
  ```
  sudo do-release-upgrade -e desktop
  ```


  実行結果　[](変更しない)


  ```
  新しい ubuntu のリリースをチェックしています
  入手可能なLTSの開発版はありません。
  最新の非LTS開発リリースにアップグレードする
  /etc/update-manager/release-upgradesにPrompt=normalとセットしてください。
  ```