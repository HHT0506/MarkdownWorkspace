

[题目链接]()

## 1.题目描述



## 2.代码

使用unordered_map

```cpp
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        unordered_map<int ,int> mymap;
        for(auto it:nums)
        {
            mymap[it]++;
        }
        for(auto it:nums)
        {
            if(mymap[it]!=1)
                return it;
        }
        return 0;

    }
};
```



哈希表法（归位大法）

```cpp
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        for(int i=0;i<nums.size();i++)
        {
            while(nums[i]!=i)
            {
                if(nums[i]!=nums[nums[i]])
                    swap(nums[i],nums[nums[i]]);
                else
                    return nums[i];
            }     
        }
        return 0;
    }
};
```

set集合大法（便插入便查询）

```cpp
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        unordered_set<int> se;
        for(auto it:nums)
        {
            if(se.count(it)==0)
                se.insert(it);
            else
                return it;
        }
        return 0;
    }
};
```



## 3.解题思路



