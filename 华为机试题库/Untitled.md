

[题目链接]()

## 1.题目描述



## 2.代码

```cpp
#include<iostream>
#include<set>
#include<string>
#include<vector>
using namespace std;
int main()
{
	set<string> se;
	int n;
	cin >> n;
    getchar();
	vector<string> vec(n,"");
	for (int i=0;i<n;i++)
	{
		getline(cin, vec[i]);
		se.insert(vec[i]);
	}
	for (auto it : se)
		cout << it<<endl ;
	return 0;
}
```



## 3.解题思路





