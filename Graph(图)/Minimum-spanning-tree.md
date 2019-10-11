## 最小生成树

### Prime(普里姆算法，基于贪心算法)适用于稠密图

从图中任意取出一个顶点，把它当成一棵树，然后从这棵树相接的边中选取一条最短(权值最小)的边

并将这条边及其所连顶点并入当前树中，然后再从与这棵树相接的边中选取一条最短的边，并将这条边及其所连顶点并入当前树中

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Prime.png)

### 逐个顶点并入

<table style="border-collapse: collapse;">
	<tr>
		<th>最小边、权的数据结构</th>
		<th>时间复杂度</th>
	</tr>
	<tr>
		<td>邻接矩阵、搜索</td>
		<td>O(|V|^2)</td>
	</tr>
	<tr>
		<td>二叉堆、邻接表</td>
		<td>O((|V|+|E|)log|V|)=O(|E|log|V|)</td>
	</tr>
	<tr>
		<td>斐波那契堆、邻接表</td>
		<td>O(|E|+|V|log|V|)</td>
	</tr>
</table>

通过邻接矩阵图表示的简易实现中，找到所有最小权边共需O（V）的运行时间。

使用简单的二叉堆与邻接表来表示的话，普里姆算法的运行时间则可缩减为O(ElogV)，其中E为连通图的边数，V为顶点数。

如果使用较为复杂的斐波那契堆，则可将运行时间进一步缩短为O(E+VlogV)，这在连通图足够密集时（当E满足Ω（VlogV）条件时），可较显著地提高运行速度。

### Krusal(库鲁斯卡尔算法，基于贪心算法)适用于稀疏图

每次找出候选边中权值最小的边，就将该边并入生成树中，重复过程知道所有边都检测完成

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Prime.png)

### 逐个边并入

### 平均时间复杂度为O(|E|log|E|)，其中E和V分别是图的边集和点集







