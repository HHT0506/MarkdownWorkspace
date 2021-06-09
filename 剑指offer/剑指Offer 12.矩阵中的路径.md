

## 代码

```cpp
class Solution {
public:
    bool exist(vector<vector<char>>& board, string word) {
        
        int rows=board.size();
        int cols=board[0].size();
        if(rows*cols<word.size())
            return false;
        vector<bool> visited_row(cols,false);
        vector<vector<bool>> visited(rows,visited_row);
        int pathLength=0;
        for(int row=0;row<rows;row++)
        {
            for(int col=0;col<cols;col++)
            {
                if(hasPathCore(board,word,row,col,pathLength,visited))
                {
                    return true;
                }
            }
        }
        return false;

    }
    bool hasPathCore(const vector<vector<char>> &board,const string &word,int row,int col,int &pathLength,vector<vector<bool>> &visited)
    {
        if(pathLength==word.size())
            return true;
        int rows=board.size();
        int cols=board[0].size();

        bool hasPath=false;
        if(row>=0&&row<rows&&col>=0&&col<cols
            &&word[pathLength]==board[row][col]&&!visited[row][col])
        {
            ++pathLength;
            visited[row][col]=true;
            hasPath=hasPathCore(board,word,row,col-1,pathLength,visited)||
                    hasPathCore(board,word,row,col+1,pathLength,visited)||
                    hasPathCore(board,word,row-1,col,pathLength,visited)||
                    hasPathCore(board,word,row+1,col,pathLength,visited);
            if(!hasPath)
            {
                --pathLength;
                visited[row][col]=false;
            }
        }
        return hasPath;

    }
};
```

