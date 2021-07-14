

[题目链接]()

## 1.题目描述



## 2.代码

暴力法：

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n=prices.size();
        if(n==0||n==1)
            return 0;
        int res=INT_MIN;
        for(int i=0;i<n-1;i++)
        {
            int temp_max=INT_MIN;
            for(int j=i+1;j<n;j++)
            {
                temp_max=max(temp_max,prices[j]-prices[i]);
            }
            res=max(res,temp_max);
        }
        return res<0?0:res;

    }
};
```



动态规划

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if(prices.size()==0)
            return 0;
        vector<int> dp(prices.size(),0);
        int minValue=prices[0];
        for(int i=1;i<prices.size();i++)
        {
            minValue=min(minValue,prices[i]);//最小值
            dp[i]=max(dp[i-1],prices[i]-minValue);
        }
        return dp[prices.size()-1];

    }
};
```



## 3.解题思路

