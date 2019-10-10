## 邻接表

邻接表是图的一种链式存储结构

邻接表存储表示的定义如下

```cpp

typedef struct ArcNode{		// 边结点
	int adjvex;				// 该边指向的结点
	struct ArcNode *nextarc;// 下一条边的指针
	int info;				// 额外信息(可省略)
}ArcNode

typedef struct VNode{		// 顶点结点
	char data;				// 顶点信息
	ArcNode *firstarc;		// 指向第一条边的指针
}VNode

typedef struct AGraph{
	VNode adjlist[maxSize];	// 邻接表
	int n, e;				// 顶点数和边数
}AGraph;

```

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Adjacency-list.png)