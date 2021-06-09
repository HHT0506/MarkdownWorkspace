

[题目链接]()

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
    vector<vector<int>> levelOrder(TreeNode* root) {
        if(root==nullptr)
            return vector<vector<int>>{};
        vector<vector<int>> res;
        int currentLayerCount=1;
        int nextLayerCount=0;
        queue<TreeNode *> que;
        que.push(root);
        vector<int> temp;
        while(!que.empty())
        {
            if(que.front()->left!=nullptr)
            {
                que.push(que.front()->left);
                nextLayerCount++;
            }
            if(que.front()->right!=nullptr)
            {
                que.push(que.front()->right);
                nextLayerCount++;
            }
            temp.push_back(que.front()->val);
            que.pop();
            currentLayerCount--;
            if(currentLayerCount==0)
            {
                currentLayerCount=nextLayerCount;
                nextLayerCount=0;
                res.push_back(temp);
                temp.clear();
            }
        }
        return res;
    }
};
```



## 3.解题思路





