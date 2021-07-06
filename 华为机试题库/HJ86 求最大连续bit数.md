

[题目链接](https://www.nowcoder.com/practice/4b1658fd8ffb4217bc3b7e85a38cfaf2?tpId=37&rp=1&ru=%2Fta%2Fhuawei&qru=%2Fta%2Fhuawei%2Fquestion-ranking)

## 1.题目描述



## 2.代码

```cpp
#include<iostream>
#include<string>
#include<algorithm>
using namespace std;
int fun(int n, string &str)//传入1的位置，返回从该位置开始，连续的1的个数
{
	if (n >= str.size() || str[n] != '1')
		return 0;
	else
		return 1 + fun(n + 1, str);
}
int main()
{
	unsigned int source;
	//cin >> source;
	while (cin >> source)
	{
		unsigned char ch = (unsigned char)source;
		int bit = 1;

		string str = "";
		for (int i = 0; i<8; i++)//将二进制转化为字符串
		{
			if ((ch&bit) != 0)//检测到为1
			{
				str.push_back('1');
			}
			else//检测到0
			{
				str.push_back('0');
			}
			bit <<= 1;
		}
        
		int res = 0;
		for (int i = 0; i<str.size(); i++)
		{
			int max_temp=0;
			if (str[i] == '1')//寻找1的位置，获得连续1的个数
			{
				max_temp = fun(i, str);
				i += max_temp - 1;
			}
			res = max(max_temp, res);//获取两者之间最大值作为当前最大值。

		}
		cout << res << endl;


	}
	return 0;
}

```

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    int n;  
    while(cin>>n){
        int count=0,cnt=0;
        while(n){
            if(n&1==1){
                cnt++;
                count=max(cnt,count);
            }
            else{
                cnt=0;
            }
            n>>=1;    
        }
        cout<<count<<endl;
    }
    system("pause");
    return 0;
}
```



## 3.解题思路

