---
layout: pofeaa
title: 具象テーブル継承
---

原文: http://www.martinfowler.com/eaaCatalog/concreteTableInheritance.html


*クラスの継承構造を、ヒエラルキー内の具象クラスごとに1個のテーブルを使って表現する。*

解説の全文は『PofEAA』 **293** ページを参照。

![](http://www.martinfowler.com/eaaCatalog/leafInheritanceTableSketch.gif)


オブジェクト純正主義者は言う。関係データベースは継承をサポートしない—事実、それがオブジェクト関係マッピングを難しくしている。オブジェクトのインスタンスの視点からテーブルのことを考えてみると、メモリ上にある各オブジェクトをデータベースの単一行にマップするのは賢いやり方だ。これは[具象テーブル継承](ConcreteTableInheritance) を意味していて、継承ヒエラルキー内の具象クラスそれぞれに対してテーブルが存在する。



このパターンを名付けるのには少してこずったことを告白しておく。多くの人はそれをリーフ指向だと考える。それは、ヒエラルキーの中のリーフクラスごとに1個のテーブルを持つのが普通だからだ。そのロジックに従えばリーフテーブル継承と呼ぶこともできた。また "leaf" という用語もこのパターンにはよく使われる。しかし厳密に言えば、リーフではない具象クラスも通常同じようにテーブルをもつので、直感的な用語ではなくとも正確になるようにした。

translated by cept <ceptcept@hotmail.com>