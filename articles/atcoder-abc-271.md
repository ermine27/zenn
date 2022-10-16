---
title: "AtCoder Beginner Contest 271 メモ(A-D)"
emoji: 🎾
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-10-13"
---



# 今回の結果
2AC
CかDのどちらかは解きたかったけどどっちも緑レベルの問題か。。
それでBまでしか解けなくてRatingが下がるのがきつい。


# A - 484558

https://atcoder.jp/contests/abc271/tasks/abc271_a

Difficulty: 28

## 参加中に考えたこと

16進数への変換に加えて以下の対応が必要となる。
- 16未満の場合は0埋めをする
- a～f は大文字に変換する

面倒だとは思いつつ、2つの変数に分けて分岐と大文字変換の処理を入れてACさせた。

## 考察・感想

`printf("%02X", n)` で一発でできるのか。
その書式指定は知らないよ。。


# B - Maintain Multiple Sequences

https://atcoder.jp/contests/abc271/tasks/abc271_b

Difficulty: 97

## 参加中に考えたこと

こういうのをジャグ配列って言うんだっけ。
push_backで要素を追加していって二次元配列を作り、
後はクエリごとにその二次元配列の要素を参照するだけ。

## 考察・感想

各数列の項数（$L$）の情報が入力にあるから、公式解説のように要素数を指定した配列を作る方法でもいい。


# C - Manga

https://atcoder.jp/contests/abc271/tasks/abc271_c

Difficulty: 842


## 参加中に考えたこと

まず、同じ巻が複数冊ある場合は1つを除いて売る対象にしてよいはずで、それを変数で持っておく
で、1巻から順番に以下の手順をシミュレーションする。

1. i巻があればiを1進める
2. i巻がない場合で、売る対象が2冊ある場合は2冊減らしてiを1進める
3. i巻がない場合で、売る対象が2冊ない場合は巻数の大きい方から1冊または2冊売る。売れない場合はそこで終了

コード量が多く、ACできないのでスキップしてD問題へ。


## 考察・感想

解説の2つ目の方法だとバグりにくいコードになりそう。
なかなか思いつかないけど。


# D - Flip and Adjust

https://atcoder.jp/contests/abc271/tasks/abc271_d

Difficulty: 886

## 参加中に考えたこと

経路まで求める問題って前回でも出題されたのでそれを参考にしようと考えた。
https://atcoder.jp/contests/abc270/tasks/abc270_c


$N \le 100$ だからDFSで出来るかと思ったら $2^{100}$ だからTLEして失敗。
メモ化すれば通るかと思ったがWAしてしまう。


## 考察・感想

この問題は答えとなるパターンを求めないといけないから、DFSで経路を持つ方法を考えてしまったけど、DPでも経路を復元する方法はあるということを知れた問題だった。
