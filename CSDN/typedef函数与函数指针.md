## 一、定义函数

代码

```cpp
#include<iostream>
using namespace std;
typedef int (FUNC)(int, int);

FUNC add;
int main()
{
	cout << add(1, 2) << endl;
	return 0;
}
int add(int a, int b)
{
	return a + b;
}
```



​        其中，`typedef int (FUNC)(int,int)`，就是定义了一个函数类型FUNC，可以使用FUNC去定义函数。

从左到右三部分解释：

* 第一个int为函数的返回值类型；

* FUNC为可以定义函数的类型名；

* (int,int)为定义的函数所具有的参数，共两个参数，均为int。

​        比如，示例代码中`FUNC add`，就是定义了一个名为add、返回值类型为int、具有两个参数且参数类型均为int的函数。这里，`FUNC add;`与`nt add(int,int);`等价。

## 二、定义函数指针

代码

```cpp
#include<iostream>
using namespace std;
typedef int (*FUNC_P)(int, int);

int add(int a, int b)
{
	return a + b;
}
int sub(int a, int b)
{
	return a - b;
}
int main()
{
	FUNC_P p = add;
	cout << p(1, 2) << endl;
	p = sub;
	cout << p(1, 2) << endl;
	return 0;
}
```

​        `typedef int (*FUNC_P)(int, int)`定义了一个函数指针类型，可以使用`FUNC_P`去定义指向函数的指针，其指向的函数类型必须是返回值为int、参数为两个且均为int。

​       比如`FUNC_P p=add`，就是定义了一个指针p，并且让其指向add函数。此时，`p(1,2)`等价于`add(1,2)`。

之后，可以改变指针指向，如，`p=sub`让其指向sub函数。

## 参考

[typedef函数指针用法](https://blog.csdn.net/qll125596718/article/details/6891881)

[typedef的用法之 typedef int (* func)(int ,int )](https://blog.csdn.net/qq_37910995/article/details/70312477?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&dist_request_id=1332042.24724.16193420395807369&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control)

[[C++] 一文带你搞定 typedef 所有用法](https://blog.csdn.net/chenhanxuan1999/article/details/99020715)