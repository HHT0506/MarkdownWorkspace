

[题目链接](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/)

## 1.题目描述



## 2.代码

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    vector<int> levelOrder(TreeNode* root) {
        if(root==nullptr)
            return vector<int>{};
        queue<TreeNode *> que;
        vector<int> res;
        que.push(root);
        while(!que.empty())
        {
            res.push_back(que.front()->val);
            if(que.front()->left!=nullptr)
                que.push(que.front()->left);
            if(que.front()->right!=nullptr)
                que.push(que.front()->right);
            que.pop();
        }
        return res;
    }
};
```



## 3.解题思路



