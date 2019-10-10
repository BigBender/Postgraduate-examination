## 深度优先搜索

类似于二叉树的先序遍历

首先访问出发点v，将其标记为已访问过，选取与v邻接的未被访问的任意一个顶点w

再选取与w邻接的未被访问的任一顶点并访问，以此重复

若一个顶点的所有邻接顶点都被访问过，回退到最近被访问过的顶点

```cpp

int visit[maxSize];

void DFS(AGraph *G, int v){
	ArcNode *p;
	Visit[v] = 1;
	Visit(v);
	p = G->adilist[v].firstarc;
	while(p != NULL){
		if(visit[p->adjvex] == 0){
			DFS(G, p->adjvex);
		}
		p = p->nextarc;
	}
}


```
#### 对于非连通图

```cpp

void dfs(AGraph *g){

	int i;
	for(i = 0;i < g->n; ++i){
		if(Visit[i] == 0){
			DFS(g, i);
		}
	}
}

```

- 二叉树地先序遍历对于每个结点要递归地访问**两个分支**
- 图的深度优先搜索遍历则是递归地访问**多个分支**

把图的深度优先搜索遍历过程**中所经历的边保留**，其余的边删掉，就会形成一棵树，成为**深度优先搜索生成树**
