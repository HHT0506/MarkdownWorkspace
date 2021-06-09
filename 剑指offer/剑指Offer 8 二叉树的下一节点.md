这道题在牛客题库和力扣题库都未找到，但是在牛客的试题广场有，链接为：

https://www.nowcoder.com/questionTerminal/9023a0c988684a53960365b889ceaf5e



## 我的代码

```cpp
/*
struct TreeLinkNode {
    int val;
    struct TreeLinkNode *left;
    struct TreeLinkNode *right;
    struct TreeLinkNode *next;
    TreeLinkNode(int x) :val(x), left(NULL), right(NULL), next(NULL) {
        
    }
};
*/
class Solution {
public:
    TreeLinkNode* GetNext(TreeLinkNode* pNode) {
        if(pNode==NULL)
            return NULL;
        //该节点有右子树，则下一节点为右子树的最左节点
        if(pNode->right!=NULL)
        {    
            pNode=pNode->right;
            while(pNode->left!=NULL)
            {
                pNode=pNode->left;
            }
            return pNode;
        }
        else
        {
            if(pNode->next!=NULL){
                if(pNode->next->right==pNode)//父节点的右子节点
                {
                    TreeLinkNode *last;
                    while(pNode->next!=NULL)
                    {
                        last=pNode;
                        pNode=pNode->next;
                    }
                    if(pNode->left==last)    
                        return pNode;
                    else
                        return NULL;
                }
                else
                {
                    return pNode->next;
                }
            }
        }
        return NULL;     
    }
};
```

注意：

1.一开始没有在最大的else开头加上pNode->next!=NULL的限制，并且最后倒数第三行没有加return NULL，

在使用pNode->next->right之前，一定要确保pNode->next不是空节点，如果是空节点，那么访问其右指针会越界。

当前节点不为空，才可以使用其right、left、next等指针，虽然这些指针可能为空。

但是如果当前节点为空，则其是没有成员的，也就不能使用right、left、next等。

对于链表也是，如果使用其next指针，一定保证该节点不为空。

## 优秀代码

```cpp
链接：https://www.nowcoder.com/questionTerminal/9023a0c988684a53960365b889ceaf5e
来源：牛客网

class Solution{
public:
    TreeLinkNode* GetNext(TreeLinkNode* pNode)
    {
        if (pNode == NULL)
            return NULL;
        if (pNode->right != NULL)
        {
            pNode = pNode->right;
            while (pNode->left != NULL)
                pNode = pNode->left;
            return pNode;
        }
        while (pNode->next != NULL)
        {
            TreeLinkNode *proot = pNode->next;
            if (proot->left == pNode)
                return proot;
            pNode = pNode->next;
        }
        return NULL;
    }
};
```

