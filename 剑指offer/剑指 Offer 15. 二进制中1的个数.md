[题目链接](https://leetcode-cn.com/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/)

## 代码

```cpp
class Solution {
public:
    int hammingWeight(uint32_t n) {
        uint32_t flag=1;
        int res=0;
        while(flag!=0)
        {
            if(flag&n)
                res++;
            flag<<=1;
        }
        return res;
    }
};
```

