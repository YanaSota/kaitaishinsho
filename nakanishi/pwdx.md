[](ファイル名はコマンド名.md)
# pwdx
プロセスの作業ディレクトリを表示するコマンド

  実行例 [](変更しない)
  
  ```
  pwdx 1
  ```


  実行結果　[](変更しない)


  ```
  $ ps aux /プロセスの確認
  USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
  root           1  0.0  0.0 167832 13452 ?        Ss   Oct05   1:39 /lib/systemd/systemd --system --deserialize 71
  root           2  0.0  0.0      0     0 ?        S    Oct05   0:00 [kthreadd]
  root           3  0.0  0.0      0     0 ?        I<   Oct05   0:00 [rcu_gp]
  root           4  0.0  0.0      0     0 ?        I<   Oct05   0:00 [rcu_par_gp]
  root           5  0.0  0.0      0     0 ?        I<   Oct05   0:00 [slub_flushwq]
  root           6  0.0  0.0      0     0 ?        I<   Oct05   0:00 [netns]
  root           8  0.0  0.0      0     0 ?        I<   Oct05   0:00 [kworker/0:0H-events_highpri]
  root          10  0.0  0.0      0     0 ?        I<   Oct05   0:00 [mm_percpu_wq]
  root          11  0.0  0.0      0     0 ?        S    Oct05   0:00 [rcu_tasks_rude_]
  root          12  0.0  0.0      0     0 ?        S    Oct05   0:00 [rcu_tasks_trace]
  root          13  0.0  0.0      0     0 ?        S    Oct05   0:01 [ksoftirqd/0]
  root          14  0.0  0.0      0     0 ?        I    Oct05   3:25 [rcu_sched]
  root          15  0.0  0.0      0     0 ?        S    Oct05   0:33 [migration/0]
  root          16  0.0  0.0      0     0 ?        S    Oct05   0:00 [idle_inject/0]
  root          18  0.0  0.0      0     0 ?        S    Oct05   0:00 [cpuhp/0]
  root          19  0.0  0.0      0     0 ?        S    Oct05   0:00 [cpuhp/1]
  ・
  ・
  ・

  $ sudo pwdx 1
 1: / //PIDが1の作業ディレクトリを表示する
  ```
この例では、PIDが1のプロセスの作業ディレクトリを表示しており、結果は/（ルート）ディレクトリであることがわかる。
