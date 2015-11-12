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

###other alg
adjacent_find
```
template<class ForwardIterator>
ForwardIterator adjacent_find(ForwardIterator first, ForwardIterator last);
```

count/count_if
```
template <class InputIterator, class T>
typename iterator_traits<InputIterator>::difference_type
count(InputIterator first, Input Iterator last, const T& value);

template <class InputIterator, class Predicate>
typename iterator_traits<InputIterator>::difference_type
count_if(InputIterator first, InputIterator last, Predicate pred);
```
find/find_if

find_end
```
//注意该函数应调用两个不同的下层函数，forward_iterator_tag, bidirectional_iterator_tag
```
find_first_of
//本算法以[first2,last2)区间内的某些元素作为查找目标，寻找它们在[first1,last1)区间内的第一次出现的点
//区别serach(fisrt1, last1, first2, last2)
```
template<class InputIterator, class ForwardIterator>
InputIterator find_first_of(InputIterator first1, Input Iterator last1, 	
				ForwardIterator first2, ForwardIterator last2);

template<class InputIterator, class ForwardIterator, class BinarayPredicate>
InputIterator find_first_of(InputIterator first1, Input Iterator last1, 	
				ForwardIterator first2, ForwardIterator last2
				BinarayPredicate comp);
```

for_each
将仿函数f施行于[first,last)区间内的每一个元素身上。f不可以改变元素内容，因为first和last都是InputIterator,不保证接受赋值行为。如果想要一一修改元素内容，应该使用算法transform()
```
template <class InputIterator, class Function>
Function for_each(InputIterator first, Input Iterator last, Function f);
```

generate/generate_n

includes

remove/remove_copy/remove_if

replace/replace_copy/replace_if/replace_copy_if

reverse/reverse_copy

rotate/rotate_copy

search/search_n

swap_ranges

transform

unique/unique_copy

###other complex alg

lower_bound/upper_bound
binary_search(调用lower_bound)

next_permutation/prev_permutation



###elegent code

####将两个向量的剩余元素插入结果
```
copy(a2_begin, a2_end, copy(b2_begin, b2_end, result));
```
