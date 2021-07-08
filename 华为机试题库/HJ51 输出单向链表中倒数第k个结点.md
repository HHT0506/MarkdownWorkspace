

[题目链接](https://www.nowcoder.com/practice/54404a78aec1435a81150f15f899417d?tpId=37&&tqId=21274&rp=1&ru=/ta/huawei&qru=/ta/huawei/question-ranking)

## 1.题目描述



## 2.代码

```cpp
#include<iostream>
#include<vector>
using namespace std;

struct ListNode{
    int value;
    ListNode *next;
};

int main()
{
    
    int n;
    while(cin>>n)
    {
        vector<int> vec(n);
        for(int i=0;i<n;i++)
        {
            cin>>vec[i];
        }
        int k;
        cin>>k;
        if(k==0)
        {
            cout<<0<<endl;
            continue;
        }
        ListNode *head=new ListNode();
        ListNode *p=head;
        for(int i=0;i<n;i++)
        {
            ListNode *temp=new ListNode();
            temp->value=vec[i];
            temp->next=nullptr;
            p->next=temp;
            p=p->next;
        }
        p=head->next;
        ListNode *right,*left;
        right=p;
        left=p;
        while(k--)
        {
            right=right->next;
        }
        while(right)
        {
            right=right->next;
            left=left->next;
        }
        cout<<left->value<<endl;
        
    }
    return 0;
}
```



## 3.解题思路





