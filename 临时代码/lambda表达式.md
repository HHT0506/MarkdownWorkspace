程序

```cpp
# include<iostream>
# include<algorithm>
# include<vector> 

using namespace std;
int main()
{
	int a = 1;
	int b = 2;

	auto func = [=, &b](int c)->int {return b += a + c; };
	cout << func(3) << endl;
	return 0;
}
```

