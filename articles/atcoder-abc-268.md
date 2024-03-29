---
title: "AtCoder Beginner Contest 268 メモ(A-D)"
emoji: 🧱
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-09-16"
---

# 今回の結果
3AC

C問題まで解けてなんとか緑パフォとれた。
C問題をもっと早く解けるようにしたい。


# A - Five Integers

https://atcoder.jp/contests/abc268/tasks/abc268_a

Difficulty: 16

## 問題文 
与えられる $5$ つの整数 $A, B, C, D, E$ の中に何種類の整数があるかを出力してください。

## 制約 

- $0 \leq A, B, C, D, E \leq 100$
- 入力はすべて整数

## 入力 
入力は以下の形式で標準入力から与えられる。
$A$ $B$ $C$ $D$ $E$

## 出力 
答えを出力せよ。

## 入出力例

**入力例 1** 
```
31 9 24 31 24
```

**出力例 1** 
```
3
```

**入力例 2** 
```
0 0 0 0 0
```

**出力例 2** 
```
1
```

## 参加中に考えたこと
連想コンテナのsetを使えば重複なしの要素になるので数を数えるのは簡単。

## 考察・感想

普通の配列に入れる方法も後から思い出した。
unique関数を使ってできるけど、ソートを挟む必要があるから少し手間。

# B - Prefix?

https://atcoder.jp/contests/abc268/tasks/abc268_b

Difficulty: 26

## 問題文 
英小文字のみからなる $2$ つの文字列 $S, T$ が与えられます。$S$ が $T$ の接頭辞かどうかを判定してください。

:::details 接頭辞とは
長さ $N$ の文字列 $T_1T_2\ldots T_N$ の接頭辞とは、
$0 \leq i \leq N$ を満たすある整数 $i$ によって、$T$ の先頭 $i$ 文字目までの文字列 $T_1T_2\ldots T_i$ として表される文字列です。例えば、$T=abc$ のとき、$T$ の接頭辞は、空文字列、a 、ab 、abc の $4$ つです。
:::

## 制約 

- $S$ と $T$ はそれぞれ英小文字のみからなる長さが $1$ 以上 $100$ 以下の文字列

## 入力 
入力は以下の形式で標準入力から与えられる。

$S$
$T$

## 出力 
$S$ が $T$ の接頭辞である場合は `Yes` を、そうでない場合は `No` を出力せよ。ジャッジは英小文字と英大文字を厳密に区別することに注意せよ。

## 入出力例

**入力例 1** 
```
atco
atcoder
```

**出力例 1** 
```
Yes
```

**入力例 2** 
```
code
atcoder
```

**出力例 2** 
```
No
```

**入力例 3** 
```
abc
abc
```

**出力例 3** 
```
Yes
```

**入力例 4** 
```
aaaa
aa
```

**出力例 4** 
```
No
```

## 参加中に考えたこと

接頭辞＝先頭からしかみないからループを使う必要はない。
$T$ の 1～(Sの文字数)までがSと完全一致するかを判定するだけでいける。
問題文に $S$ と $T$ の文字列長の大小関係が書かれてないので、念のため事前に $|S|>|T|$ の時は `No` を返して終了するようにした。

## 考察・感想
解説でも最初に $|S|>|T|$ のケースについて触れられていたので、テストケースにはこのパターンが含まれているみたい。


# C - Chinese Restaurant

https://atcoder.jp/contests/abc268/tasks/abc268_c

Difficulty: 676

## 問題文 
回転テーブルの周りに人 $0$、人 $1$、$\ldots$、人 $N-1$ がこの順番で反時計回りに等間隔で並んでいます。また、人 $i$ の目の前には料理 $p_i$ が置かれています。
あなたは次の操作を $0$ 回以上何度でも行うことが出来ます。

- 回転テーブルを反時計回りに $1$ 周の $\frac{1}{N}$ だけ回す。これによって、(この操作の直前に)人 $i$ の目の前にあった料理は人 $(i+1) \bmod N$ の目の前に移動する。

操作を完了させた後において、人 $i$ は料理 $i$ が人 $(i-1) \bmod N$、人 $i$、人 $(i+1) \bmod N$ のいずれかの目の前に置かれていると喜びます。
喜ぶ人数の最大値を求めてください。
:::details a mod m とは
整数 $a$ と正整数 $m$ に対し、$a \bmod m$ は $a-x$ が $m$ の倍数となるような $0$ 以上 $m$ 未満の整数 $x$ を表します。(このような $x$ は一意に定まることが証明できます) 
:::

## 制約 

- $3 \leq N \leq 2 \times 10^5$
- $0 \leq p_i \leq N-1$
- $i \neq j$ ならば $p_i \neq p_j$
- 入力はすべて整数

## 入力 
入力は以下の形式で標準入力から与えられる。

$N$
$p_0$ $\ldots$ $p_{N-1}$

## 出力 
答えを出力せよ。

## 入出力例

**入力例 1** 
```
4
1 2 0 3
```

**出力例 1** 
```
4
```

**入力例 2** 
```
3
0 1 2
```

**出力例 2** 
```
3
```

**入力例 3** 
```
10
3 9 6 1 7 2 8 0 5 4
```

## 参加中に考えたこと
まず問題文を理解するのに時間を要した。
よく分からないので、入力例２を実際にスプレッドシート上でシミュレーションしてみる。
入力例を見てどうなると喜ぶのかを確認したが、これは「人 $i$ は料理 $i$ が自席もしくは自席の両隣にあれば喜ぶ」ということになる。

全探索では $O(N^2)$ の計算量でTLEするので $O(N)$ で解ける方法を考えた。
回転させた状態を計算するのはなく、最初の状態だけを使って求めたい。
両隣のは一旦置いておいて、入力例２で最初の状態でそれぞれ料理 $P_i$ が、人 $i$ とどれだけ離れているかを調べてみる。
距離は一定方向にしか回せないので、$(p_i + N - i) \space mod \space N$ として求める。

|$i$   | 0     | 1     | 2     | 3     | 4     | 5     | 6     | 7     | 8     | 9     |
|------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|$p_i$ | 3     | 9     | 6     | 1     | 7     | 2     | 8     | 0     | 5     | 4     |
|距離  | 3     | 8     | 4     | 8     | 3     | 7     | 2     | 3     | 7     | 5     |

これを1回回転させると、$p_i$ がそれぞれ右に1つ動き、距離も1つ減ることに気づく。

1回操作をした後

|$i$   | 0     | 1     | 2     | 3     | 4     | 5     | 6     | 7     | 8     | 9     |
|------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|$p_i$ | 4     | 3     | 9     | 6     | 1     | 7     | 2     | 8     | 0     | 5     |
|距離  | 4     | 2     | 7     | 3     | 7     | 2     | 6     | 1     | 2     | 6     |


この距離の情報を使って求められるのではと考えた。
距離の値と回数を持たせる。
初期状態でそれぞれの距離の数を数えると、以下のようになる。

|距離  | 0     | 1     | 2     | 3     | 4     | 5     | 6     | 7     | 8     | 9     |
|------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|回数($C_i$)  | 0     | 0     | 1     | 3     | 1     | 1     | 0     | 2     | 2     | 0     |


ここで両隣の条件を追加して、 $i-1, i, i+1$ の3つの和の最大値が求めたい答えになる。
円環の処理は同じ値を2回繋げて処理。

$max(C_{i-1}+C_i+C_{i+1}) \enspace\enspace (1 \le i \le 2n-2)$

これが答えになる。
i=3の時が最大なので、3回操作を行うと最大値の5になる事もわかる。

3回操作をした後

|$i$   | 0     | 1     | 2     | 3     | 4     | 5     | 6     | 7     | 8     | 9     |
|------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|$p_i$ | 0     | 5     | 4     | 3     | 9     | 6     | 1     | 7     | 2     | 8     |
|距離  | 0     | 4     | 2     | 0     | 5     | 1     | 5     | 0     | 4     | 9     |
|判定  | 〇     |       |       | 〇     |      | 〇     |      | 〇     |      | 〇     |


## 考察・感想

探り探りで導いた解き方だから、方針はあってそうだけどもう少しスマートには書くことはできたかも。
自分にとっては問題文を見てどういった手法を使うかがすぐに分からなかったので、考えるのに時間を多く費やしたけどACできてよかった。


# D - Unique Username

https://atcoder.jp/contests/abc268/tasks/abc268_d

Difficulty: 1309

## 問題文 

高橋君はあるサービスで使うユーザー名を決めるのに困っています。彼を助けるプログラムを書いてください。

以下の条件をすべて満たす文字列 $X$ を $1$ つ求めてください。

$X$ は次の手順で得られる文字列である。
- $N$ 個の文字列 $S_1,S_2,\ldots,S_N$ を好きな順番で並べたものを $S_1', S_2', \ldots,S_N'$ とする。そして、$S_1'$、( $1$ 個以上の `_` )、$S_2'$、( $1$ 個以上の `_` )、$\ldots$、( $1$ 個以上の `_` )、$S_N'$ をこの順番で連結したものを $X$ とする。

- $X$ の文字数は $3$ 以上 $16$ 以下である。
- $X$ は $M$ 個の文字列 $T_1,T_2,\ldots,T_M$ のいずれとも一致しない。

ただし、条件をすべて満たす文字列 $X$ が存在しない場合は代わりに `-1` と出力してください。

## 制約 

- $1 \leq N \leq 8$
- $0 \leq M \leq 10^5$
- $N,M$ は整数
- $1 \leq |S_i| \leq 16$
- $N-1+\sum{|S_i|} \leq 16$
- $i \neq j$ ならば $S_i \neq S_j$
- $S_i$ は英小文字のみからなる文字列
- $3 \leq |T_i| \leq 16$
- $i \neq j$ ならば $T_i \neq T_j$
- $T_i$ は英小文字と `_` のみからなる文字列

## 入力 
入力は以下の形式で標準入力から与えられる。
$N$ $M$
$S_1$
$S_2$
$\vdots$
$S_N$
$T_1$
$T_2$
$\vdots$
$T_M$

## 出力 
条件をすべて満たす文字列 $X$ を $1$ つ出力せよ。ただし、条件をすべて満たす文字列 $X$ が存在しない場合は代わりに `-1` を出力せよ。
答えが複数存在する場合、どれを出力しても良い。

## 入出力例

**入力例 1** 
```
1 1
chokudai
chokudai
```

**出力例 1** 
```
-1
```

**入力例 2** 
```
2 2
choku
dai
chokudai
choku_dai
```

**出力例 2** 
```
dai_choku
```

**入力例 3** 
```
2 2
chokudai
atcoder
chokudai_atcoder
atcoder_chokudai
```

**出力例 3** 
```
-1
```

**入力例 4** 
```
4 4
ab
cd
ef
gh
hoge
fuga
____
_ab_cd_ef_gh_
```

**出力例 4** 
```
ab__ef___cd_gh
```

## 参加中に考えたこと

$N \leq 8$　だから組み合わせは next_permutation を使って問題なさそう。
ただ、`_` が文字列中に入る個数のパターンが多すぎてこれをどう扱うかが分からない。
恐らく、 `ab__cd_ef____gh` のみ条件を満たし、他の組み合わせが全て $T$ に含まれているといったテストケースは存在していそうで、
`_` をどこに何個入れるかを組み合わせる方法が思いつかない。

## 考察・感想

`_` の扱いについて後から考えてみたけど、組み合わせを使ってできるか試してみたもののうまくいかず解説を見る。
DFSで全探索して計算量は足りるのか。
組み合わせは next_permutation 一択かと思ってたけど、フラグを使う方法はそういう方法もあるのかと感心。
