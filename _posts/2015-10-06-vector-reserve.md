---
layout: post
title: vector的容量大小
category: coding
comments: true
---

在逐渐熟悉STL之后，vector代替c-stylr-array，成为一种我最常用的容器。但是在大量的赋值时，如果使用```.at()```，将报错提示：

> out of range

网上常用的方法是```vector.resize(size_t)```，它的好处是可以给予多出的值默认值，用法为：

```
vector.resize(size_t, default_calue)
```

但相应地，如果你将size_t的大小误输入为较小的值，将会造成元素的损失。

因此，只是单纯想扩大容量，尤其是在初始化的时候，可以采用```vector.reserve(size_t)```算法，c++ standart libray一书这样解释该用法：

> 如果容量不足，扩大之

相应地，有```vector.shrink_to_fit()```：

> 要求降低容量，以符合元素个数


