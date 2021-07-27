

[题目链接]()

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        if(s.size()==0)
            return 0;
        int res=INT_MIN;
        unordered_set<char> se;
        int j=0;
        for(int i=0;i<s.size();i++)
        {
            if(i!=0)
                se.erase(s[i-1]);
            for(;j<s.size();j++)
            {
                if(se.count(s[j])==0)
                    se.insert(s[j]);
                else
                    break;
            }
            int size=se.size();
            res=max(res,size);
        }
        return res;

    }
};
```



## 3.解题思路

与力扣第3题一样