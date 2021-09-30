## 代码

```cpp
#include<iostream>
#include<vector>
#include<algorithm>
#include<string>
using namespace std;
bool cmp(pair<string, int> &a, pair<string, int> &b)
{
	return a.second > b.second;
}
int main() {


	vector<pair<string, int>> vec;
	vec.push_back({ "hht",1 });
	vec.push_back({ "yxp",3 });
	vec.push_back({ "love",2 });
	sort(vec.begin(), vec.end(), cmp);
	for (auto it : vec)
		cout << it.first << endl;
	return 0;
}
```

第三个参数为函数名，该函数返回值必须是bool类型，并且含有两个参数，与容器内数据类型一致。

`return a.second>b.second`意思是，a是第一个参数，b是第二个参数，sort排序后需要满足第1个位置数据的second大于第2个位置数据的second。

比如，第1个位置"hht"对应的second为1，第2个位置"yxp"对应的second为3，那么排序后，需要满足第一个位置的second大于第2个位置的second，即第1个位置应该为"yxp"，第2个位置为"hht"，排序后，"yxp"在"hht"前面。

可以这么想，排序后，应该满足任何地方取两个连续的数据，前1个数据的second大于后1个数据的second。