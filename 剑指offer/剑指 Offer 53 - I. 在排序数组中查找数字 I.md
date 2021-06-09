

## 代码

```cpp
#include<iostream>
#include<vector>
using namespace std;

int findFirstTarget(const vector<int> &vec,const int &target)
{
	int size = vec.size();
	if (size == 0)
		return -1;
	if (vec[0] == target)
		return 0;
	int left = 0, right = size - 1, mid=0, res=-1;
	while (left <= right)
	{
		mid = (left + right) / 2;
		if (vec[mid] < target)
		{
			left = mid + 1;
		}
		else if (vec[mid] > target)
			right = mid - 1;
		else 
		{
			if (vec[mid - 1] == vec[mid])
			{
				right = mid - 1;
			}
			else {
				res = mid;
				break;
			}
		}
	}
	return res;
}
int findLastTarget(const vector<int> &vec, const int &target)
{
	int size = vec.size();
	if (size == 0)
		return -1;
	if (vec[size - 1] == target)
		return size - 1;
	int left = 0, right = size - 1, mid = 0, res = -1;
	while (left <= right)
	{
		mid = (left + right) / 2;
		if (vec[mid] < target)
		{
			left = mid + 1;
		}
		else if (vec[mid] > target)
			right = mid - 1;
		else
		{
			if (vec[mid + 1] == vec[mid])
			{
				left = mid + 1;
			}
			else {
				res = mid;
				break;
			}
		}
	}
	return res;
}

void main()
{
	vector<int> vec = { 3,3 };
	int firstTarget = findFirstTarget(vec, 3);
	int lastTarget = findLastTarget(vec, 3);
	int nums = 0;
	if (firstTarget != -1)
	{
		nums = lastTarget - firstTarget + 1;
	}
	cout << nums;
}
```



