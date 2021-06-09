

[题目链接]()

## 1.题目描述



## 2.代码

```cpp
class MinStack {
public:
    /** initialize your data structure here. */
    stack<int> _stack,stack_min;
    MinStack() {
    }
    
    void push(int x) {
        _stack.push(x);
        if(stack_min.empty()||x<=stack_min.top())
            stack_min.push(x);
    }
    
    void pop() {
        if(_stack.top()==stack_min.top())
            stack_min.pop();
        _stack.pop();
    }
    
    int top() {
        return _stack.top();
    }
    
    int min() {
        return stack_min.top();
    }
};
```



## 3.解题思路





