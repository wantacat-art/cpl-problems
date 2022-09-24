# 字符串哈希

## 题目描述

哈希表是又称散列表，一种以 "key-value" 形式存储数据的数据结构。所谓以 "key-value" 形式存储数据，是指任意的键值 key 都唯一对应到内存中的某个位置。只需要输入查找的键值，就可以快速地找到其对应的位置。

### 哈希函数

拿到一个对象，我们怎么知道应该把它放到内存里面的哪个位置呢？假设有一个数组供我们存放这些对象，它的下标范围是 [0, N - 1]，我们需要构造一个 对象->[0, N - 1] 的映射，这个映射就叫做哈希函数。为了减少两个不同的对象映射到相同的下标的情况，我们需要尽量让哈希函数的值分布均匀。

### 冲突

因为存在不可避免的，两个对象计算得到的索引相同的情况（确实很难构造出无冲突的哈希函数），我们转变策略：每一个下标对应一个链表，当我们计算出哈希函数的结果后，就向下标对应的链表进行操作，如果是添加，则向链表中添加；如果是查找，则遍历链表查找。

了解了哈希表的概念后，我们来实现一个存储字符串的哈希表。给出一个 M 个字符串的集合，进行 Q 次查询，字符串是否在集合中。如果用朴素的数组的做法，则需要 M *Q* Average(Length) 的时间，在本题的数据中必定超时；

如果用哈希表，则需要 Sum(Length) + Q *M / N* Average(Length) (N 为下标范围) 的时间，其中前一部分是计算哈希函数的开销，后一部分是查询次数 *单次查询链表的开销。Sum(Length) = Average(Length)* (M + Q)，掐指一算比前者快好多。

### 怎么做

具体来说，首先你需要一个指针数组，数组的每一个值都指向一个链表头。数组大小宜是集合大小的1倍以上，以减少冲突。

然后还需要一个 hash 函数，对于一个确定的字符串，根据它的每一位计算出一个固定的值，落在下标区间里。具体的映射方式由你自己决定（意思就是随便，只要对于相等的字符串能给出相等的下标就可以了）。

最后就是链表了。

## 输入格式

第一行两个整数 m, q，表示字符串数量和查询次数。（$1\leqslant m, q\leqslant 500000$）

m行每行一个字符串，表示集合中的字符串。可能重复

q行每行一个字符串，表示一次查询

集合和查询的所有字符串长度小于 1e3，总长度小于 5e7；字符串只包含大小写英文字母。

## 输出格式

字符串在集合中则输出 "Yes\n", 反之输出 "No\n"

## 脚注

这里随便提供一个可行的哈希函数

```cpp
//N是hash的范围

int hash(char *s){
    int len=strlen(s);
    int ret=0;
    for(int i=0;i<len;i++)ret=(ret+s[i]*(i+1))%N;
    return ret;
}
```

## 样例

### 样例输入

3 2
AMD
Intel
Apple
AMD
Nvidia

### 样例输出

Yes
No