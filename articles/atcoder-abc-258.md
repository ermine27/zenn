---
title: "AtCoder Beginner Contest 258 メモ(A-D)"
emoji: 🧶
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-07-05 23:10"
---


# 今回の結果
2AC

B問題でDifficulty500超え、しかもC問題よりも高い。
ここに結構時間を費やしてしまってC問題までACできなかった。
D問題までは時間があれば解ける問題だったので、時間内に解けるようになるというのが今の自分の課題。


# A - When?

https://atcoder.jp/contests/abc258/tasks/abc258_a

Difficulty: 10


## 問題文
AtCoder Beginner Contest は通常、日本標準時で $21$ 時ちょうどに始まり $100$ 分間にわたって行われます。

$0$ 以上 $100$ 以下の整数 $K$ が与えられます。$21$ 時ちょうどから $K$ 分後の時刻を `HH:MM` の形式で出力してください。ただし、`HH` は $24$ 時間制での時間を、`MM` は分を表します。時間または分が $1$ 桁のときは、先頭に $0$ を追加して $2$ 桁の整数として表してください。

## 制約
- $K$ は $0$ 以上 $100$ 以下の整数

## 入力

入力は以下の形式で標準入力から与えられる。

$K$

## 出力
$21$ 時ちょうどから $K$ 分後の時刻を問題文中の形式に従って出力せよ。


## 入出力例

**入力例 1**
```
63
```

**出力例 1**
```
22:03
```
※ 10:03 や 22:3 は不正解となる

**入力例 2**
```
45
```

**出力例 2**
```
21:45
```


**入力例 3**
```
100
```

**出力例 3**
```
22:40
```

### 参加中に考えたこと
以下の２点の処理を行えばよい。

- `HH` は60未満なら `21` 、60以上なら `22` になる
- `MM` が一桁になる場合には先頭に `0` をつける

2つ目はMMの値を見て0埋めする方法でやっちゃったけどprintf使うのが楽かな。

# B - Number Box

https://atcoder.jp/contests/abc258/tasks/abc258_b

Difficulty: 511

## 問題文
正整数 $N$ が与えられます。

$N$ 行 $N$ 列のマス目があり、上から $i$ 行目、左から $j$ 列目のマスには数字 $A_{i,j}$  が書かれています。

このマス目は上下および左右がつながっているものとします。つまり以下が全て成り立ちます。

$(1,i)$ の上のマスは $(N,i)$ であり、$(N,i)$ の下のマスは $(1,i)$ である。 $(1≤i≤N)$
$(i,1)$ の左のマスは $(i,N)$ であり、$(i,N)$ の右のマスは $(i,1)$ である。 $(1≤i≤N)$
高橋君は、上下左右および斜めの $8$ 方向のうちいずれかを初めに選びます。そして、好きなマスから決めた方向に $1$ マス移動することを $N−1$ 回繰り返します。

高橋君は $N$ 個のマス上を移動することになりますが、高橋君が通ったマスに書かれている数字を左から通った順番に並べた整数としてあり得る最大のものを求めてください。

## 制約
- $1≤N≤10$
- $1≤A_{i,j}≤9$
- 入力はすべて整数

## 入力
入力は以下の形式で標準入力から与えられる。

$N$
$A_{1,1}$ $A_{1,2}$ $\cdots$ $A_{1,N}$
$​A_{2,1​}$ $A_{2,2}$ $\cdots$ $A_{2,N}$
$\vdots$
$A_{N,1}$ $A_{N,2}$ $\cdots$ $A_{N,N}$


## 出力
答えを出力せよ。

## 入出力例

**入力例 1**
```
4
1161
1119
7111
1811
```

**出力例 1**
```
9786
```

**入力例 2**
```
10
1111111111
1111111111
1111111111
1111111111
1111111111
1111111111
1111111111
1111111111
1111111111
1111111111
```

**出力例 2**
```
1111111111
```

### 参加中に考えたこと

全探索。
各マス目について8方向の値を取っていくので、各方向について処理を書くのは面倒だしバグを生みやすい。
8方向を順に見ていくための座標の移動については、以下のような配列を持っておくと短い3重ループでコードが書けた。
（ここに辿り着くのに時間がかかり過ぎた）

```c++
const int dx[] = {1, 0, -1, 0, 1, -1, -1, 1};
const int dy[] = {0, 1, 0, -1, 1, 1, -1, -1};
```

上下左右が繋がっている部分はmodを使ってやればよい。
C++の場合、マイナスの値に対してmodを取ると期待する値とは異なる値になってしまうので、先に+Nしておいてからmodを取るようにする。

あと、出力例２に「答えが32bit型整数値に収まるとは限らない」と書かれているが、一番大きい値を取りたい、かつ桁数は揃っているので、数値で比較するのではなくて文字列として扱えばよさそう。

何回かWA出してしまったが、なんとかACできた。

### 考察・感想

配列を持っていればあっという間に解ける問題だったかな。
座標を扱う問題ではたまに出るので、4方向と8方向の２種類の配列を持っておくのがいい。


# C - Rotation

https://atcoder.jp/contests/abc258/tasks/abc258_c

Difficulty: 419


## 問題文
正整数 $N,Q$ と、長さ $N$ の英小文字からなる文字列 $S$ が与えられます。

以下で説明されるクエリを $Q$ 個処理してください。クエリは次の $2$ 種類のいずれかです。

- `1 x`: 「$S$ の末尾の文字を削除し、先頭に挿入する」という操作を $x$ 回連続で行う。
- `2 x`: $S$ の $x$ 番目の文字を出力する。

## 制約
- $2≤N≤5×10^5$
- $1≤Q≤5×10^5$
- $1≤x≤N$
- $∣S∣=N$
- $S$ は英小文字からなる。
- `2 x` の形式のクエリが $1$ 個以上与えられる。
- $N,Q,x$ はすべて整数。


## 入力
入力は以下の形式で標準入力から与えられる。

$N$ $Q$
$S$
$query_1$
$query_2$ 
$\vdots$​
$query_Q$
​
それぞれのクエリは以下の形式で与えられる。ここで、$t$ は $1$ または $2$ である。

$t$ $x$


## 出力
`2 x` の形式の各クエリについて、答えを一行に出力せよ。

## 入出力例

**入力例 1**
```
3 3
abc
2 2
1 1
2 2
```

**出力例 1**
```
b
a
```

**入力例 2**
```
10 8
dsuccxulnl
2 4
2 7
1 2
2 7
1 1
1 2
1 3
2 5
```

**出力例 2**
```
c
u
c
u
```


### 参加中に考えたこと
クエリ2は $O(1)$ でできるので、クエリ1をどうやって高速に行うかがこの問題のキーポイントだろう。
制約の値が大体は $2×10^5$ であることが多いが、$5×10^5$ であるということはシビアなものが求められるのだろうか？
dequeとか使ったら時間早くなるかなということを考えて試したところでタイムアップ。


### 考察・感想
1日置いて考え直した。
クエリ2は文字列を出力するだけで要素の変更はない。クエリ1はSの順番が変わるだけで要素数自体は変わらない。
クエリ1の処理で実際に文字を入れ替えるのではなく、動かしたとみなす工夫をすればよいことに気づいた。動かした後に元々の文字列が何文字動いたかの位置の情報だけもっておけば、そこからクエリ2で出力したい文字も計算で求められる。
ここの計算に苦戦したが、自分の場合は「クエリ1を行った後の文字列の先頭が元々の何文字目か？」を持っておくと考えて解くことができた。
解説を見るとクエリ1を行った回数を持つと書かれていて、そのほうがシンプルに考えられたかな。

# D - Trophy

https://atcoder.jp/contests/abc258/tasks/abc258_d

Difficulty: 687


## 問題文
$N$ 個のステージからなるゲームがあり、$i(1≤i≤N)$ 番目のステージは $A_i$ 分間のストーリー映像と $B_i$ 分間のゲームプレイによって構成されます。

初めて $i$ 番目のステージをクリアするためにはストーリー映像の視聴とゲームプレイを両方行う必要がありますが、二回目以降はストーリー映像をスキップすることができるので、ゲームプレイのみでクリアすることができます。

初めから遊べるのは $1$ 番目のステージのみですが、$i(1≤i≤N−1)$ 番目のステージをクリアすることにより、$i+1$ 番目のステージも遊べるようになります。

合計 $X$ 回ステージをクリアするために必要な時間の最小値を求めてください。ただし、同じステージを複数回クリアしたとしても、全てクリア回数に数えられます。

## 制約
- $1≤N≤2×10^5$
- $1≤A_i,B_i≤10^9 (1≤i≤N)$
- $1≤X≤10^9$
- 入力は全て整数

## 入力
入力は以下の形式で標準入力から与えられる。

$N$ $X$
$A_1$ $B_1$ 
$\vdots$​
$A_N$​ $B_N$
 

## 出力
答えを出力せよ。

## 入出力例

**入力例 1**
```
3 4
3 4
2 3
4 2
```

**出力例 1**
```
18
```

**入力例 2**
```
10 1000000000
3 3
1 6
4 7
1 8
5 7
9 9
2 4
6 4
5 1
3 1
```

**出力例 2**
```
1000000076
```


### 考察・感想
問題文をぱっと見た感じ、そんなに難しい問題ではなさそうに思えた。
ストーリー映像とゲームプレイの2段階あるところが一見複雑にはみえるけども、最小時間になるケースって、2回以上クリアするステージは1つしかないのでは？というのが明らかな気がする。

ステージkまで進む場合の必要な時間は、ステージ1～kまでのストーリー映像とゲームプレイの時間の合計＋(X-k-1)回ゲームプレイをする時間になる。数式であらわすと、
$\displaystyle\sum_{i=1}^{k}(A[i]+B[i]) + B[i]×(x-k-1)$
になる。
ステージ1から順番にループしてこの最小値を求めればOK。
ACするまでC問題よりも時間はかからなかった。

解いていて詰まりそうになった点としては２つあった。
１点目は、ループの終了条件として $N$ を使うのではなく、 $min(N,X)$ を使う必要があること。 $N$ までで判定すると $(x-k-1)$ の部分が負数となり正しい答えより小さい数値になってしまうケースがある。（実際に試したところ、テストケースの中に１つそういうものが用意されていた）
$X<N$ においてこのようになる場合があり、例えば以下のようなデータの場合に終了条件が $N$ までにするとステージ5の場合が最小値となってしまう。

```
5 3
6 12
3 9
4 3
1 2
1 10
```

２点目は最小値をして持っておく変数の初期値。
今まで大きな値であればいいかと思いあまり意識せず`1e18` として桁数だけ合わせていたが、これだといくつかのテストケースでWAしてしまう。この問題の場合の答えの最大値としては、$2×10^{18}$ まである。

いろんな人の提出ソースを見てみると、定数を用意している人は多いがその値はというと `2e18+7`、 `9e18`、`1<<62`、 `9223372036854775807` などのようにバラバラ。用意されている定数を使うのが一番無難だろうか。公式解説では numeric_limits を使っているが書き方がやや長いので `LLONG_MAX` でいいかと思った。
