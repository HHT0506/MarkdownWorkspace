

## 我的代码

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(l1==nullptr&&l2==nullptr)
            return nullptr;
        else if(l1==nullptr&&l2!=nullptr)
            return l2;
        else if(l1!=nullptr&&l2==nullptr)
            return l1;

        //以下保证l1和l2都不为空链表
        ListNode *res;
        if(l1->val>l2->val)//初始化res
        {
            res=l2;
            l2=l2->next;
        }
        else
        {
            res=l1;
            l1=l1->next;
        }
        ListNode *ans=res;
        while(l1!=nullptr&&l2!=nullptr)
        {
            if(l1->val>l2->val)
            {
                res->next=l2;
                res=res->next;
                l2=l2->next;
            }
            else
            {
                res->next=l1;
                res=res->next;
                l1=l1->next;
            }
        }
        //至此，其中一个已经为nullptr

        if(l1==nullptr)
        {
            while(l2!=nullptr)
            {
                res->next=l2;
                res=res->next;
                l2=l2->next;
            }
        }
        else
        {
            while(l1!=nullptr)
            {
                res->next=l1;
                res=res->next;
                l1=l1->next;
            }
        }
        res->next=nullptr;
        return ans;


    }
};
```

