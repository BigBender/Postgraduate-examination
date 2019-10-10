## 广度优先搜索遍历

广度优先搜索遍历类似于树的层次遍历

需要用到一个队列

1. 任取图中一个顶点访问，入队，并将这个顶点标记为已访问
2. 当队列不空时循环执行；出队，依次检查出队顶点的所有邻接顶点，访问没有被访问过的邻接顶点并将其入队
3. 当队列为空时跳出循环，广度优先搜索即完成

```cpp

void BFS(AGraph *G, int v, visit[maxSize]){
	// visit数组初始化全都为0
	ArcNode *p;
	int que[maxSize], front = 0, rear = 0;// 定义一个队列
	int j;
	Visit(v);					// 访问顶点v
	visit[v] = 1;				// 标记为已访问
	rear = (rear+1)%maxSize;	// 当前顶点进队
	que[rear] = v;
	while(front != rear){		// 队列空则遍历结束
		front = (front+1)%maxSize;// 顶点出队
		j = que[front];
		p = G->adjlist[j].firstarc;	// p指向出对顶点j的第一条边
		while(p != NULL){
			if(visit[p->adjvex] == 0){
				Visit(p->adjvex);
				visit[p->adjvex] = 1;
				rear = (rear+1)%maxSize;
				que[rear] = p->adjvex;
			}
			p = p->nextarc;		// p 指向j的下一条边
		}
	}
}

```

#### 对于非连通图

```cpp

void bfs(AGraph *g){

	int i;
	for(i = 0;i < g->n; ++i){
		if(Visit[i] == 0){
			BFS(g, i);
		}
	}
}

```