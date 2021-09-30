代码

```cpp
#include<iostream>

using namespace std;

//目标地址，源地址，大小
void mymemcpy(void *dest, void *src, unsigned int size)
{
	//从尾部开始复制，需要保证dest大于src，小于的话，从头开始复制即可
	if (dest > src&&(char*)dest - (char*)src < size)
	{
		for (int i = size-1; i >= 0; i--)
			*((char*)dest + i) = *((char*)src + i);
	}
	else
	{
		for (int i = 0; i < size; i++)//从头开始复制
			*((char*)dest + i) = *((char*)src + i);
	}
}
int main()
{
    
	int nums[4] = { 1,2,3,4 };

	mymemcpy(&nums[1], nums, 8);//从nums拷贝8个字节到&nums[1]，结果为1,1,2,4
	//mymemcpy( nums, &nums[1], 8);//从&nums[1]拷贝8个字节到nums，结果为2,3,3,4
	for (auto it : nums)
		cout << it << " ";
	cout << endl;
	return 0;
}
```

