[题目链接]()

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        unordered_map<int,int> mymap;
        int size=nums.size();
        for(int i=0;i<size;i++)
            mymap[nums[i]]++;
        unordered_map<int,int>::iterator it;
        for(it=mymap.begin();it!=mymap.end();it++)
        {
            if(it->second>size/2)
                return it->first;
        }
        return 0;
    }
};

```

或者

```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        return nums[nums.size()/2];
    }
};
```



## 3.解题思路





