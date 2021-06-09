

[题目链接](https://leetcode-cn.com/problems/zui-xiao-de-kge-shu-lcof/)

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    vector<int> getLeastNumbers(vector<int>& arr, int k) {
        sort(arr.begin(),arr.end());
        vector<int> res;
        for(int i=0;i<k;i++)
        {
            res.push_back(arr[i]);
        }
        return res;

    }
};
```



## 3.解题思路

