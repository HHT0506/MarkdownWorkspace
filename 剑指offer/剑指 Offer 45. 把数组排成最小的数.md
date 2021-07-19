

[题目链接](https://leetcode-cn.com/problems/ba-shu-zu-pai-cheng-zui-xiao-de-shu-lcof/)

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    static bool cmp(string a,string b)
    {
        return a+b<b+a;
    }
    string minNumber(vector<int>& nums) {
        vector<string> vec;
        for(auto it:nums)
        {
            vec.push_back(to_string(it));
        }
        sort(vec.begin(),vec.end(),cmp);
        string res;
        for(auto it:vec)
            res.append(it);
        return res;

    }
};
```



## 3.解题思路

