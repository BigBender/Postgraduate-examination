## 最小生成树

### Prime(普里姆算法)适用于稠密图

从图中任意取出一个顶点，把它当成一棵树，然后从这棵树相接的边中选取一条最短(权值最小)的边

并将这条边及其所连顶点并入当前树中，然后再从与这棵树相接的边中选取一条最短的边，并将这条边及其所连顶点并入当前树中

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Prime.png)

### 逐个顶点并入

### Krusal(库鲁斯卡尔算法)适用于稀疏图

每次找出候选边中权值最小的边，就将该边并入生成树中，重复过程知道所有边都检测完成

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Prime.png)

### 逐个边并入







