
[](tsort.md)
# tsort
トポロジカルソートを行うコマンドである。
トポロジカルソートは、有向グラフの頂点を一定の順序で並べる方法であり、ジョブのスケジューリング問題に利用される。


![](https://raw.githubusercontent.com/YanaSota/kaitaishinsho/main/goto/%E3%83%88%E3%83%9D%E3%83%AD%E3%82%B8%E3%82%AB%E3%83%AB%E3%82%BD%E3%83%BC%E3%83%88.png 

"今回用いる処理グラフ")
　　　　　　今回用いる処理グラフ
上のグラフをテキストに落とし込んだものは下のものである。以下を使用する
```
a b
a e
d e
b c
c f
e c
e f
```
<br>

実行例 [](変更しない)

```
tsort graph.txt
```

実行結果 [](変更しない)

```
a
d
b
e
c
f
```
### オプション一覧
    なし
