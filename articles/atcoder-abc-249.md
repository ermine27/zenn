---
title: "AtCoder Beginner Contest 249 メモ(A-D)"
emoji: "🐥"
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-05-01 22:56"
---

AtCoder Beginner Contest 249 メモ(A-D)

# 今回の結果
3AC（40分）

D問題が60分かけても解き方、というか問題の正確な意味を理解できず終了。
初めてパフォーマンスが800を超えた。

# A - Jogging

## 問題
https://atcoder.jp/contests/abc249/tasks/abc249_a

Difficulty:103
A問題で100 overは滅多にない。
問題文のまま処理を書くのではなく、どう実装するかを組み立てる必要がある点が今までのA問題と比べると難しいと感じた。


## 参加中に考えたこと
高橋君、青木君それぞれのX秒後の移動距離を計算して比較すればいいんだけど、「休む」をどう扱うかというところを考える必要がある。
1サイクルの移動距離を基準にするという非効率な方法でやってしまったので、A問題なのに無駄に長い時間をかけてしまった…。こういうところがまだまだ未熟。

## 考察
正攻法としては経過した秒数をインクリメントしながらループを回して、進んでいるか休んでいるかを判定して移動距離を足していけば距離は計算できた。

公式の解説には、進んだ時間と休んだ時間を合わせた1周期の時間を使えば、

周期数 q = X / (A + C)

距離 = A * B * q + min(A, X-(A+C) * q ) * B

で、ループなしで解く方法が書かれていた。なるほどー。

  　

# B - Perfect String

## 問題
https://atcoder.jp/contests/abc249/tasks/abc249_b
Difficulty:47
A問題より簡単。

## 参加中に考えたこと

素晴らしい文字列の条件が３つあるけど、大文字が現れるか小文字が現れるかは１つのループの中で判定できるので、

1. 大文字と小文字の両方が使われている
2. 全ての文字が相違なる

の２つを別々に処理する。

1.は大文字・小文字それぞれが使われたかのフラグを持っておいて、最後に両方のフラグが偽ならNoを返して終了。
大文字・小文字の判定はisupper()とislower()で。

2.については制約が 1 <= |S| <= 100 なので二重ループで解ける。

## 考察
2.の部分は連想配列に使われた文字をキーにカウントしていけばO(N)でもできるので、1つのループの中に全ての判定を入れることもできる。



# C - Just K

## 問題
https://atcoder.jp/contests/abc249/tasks/abc249_c
Difficulty:528
解くのに必要なアルゴリズムさえ知っていれば難しくはない。

## 参加中に考えたこと
N個の中から任意の個数を選ぶことと、N<=15と小さいことから、O(2^N)の計算量の方法でも使える。
となるとbit全探索で方針は決まったので、あとはループの中でKの数を集計する処理を追加するだけ。

C問題が10分でACできたのは今までで最短だった。

## 考察
DFS（深さ優先探索）で解く方法こともできる。
提出結果を見る感じでは9割近くがbit全探索で解いてる感じだった。


# D - Index Trio

## 問題
https://atcoder.jp/contests/abc249/tasks/abc249_d
Difficulty:983


## 参加中に考えたこと
条件のai/aj = akは式変形して、ai = aj * ak とする。
するとAは整数列なのでaiの約数を求めて、あとは作ることができる約数の組み合わせを数え上げれば答えが出そうと思った。
ただ、入力例３の出力が62になる理由が分からかかった。
ひとつひとつ数え上げたのに62よりも少ない数にしかならなくて、あとどんなケースが漏れてるのかを見つけられずここでハマってしまった。

## 考察

入力例３についてもう一度調べ直すがやっぱり答えの数が足りない。
問題文を見直してしばらく考えると、i,j,kが別々とは書かれてない。
もしかしたら、、と重複して使うケースありで計算し直すと数が一致した。

仕様が分かったところで改めてアルゴリズムを考える。
重複していいのであれば、単に数値ごとの個数をmapに入れておいて、個数を掛け合わせたものの総和でいいので、シンプルなコードでできた。
約数を求める部分は過去の問題で作っていたのでそれを流用。


因みに、１つのAiにおいての組み合わせ数の計算をするところのループで、約数がAiの1/2以上のものについては、その約数で割った商の時の計算結果と同じになる。
例で言うと、(Ai,Aj,Ak) = (6,1,6)と(6,6,1)の数は同じ、(6,2,3)と(6,3,2)の数も同じ。
それを使って処理をさらに高速にできるかと思ったけど、(4,2,2)のような場合は除外しないといけないので分岐が必要になってしまう。
あと、そこまで処理時間の差はでないと思うのでこの処理は加えないことにした。

