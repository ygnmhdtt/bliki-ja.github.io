http://martinfowler.com/bliki/MoreVersionControl.html

みんなはもう使ってるだろうけど、
バージョンコントロールはもっと使われてもいいように思う。
ソフトウェア開発者じゃないひとたちは、
バージョンコントロールをほとんど使っていない。
ソフトウェア開発者なら知ってるだろうけど、
バージョンコントロールは共同作業のためのグレートなメカニズムだ。
複数人がひとつのソフトウェアシステムを使って一緒に作業することができる。
バージョンコントロールがもっと広く使われるようになると、
どんなメリットがあるだろう？

業務でバージョンコントロールシステムを使うと
非常に実用的であるということが分かる。
Subversionはフリーに使えるバージョンコントロールシステムで、
バイナリフォーマットも簡単に扱えるし、
CVSで制限されていた部分も数多く扱えるようになっている。
ディスクスペースは安いから、みんなの作業ディレクトリをすべてバージョンコントロールシステム管理下に置くこともできるだろう。

今のところ、一番の障壁となっているのは、
バージョンコントロールを扱うアプリケーションやツールが十分ではないという点だろう。
MS Wordには以前から変更履歴機能がついているが、
バージョンコントロールの機能まではつかないみたいだ。
diffやmergeなどのバージョンコントロールの機能は、どういった感じになれば、
みんなが使っている一般的なアプリケーションのためになるのだろうか。
どうすれば、バージョンコントロールの考え方がそういったアプリケーションに取り入れられるのだろうか？

私はVisioなどを使って設計図を作っている。
diffを使うと、バージョン間でどこが変わったのか、
他のひとがどこに変更を加えたのかが分かる。
これは素晴らしいことだと思う。
だが、こういったものから本当に価値を得ようとするなら、
[[セマンティックdiff|SemanticDiff]]をサポートしたツールが必要になるかもしれない。

全員が[[subversion|http://subversion.tigris.org/]]を使用できるオープンソースコミュニティでは、
このセマンティックdiffの方向に転換するいい機会かもしれない。
ここらへんのアイデアは共同作業を促進すると思う。