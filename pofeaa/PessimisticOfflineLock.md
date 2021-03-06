---
layout: pofeaa
title: 悲観的オフラインロック
---

原文: http://www.martinfowler.com/eaaCatalog/pessimisticOfflineLock.html

**by David Rice**

*同時にデータにアクセスするビジネストランザクションを1つだけにすることで並行するビジネストランザクションの競合を避ける*

解説の全文は『PofEAA』 **426** ページを参照。

![](http://www.martinfowler.com/eaaCatalog/PessimisticSketch.gif)

オフライン並行性により複数のリクエストを跨いだビジネストランザクションによるデータの操作が行われるので、最も簡単なアプローチは、ビジネストランザクション全体で1つのシステムトランザクションを開くことだと思われる。しかし残念ながら、トランザクションシステムはトランザクションが長くなるとうまく動かないのでこれがいつもうまくいくとは限らない。このため、データへの並行アクセスを管理するためのデバイスで複数のシステムトランザクションを使わないといけない。

まず最初に試みるべきアプローチは[楽観的オフラインロック](OptimisticOfflineLock)(416)だ。でもこのパターンには問題がある。何人かが同じビジネストランザクションで同じデータにアクセスするとしよう。一人は簡単にコミットできるが、他はコンフリクトを起こして失敗してしまう。コンフリクトはビジネストランザクションの最後にならないと分からないので犠牲者(訳注：アボートされるトランザクション)は最後の瞬間にならないと全ての処理が失敗したことが分からないのでトランザクションの処理を全て実行して時間も浪費してしまう。もし、長いビジネストランザクション上でこんなことが起こったら、システムはすぐに閑古鳥が鳴いてしまうだろう。

悲観的オフラインロックではこれらを全て回避することでコンフリクトを防ぐ。悲観的オフラインロックではビジネストランザクションがあるデータ片を使う前に強制的にロックをかけさせる。その結果、通常は、一旦ビジネストランザクションが始まると、並行制御によってつき返されることなくかなり確実にトランザクションを完了することができる。

translated by money@andore.com
