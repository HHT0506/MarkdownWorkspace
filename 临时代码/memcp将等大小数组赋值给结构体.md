代码

```cpp
#include <iostream>  
#include<vector>
using namespace std;

class A {
public:
	int d;
	int c;
	int fun(int a)
	{
		cout << a << endl;
	}
};
int main() {

	int vec[2] = { 333,444 };
	A a;
	memcpy(&a, vec, 8);
	cout << a.d << endl;
	cout << a.c << endl;
	return 0;
}
```



继承类后，内存模型改变

```cpp
#include <iostream>  
#include<vector>
using namespace std;

class Base {
public:
	int a;
};
class A :public Base{
public:
	int d;
	int c;
	int fun(int a)
	{
		cout << a << endl;
	}
};
int main() {

	int vec[2] = { 333,444 };
	A a;
	//memcpy(&a.d, vec, 8);
	memcpy(&a, vec, 8);
	cout << a.d << endl;
	cout << a.c << endl;
	return 0;
}
```

