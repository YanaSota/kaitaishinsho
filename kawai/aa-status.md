[](ファイル名はコマンド名.md)
# aa-status
AppArmorプロファイルの状態を表示するコマンド。デフォルトでは、--verboseオプションと同じ情報が表示される。

  実行例 [](変更しない)
  
  ```
  aa-status
  ```


  実行結果　[](変更しない)


  ```
  apparmor module is loaded.
  You do not have enough privilege to read the profile set.
  ```

### オプション一覧


- **--enabled**
  
  AppArmorが利用不可の場合にエラーコードを表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --enabled
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--profiled** 
    
  読み込まれたAppArmorポリシーの数を表示する。
  
  実行例　[](変更しない)
  
  ```
  aa-status --profiled
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--enforced**
  
  読み込まれた強制AppArmorポリシーの数を表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --enforced
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--complaining**
  
  読み込まれた非強制AppArmorポリシーの数を表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --complaining
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--kill**
  
  ポリシー違反時にタスクを強制終了する強制AppArmorポリシーを読み込み、数を表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --kill
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--special-unconfined**
  
  特別な無制限モードにある、非強制AppArmorポリシーを読み込み、数を表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --special-unconfined
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--process-mixed**
  
  異なるモードのプロファイルを持つプロファイルスタックによって制限されたプロセスの数を表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --process-mixed
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--verbose**
  
  AppArmorプロファイルの状態を表示する

  実行例 [](変更しない)
  
  ```
  aa-status --verbose
  ```


  実行結果　[](変更しない)


  ```
  apparmor module is loaded.
  You do not have enough privilege to read the profile set.
  ```
- **--json**
  
  AppArmorプロファイルの状態を、JSON形式で表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --json
  ```


  実行結果　[](変更しない)


  ```
  
  ```
- **--pretty-json**
  
  AppArmorプロファイルの状態を、人間も読める形式で表示する。

  実行例 [](変更しない)
  
  ```
  aa-status --pretty-json
  ```


  実行結果　[](変更しない)


  ```
  
  ```
