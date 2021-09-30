1.递归版

```cpp
#include<iostream>
#include<assert.h>
using namespace std;

int mystrlen(const char* src)
{
	assert(src);
	if (*src == '\0')
		return 0;
	return 1 + mystrlen(src + 1);
}
int main() {

	
	char a[]="hello";
	char *b = "world!";
	cout << mystrlen(a) << endl;
	cout << mystrlen("hht") << endl;
	cout << mystrlen(b) << endl;
	return 0;
}
```



2.计数

```cpp
#include<iostream>
#include<assert.h>
using namespace std;

int mystrlen(const char* str)
{
	assert(str);
	int count = 0;
	while (*str != '\0')
	{
		count++;
		str++;
	}
	return count;
}
int main() {

	
	char a[]="hello";
	char *b = "world!";
	cout << mystrlen(a) << endl;
	cout << mystrlen("hht") << endl;
	cout << mystrlen(b) << endl;
	return 0;
}
```

