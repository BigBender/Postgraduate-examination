## 堆排序

### 优先队列

0个或多个元素的集合，每个元素都有一个优先权或值

与FIFO结构的队列不同，优先队列中的元素出队列的顺序由元素的优先级决定

从优先队列中删除元素时根据**优先权高或低**的次序，而不是元素进入队列的次序

对优先队列执行的操作有：

1. 查找一个元素

2. 插入一个新元素

3. 删除一个元素

### 最小优先队列(Min priority queue)

"搜索/删除" 优先权最小的元素

### 最大优先队列(Min priority queue)

"搜索/删除" 优先权最小的元素

### 要选出优先级最高的元素则可以借助堆来完成

代表堆的这颗完全二叉树的**根结点**的值是最大（或最小）的

因此将一个无序序列调整为一个堆，就可以找出这个序列的最大（或最小）的值

然后将找出的这个值交换到序列的最后（或最前），有序序列关键字增加1个，无序序列中关键字减少1个

对新的无序序列重复这样的操作，就实现了排序

* 堆排序最关键的操作就是**将序列调整为堆**。

* 堆排序算法：将要排序的n个元素初始化为一个最大（小）堆，每次从堆中提取元素。<br/>
如果使用**最大堆**，各元素将按照**非递减**次序排列；如果使用**最小堆**，各元素将按照**非递增**次序排列。

* 时间复杂度 初始化需要的时间为n，每次删除所需要的时间为O(logn)，因此总时间为O(nlogn)。

### 建堆过程(筛选法建堆)

- n个结点的完全二叉树，最后一个结点是第 ⌊n/2⌋ 个结点的孩子

- 对第 ⌊n/2⌋ 个结点为根的子树筛选

- 依次对各结点 ⌊n/2⌋~1 为根的子树进行筛选，看该结点值进行筛选 

- 交换过程可能出现下一级的堆，继续重复上述方法，直到以该结点为根的子树构成堆(局部堆)为止

- 反复利用上述调整堆的方法建堆，直到根结点

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Big-root-heap-adjustment.png)

大根堆调整过程

### 示例

对序列：**20，12，35，15，10，80，30，17，2，1**进行堆排序，结果为非递减序列。

1. 先将序列形成完全二叉树。

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort1.png)

2. 再将其调整为大根堆。

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort2.png)

3. 大根堆里删除元素，重构大根堆，直到堆中的所有元素被删除。

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort3.png)

80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort4.png)

35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort5.png)

30 35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort6.png)

20 30 35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort7.png)

17 20 30 35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort8.png)

15 17 20 30 35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort9.png)

12 15 17 20 30 35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort10.png)

10 12 15 17 20 30 35 80

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/HeapSort11.png)

2 10 12 15 17 20 30 35 80

最后结果

1 2 10 12 15 17 20 30 35 80

### 时间复杂度分析

整个算法的基本操作次数为O(log2n) * (n/2) + O(log2n)*(n-1)

化简后得到时间复杂度O(nlog2n)。

### 空间复杂度分析

算法所需的辅助存储空间不随待排序列规模变化而变化，是个常量，空间复杂度为O(1)。

### 说明

堆排序在最坏情况下时间复杂度也是O(nlog2n)

这是它相对于快速排序最大的优点。

堆排序空间复杂度为O(1)，是在所有时间复杂度为O(nlog2n)的排序中最小的

堆排序适用的场景是关键字很多的情况下，典型的例子是，从10000个关键字中选取前10个中最小的，这种情况，堆排序最好，如果关键字较少，则不提倡使用堆排序。