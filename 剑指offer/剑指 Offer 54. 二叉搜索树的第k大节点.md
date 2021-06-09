

## 代码

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
    int kthLargest(TreeNode* root, int k) {
        midorderTraversal(root);
        return vec[vec.size()-k];

    }
    vector<int> vec;
    void midorderTraversal(TreeNode *root)
    {
        if(root!=NULL)
        {
            midorderTraversal(root->left);
            vec.push_back(root->val);
            midorderTraversal(root->right);
        }

    }
};
```

