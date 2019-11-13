## 栈

### 栈的顺序存储结构

```cpp

#define MaxSize 50
typedef struct{
	Elemtype data[MaxSize];	// 存放栈中元素
	int top;				// 栈顶指针
} SqStack;

```
### 共享栈

- 利用栈底位置相对不变的特性，让两个顺序栈共享一个一维数据空间

- 两个栈的栈底分别设置在共享空间的两端，两个栈顶向共享空间中间延伸

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Two-sequential-stack-shared-storage-spaces.png)

- 两个栈的栈顶指针都指向栈顶元素，top0=-1时，0号栈为空，top1=MaxSize时1号栈为空

- 仅当两个栈顶指针相邻(top1-top0=1)时，判断为栈满

- 当0号栈进栈时top0先加1再赋值，1号栈进栈时top1先减1再赋值；出栈时刚好相反

- 共享栈是为了更有效地利用存储空间，两个栈的空间相互调节，只有在整个存储空间被占满时才发生上溢

- 存取数据地时间复杂度为O(1)，对存取效率没有什么影响

### 链式存储结构

- 优点: 便于多个栈共享存储空间和提高其效率，不存在栈满上溢的情况

- 采用的**单链表**实现，规定所有操作都在单链表的表头进行

- 规定Lhead指向栈顶元素

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Chain-storage-structure-of-Stack.png)

```cpp

typedef struct Linknode{
	ElemType data;		
	struct Linknode *next;
} *LiStack;

```

### 卡特兰数(Catalan)

- 1/(1+n)C(n 2n)

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Catalan.png)

### 典型例题

- 对于n个不同元素进栈，出栈序列的个数为，卡特兰数

### 栈的应用

#### 中缀转后缀

- 从左向右扫描表达式，遇到 "(" 或 +-\*/ 入栈

- 当前需要入栈的运算符优先级**小于等于**栈顶元素，栈顶元素出栈

- 遇到 ")"，元素出栈直到 "(" (包括"("本身也要出栈)

#### 中缀转前缀

- 从右向左扫描表达式，遇到 "(" 或 +-\*/ 入栈

- 当前需要入栈的运算符优先级**小于**栈顶元素入栈，栈顶元素出栈

- 遇到 "("，元素出栈直到 ")" (包括")"本身也要出栈)
