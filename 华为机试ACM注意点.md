## 1.万能头文件

```cpp
#include <bits/stdc++.h>
```

但不建议用。

## 2.输入多组字符串

```cpp
string str;
while(cin>>str)
{
    ...
}
```

注意这种只能输入不含空格的字符串。

如果字符串含有空格，需使用：

```cpp
while(getline(cin,str));
```

