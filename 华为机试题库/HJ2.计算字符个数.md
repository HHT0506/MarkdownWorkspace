

[题目链接](https://www.nowcoder.com/practice/a35ce98431874e3a820dbe4b2d0508b1?tpId=37&rp=1&ru=%2Fta%2Fhuawei&qru=%2Fta%2Fhuawei%2Fquestion-ranking)

## 1.题目描述



## 2.代码

```cpp
#include<iostream>
#include<string>
using namespace std;

int main()
{
	string str;
	getline(cin,str);
	string target;
	getline(cin,target);
	int num = 0;
	for (unsigned int i = 0; i < str.size(); i++)
	{
		if (target[0] >= 'a'&&target[0] <= 'z')
		{
			if (target[0] == str[i]||target[0]==str[i]+32)
				num++;
		}
		else if (target[0] >= 'A'&&target[0] <='Z')
		{
			if (target[0] == str[i] || target[0] == str[i] - 32)
				num++;
		}
	}
	cout<< num;
	return 0;
}
```



## 3.解题思路





