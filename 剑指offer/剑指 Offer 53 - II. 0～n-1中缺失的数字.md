

## 代码

```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {

        int size = nums.size();
        if (nums[0] != 0)
            return 0;
        if (nums[size - 1] != size)
            return size;
        int left = 0, right = size - 1, res = 0,mid=0;
        //二分法查找，中间数与下标，中间数大于下标，则在左部分，小于等于，则在右半部分
        //举例，0，1，2，3，5，6
        //      0, 1, 2, 3, 4, 5
        while (right - left != 1)
        {
            mid = (right + left) / 2;
            if (nums[mid] > mid)
                right = mid;
            else
                left = mid;
        }
        if (nums[right] == right)
            return right - 1;
        else
            return left + 1;
    }
};
```

