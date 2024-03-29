---
title: "AtCoder Beginner Contest 267 メモ(A-D)"
emoji: 🥾
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-09-08"
---


# 今回の結果
2AC

調子悪いのが続いてる。
Ratingも右肩下がり。


# A - Saturday

https://atcoder.jp/contests/abc267/tasks/abc267_a

Difficulty: 13


## 問題文 
ある日、学校へ行くのに疲れてしまった高橋くんは、土曜日まであと何日あるかを知りたくなりました。
その日は平日で、曜日を英語で表すと $S$ だったことが分かっています。その日より後の直近の土曜日は何日後かを求めてください。  
なお、月曜日、火曜日、水曜日、木曜日、金曜日はそれぞれ英語で `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday` です。

## 制約 

- $S$ は `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday` のいずれかである


## 入力 
入力は以下の形式で標準入力から与えられる。

$S$

## 出力 
答えを整数として出力せよ。

## 入出力例


**入力例 1**
```
Wednesday
```

**出力例 1** 
```
3
```

**入力例 2** 
```
Monday
```

**出力例 2** 
```
5
```

## 参加中に考えたこと
if文を5つ並べて曜日ごとに対応する数値を選ぶようにするだけ。


# B - Split?

https://atcoder.jp/contests/abc267/tasks/abc267_b

Difficulty: 171

## 問題文 
ボウリングのピンは $1$ から $10$ の番号が付けられており、上から見ると下図のように配置されます。

![](/images/atcoder-abc-267-b.png)

この図の二つの点線に挟まれた部分を列と呼ぶことにします。
例えば、ピン $1, 5$ とピン $3, 9$ はそれぞれ同じ列に存在します。
いくつかのピンが倒れた状態のうち、特殊なものはスプリットと呼ばれます。
ピンの配置がスプリットであるとは、以下の条件が全て成り立つことを言います。

- ピン $1$ が倒れている。
ある二つの異なる列であって、次の条件を満たすものが存在する。
- それぞれの列には、立っているピンが $1$ 本以上存在する。
- それらの列の間に、ピンが全て倒れている列が存在する。

具体例は入出力例を参考にしてください。
さて、あるピンの配置が長さ $10$ の文字列 $S$ として与えられます。
$i = 1, \dots, 10$ について、ピン $i$ が倒れているとき $S$ の $i$ 文字目は `0` であり、ピン $i$ が立っているとき $S$ の $i$ 文字目は `1` です。
$S$ で表されるピンの配置がスプリットかどうか判定してください。

## 制約 

- $S$ は `0` と `1` からなる長さ $10$ の文字列

## 入力 
入力は以下の形式で標準入力から与えられる。

$S$

## 出力 
$S$ で表されるピンの配置がスプリットなら `Yes` を、そうでないなら `No` を出力せよ。

## 入出力例

**入力例 1**
```
0101110101
```

**出力例 1** 
```
Yes
```

**入力例 2** 
```
0100101001
```

**出力例 2** 
```
Yes
```

**入力例 3** 
```
0000100110
```

**出力例 3** 
```
No
```

**入力例 4** 
```
1101110101
```

**出力例 4** 
```
No
```

## 参加中に考えたこと

問題文のスプリットの条件を順に判定していく。
まず、ピン $1$ が倒れていなければ `No` を出力して終了。
次の2つの列ごとの条件については、まず図を見てそれぞれのピンがどの列に入っているか、そしてその列に立っているピンの有無の情報を持たせておいて、左側、右側、2つの列の間の3重ループでチェックする。
2重ループだと間の2列以上にピンがない場合の判定ができない。


# C - Index × A(Continuous ver.)

https://atcoder.jp/contests/abc267/tasks/abc267_c

Difficulty: 524

## 問題文 
長さ $N$ の整数列 $A=(A_1,A_2,\dots,A_N)$ が与えられます。
長さ $M$ の $A$ の連続部分列 $B=(B_1,B_2,\dots,B_M)$ に対する、$\displaystyle \sum_{i=1}^{M} i \times B_i$ の最大値を求めてください。

## 注記 
数列の **連続部分列** とは、数列の先頭から $0$ 個以上、末尾から $0$ 個以上の要素を削除して得られる列のことをいいます。  
例えば $(2, 3)$ や $(1, 2, 3)$ は $(1, 2, 3, 4)$ の連続部分列ですが、$(1, 3)$ や $(3,2,1)$ は $(1, 2, 3, 4)$ の連続部分列ではありません。  

## 制約 

- $1 \le M \le N \le 2 \times 10^5$
- $- 2 \times 10^5 \le A_i \le 2 \times 10^5$
- 入力は全て整数。

## 入力 
入力は以下の形式で標準入力から与えられる。

$N$ $M$
$A_1$ $A_2$ $\dots$ $A_N$

## 出力 
答えを出力せよ。

## 入出力例

**入力例 1** 
```
4 2
5 4 -1 8
```

**出力例 1** 
```
15
```

**入力例 2** 
```
10 4
-3 1 -4 1 -5 9 -2 6 -5 3
```

**出力例 2** 
```
31
```

## 参加中に考えたこと
$N \le 2 \times 10^5$ なので $O(N^2)$ の計算量だとTLEする。
それ以下の方法を考える必要がある。
$M$ が固定なので、例えば入力例2の $M=4$ なら、$(1,2,3,4)$ の値を計算した後にひとつ右の値を取ってひとる左を捨てて $(2,3,4,5)$ の値が求めれれば $O(N)$ で求められそう。
問題は単純な部分和ではなくて $i \times B_i$ の場合にどうやって同じことができるか？
方向性がこれであってるのか分からず、30分ほど悩んでやっとこの方針で答えが出せそうな道筋が見えてきた。

入力例2において計算してみると、以下のようになる。

$S_1 = (A_1,A_2,A_3,A_4) = (-3) + 1 \times 2 + (-4) \times 3 + 1 \times 4 = -9$ 
$S_2 = (A_2,A_3,A_4,A_5) = 2 + (-4) \times 2 + 1 \times 3 + (-5) \times 4 = -24$
$S_3 = (A_3,A_4,A_5,A_6) = (-4) + 1 \times 2 + (-5) \times 3 + 9 \times 4 = 19$

$S_1$ を使って $S_2$ を求め、同様に $S_2$ を使って $S_3$ を求めるようにしたい。
$S_1 \rightarrow S_2 \rightarrow S_3$ と1つ進むにあたって $A_3$ は $(-4) \times 3, (-4) \times 2, (-4)$ と $-4$ ずつ値が減っている。$A_4$ も同様に $1$ ずつ減っている。
この性質に加えて、両端の考慮を入れて左端を1つ消して右端を1つ足してやれば $S_{i-1}$ から $S_i$ の値は求められそう。
数式をで表すと、

$S_i = S_{i-1} - A_{i-1} - (A_i+A_{i+1}+...+A_{i+M-1}) + A_{i+M} \times M$

となる。

ただし、$(A_i+A_{i+1}+...+A_{i+M-1})$ の部分を毎回計算すると結局 $O(N^2)$ になってしまうので、この部分は累積和を使う。
$C_i = C_{i-1}+A_i$ として先に計算しておけばこの部分は差分を取るだけで求まる。すると、

$S_i = S_{i-1} - A_{i-1} - (C_{i+M-1} - C_i) + A_{i+M} \times M$

で求まるので $max(S_i)$ が求めたい答えになる。


と、方針が決まってコードを書いたがほとんどのケースでWAになってしまい、時間が残っておらず終了。


## 考察・感想

原因はどこだろうとコードを見直してると、
累積和の配列をint型で持ってるとオーバーフローするのでは。。
入力の $A$ と同じところで変数の宣言を書いててintで扱ってるのが間違いだった。
long long 型に変えたらACした。。

マクロの作成や他の人のコードを見てて、全部long longで扱ってる人や、`#define int long long` と書いて強制的にlong long を使うようにしている人を見たけど、ここで詰まってACできないのは勿体ないし、害になることはなさそうならその書き方を採用しようかな？

あとは上で考えていた数式のところは、

$S_i = S_{i-1} - (C_{i+M-1} - C_{i-1}) + A_{i+M} \times M$

ともう少し綺麗にできた。

公式の解説を見ると、$A$ ではなくて $\displaystyle \sum_{i=1}^{M} i \times B_i$ のほうで累積和を持っておくのか。
全ての提出をいくつか見てるとどっちのやり方もあるけど公式と同じ考え方のほうが多いかな。


# D - Index × A(Not Continuous ver.) 

https://atcoder.jp/contests/abc267/tasks/abc267_d

Difficulty: 864

## 問題文 
長さ $N$ の整数列 $A=(A_1,A_2,\dots,A_N)$ が与えられます。
長さ $M$ の $A$ の部分列(連続でなくてもよい) $B=(B_1,B_2,\dots,B_M)$ に対する、$\displaystyle \sum_{i=1}^{M} i \times B_i$ の最大値を求めてください。

## 注記 
数列の **部分列** とは、数列から $0$ 個以上の要素を取り除いた後、残りの要素を元の順序で連結して得られる数列のことをいいます。
例えば、$(10,30)$ は $(10,20,30)$ の部分列ですが、$(20,10)$ は $(10,20,30)$ の部分列ではありません。

## 制約 

- $1 \le M \le N \le 2000$
- $- 2 \times 10^5 \le A_i \le 2 \times 10^5$
- 入力は全て整数。

## 入力 
入力は以下の形式で標準入力から与えられる。

$N$ $M$
$A_1$ $A_2$ $\dots$ $A_N$

## 出力 
答えを出力せよ。

## 入出力例

**入力例 1** 
```
4 2
5 4 -1 8
```

**出力例 1** 
```
21
```

**入力例 2** 
```
10 4
-3 1 -4 1 -5 9 -2 6 -5 3
```

**出力例 2** 
```
54
```

## 参加中に考えたこと
C問題と似ているが異なるのは以下の2点。
- 連続部分列　→　部分列
- $M,N$ の上限が$2 \times 10^5$ 　→　 $2000$

全探索すると確実にTLEするのでこういう時はDPかなと思ったが、漸化式が思いつかなかった。

## 考察・感想
解き方が分からないので解説を読んで方針だけ見て、後はコードは悩まずに解けた。
漸化式が分かれば全然解ける問題だったな。
入力例2の場合のDPは以下のような感じになる。

| 0    | 1    | 2    | 3    | 4  | 5  | 6  | 7  | 8  | 9  | 10 |
|------|------|------|------|----|----|----|----|----|----|----|
| 0    | 0    | 0    | 0    | 0  | 0  | 0  | 0  | 0  | 0  | 0  |
| -INF | -3   | 1    | 1    | 1  | 1  | 9  | 9  | 9  | 9  | 9  |
| -INF | -INF | -1   | -1   | 3  | 3  | 19 | 19 | 21 | 21 | 21 |
| -INF | -INF | -INF | -13  | 2  | 2  | 30 | 30 | 37 | 37 | 37 |
| -INF | -INF | -INF | -INF | -9 | -9 | 38 | 38 | 54 | 54 | 54 |


C問題よりD問題のほうが簡単だという声がいくつがあったみたいだが、DPの中ではそんなに難しいものではないのでDPに慣れている人はそう感じたのかもしれない。
