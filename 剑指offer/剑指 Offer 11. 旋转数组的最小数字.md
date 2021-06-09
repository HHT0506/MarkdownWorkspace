

## 我的代码

通不过的版本

```cpp
class Solution {
public:
    int minArray(vector<int>& numbers) {
        
        int size=numbers.size();
        if(size==1)
            return numbers[0];
        if(size==0)
            return NULL;
        if(size==2&&numbers[0]==numbers[1])
            return numbers[0];
        if(numbers[size-1]>numbers[0])
            return numbers[0];
        int left=0,right=size-1;
        int mid=0;
        while(left<right)
        {
            if(numbers[left]==numbers[left+1])
                left++;
            else if(numbers[right]==numbers[right-1])
               right--;
            else 
                break;
        }
        while(right-left!=1)
        {
            mid=(right+left)/2;
            if(numbers[left]<numbers[mid])
            {
                left=mid;
            }
            else
                right=mid;
        }
        return numbers[right];

    }
};
```

看书上解析，修改后的代码

```cpp
class Solution {
public:
    int minArray(vector<int>& numbers) {
        
        int size=numbers.size();
        if(size==1)
            return numbers[0];
        if(size==0)
            return NULL;

        if(numbers[size-1]>numbers[0])
            return numbers[0];
        int left=0,right=size-1;
        int mid=0;
        //左边界、右边界、中间都一样
        if(numbers[left]==numbers[right]&&numbers[left]==numbers[(left+right)/2])
        {
            for(int i=0;i<size-1;i++)
            {
                if(numbers[i]>numbers[i+1])
                    return numbers[i+1];
            }
            return numbers[0];//如果都遍历完成，还没返回，那就说明整个数组都一样，返回第一个数即可
        }
        
        while(right-left!=1)
        {
            mid=(right+left)/2;
            if(numbers[left]<=numbers[mid])
            {
                left=mid;
            }
            else
                right=mid;
        }
        return numbers[right];

    }
};
```

