---
title: "AtCoder Beginner Contest 251 ใกใข(A-E)"
emoji: "๐ญ"
type: "tech"
topics: ["atcoder"]
published: true
published_at: "2022-05-15 23:56"
---


# ไปๅใฎ็ตๆ
3AC

Cๅ้กใฏๅๅใใใฏๆใใๅ้กใ ใฃใใฎใงใใใใพใงใฏ่งฃใใฆใใใฃใใ
Dๅ้กใฏ่งฃใๆนใฎๆค่จใใคใใชใใชใ่ฆๅใใใคใใฆในใญใใใใEใซ้ฒใใจEๅ้กใๅใใไบบใใใใจๆใใ


# A - Six Characters 

https://atcoder.jp/contests/abc251/tasks/abc251_a

Difficulty: 9


## ๅ้กๆ
่ฑๅฐๆๅญใใใชใๆๅญๅ $S$ ใไธใใใใพใใ $S$ ใฎ้ทใใฏ $1$ ไปฅไธใใค $3$ ไปฅไธใงใใ

$S$ ใ็นฐใ่ฟใใฆๅพใใใๆๅญๅใงใใฃใฆใ้ทใใ $6$ ใฎใใฎใๅบๅใใฆใใ ใใใ

ๆฌๅ้กใฎๅถ็ดไธใงใใใฎใใใชๆๅญๅใฏใใ ไธใคๅญๅจใใใใจใ็คบใใพใใ

## ๅถ็ด
- $S$ ใฏ่ฑๅฐๆๅญใใใชใ้ทใ $1$ ไปฅไธ $3$ ไปฅไธใฎๆๅญๅ

## ๅฅๅ
ๅฅๅใฏไปฅไธใฎๅฝขๅผใงๆจๆบๅฅๅใใไธใใใใใ

S

## ๅบๅ
็ญใใจใชใ้ทใ $6$ ใฎๆๅญๅใๅบๅใใใ

## ๅฅๅบๅไพ

**ๅฅๅไพ 1**

```
abc
```

**ๅบๅไพ 1**
```
abcabc
```

**ๅฅๅไพ 2**
```
zz
```
**ๅบๅไพ 2**
```
zzzzzz
```

### ๅๅ ไธญใซ่ใใใใจ

ๅๅใพใงใฎAๅ้กใซๆฏในใใจใใฃใจ็ฐกๅใชใใฎใซๆปใฃใๆใใใใใ
Sใฎๆๅญๅ้ทใฎใใฟใผใณใฏใใใใ๏ผใคใชใฎใงใifๆใงไธฆในใใใใใ6ใงๅฒใฃใๆฐใงforๆใงๅใใใใใใใใใใๆนใงๆธใใฐใใใใจใ
่ชๅใฏforๆใงๆธใใพใใใ


# B - At Most 3 (Judge ver.)

https://atcoder.jp/contests/abc251/tasks/abc251_b

Difficulty: 181

## ๅ้กๆ
ใใใ $1,$ ใใใ $2, โฆ,$ ใใใ $N$ ใฎ $N$ ๅใฎใใใใใใใพใใใใใ $i$ ใฎ้ใใฏ $A_i$ ใงใใ
ไปฅไธใฎๆกไปถใๆบใใๆญฃๆดๆฐ $n$ ใ **่ฏใๆดๆฐ** ใจๅผใณใพใใ

- **$3$ ๅไปฅไธ** ใฎ็ฐใชใใใใใ่ช็ฑใซ้ธใใงใ้ธใใ ใใใใฎ้ใใฎๅใ $n$ ใซใใใใจใใงใใใ
$W$ ไปฅไธใฎๆญฃๆดๆฐใฎใใกใ่ฏใๆดๆฐใฏไฝๅใใใพใใ๏ผ

## ๅถ็ด
- $1โคNโค300$
- $1โคWโค10$
- $1โคA_iโค10^6$
- ๅฅๅใใใๅคใฏใในใฆๆดๆฐ

## ๅฅๅ
ๅฅๅใฏไปฅไธใฎๅฝขๅผใงๆจๆบๅฅๅใใไธใใใใใ

N W
$A_1$ $A_2$ ... $A_N$ 
 
## ๅบๅ
็ญใใๅบๅใใใ

## ๅฅๅบๅไพ

**ๅฅๅไพ 1**
```
2 10
1 3
```
**ๅบๅไพ 1**
```
3
```

**ๅฅๅไพ 2**
```
2 1
2 3
```
**ๅบๅไพ 2**
```
0
```

**ๅฅๅไพ 3**
```
4 12
3 3 3 3
```

**ๅบๅไพ 3**
```
3
```

**ๅฅๅไพ 4**
```
7 251
202 20 5 1 4 2 100
```
**ๅบๅไพ 4**
```
48
```

### ๅๅ ไธญใซ่ใใใใจ
้ธใถใใใใฏ3ๅไปฅไธใ ใใใ1ๅ้ธใใง่ฏใๆดๆฐใใงใใๅ ดๅใ2ๅใฎๅ ดๅใ3ๅใฎๅ ดๅใใใใใ้่จใใใฐใใใใใ
$Nโค300$ ใ ใใ๏ผ้ใซใผใใงใ $(3ร10^2)^3 \fallingdotseq 10^6๏ฝ10^7$ ็จๅบฆใฎ็ฏๅฒใ ใใ่จ็ฎ้ใฏๅ้กใชใใ
ๆฑใใใฎใฏ่ฏใๆดๆฐใฎๅๆฐใ ใใใ้่คใใชใใใใซๅใใใ็ฏๅฒใฎ้ๅใงใใฉใฐใๆใฃใฆใใใฆใๆๅพใซใใฉใฐใ็ซใฃใฆใใ่ฆ็ด ใฎๆฐใๆฐใไธใใใๆฑใพใใ
ใใใฏsetไฝฟใฃใฆๆๆใใใใ


# C - Poem Online Judge

https://atcoder.jp/contests/abc251/tasks/abc251_c

Difficulty: 246

## ๅ้กๆ
ใใจใ ใชใณใฉใคใณใธใฃใใธ (Poem Online Judge, ไปฅไธ POJ ใจ่กจ่จ) ใฏๆๅบใใใๆๅญๅใซๅพ็นใใคใใใชใณใฉใคใณใธใฃใใธใงใใ
POJ ใซ $N$ ๅใฎๆๅบใใใใพใใใๆฉใๆนใใ $i$ ็ช็ฎใฎๆๅบใงใฏๆๅญๅ $S_i$ ใๆๅบใใใฆใๅพ็นใฏ $T_i$ ใงใใใ(ๅใๆๅญๅใ่คๆฐๅๆๅบใใใๅ ดๅใใใใพใ)
ใใ ใใPOJ ใงใฏ **ๅใๆๅญๅใๆๅบใใฆใๅพ็นใ็ญใใใจใฏ้ใใชใ** ใฎใซๆณจๆใใฆใใ ใใใ

$N$ ๅใฎๆๅบใฎใใกใใใฎๆๅบใใใๆฉใๆๅบใงใใฃใฆๆๅญๅใไธ่ดใใใใฎใๅญๅจใใชใใใใชๆๅบใ **ใชใชใธใใซ** ใงใใใจๅผใณใพใใ
ใพใใใชใชใธใใซใชๆๅบใฎไธญใงๆใๅพ็นใ้ซใใใฎใ **ๆๅช็ง่ณ** ใจๅผใณใพใใใใ ใใใใฎใใใชๆๅบใ่คๆฐใใๅ ดๅใฏใๆใๆๅบใๆฉใใใฎใๆๅช็ง่ณใจใใพใใ

ๆๅช็ง่ณใฏๆฉใๆนใใไฝ็ช็ฎใฎๆๅบใงใใ๏ผ

## ๅถ็ด
- $1โคNโค10^5$ 
- $S_i$ ใฏ่ฑๅฐๆๅญใใใชใๆๅญๅ
- $S_i$ ใฎ้ทใใฏ $1$ ไปฅไธ $10$ ไปฅไธ
- $0โคT_iโค10^9$
- $N, T_i$ ใฏๆดๆฐ

## ๅฅๅ
ๅฅๅใฏไปฅไธใฎๅฝขๅผใงๆจๆบๅฅๅใใไธใใใใใ

$N$
$S_1$ $T_1$
$S_2$ $T_2$
$\vdots$
$S_N$ $T_N$
 
## ๅบๅ
็ญใใๅบๅใใใ

## ๅฅๅบๅไพ

**ๅฅๅไพ 1**
```
3
aaa 10
bbb 20
aaa 30
```
**ๅบๅไพ 1**
```
2
```

**ๅฅๅไพ 2**
```
5
aaa 9
bbb 10
ccc 10
ddd 10
bbb 11
```
**ๅบๅไพ 2**
```
2
```

**ๅฅๅไพ 3**
```
10
bb 3
ba 1
aa 4
bb 1
ba 5
aa 9
aa 2
ab 6
bb 5
ab 3
```
**ๅบๅไพ 3**
```
8
```

### ๅๅ ไธญใซ่ใใใใจ

ๆๅช็ง่ณใๆฑบใใๅชๅ้ ไฝใใใใคใใใใใๆด็ใใใจไปฅไธใฎ้ ๅบใซใชใใ
1. ใชใชใธใใซใงใใ๏ผ่ช่บซใจๅใๆๅญๅใๆขใซๆๅบใใใฆใใชใ๏ผ
2. 1ใฎไธญใงๅพ็นใๆใ้ซใ
3. 1ใจ2ใๆบใใใใฎๅๅฃซใฎๅ็นใๅใๅ ดๅใฏใๅใซๆๅบใใใปใใๆๅช็ง่ณใซใชใ

ๅคๅฎใใใใฎใๅคใใฎใงใใพใใชใชใธใใซใ ใใmapไฝฟใฃใฆๆใๅบใใใจใซใ
ใใใง้ฃๆณ้ๅใไฝฟใใชใใจๆใใ$O(N^2)$ ใฎ่จ็ฎ้ใงTLEใใใฑใผในใๅบใฆใใใ
mapใซใฏๅพ็นใจ้ ๅบใฎ2ใคใๅฟ่ฆใชใฎใงใ`map<int<pair<int,int>>>` ใงๅฎ็พฉใ

ใชใชใธใใซใ ใใฎใใผใฟใใงใใใใใซใผใใใฆ2ใจ3ใฎๆกไปถใ่ฆใชใใ็ญใใๆขใๆงใชใณใผใใๆธใใฆACใงใใใ

### ่ๅฏใปๆๆณ

ๅพใใๆฐไปใใใใฉใใชใๅใใใฉใๅฎ่ฃใใใฆใใ
ไธใใ้ ใซๅฅๅใ1่ก่ชญใใใณใซๆๅช็ง่ณใซใชใใใฎๅคๅฎใพใงใงใใใฎใงใ

- ใชใชใธใใซใใฉใใใๅคๅฎใใใใใฎ้ฃๆณ้ๅ
- ๆๅช็ง่ณใฎ็นๆฐ
- ๆๅช็ง่ณใไฝ็ช็ฎใ

ใฎ๏ผใคใๆใฃใฆใใใฐ1ใคใฎใซใผใใงๅๅใ ใฃใใ
ใใใชใใชใชใธใใซใใฉใใใฎๅคๅฎใsetใงๆๅญๅใ ใๆใฆใฐไบ่ถณใใใ


# D - At Most 3 (Contestant ver.)

https://atcoder.jp/contests/abc251/tasks/abc251_d

Difficulty: 1463

## ๅ้กๆ
ๆดๆฐ $W$ ใไธใใใใพใใ
ใใชใใฏไปฅไธใฎๆกไปถใใในใฆๆบใใใใใซใใใคใใฎใใใใ็จๆใใใใจใซใใพใใใ

- ใใใใฎๅๆฐใฏ $1$ ๅไปฅไธ $300$ ๅไปฅไธใงใใใ
- ใใใใฎ้ใใฏ $10^6$  ไปฅไธใฎๆญฃๆดๆฐใงใใใ
- 1 ไปฅไธ $W$ ไปฅไธใฎใในใฆใฎๆญฃๆดๆฐใฏ **่ฏใๆดๆฐ** ใงใใใใใใงใไปฅไธใฎๆกไปถใๆบใใๆญฃๆดๆฐ $n$ ใ่ฏใๆดๆฐใจๅผใถใ
  - ็จๆใใใใใใฎใใก **$3$ ๅไปฅไธ** ใฎ็ฐใชใใใใใ่ช็ฑใซ้ธใใงใ้ธใใ ใใใใฎ้ใใฎๅใ $n$ ใซใใใใจใใงใใใ ใ
ๆกไปถใๆบใใใใใชใใใใฎ็ตใ $1$ ใคๅบๅใใฆใใ ใใใ

## ๅถ็ด
- $1โคWโค10^6$
- $W$ ใฏๆดๆฐ

## ๅฅๅ
ๅฅๅใฏไปฅไธใฎๅฝขๅผใงๆจๆบๅฅๅใใไธใใใใใ

W

## ๅบๅ
$N$ ใใใใใฎๅๆฐใ$A_i$ ใ $i$ ็ช็ฎใฎใใใใฎ้ใใจใใฆใไปฅไธใฎๅฝขๅผใงๅบๅใใใ็ญใใ่คๆฐๅญๅจใใๅ ดๅใใฉใใๅบๅใใฆใๆญฃ่งฃใจใฟใชใใใใ

$N$
$A_1$ $A_2$ $\cdots$ $A_N$ 
 
ใใ ใใ$N$ ใใใณ $A_1$ $A_2$ $\cdots$ $A_N$ ใฏไปฅไธใฎๆกไปถใๆบใใๅฟ่ฆใใใใ

- $1โคNโค300$
- $1โคA_iโค10^6$
 
## ๅฅๅบๅไพ

**ๅฅๅไพ 1**
```
6
```
**ๅบๅไพ 1**
```
3
1 2 3
```

**ๅฅๅไพ 2**
```
12
```
**ๅบๅไพ 2**
```
6
2 5 1 2 5 1
```

### ๅๅ ไธญใซ่ใใใใจ

1ใใ้ ใซๆธใๅบใใฆใฟใใ่งฃๆณใ้ใใชใใ
$Nโค300$ ใจใใใใจใฏใไธ็ชๅคงใใช $10^6$ ใงใ300ๅใใใฐ$1๏ฝ10^6$ใฎๅจใฆใฎ่ฏใๆดๆฐใไฝใใใจใใใใจใซใชใใ
300ใจใใๆฐๅญใไฝใๆๅณใใๆฐใซๆใใใใใ
ใใจใ $W$ ใซใใฃใฆ $N$ ใฎๆๅฐๅคใๆฑใใๅฟ่ฆใใใใฎใใจๆใฃใใใๅ้กๆใ่ฆๆธกใใฆใใใฎใใใช่จ่ฟฐใ่ฆๅฝใใใชใใ$N$ ใฏๅบๅฎใง300ใ่ฟใใฆใใใใฎใ ใใใ๏ผ
ไฝใ่ฆๅๆงใ่ฆใคใใชใใจ่งฃใใชใๅ้กใชๆฐใใใใฎใงใใใฎๅ้กใฏในใญใใใ

### ่ๅฏใปๆๆณ

ๅฌๅผ่งฃ่ชฌใฎใใณใใ่ฆใฆ่งฃๆณใๅใใฃใใ
ใใณใ1๏ฝ3ใ็ตใฟๅใใใใจใ$10^6$ ใฎ่งฃใฏใ

- $1,2,3,\cdots ,8,9$
- $10,20,30,\cdots ,80,90$
- $100,200,300,\cdots ,800,900$
- $1000,2000,3000,\cdots ,8000,9000$
- $10000,20000,30000,\cdots ,80000,90000$
- $100000,200000,300000,\cdots ,800000,900000$

ใใฎ6ใคใ1ใคใใค้ธในใฐ่ฏใๆดๆฐใไฝใใใ
ไฝใใ้ธในใใฎใฏ6ใคใงใฏใชใ3ใคใชใฎใงใใใฎๆนๆณใ่ใใใ
ไธ่จใฎๅ ดๅใ$N=10ร6=60$ ใง็จๆใงใใใใใใฎๆฐใซใฏใพใ  $240$ ๅใไฝใฃใฆใใใ
ใใฎๆฐๅญใ็บใใฆใใใจใไธใฎ2่กใฎๅใงใใ $1๏ฝ99$ ใฏ100ๅ็จๆใใใฐ1ใคใง่ฏใๆดๆฐใไฝใใใใจใซๆฐไปใใใ
ๅๆงใซ $100๏ฝ9999$ ใจ $10000๏ฝ999999$ ใซใคใใฆใ100ๅใใค็จๆใใใฐ $99ร3=297$ ๅใไฝฟใฃใฆๅจใฆๆๅคง3ใค้ธใถใจใใๆกไปถใฎใใจใๅจใฆใฎ่ฏใๆดๆฐใไฝใใใ
$10^6$ ใใ${10^2}^3$ ใจใใฆ่ใใใฎใใใฎๅ้กใฎใใคใณใใซใชใใ
ใคใพใๅฟ่ฆใชใใใใฏใ

- $1,2,3,\cdots,97,98,99$
- $100,200,300,\cdots,9700,9800,9900$
- $10000,20000,30000,\cdots,970000,980000,990000$

ใใฎใใใซ็จๆใใฆใใใฐ่ฏใใ

ใใใฆใใฎๅ้กใงใฏ $N$ ใฎๆๅฐๅคใๆฑใใๅฟ่ฆใใชใใฎใงใ $W$ ใฎๅคใซ้ขไฟใชใๆฑบใพใฃใๅบๅใใใ ใใงใใใใ
ใณใผใใฏAๅ้กไธฆใซ็ฐกๅใงใใขใซใดใชใบใ ใ็่งฃใใใใใฐ่งฃใใใจใใๅคใใฃใๅฝขๅผใฎๅบ้กใ ใฃใใ

่งฃ่ชฌใซใใใฐใใใใใๅ้กใฏใๆง็ฏ/ๆงๆ (constructive problem) ใจใใใธใฃใณใซๅใงๅผใฐใใใใจใฎใใจใ
ๆง็ฏๅ้กใฏใใ็จฎใฎ้ใใ่ฆๆฑใใใฎใงใใใบใซใๅพๆใชไบบใ ใจ่งฃใใใใใใใใ


# E - Tahakashi and Animals

https://atcoder.jp/contests/abc251/tasks/abc251_e

Difficulty: 1227

## ๅ้กๆ
้ซๆฉๅใจ $N$ ๅนใฎๅ็ฉใใใพใใ $N$ ๅนใฎๅ็ฉใฏใใใใๅ็ฉ $1$ ใๅ็ฉ $2$ ใโฆ ใๅ็ฉ $N$ ใจๅผใฐใใพใใ

้ซๆฉๅใฏไธ่จใฎ $N$ ็จฎ้กใฎ่กๅใใใใใๅฅฝใใชๅๆฐใ ใ๏ผ $0$ ๅใงใ่ฏใ๏ผ่กใใพใใ

- $A_1$ ๅๆใใๅ็ฉ $1$ ใจๅ็ฉ $2$ ใซ้คใใใใใ
- $A_2$ ๅๆใใๅ็ฉ $2$ ใจๅ็ฉ $3$ ใซ้คใใใใใ
- $A_3$ ๅๆใใๅ็ฉ $3$ ใจๅ็ฉ $4$ ใซ้คใใใใใ
- $\cdots$
- $A_i$ ๅๆใใๅ็ฉ $i$ ใจๅ็ฉ $(i+1)$ ใซ้คใใใใใ
- $\cdots$
- $A_{N-2}$ ๅๆใใๅ็ฉ $(N-2)$ ใจๅ็ฉ $(N-1)$ ใซ้คใใใใใ
- $A_{N-1}$ ๅๆใใๅ็ฉ $(N-1)$ ใจๅ็ฉ $N$ ใซ้คใใใใใ
- $A_N$ ๅๆใใๅ็ฉ $N$ ใจๅ็ฉ $1$ ใซ้คใใใใใ
ไธ่จใฎ $N$ ็จฎ้ก็ฎใฎ่กๅใงใฏใใๅ็ฉ $N$ ใจๅ็ฉ $1$ ใซใ้คใใใใใใจใซๆณจๆใใฆใใ ใใใ

ใในใฆใฎๅ็ฉใซใใใใ $1$ ๅไปฅไธ้คใใใใใพใงใซใใใ่ฒป็จใฎๅ่จใจใใฆ่ใใใใๆๅฐๅคใๅบๅใใฆใใ ใใใ

## ๅถ็ด
- $2โคNโค3ร10^5$
- $1โคA_iโค10^9$
- ๅฅๅใฏใในใฆๆดๆฐ

## ๅฅๅ
ๅฅๅใฏไปฅไธใฎๅฝขๅผใงๆจๆบๅฅๅใใไธใใใใใ

$N
$A_1$ $A_2$ $\cdots$ $A_N$
โ 
## ๅบๅ
ใในใฆใฎๅ็ฉใซใใใใ $1$ ๅไปฅไธ้คใใใใใพใงใซใใใ่ฒป็จใฎๅ่จใจใใฆ่ใใใใๆๅฐๅคใๅบๅใใใ

## ๅฅๅบๅไพ

**ๅฅๅไพ 1**
```
5
2 5 3 2 5
```
**ๅบๅไพ 1**
```
7
```

**ๅฅๅไพ 2**
```
20
29 27 79 27 30 4 93 89 44 88 70 75 96 3 78 39 97 12 53 62
```
ๅบๅไพ 2 
```
426
```

### ๅๅ ไธญใซ่ใใใใจ

้คใใใใ่กๅใไธ่ฌๅใใใจใใฎ1่กใง่กจ็พใงใใใใ
- $A_i$ ๅๆใใๅ็ฉ $i$ ใจๅ็ฉ $(i+1 \enspace mod \enspace N)$ ใซ้คใใใใใ
ใพใใใในใฆใฎๅ็ฉใซ1ๅไปฅไธ้คใใใใ็บใฎๅฟ่ฆๆกไปถใจใใฆไปฅไธใ่ใใใใ
- $A_i$ ๅใป $A_{i+1}$ ๅใฎใฉใกใใๆใใชใใฑใผในใๅญๅจใใชใ
ใใใ่ธใพใใฆ่ฒป็จใฎๆๅฐๅคใ่ใใฆใใใ

ใใญใผใ่ใใใจใใใใๆใใซใชใใ
oใฏ่ณผๅฅใใๅ ดๅใxใฏ่ณผๅฅใใชใใฃใๅ ดๅ
๏ผๅพใใฎ1aใ2bใฏใฐใฉใใฎไฝๆ็จใจใใฆไฝฟใฃใฆใใใฎใงๆๅณใฏใชใ๏ผ

```mermaid

flowchart LR
   S --> o1a & x1a
   
   o1a --> o2a & x2a
   x1a --> o2b

   o2a --> o3a & x3a
   x2a --> o3b
   o2b --> o3c & x3c
      
   o3a --> o4a & x4a
   x3a --> o4b
   o3b --> o4c & x4c
   o3c --> o4d & x4d
   x3c --> o4e
   

```

$Nโค3ร10^5$ ใชใฎใงใDFS๏ผใกใขๅๅๅธฐใใช๏ผ
ใจ่ใใฆใณใผใใๆธใใฆๅฅๅบๅไพ๏ผใไธๆใใใใชใใจใใใงใฟใคใ ใขใใ

### ่ๅฏใปๆๆณ

๏ผไฝๆไธญ๏ผ

