# 二分查找 (bsearch)

## 题目描述

给定一个包含 $n$ 个整数的数组 $A$，这 $n$ 个整数各不相同且按升序排列（即，$A[0] < A[1] < \ldots < A[n - 1]$）。

现对该数组进行 $q$ 次询问，每次询问输入一个数，需返回该数在数组 $A$ 中的下标。

若该数不存在，则输出 $-1$。

## 输入格式

* 第一行两个 `int` 型整数 $n$, $q$ ($1 \leqslant n, q\leqslant 1e6$)，分别表示数组大小和询问的次数。
* 第二行 $n$ 个 `int` 型整数。保证升序排序，且互不相同。
* 接下来 $q$ 行，每行一个 `int` 型整数，代表被查询的数。

## 输出格式

每行一个整数，为待查询整数在数组中的下标。

若待查询整数不存在，则输出 $-1$。

## 脚注

### 数据规模与约定

对于 60% 的数据，$1\leqslant n, q\leqslant 10,000$

对于剩余 40% 的数据，$1 \leqslant n, q\leqslant 1,000,000$

## 样例输入

4 3
-1 2 3 4
-1
2
3

## 样例输出

0
1
2