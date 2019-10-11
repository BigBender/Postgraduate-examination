## 弗洛伊德算法(基于动态规划)

### 求各顶点间最短路径问题(又称插点法) 

### 稠密图最佳，不适合大量数据运算

已知一个各边权值均大于0的带权有向图，对每一对顶点 vi≠vj，要求求出vi与vj之间的最短路径和最短路径长度

Floyd基本思想

递推产生一个n阶方阵序列A^(-1)，A^(0)，...，A^(k)，...，A^(n-1)，其中A^(k)[i][j]表示从顶点vi到顶点vj的路径长度，k表示绕行第k个顶点的运算步骤

初始时，对于任意两个顶点vi和vj，若它们之间存在边，则以此边上的权值作为它们之间的最短路径长度；若他们之间不存在有向边，则以∞作为它们之间的最短路径长度

以后逐步尝试在原路径中加入顶点k (k = 0, 1, ..., n - 1)作为中间顶点。

如果增加中间顶点后，得到的路径比原来的路径长度减少了，则以此新路径代替原路径

定义一个n阶方阵序列：A^(-1)，A^(0)，...，A^(n-1)，其中

A^(-1)[i][j]=arcs[i][j]

A^(k)[i][j]=Min{A^(k-1)[i][j]}，A^(k-1)[i][k]+A^(k-1)[k][j]}，k=0，1，...，n-1

其中 A^(k)[i][j]是从顶点vi到vj、中间顶点的序号不大于k的最短路径长度

Floyd算法是一个迭代的过程，每迭代一次，在从vi到vj的最短路径上多考虑一个顶点，经过n此迭代后所得到的A^(n-1)[i][j]就是vi到vj的最短路径长度，即方针A^(n-1)中就保存了任意一对顶点之间的最短路径长度


![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Floyd.png)


<table style="border-collapse: collapse;">
	<tr>
		<th>dist</th>
		<th colspan="3">dist^(-1)</th>
		<th colspan="3">dist^(0)</th>
		<th colspan="3">dist^(1)</th>
		<th colspan="3">dist^(2)</th>
	</tr>	
	<tr>
		<td>v0</td>
		<td>v1</td>
		<td>v2</td>
		<td>v0</td>
		<td>v1</td>
		<td>v2</td>
		<td>v0</td>
		<td>v1</td>
		<td>v2</td>
		<td>v0</td>
		<td>v1</td>
		<td>v2</td>		
	</tr>	
	<tr>
		<td>0</td>
		<td>6</td>
		<td>13</td>
		<td>0</td>
		<td>6</td>
		<td>13</td>
		<td>0</td>
		<td>6</td>
		<td>10</td>
		<td>0</td>
		<td>6</td>
		<td>10</td>
	</tr>	
	<tr>
		<td>10</td>
		<td>0</td>
		<td>4</td>
		<td>10</td>
		<td>0</td>
		<td>4</td>	
		<td>10</td>
		<td>0</td>
		<td>4</td>	
		<td>9</td>
		<td>0</td>
		<td>4</td>	
	</tr>	
	<tr>
		<td>5</td>
		<td>∞</td>
		<td>0</td>
		<td>5</td>
		<td>11</td>
		<td>0</td>
		<td>5</td>
		<td>11</td>
		<td>0</td>
		<td>5</td>
		<td>11</td>
		<td>0</td>
	</tr>		
</table>

### Floyd时间复杂度O(|V|^3)，对于中等规模来说，仍然是有效的

### Floyd算法那允许图中有带负权值的边，不允许有包含带负权值的边组成的回路


