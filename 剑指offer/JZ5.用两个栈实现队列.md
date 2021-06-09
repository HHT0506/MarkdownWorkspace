## 题目描述

[题目链接](https://www.nowcoder.com/practice/54275ddae22f475981afa2244dd448c6?tpId=13&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking&tab=answerKey)

用两个栈来实现一个队列，完成队列的Push和Pop操作。 队列中的元素为int类型。

## 代码

```cpp
class Solution
{
public:
    void push(int node) {
        stack1.push(node);
    }

    int pop() {
        while(!stack1.empty())
        {
            stack2.push(stack1.top());
            stack1.pop();
        }
        int res=stack2.top();
        stack2.pop();
        while(!stack2.empty())
        {
            stack1.push(stack2.top());
            stack2.pop();
        }
        return res;
    }

private:
    stack<int> stack1;//存放数据
    stack<int> stack2;//临时容器
};
```

## 解决思路

用两个栈实现一个队列，无非就是实现与队列相同的效果，即`先进先出`。

添加数据时，直接放入stack1中；

取出数据时，将stack1中的数据，依次弹入stack2中，此时stack2存放的数据顺序正好与stack1相反。

然后记录stack2的栈顶元素，该元素就是需要返回的数据。

弹出stack2栈顶元素，再将其余元素”倒入“stack1”。

最后返回记录的栈顶元素。