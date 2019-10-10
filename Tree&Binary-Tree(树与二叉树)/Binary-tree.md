## 二叉树

### 二叉树定义

二叉树是有序树，将的**左右子树颠倒就成为了另一棵树**，即使树中结点只有一颗子树，也要区分他是左、右子树

#### 二叉树与度为2的有序树的区别

* 度为2的有序树至少有3个结点，二叉树可以为空
* 度为2的有序树其孩子结点的有序次数是相对于另一孩子而言，若某结点中只有一个结点，无需区分左右次序

**二叉树的五种形态**

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Binary-tree.png)

#### 二叉树的性质

1. 非空二叉树，叶子结点等于度为2的结点数加一  N0 = N2 + 1

根据树的性质，|E|=|V|-1，二叉树中，|E|=N1 + 2N2，|V|=N0+N1+N2，联立推出 N0=N2+1

2. 非空二叉树第k层上结点最多有 2^(k-1) 个结点
3. 高度为H的二叉树至多有 2^H - 1个 结点

#### 完全二叉树

1. i>1，双亲结点编号 ⌊i/2⌋，i为偶数，是左孩子，i为奇数，是右孩子
2. 2i<=N，有左孩子2i，否则没有左孩子
3. 2i+1<=N，有有孩子2i+1，否则没有右孩子
4. 结点i所在的层次深度 ⌊log2 i⌋ + 1
5. 具有n个结点的完全二叉树高度为 ⌊log2 N⌋ + 1 


任意一个二叉树的高度可能是 ⌊log2 N⌋ + 1 ~ N

### 二叉树存储结构

#### 顺序存储

一组地址连续的存储单元自上而下，自左至右存储

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Bianary-tree-Sequential%20-sotrage.png)


#### 链式存储

二叉链表至少包含3个域，数据data，左指针lchild，右指针rchild

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Binary-tree-chain-sotrage.png)

```cpp

typedef struc BiTNode{
	ElemType data;
	struct BiTNode *lchild, *rchild;	
}BiTNode, *BiTree

```

n个结点的二叉链表含有 n+1 个空链域

### 树与二叉树的转换

左孩子右兄弟











