只转换int的测试代码

```cpp
#include<iostream>

using namespace std;

int fun(int &num)
{
	int res;
	char temp[4];
	temp[3] = *((char *)&num);
	temp[2] = *((char *)&num + 1);
	temp[1] = *((char *)&num + 2);
	temp[0] = *((char *)&num + 3);
	res = *(int *)temp;
	return res;
}

void main()
{
	int a = 5;
	int b = fun(a);
	cout << fun(b);
}	
```



模板

```cpp
#include<iostream>

using namespace std;
template<typename T>
T fun(T &num)
{
	T res;


	char *p = new char[sizeof(T)];
	int size = sizeof(T);
	for (int i = 0; i < size; i++)
	{
		p[size - i - 1] = *((char*)&num + i);
	}

	res = *((int *)p);
	return res;
}

int main()
{
	short a = 1;
	short b = fun(a);//或者short b=fun<short>(a);
	short c = fun(b);
	cout << b << endl;
	cout << c << endl;
	return 0;
}
```

