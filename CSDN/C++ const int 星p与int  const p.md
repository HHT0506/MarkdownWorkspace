## 1.两个约定

* const只是==修饰==作用，修饰的对象遵循==默认修饰左边的对象，若左边无对象，则修饰右边对象==

* 声明一级指针时含有const，无非两种情况：不能改变指针的指向，不能通过指针修改指向的内容

根据上述约定：

#### （1）const int *p

> const修饰int，即不能通过指针修改指向的内容。

#### （2）int const *p

> const修饰int，即不能通过指针修改指向的内容。

#### （3）int * const p

> const修饰指针p，即p的指向不能改变。

#### （4）int const * const p

> 第一个const修饰int，即不能通过指针修改指向的内容；
>
> 第二个const修饰指针p，即p的指向不能改变。

#### （5）const int * const p

> 第一个const修饰int，即不能通过指针修改指向的内容；
>
> 第二个const修饰指针p，即p的指向不能改变。

## 2.解释

上述，1和2等价，4和5等价。

### const int *p 或 int const *p

```cpp
int a = 1,b=3;
const int *p = &a;
*p = 3;//错误，不能通过p修改指向的内容
p = &b;//正确，可以修改p的指向
```

### int * const p

```cpp
int a = 1, b = 2;
int * const p = &a;
*p = 0;//正确，可以通过指针p修改指向的内容
p = &b;//错误，不可以修改p的指向
```

### int const * const p 或 const int * const p

```cpp
int a = 1, b = 2;
int const * const p = &a;
*p = 0;//错误，不能通过p修改指向的内容
p = &b;//错误，不能修改p的指向
```



## 3.注

​	严格意义上来说，类型只有int、short、float等，而没有const int、const short、const float等。

​	一些说法，比如const int *p解释为，p是指向const int类型的指针或者p是指向常量整型的指针，均不太正确。

​	持这种说法的人认为const int *p=&a;那么a必定是这样定义的：`const int a=0;`，上述的第一段代码就已经证明，a的定义`int a = 1;`是完全没有问题的。

​	还是那句话，类型是int类型，const是修饰作用，这里仅仅是说不能通过p来修改指向的内容，即不能通过p来修改a的值，`至于a的值本身能不能被修改（定义时是否有const修饰），并不是这个const所决定的`。

​	另外，上述int * const p对应的代码中，定义a时不能是`const int a = 1`，这是因为int * const p=&a;说明是可以通过p修改a的值的，但a的定义本身是不允许a被修改，这就产生了冲突。