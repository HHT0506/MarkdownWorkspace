## 题目描述

[题目链接](https://www.nowcoder.com/practice/0e26e5551f2b489b9f58bc83aa4b6c68?tpId=13&tqId=11155&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking&tab=answerKey)

请实现一个函数，将一个字符串中的每个空格替换成“%20”。例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。

## 注意的点

函数原形为：`void replaceSpace(char *str, int length)`

需要在该函数内直接改变str，str需要增长，意味着：str的总容量，需要比传进的str字符串要大。

比如，在外部必须是显示定义字符数组：char str[20]="We Are Happy"；

而不能是隐式定义：char str[]="We Are Happy"，隐式定义是根据后面的字符串大小，确定str的容量，这样的话，就不能将str存储的内容变长了。

所以，程序中应该判断传入的str容量length，是否大于替换空格后的字符串大小。

[`初始版本代码`](#初始版本代码)  以及[`初始版本解题思路`](#初始版本解题思路)  能测试通过，应该是测试用例给的都满足这一条件了，但是实际工程中，应该检查输入是否满足要求。









## <span id=初始版本代码>`初始版本代码`</span>

```cpp
class Solution {
public:
    void replaceSpace(char *str, int length) {
        //(1)创建str的副本temp
        char *temp = new char[length + 1];
        int t = 0;
        for (; str[t] != '\0'; t++)
            temp[t] = str[t];
        temp[t] = '\0';
        
        //(2)遍历temp，重新写入str
        int i = 0, j = 0;
        while (temp[i] != '\0')
        {
            if (temp[i] != ' ')
                str[j++] = temp[i++];
            else
            {
                str[j++] = '%';
                str[j++] = '2';
                str[j++] = '0';
                i++;
            }
        }
        str[j] = '\0';
        delete[] temp;
    }
};
```



## <span id=初始版本解题思路>`初始版本解题思路`</span>

（1）创建str的副本temp，经过此步，temp="We Are Happy"

（2）遍历temp，重新写入str。比如

* 前两次循环，向str写入"We"；
* 第三次循环，检测到空格，在`else`分支中，向str写入“%20"；
* 第四次循环，向str写入'A'；
* 直到遍历完temp，str内容最终为"We%20Are%20Happy"。



## 另一方法（也存在问题）

```cpp
void replaceSpace(char *str, int length) {
	//遍历，得到空格个数
	int spaceNums = 0;
	for (int i = 0; str[i] != '\0'; ++i)
	{
		if (str[i] == ' ')
			++spaceNums;
	}
	//双指针，p1指向原始字符串末尾，p2指向增长后字符串最后
	int p1 = length - 1;
	int p2 = length - 1 + 2 * spaceNums;
	str[p2 + 1] = '\0';
	while (p1 != -1)
	{
		if (str[p1] != ' ')
			str[p2--] = str[p1--];
		else
		{
			str[p2--] = '0';
			str[p2--] = '2';
			str[p2--] = '%';
			p1--;
		}
	}
}
```

