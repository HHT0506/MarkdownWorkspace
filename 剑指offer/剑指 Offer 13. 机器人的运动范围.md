[题目链接](https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/)

## 代码

```cpp
class Solution {
public:
    int movingCount(int m, int n, int k) {
        
        vector<bool> temp(n,false);
        vector<vector<bool>> visited(m,temp);
        int m_0=0,n_0=0;
        return dfs(0,0,m,n,k,visited);
    }
    //起始点，visited数组，边界,k
    int dfs(int row,int col,int &m,int &n,int &k,vector<vector<bool>> &visited)
    {
        if(row>=m||col>=n||visited[row][col]||getSum(row)+getSum(col)>k)
            return 0;
        visited[row][col]=true;
        
        return 1+dfs(row,col+1,m,n,k,visited)+dfs(row+1,col,m,n,k,visited);

    }
    int getSum(int value)
    {
        int sum=0;
        while(value>0)
        {
            sum+=value%10;
            value/=10;
        }
        return sum;
    }
};
```

参考了这个[评论代码](https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/comments/864232)，但有修改：

1.dfs函数的if判断中，去掉了row<0和col<0，因为并没有向上或向左走，不用担心上面和左面的边界。

2.visited数组改为bool类型。

3.dfs形参中m,n,k加了引用。