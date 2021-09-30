

[题目链接]()

## 1.题目描述



## 2.代码

```cpp
class Solution {
public:
    int rows;
    int cols;
    vector<vector<bool>> visited;
    bool exist(vector<vector<char>>& board, string word) {
        
        //变量初始化
        rows=board.size();
        cols=board[0].size();
        visited.resize(rows,vector<bool>(cols,false));

        for(int row=0;row<rows;row++)
        {
            for(int col=0;col<cols;col++)
            {
                if(hasPathCore(board,word,row,col,0))
                {
                    return true;
                }
            }
        }
        return false;

    }
    bool hasPathCore(const vector<vector<char>> &board,const string &word,int row,int col,int pathLength)
    {
        //终止条件
        if(pathLength==word.size())
            return true;
        if(row<0||row>=rows||col<0||col>=cols||visited[row][col]==true||word[pathLength]!=board[row][col])
            return false;

        visited[row][col]=true;//1.处理节点

                                //2.递归
        bool hasPath=hasPathCore(board,word,row,col-1,pathLength+1)||
                hasPathCore(board,word,row,col+1,pathLength+1)||
                hasPathCore(board,word,row-1,col,pathLength+1)||
                hasPathCore(board,word,row+1,col,pathLength+1);
        
        visited[row][col]=false;//3.回溯，撤销节点处理
        
        return hasPath;//返回结果

    }
};
```



## 3.解题思路





