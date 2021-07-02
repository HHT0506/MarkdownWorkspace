

[题目链接](https://www.nowcoder.com/practice/440f16e490a0404786865e99c6ad91c9?tpId=37&&tqId=21238&rp=1&ru=/ta/huawei&qru=/ta/huawei/question-ranking)

## 1.题目描述



## 2.代码

```cpp
#include<iostream>
using namespace std;

int main()
{

	int number;
	cin >> number;
	int times = sizeof(int) * 8;
	int temp = 1;
	int res = 0;
	for (int i = 0; i<times; i++)
	{
		if ((number&temp)!= 0)
			res++;
		temp <<=1;
	}
	cout << res;
	return 0;
}
```



## 3.解题思路

