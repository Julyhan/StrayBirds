---
layout: post
title: 《The Annotated STL Sources》
category: coding
comments: true
---

###set的作用
分别包含```set```, ```multiset```

头文件: ```#include <set>```

```
set_union(InputIterator1 first1, InputIterator1 last1, InputIterator2 first2, InputIterator2 last2, OutputIterator result);
set_intersection
set_difference
set_symmetric_difference
```

###仿函数
```
template<class T>
struct display
{
	void operator()(const T &x) const
	{
		cout << x << ' ';
	}
};

//调用
for_each(a.begin(), a.end(), display<int>());
```

###elegent code

####将两个向量的剩余元素插入结果
```
copy(a2_begin, a2_end, copy(b2_begin, b2_end, result));
```
