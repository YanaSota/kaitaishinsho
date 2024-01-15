
[](uclampset.md)
# uclampset
uclampsetは、既存のPIDの利用クランピング属性を設定または取得する。
LinuxカーネルのCPUクランプ制御のためのユーティリティである。CPUクランプは、特定のプロセスやプロセスグループに対してCPU使用率の制限を設定する機能である。
プロセスの上限を1024未満に設定すると、タスクの実行時に常にこの利用率から始まるので、実質的にタスクの上限が設定される。
利用率の全範囲は[0:1024]。-1は特別な値であり、システムをデフォルトにリセットするために使われる。

実行例 [](変更しない)

```
uclampset [-m 最小値] [-M 最大値] 起動したいコマンド [ arguments ]
```

実行結果 [](変更しない)

```
状況に応じて異なるため省略
```
### オプション一覧
    
- **-a, --all-tasks**

  指定されたpidのすべてのタスク（スレッド）を操作、確認する。

  実行例 [](変更しない)

  ```
  uclampset -p 2271 -a
  ```

  実行結果 [](変更しない)

  ```
  firefox (2271) util_clamp: min: 100 max: 1024
  glean.dispatche (2368) util_clamp: min: 0 max: 1024
  IPC I/O Parent (2370) util_clamp: min: 0 max: 1024
  Timer (2371) util_clamp: min: 0 max: 1024
  Netlink Monitor (2372) util_clamp: min: 0 max: 1024
  Socket Thread (2373) util_clamp: min: 0 max: 1024
  IPDL Background (2374) util_clamp: min: 0 max: 1024
  HTML5 Parser (2376) util_clamp: min: 0 max: 1024
  JS Watchdog (2378) util_clamp: min: 0 max: 1024
  TaskCon~ller #0 (2380) util_clamp: min: 0 max: 1024
  TaskCon~ller #1 (2381) util_clamp: min: 0 max: 1024
  TaskCon~ller #2 (2382) util_clamp: min: 0 max: 1024
  TaskCon~ller #3 (2383) util_clamp: min: 0 max: 1024
  Cache2 I/O (2384) util_clamp: min: 0 max: 1024
  Cookie (2385) util_clamp: min: 0 max: 1024
  Worker Launcher (2389) util_clamp: min: 0 max: 1024
  pool-spawner (2390) util_clamp: min: 0 max: 1024
  gmain (2391) util_clamp: min: 0 max: 1024
  gdbus (2392) util_clamp: min: 0 max: 1024
  Softwar~cThread (2415) util_clamp: min: 0 max: 1024
  CanvasRenderer (2416) util_clamp: min: 0 max: 1024
  Renderer (2417) util_clamp: min: 0 max: 1024
  WRWorker#0 (2418) util_clamp: min: 0 max: 1024
  WRWorker#1 (2419) util_clamp: min: 0 max: 1024
  WRWorker#2 (2420) util_clamp: min: 0 max: 1024
  WRWorker#3 (2421) util_clamp: min: 0 max: 1024
  WRWorkerLP#0 (2422) util_clamp: min: 0 max: 1024
  WRWorkerLP#1 (2423) util_clamp: min: 0 max: 1024
  WRWorkerLP#2 (2424) util_clamp: min: 0 max: 1024
  WRWorkerLP#3 (2425) util_clamp: min: 0 max: 1024
  Compositor (2426) util_clamp: min: 0 max: 1024
  firefox:disk$0 (2427) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (2428) util_clamp: min: 0 max: 1024
  ImageIO (2429) util_clamp: min: 0 max: 1024
  firefox:disk$0 (2430) util_clamp: min: 0 max: 1024
  Permission (2431) util_clamp: min: 0 max: 1024
  Breakpad Server (2432) util_clamp: min: 0 max: 1024
  SandboxReporter (2433) util_clamp: min: 0 max: 1024
  IPC Launch (2434) util_clamp: min: 0 max: 1024
  QuotaManager IO (2438) util_clamp: min: 0 max: 1024
  FSBroker2435 (2444) util_clamp: min: 0 max: 1024
  TRR Background (2448) util_clamp: min: 0 max: 1024
  StyleThread#0 (2449) util_clamp: min: 0 max: 1024
  StyleThread#1 (2450) util_clamp: min: 0 max: 1024
  StyleThread#2 (2451) util_clamp: min: 0 max: 1024
  GMPThread (2454) util_clamp: min: 0 max: 1024
  ImageBridgeChld (2455) util_clamp: min: 0 max: 1024
  FSBroker2452 (2456) util_clamp: min: 0 max: 1024
  ProcessHangMon (2457) util_clamp: min: 0 max: 1024
  WRScene~ilder#1 (2460) util_clamp: min: 0 max: 1024
  WRScene~derLP#1 (2461) util_clamp: min: 0 max: 1024
  WRRende~ckend#1 (2462) util_clamp: min: 0 max: 1024
  AudioIP~ver RPC (2478) util_clamp: min: 0 max: 1024
  AudioIP~allback (2479) util_clamp: min: 1024 max: 1024
  AudioIP~ion RPC (2480) util_clamp: min: 0 max: 1024
  threaded-ml (2482) util_clamp: min: 0 max: 1024
  dconf worker (2484) util_clamp: min: 0 max: 1024
  sqldb:p~lite #1 (2486) util_clamp: min: 0 max: 1024
  sqldb:c~lite #2 (2558) util_clamp: min: 0 max: 1024
  sqldb:p~lite #3 (2559) util_clamp: min: 0 max: 1024
  FSBroker2572 (2573) util_clamp: min: 0 max: 1024
  URL Classifier (2661) util_clamp: min: 0 max: 1024
  MemoryPoller (2716) util_clamp: min: 0 max: 1024
  glean.mps (2720) util_clamp: min: 0 max: 1024
  FSBroker2721 (2722) util_clamp: min: 0 max: 1024
  FSBroker2736 (2737) util_clamp: min: 0 max: 1024
  sqldb:p~lite #4 (2783) util_clamp: min: 0 max: 1024
  sqldb:p~lite #5 (2785) util_clamp: min: 0 max: 1024
  sqldb:f~lite #6 (2787) util_clamp: min: 0 max: 1024
  sqldb:c~lite #7 (2841) util_clamp: min: 0 max: 1024
  RemoteLzyStream (2844) util_clamp: min: 0 max: 1024
  sqldb:p~lite #8 (2845) util_clamp: min: 0 max: 1024
  LS Thread (2849) util_clamp: min: 0 max: 1024
  DOM Worker (2850) util_clamp: min: 0 max: 1024
  FSBroker2856 (2857) util_clamp: min: 0 max: 1024
  FSBroker2887 (2888) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (2960) util_clamp: min: 0 max: 1024
  SwComposite (34389) util_clamp: min: 0 max: 1024
  WRScene~ilder#2 (34390) util_clamp: min: 0 max: 1024
  WRScene~derLP#2 (34391) util_clamp: min: 0 max: 1024
  WRRende~ckend#2 (34392) util_clamp: min: 0 max: 1024
  speechd init (34553) util_clamp: min: 0 max: 1024
  FSBroker34587 (34588) util_clamp: min: 0 max: 1024
  FSBroker34575 (34589) util_clamp: min: 0 max: 1024
  FSBroker34602 (34604) util_clamp: min: 0 max: 1024
  SwComposite (34735) util_clamp: min: 0 max: 1024
  WRScene~ilder#3 (34736) util_clamp: min: 0 max: 1024
  WRScene~derLP#3 (34737) util_clamp: min: 0 max: 1024
  WRRende~ckend#3 (34738) util_clamp: min: 0 max: 1024
  threaded-ml (34740) util_clamp: min: 0 max: 1024
  SwComposite (36416) util_clamp: min: 0 max: 1024
  WRScene~ilder#5 (36417) util_clamp: min: 0 max: 1024
  WRScene~derLP#5 (36418) util_clamp: min: 0 max: 1024
  WRRende~ckend#5 (36419) util_clamp: min: 0 max: 1024
  FSBroker36476 (36477) util_clamp: min: 0 max: 1024
  FSBroker36522 (36523) util_clamp: min: 0 max: 1024
  FSBroker36558 (36559) util_clamp: min: 0 max: 1024
  DOMCacheThread (36578) util_clamp: min: 0 max: 1024
  FSBroker36590 (36593) util_clamp: min: 0 max: 1024
  FSBroker36898 (36899) util_clamp: min: 0 max: 1024
  threaded-ml (37085) util_clamp: min: 0 max: 1024
  DOM Worker (37094) util_clamp: min: 0 max: 1024
  SwComposite (37152) util_clamp: min: 0 max: 1024
  WRScene~ilder#6 (37153) util_clamp: min: 0 max: 1024
  WRScene~derLP#6 (37154) util_clamp: min: 0 max: 1024
  WRRende~ckend#6 (37155) util_clamp: min: 0 max: 1024
  SwComposite (37678) util_clamp: min: 0 max: 1024
  WRScene~ilder#7 (37679) util_clamp: min: 0 max: 1024
  WRScene~derLP#7 (37680) util_clamp: min: 0 max: 1024
  WRRende~ckend#7 (37681) util_clamp: min: 0 max: 1024
  FSBroker37696 (37698) util_clamp: min: 0 max: 1024
  FSBroker38098 (38099) util_clamp: min: 0 max: 1024
  SwComposite (38178) util_clamp: min: 0 max: 1024
  WRScene~ilder#8 (38179) util_clamp: min: 0 max: 1024
  WRScene~derLP#8 (38180) util_clamp: min: 0 max: 1024
  WRRende~ckend#8 (38181) util_clamp: min: 0 max: 1024
  SwComposite (38184) util_clamp: min: 0 max: 1024
  WRScene~ilder#9 (38185) util_clamp: min: 0 max: 1024
  WRScene~derLP#9 (38186) util_clamp: min: 0 max: 1024
  WRRende~ckend#9 (38187) util_clamp: min: 0 max: 1024
  SwComposite (38730) util_clamp: min: 0 max: 1024
  WRScene~lder#12 (38731) util_clamp: min: 0 max: 1024
  WRScene~erLP#12 (38732) util_clamp: min: 0 max: 1024
  WRRende~kend#12 (38733) util_clamp: min: 0 max: 1024
  FSBroker39201 (39202) util_clamp: min: 0 max: 1024
  FSBroker39401 (39402) util_clamp: min: 0 max: 1024
  FSBroker39438 (39439) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (39478) util_clamp: min: 0 max: 1024
  FSBroker39480 (39482) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (39525) util_clamp: min: 0 max: 1024
  FSBroker39562 (39563) util_clamp: min: 0 max: 1024
  FSBroker39638 (39639) util_clamp: min: 0 max: 1024
  FSBroker39676 (39677) util_clamp: min: 0 max: 1024
  FSBroker39712 (39724) util_clamp: min: 0 max: 1024
  DOMCacheThread (39785) util_clamp: min: 0 max: 1024
  FSBroker39822 (39828) util_clamp: min: 0 max: 1024
  FSBroker39891 (39892) util_clamp: min: 0 max: 1024
  FSBroker39970 (39971) util_clamp: min: 0 max: 1024
  FSBroker39977 (39980) util_clamp: min: 0 max: 1024
  FSBroker40035 (40036) util_clamp: min: 0 max: 1024
  FSBroker40066 (40067) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (40183) util_clamp: min: 0 max: 1024
  FSBroker40599 (40601) util_clamp: min: 0 max: 1024
  DNS Res~er #782 (40638) util_clamp: min: 0 max: 1024
  DNS Res~er #784 (40777) util_clamp: min: 0 max: 1024
  DNS Res~er #785 (41061) util_clamp: min: 0 max: 1024
  DNS Res~er #787 (41093) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (41145) util_clamp: min: 0 max: 1024
  FSBroker41792 (41794) util_clamp: min: 0 max: 1024
  SwComposite (41890) util_clamp: min: 0 max: 1024
  WRScene~lder#16 (41891) util_clamp: min: 0 max: 1024
  WRScene~erLP#16 (41892) util_clamp: min: 0 max: 1024
  WRRende~kend#16 (41893) util_clamp: min: 0 max: 1024
  FSBroker41913 (41914) util_clamp: min: 0 max: 1024
  FSBroker41974 (41981) util_clamp: min: 0 max: 1024
  firefox:gdrv0 (42078) util_clamp: min: 0 max: 1024
  DNS Res~er #793 (181174) util_clamp: min: 0 max: 1024
  DNS Res~er #794 (327352) util_clamp: min: 0 max: 1024
  BgIOThr~l #1889 (685858) util_clamp: min: 0 max: 1024
  Backgro~ #11771 (692244) util_clamp: min: 0 max: 1024
  FSBroker692291 (692292) util_clamp: min: 0 max: 1024
  StreamT~s #2310 (692341) util_clamp: min: 100 max: 1024
  FSBroker692342 (692343) util_clamp: min: 100 max: 1024
  FSBroker692371 (692372) util_clamp: min: 100 max: 1024
  ```

- **-p, --pid <pid>**

  既存の指定されたpidを操作し、新しくタスクを起動しない。

  実行例 [](変更しない)

  ```
  uclampset -p 2271
  ```

  実行結果 [](変更しない)

  ```
  firefox (2271) util_clamp: min: 0 max: 1024
  ※PID2271に当たるプロセスで使えるcpuの下上限を確認。
  ```

- **-s, --system**

  システム全体の使用率クランプを設定または取得する。

  実行例 [](変更しない)

  ```
  uclampset -s
  ```

  実行結果 [](変更しない)

  ```
  System util_clamp: min: 1024 max: 1024
  ```

- **-R, --reset-on-fork**

  SCHED_FLAG_RESET_ON_FORKフラグを設定する。

  実行例 [](変更しない)

  ```
  uclampset -R -m 0 -M 100 top
  ```

  実行結果 [](変更しない)

  ```
  top - 03:38:29 up 26 days, 12:46,  9 users,  load average: 0.22, 0.21, 0.18
  Tasks: 268 total,   1 running, 267 sleeping,   0 stopped,   0 zombie
  ~~~省略~~~
  見かけ上の変化はない
  ```

- **-v, --verbose**

  ステータス情報の表示をする。

  実行例 [](変更しない)

  ```
  $ uclampset -v -m 0 -M 100 top
  ```

  実行結果 [](変更しない)

  ```
  top (692978) util_clamp: min: 0 max: 100 ※此処の部分
  top - 03:34:47 up 26 days, 12:42,  9 users,  load average: 0.21, 0.24, 0.19
  Tasks: 269 total,   1 running, 268 sleeping,   0 stopped,   0 zombie
  %Cpu(s):  3.3 us,  1.0 sy,  0.0 ni, 95.6 id,  0.1 wa,  0.0 hi,  0.0 si,
  ~~~省略~~~
  ```