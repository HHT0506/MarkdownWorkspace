[题目链接](https://www.nowcoder.com/practice/d9162298cb5a437aad722fccccaae8a7?tpId=37&&tqId=21227&rp=1&ru=/ta/huawei&qru=/ta/huawei/question-ranking)

## 1.题目描述



## 2.代码

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
	string str;
	while (cin >> str)
	{
		int temp = 0;
		for (int i = 0; i < str.size(); i++)
		{
			cout << str[i];
			temp++;
			if (temp == 8)
			{
				temp = 0;
				cout << endl;
			}
		}
        if(temp!=0)
        {
            for (int i = 0; i < 8 - temp; i++)
                cout << '0';            
            cout << endl;
        }
	}
	return 0;
}
```



## 3.解题思路

