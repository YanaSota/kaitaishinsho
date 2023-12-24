[](ファイル名はコマンド名.md)
# pwdx
プロセスの作業ディレクトリを表示するコマンド

  実行例 [](変更しない)
  
  ```
  pwdx [PSID]
  ```
  実行結果.1　[](変更しない)


  ```
  $ ps //プロセスの確認
    PID TTY          TIME CMD
  1071025 pts/0    00:00:00 bash
  1072332 pts/0    00:00:00 ps

  $ pwdx 1071025 //bashを対象にpwdxを実行
  1071025: /home/user/
  ```



  実行結果　[](変更しない)


  ```
  $ ps aux //Linuxのシステムが動かしているプロセスを確認
  USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
  root           1  0.0  0.0 167728 13464 ?        Ss   Oct05   1:44 /lib/systemd/systemd --system --deserialize 71
  root           2  0.0  0.0      0     0 ?        S    Oct05   0:00 [kthreadd]
  root           3  0.0  0.0      0     0 ?        I<   Oct05   0:00 [rcu_gp]
  root           4  0.0  0.0      0     0 ?        I<   Oct05   0:00 [rcu_par_gp]
  root           5  0.0  0.0      0     0 ?        I<   Oct05   0:00 [slub_flushwq]
  ・
  ・
  ・

 
  $ sudo pwdx 1
 1: / 
  $ sudo pwdx 2
 2: /
  $ sudo pwdx 3
 3: /
  $ sudo pwdx 4
 4: /
  $ sudo pwdx 5
 5: /
 ・
 ・
 ・
  ```
この例では、Linuxのシステムが自動的に実行しているプロセスに対してpwdxを行った。このことからシステムが動かしているプロセスは/(ルート)で動かしていることがわかる。