---
title: "ミーティングログ/議事録の取り方についてのメモ"
author: azu
layout: post
date : 2020-04-24T10:00
category: 雑記
tags:
    - ミーティング

---

この記事はミーティングログの取り方についてのメモです。
以前書いた勉強会でのメモの取り方と似た話です。

- [勉強会でのメモの取り方について | Web Scratch](https://efcl.info/2014/07/19/study-note/)

自分は書きながら話を聞くのが習慣化しているので、こんな感じでミーティングログ(ミーティングノート)を書いていますという話です。
この記事はメモ書きなのであんまり読みやすくないです。

このログの取り方は正確さログや整形されたログを取る方法ではありません。

## 2種類のミーティングログ

自分の場合は主に2種類のミーティングログを取ることが多いです。
ミーティングの内容によってどちらで取るのかを使い分けています。

- [リアルタイムモード](#リアルタイムモードのミーティングログ)
    - 対面、リモートでのミーティング
- [回想モード](#回想モードのミーティングログ)
    - ブレスト系のミーティング([JavaScript Primer](https://jsprimer.net/)の出版に関するミーティングなど)

この記事ではこの２つのミーティングログの取り方について書いていきます。

### ミーティングログで共通のこと

どちらもログの取り方でも共通することは次の4つです。

- Markdownで書いてる([Quiver](https://happenapps.com/)を使ってるけど箇条書きの補助があるなら何でもよさそう)
- `人: ~~~` の形式の箇条書きでログを取る
- ログをトピックごとにグルーピングする
- 次のアクション/結論をまとめる

誰が話したかはミーティングログを取るときには曖昧になりやすいので、明確にするため `人: ~~~` の形式の箇条書きで書いています。
[勉強会の場合](https://efcl.info/2014/07/19/study-note/)は発表者になるので自明ですが、ミーティングの場合は曖昧になりやすいです。

## リアルタイムモードのミーティングログ

リアルタイムモードなミーティングログでは、主に次のことをやっています。

- Slackにミーティングのスレッドを作る(大体カレンダーの通知やZoomやHangoutのURLを通知する投稿のスレッドをそのまま使う)
- リアルタイムにミーティングログを書いていく
- 話の区切りや呼吸のタイミングで、Slackのスレッドにそこまでのログを投稿していく

リモートや対面のミーティングでは、リアルタイムにログも書いています。
ミーティングをしながら、誰が何を言ったのかをひたすら箇条書きで書いていく形です。
関連するドキュメントがあったら、それを追加したりもします。

```
- tom: これってどういう問題?
- alice: アクセス数が多すぎて起きる問題で、詳しくはここ見て
    - https://example.com/docs
```

合わせて、ある程度の話の塊になったり呼吸のタイミングで、そこまで書いた箇条書きをslackにペタっと貼ります。

![slack](https://efcl.info/wp-content/uploads/2020/04/23-1587646638.png)

これによって、そのコンテキストに詳しくない人も話している内容を追えるように補完する意味も持っています。
また、ミーティングに参加してなかったり遅れたりした人が、途中からミーティングに参加しやすくする/興味を持ってもらうとかの意味合いもあります。
(リモートの場合に、途中からミーティングに参加するのはものすごい壁なので)

途中でテーマが変わったらそこで新しい`# Header`を入れて、後で見やすようにグループ化しています。
リモートのミーティングだと特にそうですが、事前にアジェンダを作った方が進行しやすいので、アジェンダを元にグルーピングすることが多いです。

```markdown
## テーマA

- tom: これってどういう問題?
- alice: アクセス数が多すぎて起きる問題で、詳しくはここ見て
    - https://example.com/docs

## 次のテーマ

- tom: ...

```

ミーティングが終わったら、書いたログを`{year}-{month}-{day}: ミーティングログ`としてdocs,esa,wikiなどペタっと貼って終わりです。
ミーティングが終わって1分以内には、ミーティングログのページが作れるので、ミーティングログへのリンクをSlackのスレッドに書いてミーティング終了です。

長時間のミーティングは録画があってもそれを見るコストが高すぎるし、内容に対してパーマネントリンクを貼るのが難しいです。
そのため、要点だけでもざっくりとしたメモ書きがあれば、前回ここでそういう話をしたということをURLで表現できます。

あとミーティングログをSlackとドキュメント管理システムどちらでも検索できるようになります。

### リアルタイムログを取るときの工夫

#### 人名の省略

"誰"の部分もできるだけ簡略化しています。
基本的にハンドルネームか名前をアルファベットにして書いています。
日本語で書くと漢字の変換を考えないといけないためです。

#### 次のアクション/まとめ欄を作っておく

リアルタイムでメモを取る際に、次のミーティングまでにやることやまとめ欄を別途設けておくと良いです。
ミーティングをしたことに満足して、決定事項を忘れがちです。
そのため、リアルタイムでメモを取りながら、Todoを合わせて作っておくと、振り返るときに役に立ちます。

自分の場合は、下の方に同じように箇条書きのリストで適宜書いていくだけの形式を取っています。

```
## メモ

### テーマX

- who: ...|(カーソルは基本この辺)
- ... リアルタイムのメモ

---

## 結論

- xxx

## 次までにやること

- [ ] 誰: 何をする
```

#### 速度を優先して書くために省略する

リアルタイムログは正確さよりも速度を優先して書くことにしています。
(正確さがほしいなら録画/録音したものを使えばいいです)

typoとか細かいことは忘れて、喋ってる人が話し始めた段階で、左側に名前を置いておきます。

たとえば、kenが話し始めた(HangoutやZoomなら画面にでてきたタイミング)で、次のような状態にしています。

```
- ken: |(カーソル)
```

kenがなんか意味あることを言ったら、その内容をメモに書きます。
kenが意味ないことを言ったら、Ctrl+Deleteとかで行をまるっと削除すればいいだけです。

また、口調とか丁寧語とかそういうのは、意味がないことが多いので、入力をとにかく減らすつもりで削ってしまうのがいいと思います。
"かも"(may)とかその辺のコンテキストは削ると意味が変わってしまうので、そのまま置くことは多いです。

```
- ken: この問題は4月中に解決します?
- azu: しないかも
```

また聞き取れなかったり、話が通り過ぎてしまった場合はそれを書くのがいい気がします。
`...`とか`[snip]` とか `???` みたいな適当な記号を置いておくといい気がします。(あとから誰かに聞いて補完する)

```
- ken: この問題は[snip]?
- azu: しないかも
```

あとは、疑問形ならとりあえず語尾に`?`をつければ疑問っぽくなるのでその辺は区別できるようにしたほう見やすいです。

正確なログを残す事自体はそこまで重要視していないため、
その人が喋ってることを正確に文字起こしすることは目的にしていません。
現実的にそれをリアルタイムにやるのは難しいし、正確なものがほしいなら録画/録音をしたほうがいいと思います。

なので、その人が2~3行分のことを喋っていても、1行にまとめてしまうことが多いです。

たとえば、次のようなログを書くよりも

```
ken: 4月で一区切りですね。それで今のチームって一応4月までの予定だったと思うんですけど、4月からのチームが体制がどうなるかってなにか決まってたりするんですか? なにか変わるところってありますか?
tom: 今まだ話し合ってるところなので、確定はしてないけど、変わる部分があるかもしれない。
```

速度を優先して、次のようなログになっていることが多いです。

```
ken: 4月からチームってなにか変わります?
tom: 確定してないけど、変わるかも。
```

#### 共同でリアルタイムログをやる場合

共同でやる場合はGoogle Doc、Dropbox Paper、esaの共同編集などが使えます。

リアルタイムログは勉強会でも結構有用で、勉強会にくる人にメモを取らせるより話に集中させる効果があります。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">このイベントはDropbox Paperで議事録がリアルタイムで書かれていきます。<br>頑張ってメモを取る必要はありません。話に集中しましょう。<a href="https://t.co/kyQT96Ynrq">https://t.co/kyQT96Ynrq</a> <a href="https://twitter.com/hashtag/jserinfo?src=hash&amp;ref_src=twsrc%5Etfw">#jserinfo</a></p>&mdash; azu (@azu_re) <a href="https://twitter.com/azu_re/status/1043368586041913344?ref_src=twsrc%5Etfw">September 22, 2018</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

結構これ集中力が必要なので、慣れてる自分でも2時間ぐらいが限界です。
30分ぐらいで結構疲れが来るので、トピックごとに交代でやるのがいいと思います。

## 回想モードのミーティングログ

もう一つのメモの取り方としてミーティングが終わったあとに思い出しながらログを書く方法です。
思い出しながら書いているので回想モードと呼ぶことにします。

[4月27日に出版](https://efcl.info/2020/04/14/pre-jsprimer/)する[JavaScript Primer](https://jsprimer.net/)では、月一でミーティングをしています。
このミーティングに関するログはミーティング終了後に書いています。
そして、すべてのミーティングログをGitHub上に公開しています。

- https://github.com/asciidwango/js-primer/tree/master/meetings

このミーティングログは回想モードで作られています。
ミーティングはざっくりとしたアジェンダはありますが、ブレインストーミングに近いミーティングなので、その場でログを取るのは難しいです。

- アジェンダ: [2019-01-24 ミーティングアジェンダ · Issue #623 · asciidwango/js-primer](https://github.com/asciidwango/js-primer/issues/623)
- ミーティングログ: [2019-01-24 Meeting Notes](https://github.com/asciidwango/js-primer/blob/master/meetings/2019-01-24/README.md)

リアルタイムではミーティングログを取らない代わりに、次のようなパターンでポイントごとのログを取っています。

- その場で話していることをGitHub Issueに書く
- その場で決まったことをGitHub Issueに書く または Issueを作成する

ポイントだけをメモっておくことで、あとから振り返ったときに何のテーマを話していたかとその結論だけを追えるようになります。
そしてミーティングが終わったら、そのポイントからミーティングログを再構築していきます。
この辺は記憶との戦いの世界なので、できるだけすぐ作るようにしています。

意外とポイントだけでもわかっていると、その前後の発言は記憶にあるので補完できます。

回想モードでは次のことを意識してミーティングログを作っています

- ログを書いてトピックごとにグルーピングする
- トピックごとに結論を付ける

具体的に次のミーティングログを見てみるとわかりやすいかもしれません。

- [2019-02-25 Meeting Notes](https://github.com/asciidwango/js-primer/tree/master/meetings/2019-02-25)

それぞれのログをトピックごとにまとめて、トピックで話した結果何をするかを結論としてまとめています。
jsprimerの場合は、結論を書くときに一緒にIssueを作って結論にリンクを貼るパターンが多かったです。
結論を書くことで結局何をするかが明確になると思うので、ログ以上の価値が出てきやすいです。(ミーティング中だとどうしてもIssueまでは作れないけどちゃんとIssue化できる)

```
## 章の調整

- https://textstat-viewer.netlify.com/?gist=2a5d12080063327053fb6711fb13e04e を見ながら
- laco: ラッパーオブジェクトの章で文字数がガクッと落ちてる。移動できるか？
    - [jsprimer.net/basic/wrapper-object](https://jsprimer.net/basic/wrapper-object/)
- laco: ラッパーオブジェクトの脱線感をどうにかしたい
- azu: 移動するならデータ型の後ろとか
- azu: 何に依存してるんだろ
- laco: Stringとメソッド
...

## 結論

- assign to @azu
- [データ型とリテラル: ラッパーオブジェクトについてのコラム · Issue #674 · asciidwango/js-primer](https://github.com/asciidwango/js-primer/issues/674 "データ型とリテラル: ラッパーオブジェクトについてのコラム · Issue #674 · asciidwango/js-primer")
- [ラッパーオブジェクト: 章の移動 · Issue #675 · asciidwango/js-primer](https://github.com/asciidwango/js-primer/issues/675 "ラッパーオブジェクト: 章の移動 · Issue #675 · asciidwango/js-primer")
```

このトピック + 結論(Conclusion)を付けるログの書き方はECMAScriptの仕様についてミーティングしてる TC39 MTGのやり方を参考にしています。

- [ECMA, TC39 Meeting Notes](https://github.com/tc39/notes)

アーキテクチャの決定過程を記録するArchitecture Decision Records(ADR)も基本的にやり方は似ていると思います。

- [アーキテクチャの「なぜ？」を記録する！ADRってなんぞや？ - Qiita](https://qiita.com/fuubit/items/dbb22435202acbe48849)
- [アーキテクチャの意思決定を記録する Lightweight Architecture Decision Records について - Tbpgr Blog](http://tbpgr.hatenablog.com/entry/2017/02/22/080000)

この回想モードで書く場合は、ミーティングに書いている雑なメモ書きが結構重要です。
特に結論に関することは自分だけがわかるような形でもいいので、メモ書きをしておくと思い出しやすいです。

- リアルタイムでのメモ: [2019-02-25のミーティングアジェンダ · Issue #669 · asciidwango/js-primer](https://github.com/asciidwango/js-primer/issues/669)
- ミーティングログ: [2019-02-25 Meeting Notes](https://github.com/asciidwango/js-primer/tree/master/meetings/2019-02-25)

この回想モードは以前書いた勉強会のメモにおける"[記憶からのメモ](https://efcl.info/2014/07/19/study-note/#%E8%A8%98%E6%86%B6%E3%81%8B%E3%82%89%E3%81%AE%E3%83%A1%E3%83%A2)"とかなり近いやり方になっています。

- [勉強会でのメモの取り方について | Web Scratch](https://efcl.info/2014/07/19/study-note/)

## おわりに

勉強会やミーティングでは大体ログを取りながら話したり聞いたりすることが多いです。
なんでログを取ってるかはよくわからないですが、多分聞いたこと/話したことを頭の中から忘れたいからな気がしています。
自分の記憶容量が小さいことは常に意識してるので、外部に出力して忘れる習慣がついているのかもしれません。

普段からメモを取って公開する習慣があったので、リモートワークが中心になってもあまりやり方は変わっていません。
これは、リモートワークになってもちゃんと機能することを意識してやっていたからかもしれません。