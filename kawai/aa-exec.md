[](ファイル名はコマンド名.md)
# aa-exec
指定したAppArmor(Linuxのセキュリティプロファイルを結びつけることで、ネットワークアクセスやRaw socketアクセス、ファイルへの読み書き実行などの機能に制限をかけることができるプログラム。例えば、あるプログラムに対して、参照しかしないファイルへの書き込み、利用するはずがないファイルへのアクセス、関係がない別のプログラムの呼び出しを禁止できる。"/etc/apparmor/parser.conf"に記述された通りに制限がかけられる。)プロファイルや、指定したnamespace(イメージとしてはコンテナに近い。OS起動時にはデフォルトのnamespaceが存在し、全てのプロセスはデフォルトのnamespaceに属している。プロセスの起動時に独立したnamespaceで実行する指定を行うと、そのプロセスは別のnamespaceで実行できる。独立したnamespaceで実行することで、namespaceごとにドメイン名を持てたり、namespaceごとにマウント操作を行えたり、namespaceごとに各種ネットワークリソースを持つことができたりする。)で、特定のプログラムを起動するためのコマンド。namespaceとプロファイルの両方を指定した場合、新しいnamespace内でプロファイルの制限を受けることになる。namespaceのみを指定した場合、現在の制約のプロファイル名が使用される。プロファイルもnamespaceも指定しない場合、aa-execコマンドなしで実行された場合と同様の実行結果となる。root権限が必要。

  実行例 [](変更しない)
  
  ```
  sudo aa-exec /bin/aa-enabled
  ```


  実行結果　[](変更しない)


  ```
  Yes
  ```

### オプション一覧


- **-p "PROFILE"**
  
  指定したプロファイルでコマンドを制限して実行する。

  実行例 [](変更しない)
  
  ```
  sudo aa-exec -p /usr/bin/evince aa-enabled
  ```


  実行結果　[](変更しない)


  ```
  Yes
  ```
- **-n "NAMESPACE"** 
    
  指定したnamespace内のプロファイルでコマンドを制限して実行する。
  
  実行例　[](変更しない)
  
  ```
  sudo aa-exec -n ns1 aa-enabled
  ```


  実行結果　[](変更しない)


  ```
  Yes
  ```
- **-i** 
    
  現在のプロファイルに従ってコマンドを制限して実行する。このオプションを実行する前に指定したいプロファイルに遷移しておく必要がある。
  
  実行例　[](変更しない)
  
  ```
  sudo aaa-exec -i aa-enabled
  ```


  実行結果　[](変更しない)


  ```
  Yes
  ```
- **-v** 
    
  実行するコマンドを表示する。
  
  実行例　[](変更しない)
  
  ```
  sudo aa-exec -v aa-enabled
  ```


  実行結果　[](変更しない)


  ```
  [3037] exec aa-enabled
  Yes
  ```
- **-d** 
    
  実行するコマンドとエラーコードを表示する
  
  実行例　[](変更しない)
  
  ```
  sudo aa-exec -d -- cd aaaaaaaaaa
  ```


  実行結果　[](変更しない)


  ```
  [3911] aa-exec: ERROR: Failed to execute "cd": No such file or directory
  ```
- **--** 
    
  --以前のオプションを終了させ、--以降の引数はコマンドの引数として扱われる。aa-execによって呼び出されるコマンドに引数を渡す場合に便利。
  
  実行例　[](変更しない)
  
  ```
  sudo aa-exec -d -- cd aaaaaaaaaa
  ```


  実行結果　[](変更しない)


  ```
  [3911] aa-exec: ERROR: Failed to execute "cd": No such file or directory
  ```
