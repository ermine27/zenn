---
title: "AtCoder Beginner Contest 275 メモ(A-D)"
emoji: 🎾
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-11-02"
---



# 今回の結果
3AC

B問題が考えても解けず、A,C,Dの3AC。
C,Dが両方解けて順位は過去最高、Highestも更新。
少しずつ上がってきたけど緑はまだ遠い。


# A - Find Takahashi

https://atcoder.jp/contests/abc275/tasks/abc275_a

Difficulty: 14

## 参加中に考えたこと

最も高い橋が何番目かを求めたいので、高さの最大値とそれが何本目かの情報を保持して、１つずつ順番に高さを比較して最大値が更新される時にそれぞれを更新してあげる。
chmaxマクロは値の更新をしつつ更新されたかの結果を返すので、trueを返したら何本目かの情報を更新してあげると最も長い橋が何番目かを取得できる。


# B - ABC-DEF

https://atcoder.jp/contests/abc275/tasks/abc275_b

Difficulty: 147

## 参加中に考えたこと

各値が最大 $10^{18}$ もあるので単純に乗算すると、 $A \times B$ が $10^{36}$ くらいまでなることがあり Long Long 型でも桁あふれが起きてしまう。
最終的に求めたい答えが 998244353 で割った余りなので先に $A～F$ を 998244353 で割った余りにすれば桁あふれすることなく計算が行えるのかと思ったがWAになってしまう。
$(A \times B) mod X = ((A mod X) \times (B mod X)) mod X$ であってると思うけど確証は持てず、行き詰ってしまった。


## 考察・感想

Pythonだと桁あふれの考慮なくそのまま数式の処理ができる問題。
C++とPythonとで難易度が全然違うんだけど、パフォーマンスには言語ごとの差って考慮されてないですよね。。？


# C - Counting Squares

https://atcoder.jp/contests/abc275/tasks/abc275_c

Difficulty: 760


## 参加中に考えたこと

方針を立てるにあたってまず検討できそうな事柄を整理する。

1. 二次元平面の広さは $9 \times 9$ と小さいので全探索は問題なくできそう。 $O(N^3)$ か、 $O(N^4)$ くらいまで可能？
2. 1つの頂点が複数の正方形の頂点になることがある
3. 入力例１のようにxy軸と平行でない正方形については、x軸とy軸にそれぞれいくつ移動するかの値を持つことで事足りる。三角関数は必要ない。
4. 正方形を数える際に重複が生じないようにする、または最後に重複分で割る

1点目と2点目から全探索の方向性で進めて問題なさそう。

3点目の、正方形をどうやって探すかという点については、 ポーンが置いてある座標について2点を選び、正方形を作れるかを判断していく方向でいけそう。
点A $(X_A,Y_A)$、点B $(X_B,Y_B)$ を使って正方形があるかを判定するには、線分ABを $d (d_x,d_y)$ とすると線分の両側の２つ確認する必要がある。

- $C(X_A + d_y, Y_A - d_x), D(X_B - d_y, Y_B + d_x)$ 
- $C(X_A - d_y, Y_A + d_x), D(X_B + d_y, Y_B - d_x)$

この2種類についてそれぞれ点C,Dにポーンがあれば正方形があることが分かる。
（最初はBからC,Dの位置を求めようとしたが B→C→Dと辿ってDの位置を探すのが複雑になると思った）

4点目については、正方形ができたらsetに格納すれば重複なく数えることはできそうだが、重複込みで数えた後に重複分の数を割る方法を取ることにした。
全探索で調べた時に1つの正方形についていくつ重複が発生するかは、頂点が4つあり、各頂点について右回り、左回りの2つあるので $4 \times 2 = 8$ パターンある。よって重複込みで数え上げたのから8で割ったものが求める答えになる。

入力例1,2がACし、あとはTLEにならないかを全て `#` にしたデータで確認して問題なかったので提出してAC。

## 考察・感想
点C,Dを求める時に、9x9の平面に収まらないときは収まるようにする必要があり、`max(0,min(8,x))` と書いていたが、 C++17 だと `clamp関数` というのがあるのを解説を見て知った。

公式の解説は左回りで固定してる。
そっちのほうがC,Dは一意になるので処理はこっちのほうが簡単になりそうと解説のコードみて思った。


# D - Yet Another Recursive Function

https://atcoder.jp/contests/abc275/tasks/abc275_d

Difficulty: 606

## 参加中に考えたこと
- $f(0) = 1$
- $f(k) = f(\lfloor \frac{k}{2}\rfloor) +  f(\lfloor \frac{k}{3}\rfloor)$

これを再帰関数で書けばいいだけ？
条件の2つ目は小数点以下を切りすてるのでそれぞれ整数のまま計算すればこれはできるので、以下のように書けばよさそう。

```c++
return f(k/2) + f(k/3);
```

これだけだとC問題のレベル。。
制約の、 $N \le 10^{18}$ に目が行き、$N=10^{18}$ でテストすると処理が終わらない。

$f(\lfloor \frac{k}{2}\rfloor)$ と $f(\lfloor \frac{k}{3}\rfloor)$ の計算を何度もしているので答えをメモ化することに。
これで $N=10^{18}$ でも全然早いので提出してAC。


