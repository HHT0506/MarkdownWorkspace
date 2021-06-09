



## 题目描述

[题目链接](https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof)

输入一个递增排序的数组和一个数字s，在数组中查找两个数，使得它们的和正好是s。如果有多对数字的和等于s，则输出任意一对即可。

 

示例 1：

输入：nums = [2,7,11,15], target = 9
输出：[2,7] 或者 [7,2]
示例 2：

输入：nums = [10,26,30,31,47,60], target = 40
输出：[10,30] 或者 [30,10]


限制：

1 <= nums.length <= 10^5
1 <= nums[i] <= 10^6

## 代码

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        //双指针解法
        vector<int> res(2,0);
        int left=0,right=nums.size()-1;
        int sum=0;
        while(left<right)
        {
            sum=nums[left]+nums[right];
            if(sum<target)
                left++;
            else if(sum>target)
                right--;
            else
            {
                res[0]=nums[left];
                res[1]=nums[right];
                break;
            }
        }
        return res;
    }
};
```



## 解题思路

输入有一个很关键的条件，就是数组有序。



![](E:\MarkdownWorkspace\剑指offer\image\JZ57.png)















