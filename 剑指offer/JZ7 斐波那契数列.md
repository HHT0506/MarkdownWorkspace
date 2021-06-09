## 题目描述

[题目链接](https://www.nowcoder.com/practice/c6c7742f5ba7442aada113136ddea0c3?tpId=13&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking&tab=answerKey)

大家都知道斐波那契数列，现在要求输入一个整数n，请你输出斐波那契数列的第n项（从0开始，第0项为0，第1项是1）。*n*≤39

示例1

##### 输入

```
4
```

##### 返回值

```
3
```

## 递归解法

```cpp
class Solution {
public:
    int Fibonacci(int n) {
        //终止条件
        if(n==0)
            return 0;
        else if(n==1)
            return 1;
        //要做什么
        //返回值
        return Fibonacci(n-1)+Fibonacci(n-2);
    }
};
```



## 非递归解法

```cpp
public:
    int Fibonacci(int n) {
        if(n==0)
            return 0;
        else if(n==1)
            return 1;
        vector<int> vec;
        vec.push_back(0);
        vec.push_back(1);
        for(int i=2;i<=n;i++)
        {
            vec.push_back(vec[i-1]+vec[i-2]);
        }
        return vec[n]; 
    }
};
```



## 扩展

[关于斐波那契数列在人生规划中的重要作用](https://xw.qq.com/cmsid/20201001A07FNV00)