

[题目链接]()

## 1.题目描述



## 2.代码

模拟，会超时

```cpp
int lastRemaining(int n, int m)
{
	list<int> listCircle;
	for (int i = 0; i < n; i++)//初始化链表
	{
		listCircle.push_back(i);
	}
	list<int>::iterator it = listCircle.begin();
	while (listCircle.size() != 1)
	{

		for (int i = 1; i < m; i++)
		{
			it++;
			if (it == listCircle.end())
				it = listCircle.begin();
		}
		auto temp = it;
		it++;
		if (it == listCircle.end())
			it = listCircle.begin();
		listCircle.erase(temp);

	}
	return listCircle.front();
    
}
```



## 3.解题思路





