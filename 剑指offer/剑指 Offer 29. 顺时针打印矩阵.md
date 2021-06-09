

[题目链接](https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        if(matrix.size()==0)
            return vector<int>{};
        int row=matrix.size();
        int col=matrix[0].size();
        int up=0,down=row-1,left=0,right=col-1;
        vector<int> res;
        while(true)
        {
            if(right<left)
                break;
            for(int i=left;i<=right;i++)
                res.push_back(matrix[up][i]);
            up++;
            if(down<up)
                break;
            for(int j=up;j<=down;j++)
                res.push_back(matrix[j][right]);
            right--;

            if(right<left)
                break;
            for(int i=right;i>=left;i--)
                res.push_back(matrix[down][i]);
            down--;

            if(down<up)
                break;
            for(int j=down;j>=up;j--)
                res.push_back(matrix[j][left]);
            left++;
        }
        return res;

    }
};
```



## 3.解题思路

跟[这个思路](https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/solution/mian-shi-ti-29-shun-shi-zhen-da-yin-ju-zhen-she-di/)一毛一样.

