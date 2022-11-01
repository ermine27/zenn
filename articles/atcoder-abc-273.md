---
title: "AtCoder Beginner Contest 273 メモ(A-D)"
emoji: 🔗
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-10-17"
---



# 今回の結果
3AC

なんとかC問題まで。
解くまでの時間が長いから同じ点数の中でも下位の方。


# A - Recursive Function

https://atcoder.jp/contests/abc273/tasks/abc273_a

Difficulty: 11

## 参加中に考えたこと

再帰関数を作ってほしいという問題のようだけど、この問題はforループでもできるのでforで。
$N \le 10$ なのでintでもオーバーフローはしない。


# B - Broken Rounding

https://atcoder.jp/contests/abc273/tasks/abc273_b

Difficulty: 178

## 参加中に考えたこと

一、十、百、千、・・・と順に四捨五入を繰り返したい。
順番に桁を見ていって5より大きいならその桁を繰り上げ、4以下なら切り捨ての処理をする。


# C - (K+1)-th Largest Number

https://atcoder.jp/contests/abc273/tasks/abc273_c

Difficulty: 370


## 参加中に考えたこと

vectorで持つかmapで持つか悩んだ。
mapだと $A_i$ より大きい最小の値を取れないと思い、vectorの配列に入れた後、重複する要素を削除して、二分探索で $A_i$ より多い要素数を数える方法にした。


## 考察・感想

難しめの問題だと思っていたら灰レベルなのにびっくり。
問題文を理解するのに時間がかかった。


# D - LRUD Instructions

https://atcoder.jp/contests/abc273/tasks/abc273_d

Difficulty: 1119

## 参加中に考えたこと

座標圧縮みたいなことをするのだろうか？
でもそれを二次元でやる方法が思いつかずタイムアップ。

## 考察・感想

一旦、コンテスト中に考えた方法でやってみて、ダメなら解説見ます。
