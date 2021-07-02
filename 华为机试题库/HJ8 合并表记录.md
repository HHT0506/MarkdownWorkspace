

[题目链接](https://www.nowcoder.com/practice/de044e89123f4a7482bd2b214a685201?tpId=37&&tqId=21231&rp=1&ru=/ta/huawei&qru=/ta/huawei/question-ranking)

## 1.题目描述



## 2.代码

```cpp
#include<iostream>
#include<map>
using namespace std;

int main() {
	int n;
	cin >> n;
	map<int, int> mymap;
	for (int i = 0; i < n; i++)
	{
		int key,value;
		cin >> key >> value;
		mymap[key] += value;

	}
	for (auto it : mymap)
	{
		cout << it.first << " " << it.second << endl;
	}
	return 0;
}
```



## 3.解题思路

