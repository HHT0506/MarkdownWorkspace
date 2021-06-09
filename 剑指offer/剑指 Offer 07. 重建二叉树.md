

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
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        //递归
        if(preorder.size()==0||inorder.size()==0)
            return NULL;
        TreeNode *root=new TreeNode;
        root->val=preorder[0];
        int target=preorder[0];
        int index=0;//root在中序遍历中的位置下标
        for(int i=0;i<inorder.size();i++)
        {
            if(inorder[i]==target)
            {
                index=i;
                break;
            }
        }
        vector<int> preorder_left,preorder_right,inorder_left,inorder_right;
        for(int i=1;i<preorder.size();i++)
        {
            if(i<=index)
                preorder_left.push_back(preorder[i]);//前序遍历左子树
            else
                preorder_right.push_back(preorder[i]); //前序遍历右子树
        }
        for(int i=0;i<inorder.size();i++)
        {
            if(i<index)
                inorder_left.push_back(inorder[i]);//中序遍历左子树
            else if(i>index)
                inorder_right.push_back(inorder[i]);//中序遍历右子树
        }

        //递归
        root->left=buildTree(preorder_left,inorder_left);
        root->right=buildTree(preorder_right,inorder_right);

        return root;
    }
};
```



## 其他参考代码

```cpp
class Solution {
public:
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        this->preorder = preorder;
        for(int i = 0; i < inorder.size(); i++)
            dic[inorder[i]] = i;
        return recur(0, 0, inorder.size() - 1);
    }
private:
    vector<int> preorder;
    unordered_map<int, int> dic;
    TreeNode* recur(int root, int left, int right) { 
        if(left > right) return nullptr;                        // 递归终止
        TreeNode* node = new TreeNode(preorder[root]);          // 建立根节点
        int i = dic[preorder[root]];                            // 划分根节点、左子树、右子树
        node->left = recur(root + 1, left, i - 1);              // 开启左子树递归
        node->right = recur(root + i - left + 1, i + 1, right); // 开启右子树递归
        return node;                                            // 回溯返回根节点
    }
};

作者：jyd
链接：https://leetcode-cn.com/problems/zhong-jian-er-cha-shu-lcof/solution/mian-shi-ti-07-zhong-jian-er-cha-shu-di-gui-fa-qin/
来源：力扣（LeetCode）
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```

