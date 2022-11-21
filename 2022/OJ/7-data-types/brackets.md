# 括号序列 (brackets.c)

## 题目描述

### 做题须知

* 在正式开始做题之前，你应该先了解 **栈（stack）** 的有关内容，了解这种抽象的结构，比如，你可以阅读 [Stacks](https://eng.libretexts.org/Courses/Folsom_Lake_College/CISP_430%3A_Data_Structures_(Aljuboori)/03%3A_Stacks_and_Queues/3.01%3A_Stacks) 的页面中具体代码实现之前的部分。
* 了解了概念之后，就可以尝试实现了，我们为你准备了一道模板题 [栈 (stack.c)](https://oj.cpl.icu/contest/29/problem/147) 。你可以阅读课本的 **10.2.1** 节的代码 **（允许抄书）**，也可以去搜集网上的资料，那些实现（指针）大多超出授课进度，但对于这道题来说，一维数组已经足够。
* 做完了以上步骤，你可以阅读本题剩下的题面，并思考如何使用栈这种结构“方便”地完成这道题目，你可以直接照抄自己在模板题中的实现。
* 我们在数据中设置了一些小小的障碍，如果你忽略了以上步骤并试图设计一些“巧妙”的方法，那么很有可能无法通过本题。
* 如果实在没有思路，就来线下答疑向助教求助吧。使用搜索引擎或许能找到很多内容（这也是非常经典的问题），但是那些内容对于大家来说可能还是太难了 qaq 。

---

定义一个合法括号序列（balanced bracket sequence）为仅由`()[]{}`构成的字符串且:

- 空串是一个合法括号序列。
- 如果串`s`是合法括号序列，那么`(s)`，`[s]`和`{s}`也都是合法括号序列。（`(s)`表示在`s`两边加上`()`得到的字符串，如`s = [()]`，那么`(s) = ([()])`）
- 如果`s`, `t`都是合法括号序列，那么`st`也是合法括号序列。(`st`表示`s`和`t`相连得到的字符串)

给出 $T$ 个字符串，判断每个字符串是否是一个合法的括号序列。

## 输入格式

第一行一个整数 $T$（$T \leqslant 30$），表示一共有 $T$ 组数据。

之后 $T$ 行每行输入一个字符串 $s$（$|s| \leqslant 10^5$），为给定的括号序列。

## 输出格式

一共 $T$ 行，每行一个`True`或者`False`，表示对应的字符串 $s$ 是/不是合法的括号序列。

## 示例

### 示例输入1

```text
4
[(])
([)]
([{}])([])
())(()
```

### 示例输出1

```text
False
False
True
False
```