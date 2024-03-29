---
title: "AtCoder Beginner Contest 260 メモ(A-D)"
emoji: 🪕
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-07-21 21:30"
---



# 今回の結果
3AC
D問題は解けないとしても、C問題までを解く時間を早くなりたい。
特に今回のC問題はそこまで難しい問題ではないので、D問題を解けるか解けないかじゃなくて、
スピードでパフォーマンスを上げることも意識していきたい。


# A - A Unique Letter

https://atcoder.jp/contests/abc260/tasks/abc260_a

Difficulty: 12


## 問題文
長さ $3$ の文字列 $S$ が与えられます。
$S$ に $1$ 度だけ含まれる文字を $1$ つ出力してください。
但し、そのような文字が存在しない場合は代わりに `-1` と出力してください。

## 制約
- $S$ は英小文字のみからなる $3$ 文字の文字列

## 入力

入力は以下の形式で標準入力から与えられる。

$S$

## 出力
答えを出力せよ。正解が複数ある場合、どれを出力してもよい。


## 入出力例

**入力例 1**
```
pop
```

**出力例 1**
```
o
```

**入力例 2**
```
abc
```

**出力例 2**
```
a
```

**入力例 3**
```
xxx
```

**出力例 3**
```
-1
```

### 参加中に考えたこと

3文字の文字列のパターンは、
1. 3文字とも異なる
2. 2文字が同じで1文字が他と異なる
3. 全て同じ文字

の3通りある。
1.の場合はどの文字を出力してもよくて、2.の場合は重複していない1文字を出力するようにすればよい。
3文字しかないのでそのまま分岐を書く。


# B - Better Students Are Needed!

https://atcoder.jp/contests/abc260/tasks/abc260_b

Difficulty: 195


## 問題文
入学試験の受験者が $N$ 人います。
試験の結果、 $i$ 番の受験生は数学で $A_i$ 点、英語で $B_i$ 点を取りました。

試験の合格者は次のように決められます。

1. 数学の点が高い方から $X$ 人を合格とする。
2. 次に、この時点でまだ合格となっていない受験者のうち、英語の点が高い方から $Y$ 人を合格とする。
3. 次に、この時点でまだ合格となっていない受験者のうち、数学と英語の合計点が高い方から $Z$ 人を合格とする。
4. ここまでで合格となっていない受験者は、不合格とする。

ただし、 1. から 3. までのどの段階についても、同点であった場合は受験生の番号の小さい方を優先します。入出力例も参照してください。

以上の手順で合格者を決める時、合格となった受験生の番号を小さい方から順に改行区切りで出力してください。


## 制約
- 入力は全て整数
- $1≤N≤1000$
- $0≤X,Y,Z≤N$
- $1≤X+Y+Z≤N$
- $0≤A_i ,B_i ≤100$

## 入力

入力は以下の形式で標準入力から与えられる。

$N$ $X$ $Y$ $Z$
$A_1$ $A_2$ ​$\cdots$ $A_N$
$B_1$ $B_2$ ​$\cdots$ $B_K$

## 出力
合格となった受験生の番号を小さい方から順に改行区切りで出力せよ。

## 入出力例

**入力例 1**
```
6 1 0 2
80 60 80 60 70 70
40 20 50 90 90 80
```

**出力例 1**
```
1
4
5
```

**入力例 2**
```
5 2 1 2
0 100 0 100 0
0 0 100 100 0
```

**出力例 2**
```
1
2
3
4
5
```

**入力例 3**
```
15 4 3 2
30 65 20 95 100 45 70 85 20 35 95 50 40 15 85
0 25 45 35 65 70 80 90 40 55 20 20 45 75 100
```

**出力例 3**
```
2
4
5
6
7
8
11
14
15
```

### 参加中に考えたこと
$N \le 1000$ なので全探索の繰り返しで解いた。
出力は受験生の番号の昇順という指定があるので、合格者はsetで持たせて範囲forで出力させた。


# C - Changing Jewels

https://atcoder.jp/contests/abc260/tasks/abc260_c

Difficulty: 413


## 問題文
高橋君はレベル $N$ の赤い宝石を $1$ 個持っています。(他に宝石は持っていません。)
高橋君は次の操作を好きなだけ行うことができます。

- レベル $n$ の赤い宝石 ( $n$ は $2$ 以上) を「レベル $n−1$ の赤い宝石 $1$ 個と、レベル $n$ の青い宝石 $X$ 個」に変換する。
- レベル $n$ の青い宝石 ( $n$ は $2$ 以上) を「レベル $n−1$ の赤い宝石 $1$ 個と、レベル $n−1$ の青い宝石 $Y$ 個」に変換する。

高橋君はレベル $1$ の青い宝石ができるだけたくさんほしいです。操作によって高橋君はレベル $1$ の青い宝石を最大何個入手できますか？

## 制約
- $1≤N≤10$
- $1≤X≤5$
- $1≤Y≤5$
- 入力される値はすべて整数

## 入力
入力は以下の形式で標準入力から与えられる。

$N$ $X$ $Y$

## 出力
答えを出力せよ。

## 入出力例

**入力例 1**
```
2 3 4
```

**出力例 1**
```
12
```

**入力例 2**
```
1 5 5
```

**出力例 2**
```
0
```

**入力例 3**
```
10 5 5
```

**出力例 3**
```
3942349900
```


### 参加中に考えたこと
いかにもDFS使って解いてくださいと言わんばかりの問題だと思えた。
赤・青の2種類の宝石があるので、それをどういうかたちで再帰にするかで悩む。
結局、引数にはレベルだけ持たせて、他はグローバルで持っておくようにした。

### 考察・感想
DPでも解く方法もあったか。
解き方を考えているときに少しよぎったけど、問題文の流れでDFSのほうがやりやすそうと思ってDFSで解いた。
慣れてるほうで解けばいいと思うけど、DPのほうが簡単に解けたかな。。


# D - Draw Your Cards

https://atcoder.jp/contests/abc260/tasks/abc260_d

Difficulty: 1074


## 問題文
$1$ から $N$ が書かれた $N$ 枚のカードが裏向きで積まれた山札があり、上から $i$ 枚目のカードには整数 $P_i$ が書かれています。

この山札を使って、以下の行動を $N$ ターン繰り返します。

- 山札の一番上のカードを引いて、そこに書かれた整数を $X$ とする。
- 場に見えている表向きのカードであって書かれた整数が $X$ 以上であるもののうち、書かれた整数が最小のものの上に、引いたカードを表向きで重ねる。もし場にそのようなカードがなければ、引いたカードをどれにも重ねずに表向きで場に置く。
- その後、表向きのカードが $K$ 枚重ねられた山が場にあればその山のカードを全て食べる。食べられたカードは全て場から消滅する。

各カードについて、何ターン目に食べられるか、あるいは最後まで食べられないかを求めてください。

## 制約
- 入力は全て整数
- $1≤K≤N≤2×10^5$
- $P$ は $(1,2,…,N)$ の順列 ( $(1,2,…,N)$ を並べ替えて得られる列 ) である

## 入力
入力は以下の形式で標準入力から与えられる。

$N$ $K$
$P_1$ $P_2$ ​$\cdots$ $P_N$

## 出力
$N$ 行出力せよ。
そのうち $i$ $(1≤i≤N)$ 行目には、整数 $i$ が書かれたカードについて、以下のように出力せよ。

- もし $i$ が書かれたカードが食べられるなら、それが何ターン目であるかを整数として出力せよ。
- そうでないなら $−1$ と出力せよ。

## 入出力例

**入力例 1**
```
5 2
3 5 2 1 4
```

**出力例 1**
```
4
3
3
-1
4
```

**入力例 2**
```
5 1
1 2 3 4 5
```

**出力例 2**
```
1
2
3
4
5
```

**入力例 3**
```
15 3
3 14 15 9 2 6 5 13 1 7 10 11 8 12 4
```

**出力例 3**
```
9
9
9
15
15
6
-1
-1
6
-1
-1
-1
-1
6
15
```

### 参加中に考えたこと
問題文の手順の2点目の、「$X$ 以上であるもののうち、書かれた整数が最小のもの」の部分は lower_bound() を使って高速化をするのだろうと予想。
ただ、データをどう持たせるのがいいのかが分からなくて実装ができずに終了。


### 考察・感想
Difficulty 1000超えは解いたことがほとんどないけど後日チャレンジしてみた。
いろいろ考えたが結局解けず、解説を見てみるがそれでも分からないところが多い。
実装スキルが求められる問題だと感じた。

データの持たせ方としてはmapを使って持たせることにした。キーが表向きのカード、値にその山のカードの配列となるようにして。二分探索すればカードをどの山の上に置くかを決められる。
（解説の2つ目と同じ解き方）

これで必要な行動ができるだろうと思って提出すると1つのケースだけTLEする。。
何が原因なのかを調べると、これも解説にあった通りでキーを割り当て直す際に配列のコピーをすると計算量が悪化するというのが原因だった。moveについて調べるとムーブ セマンティクスというキーワードが見つかって、右辺値、左辺値など知らなかった言葉も多くあって、調べながらコードを書き替えてようやくACすることができた。
解説１のように配列を別々に用意すればこの点では躓くことはない。
