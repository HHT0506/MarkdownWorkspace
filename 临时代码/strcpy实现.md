代码

```cpp
#include<iostream>
#include<assert.h>
using namespace std;


char *my_strcpy(char *dest, const char *src)
{
	assert(dest != NULL&&src != NULL);
	if (dest == NULL || src == NULL)
		return NULL;
	char *res = dest;
	while (*src != '\0')
	{
		*dest++ = *src++;
	}
	*dest = '\0';
	return res;
}

int main() {
	
	
	char dest[10] ;
	char src[]="1234567";

	cout << my_strcpy(dest, src) << endl;

	cout << dest << endl;
	return 0;
}


```

