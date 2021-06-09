

## 代码

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
    ListNode* reverseList(ListNode* head) {

        if(head==NULL||head->next==NULL)
            return head;
        ListNode *p_left=head;
        ListNode *p_mid=p_left->next;
        ListNode *p_right=p_mid->next;
        head->next=NULL;
        while(p_right!=NULL)
        {
            p_mid->next=p_left;
            p_left=p_mid;
            p_mid=p_right;
            p_right=p_right->next;
        }
        p_mid->next=p_left;
        return p_mid;
    }
};
```





## 双指针代码

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
    ListNode* reverseList(ListNode* head) {

        if(head==nullptr||head->next==nullptr)
            return head;
        ListNode *p_left=head;
        ListNode *p_right=p_left->next;
        head->next=nullptr;
        while(p_right!=nullptr)
        {
            ListNode *right_next=p_right->next;
            p_right->next=p_left;
            p_left=p_right;
            p_right=right_next;
        }
        return p_left;
    }
};
```



## 优化后代码

```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode *p_left=nullptr;
        ListNode *p_right=head;
        while(p_right!=nullptr)
        {
            ListNode *right_next=p_right->next;
            p_right->next=p_left;
            p_left=p_right;
            p_right=right_next;
        }
        return p_left;
    }
};
```

