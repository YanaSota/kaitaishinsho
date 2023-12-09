[](ファイル名はコマンド名.md)
# aa-remove-unknown
/etc/apparmor.d/に記述されていないプロファイルを削除し、そのプロファイル名を出力する。/etc/apparmor.d/にはAppArmorの設定ファイルや、ネットワークアクセスやRaw socketアクセス、ファイルへの読み書き実行などの機能への制限ルールが記述されたプロファイルなどが含まれている。実行にはroot権限が必要。

  実行例 [](変更しない)
  
  ```
  sudo aa-remove-unknown
  ```


  実行結果　[](変更しない)


  ```
  Removing 'docker-default'
  ```

### オプション一覧


- **-n**
  
  コマンドをデフォルトで実行した際に削除されるプロファイルのプロファイル名を出力する。デフォルトで実行する前にこのオプションを付けて実行し、確認することが推奨されている。

  実行例 [](変更しない)
  
  ```
  sudo aa-remove-unknown -n
  ```


  実行結果　[](変更しない)


  ```
  Would remove 'docker-default'
  ```