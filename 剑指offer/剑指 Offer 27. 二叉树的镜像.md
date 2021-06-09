

[题目链接](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    TreeNode* mirrorTree(TreeNode* root) {
        swapTree(root);
        return root;
    }
    void swapTree(TreeNode *root)
    {
        if(root==nullptr)
            return;
        swap(root->right,root->left);
        swapTree(root->left);
        swapTree(root->right);
    }
};
```



## 3.解题思路





