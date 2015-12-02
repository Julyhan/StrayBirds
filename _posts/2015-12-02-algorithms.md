---
layout: post
title: 《C++ standard libray ver.2》
category: coding
comments: true
---


最近开始学习[《算法》](http://algs4.cs.princeton.edu/home/)。

###java

> 要执行一个Java程序，首先需要用javac命令*编译*它，然后再用java命令*运行*它
。

```
javac Test.java
java Test
```

```
import java.util.Arrays;

public class Test //filename must be Test.java
{
	public static void main(String[] args)
	{
	}
}
```

###数组

```
double[] a;
a = new double[N];
a[i] = 0.0;

double[] b = new double[N];

double[] c = {1.0, 2.0};
```

###创建对象
```
Counter heads = new Couter("heads");
Counter tails = new Couter("tails");
```

###main函数的意义

> 为了强调用例和实现的分离，我们一般会将用例独立成为含有一个静态方法main()的类，并将数据类型定义中的main()方法预留为一个用于开发和最小单元测试的测试用例（至少调用每个实例方法一次）。

###java final
java final关键字类似C/C++ const关键字

###P62 保护性复制

###接口继承
```
public interface Datable
{
	int month();
	int day();
	int year();
}
```
并在实现中引用该接口：
```
public class Date implements Datable
{
	//
}
```

###断言
```
assert index >= 0 : "Negative index in method X";
```
默认设置没有启动断言，可以在命令行下使用-enableassertion标志启动断言。

###中缀表达式

* 将操作数压入操作数栈

* 将运算符压入运算符栈

* 忽略左括号

* 在遇到右括号时，弹出一个运算符，弹出所需数量的操作数，并将运算符和操作数的运算结果压入操作数栈。


