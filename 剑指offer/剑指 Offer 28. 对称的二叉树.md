

[题目链接](https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/)

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
        if(root==nullptr)
            return true;
        //最笨的方法，复制一棵二叉树，镜像，与原二叉树一一比较

        //1.复制一棵二叉树
        TreeNode* copyTree=new TreeNode(0);
        CopyTree(root,copyTree);

        //2.对复制的二叉树镜像
        MirrorTree(copyTree);

        //3.与原二叉树一一比较
        return TreeIsEqual(root,copyTree);
    }
    bool TreeIsEqual(TreeNode *root,TreeNode *copyTree)
    {
        if(root==nullptr&&copyTree==nullptr)
            return true;
        if(root==nullptr&&copyTree!=nullptr||root!=nullptr&&copyTree==nullptr)
            return false;
        if(root->val!=copyTree->val)
            return false;
        if(TreeIsEqual(root->left,copyTree->left)&&TreeIsEqual(root->right,copyTree->right))
            return true;
        else 
            return false;

    }
    void CopyTree(TreeNode *root,TreeNode *copyTree)
    {
        if(root==nullptr)
            return;
        copyTree->val=root->val;
        if(root->left!=nullptr)
        {
           copyTree->left=new TreeNode(0);
           CopyTree(root->left,copyTree->left);
        }
        if(root->right!=nullptr)
        {
            copyTree->right=new TreeNode(0);
            CopyTree(root->right,copyTree->right);
        }
        return ;
    }
    void MirrorTree(TreeNode *root)
    {
        if(root==nullptr)
            return ;
        if(root->right==nullptr&&root->left==nullptr)
            return ;
        TreeNode *temp=root->right;
        root->right=root->left;
        root->left=temp;
        MirrorTree(root->left);
        MirrorTree(root->right);
        return ;
    }
};
```



## 3.解题思路

