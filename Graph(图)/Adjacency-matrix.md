## 邻接矩阵

- 邻接矩阵是图的**顺序存储结构**

- 邻接矩阵结构型定义

```cpp

typedef struct{
	int no;		// 顶点编号
	char info;	// 其他信息
}VertexType;	// 节点类型

```

### 图的定义

```cpp

typedef struct{
	int edges[maxSize][maxSize];// 
	int n,e;					// 顶点数和边数
	VertexType vex[maxSize];	// 存放结点信息
}MGraph							// 邻接矩阵类型

```

### 典型例题

- 有向图的邻接矩阵中，计算第i个顶点入度的方法 是 统计第i列元素的个数

- 有向图的邻接矩阵中，计算第i个顶点出度的方法 是 统计第i行元素的个数

