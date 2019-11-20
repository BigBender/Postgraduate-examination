## 拓扑排序

### 有向无环图：一个有向图不存在换，称有向无环图，简称DAG图

### AOV网(是一种原始点到终点的最短距离)

如果一个DAG图表示一个工程，顶点表示活动，有向边<Vi, Vj>表示活动Vi必须先于活动Vj进行的这样一种关系，则将这种有向图称为**顶点表示活动的网络**

在AOV网中，活动Vi是活动Vj的直接前驱，活动Vj是活动Vi的直接后继，这种前驱和后继关系具有传递性，且任何活动Vi不能以它自己作为自己的前驱或后继

### 拓扑排序

图论中，一个有向无环图的顶点组成的序列，当且仅当满足下列条件，称为改图的拓扑排序

- 每个顶点出现且只出现一次

- 若顶点A在序列中排在顶点B的前面，图中不存在从顶点B到顶点A的路径

或者：拓扑排序是堆**有向无环图**的顶点的一种排序，它使得如果存在一条从顶点A到顶点B的路径，那么排序中顶点B出现在顶点A的后面，每个DAG图都有一个或多个拓扑排序序列

### 对一个DAG图进行拓扑排序的算法

- 从DAG图中选择一个没有前驱的顶点并输出

- 从图中删除该顶点和所有以它为起点的有向边

- 重复1和2步骤直到当前的DAG图为空或当前图中不存在无前驱的顶点为止，后一种情况则说明有向图中**必然存在环**

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Topological-sort.png)

<table style="border-collapse: collapse;">
	<tr>
		<td>结点号</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
		<td>4</td>
		<td>5</td>		
	</tr>
	<tr>
		<td>初始入度</td>
		<td>0</td>
		<td>1</td>
		<td>2</td>
		<td>2</td>
		<td>2</td>
	</tr>
	<tr>		
		<td>第一轮</td>
		<td></td>
		<td>0</td>
		<td>2</td>
		<td>1</td>
		<td>2</td>	
	</tr>
	<tr>
		<td>第二轮</td>
		<td></td>
		<td></td>
		<td>1</td>
		<td>0</td>
		<td>2</td>
	</tr>
	<tr>
		<td>第三轮</td>	
		<td></td>
		<td></td>
		<td>0</td>
		<td></td>
		<td>1</td>
	</tr>
	<tr>
		<td>第四轮</td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td>0</td>
	</tr>
	<tr>
		<td>第五轮</td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
</table>


```cpp

bool TopologicalSort(Graph G){
	// 如果G存在拓扑序列，返回true；否则返回false，这时G中存在环
	InitStack(S);	// 初始化栈，存储入度为0的顶点
	for(int i=0;i<G.vexnum;i++){
		if(indegree[i] == 0){
			Push(S, i);
		}
	}
	int count = 0;
	while(!IsEmpty(S)){
		Pop(S, i);
		print[count++]=i
		for(p=G.vertices[i].firstarc;p;p=p->nextarc){
			// 将所有i指向的顶点的入度减1，并且将入度减为0的顶点压入栈S
			v=p->adjvex;
			if(!(--indegree[v])){
				Push(S, v);			// 入度为0，则入栈
			}
		}
	}
	if(count < G.vexnum){			// 排序失败，有向图中有回路
		return false;
	}else{
		return true;				// 拓扑排序成功
	}
}

```

### 用拓扑算法处理DAG图时，应注意

- 入度为零的顶点即没有前驱活动的，或前驱活动都已经完成的顶点，工程可以从这个顶点所代表的活动开始或继续

- 如果一个顶点有多个直接后继，则拓扑排序的结果通常不唯一

但如果各个顶点已经排在一个**线性有序**的序列中，每个顶点**有唯一的前驱后继关系**，再做拓扑排序时，**排序的结果是唯一**的

- 由于DAG图中各顶点的地位平等，每个顶点编号是人为的，可以按照拓扑排序的结果重新安排顶点的序号

- 生成的图的新的邻接矩阵存储表示，可以是**三角矩阵**

- 对于一般的图，如果邻接矩阵是**三角矩阵**，存在拓扑排序；反之不一定成立