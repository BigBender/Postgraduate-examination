## 邻接矩阵

邻接矩阵是图的顺序存储结构

邻接矩阵结构型定义

```cpp

typedef struct{
	int no;		// 顶点编号
	char info;	// 其他信息
}VertexType;	// 节点类型

```

图的定义

```cpp

typedef struct{
	int edges[maxSize][maxSize];// 
	int n,e;					// 顶点数和边数
	VertexType vex[maxSize];	// 存放结点信息
}MGraph							// 邻接矩阵类型

```

