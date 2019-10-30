## 栈

### 栈的顺序存储结构

```cpp

#define MaxSize 50
typedef struct{
	Elemtype data[MaxSize];	// 存放栈中元素
	int top;				// 栈顶指针
} SqStack;

```

### 链式存储结构

- 优点: 便于多个栈共享存储空间和提高其效率，不存在栈满上溢的情况

- 采用的**单链表**实现，规定所有操作都在单链表的表头进行

- 规定Lhead指向栈顶元素

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Chain-storage-structure-of-Stack.png )

```cpp

typedef struct Linknode{
	ElemType data;		
	struct Linknode *next;
} *LiStack;


```
