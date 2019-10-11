## 迪杰斯特拉算法(基于贪心策略)

### 求单源最短路径问题

求带权有向图中某个源点到其余各顶点的最短路径，常用 Dijkstra 算法

该算法设置了一个集合S记录已求得的最短路径的顶点，可用一个数组s[]实现，初始化为0，当
s[vi]=1时表示将顶点vi放入s中，初始时把源点v0放入S中，在构造过程中还设置了两个辅助数组：

dist[]：记录了从源点v0其他各顶点当前的最短路径长度，dist[i]初值为arcs[v0][i]

path[]：path[i]表示从源点到顶点i之间的最短路径的前驱结点，在算法结束时，可根据值追溯得到源点v0到顶点vi的最短路径

假设从顶点0出发，即v0=0，集合S最初只包含顶点0，邻接矩阵arcs表示带权有向图，arcs[i][j]表示有向边<i, j>的权值，若不存在有向边<i, j>，则arcs[i][j]为∞

1. 初始化：集合S初始为{0}，dist[]的初始值dist[i]=arcs[0][i]，i=1，2，...，n - 1
2. 从顶点集合V-S中选出vj，满足dist[j]=Min{dist[i]|vi∈V-S}，vj就是当前求得的一条从v0出发的最短路径的终点，令S=S∪{j}
3. 修改从v0出发到集合V-S上任意顶点vk可达的最短路径长度：如果dist[j] + arcs[j][k]<dist[k]，则令dist[k]=dist[j] + arcs[j][k]
4. 重复2~3步骤，操作共n - 1，直到所有的顶点都包含在S中

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Dijkstra.png)

<table style="border-collapse: collapse;">
	<tr>
		<th>顶点</th>
		<th>第1趟</th>
		<th>第2趟</th>
		<th>第3趟</th>
		<th>第4趟</th>
	</tr>	
	<tr>
		<td>2</td>
		<td>10 </br> v1->v2</td>
		<td>8 </br> v1->v5->v2</td>
		<td>8 </br> v1->v5->v2</td>
		<td></td>
	</tr>	
	<tr>
		<td>3</td>
		<td>∞</td>
		<td>14 </br> v1->v5->v3</td>
		<td>13 </br> v1->v5->v4->v3</td>
		<td style="background-color: #ccc;">9 </br> v1->v5->v2->v3</td>
	</tr>	
	<tr>
		<td>4</td>
		<td>∞</td>
		<td style="background-color: #ccc;">7 </br> v1->v5->v4</td>
		<td></td>
		<td></td>		
	</tr>	
	<tr>
		<td>5</td>
		<td style="background-color: #ccc;">5 </br> v1->v5</td>
		<td></td>
		<td></td>
		<td></td>
	</tr>	
	<tr>
		<td>集合S</td>
		<td>{1, 5}</td>
		<td>{1, 5, 4}</td>
		<td>{1, 5, 4, 2}</td>
		<td>{1, 5, 4, 2, 3}</td>
	</tr>	
</table>

### 时间复杂度为 O(|V|^2)

### 如果边上有负权值，Dijkstra算法不适用
