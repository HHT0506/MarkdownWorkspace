

## 代码

```cpp
class Solution {
public:
    vector<int> exchange(vector<int>& nums) {
        int size=nums.size();
        int left=0,right=size-1;
        while(left<right)
        {
            if((nums[left]&1)==0)//偶数
            {
                if((nums[right]&1)==1)//奇数
                    swap(nums[left],nums[right]);
                else
                    right--;
            }
            else
                left++;
        }
        return nums;
    }
};
```



## 流程图

![](E:\MarkdownWorkspace\剑指offer\image\JZ21.png)

