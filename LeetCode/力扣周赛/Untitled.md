```cpp
class Solution {
public:
    int countPalindromicSubsequence(string s) {
        unordered_set<string> se;
        int size=s.size();
        for(int i=0;i<size;i++)
        {
            int left=s.find(s[i]);
            int right=s.rfind(s[i]);
            if(left!=right)
            {
                for(int j=left+1;j<right;j++)
                {
                    string str;
                    str.push_back(s[left]);
                    str.push_back(s[j]);
                    str.push_back(s[right]);
                    se.insert(str);
                }
            }
        }
        return se.size();

    }
};
```

