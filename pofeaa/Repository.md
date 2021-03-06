---
layout: pofeaa
title: Repository
---

原文: http://www.martinfowler.com/eaaCatalog/repository.html

**by Edward Hieatt and Rob Mee**

*ドメインオブジェクトにアクセスするためのコレクション ライクなインターフェースを使って、ドメイン—データ マッピングレイヤ間の仲介を行う。*

解説の全文は『PofEAA』 **322** ページを参照。

![](http://www.martinfowler.com/eaaCatalog/repositorySketch.gif)

複雑なドメインモデルのあるシステムは、ドメイン オブジェクトをデータベースアクセスコードから分離するDataMapper(165)などのレイヤの恩恵を受けやすい。
そのようなシステムでは、クエリ構文を構築するマッピングレイヤ上にもうひとつ抽象的なレイヤを設けると良い。
ドメインのクラスやクエリが膨大になれば、このことは重要になってくる。
特にこの場合、レイヤを追加することでクエリロジックの重複が最小化される。

Repositoryはメモリ内ドメインオブジェクトのコレクションのように振る舞い、
ドメイン—データ マッピング レイヤの仲介を行う。 クライアント
オブジェクトはクエリ構文を明示的に作成し、Repositoryにsubmitする。
オブジェクトは、シンプルなオブジェクトのコレクションの形で
Repositoryに追加または削除される。
Repositoryによりカプセル化されたマッピングコードは、
その裏側で適切に処理を行う。
Repositoryはデータストアに保存されたオブジェクトの集合をカプセル化し、そこで操作が実行されていると考えるとよいだろう。そうすることで、永続化レイヤにオブジェクト指向的なビューを提供している。
Repositoryはまた、ドメイン—データマッピングレイヤ間の明確な分離、
一方向の依存性を実現させてくれる。
