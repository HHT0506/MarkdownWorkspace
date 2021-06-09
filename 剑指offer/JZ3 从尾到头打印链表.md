## 题目描述

[题目链接](https://www.nowcoder.com/practice/a861533d45854474ac791d90e447bafd?tpId=13&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking&tab=answerKey)

输入一个链表，按链表从尾到头的顺序返回一个ArrayList。

示例1

##### 输入

```
{67,0,24,58}
```

##### 返回值

```
[58,24,0,67]
```

## 代码

```cpp
/**
*  struct ListNode {
*        int val;
*        struct ListNode *next;
*        ListNode(int x) :
*              val(x), next(NULL) {
*        }
*  };
*/
class Solution {
public:
    vector<int> printListFromTailToHead(ListNode* head) {
        //（1）遍历链表，依次将元素压入栈中
        stack<int> s;
        ListNode* p;
        p=head;
        while(p)
        {
            s.push(p->val);
            p=p->next;
        }
        //（2）遍历栈，依次读入数组并弹出
        vector<int> res;
        while(!s.empty())
        {
            res.push_back(s.top());
            s.pop();
        }
        return res;
    }
};
```

## 解题思路

充分利用栈的`先入后出`特性：

（1）遍历链表，依次将元素压入栈中；

（2）遍历栈，依次读入数组并弹出。