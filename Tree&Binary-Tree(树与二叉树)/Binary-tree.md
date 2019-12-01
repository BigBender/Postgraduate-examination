## 二叉树

### 二叉树定义

- 二叉树是有序树，将的**左右子树颠倒就成为了另一棵树**，即使树中结点只有一颗子树，也要区分他是左、右子树

#### 二叉树与度为2的有序树的区别

- 度为2的有序树至少有3个结点，二叉树可以为空

- 度为2的有序树其孩子结点的有序次数是相对于另一孩子而言，若某结点中只有一个结点，无需区分左右次序

- **二叉树的五种形态**

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Binary-tree.png)

#### 二叉树的性质

- 非空二叉树，叶子结点等于度为2的结点数加一  N0 = N2 + 1

- 根据树的性质，|E|=|V|-1，二叉树中，|E|=N1 + 2N2，|V|=N0+N1+N2，联立推出 N0=N2+1

- 非空二叉树第k层上结点最多有 2^(k-1) 个结点

- 高度为H的二叉树至多有 2^H - 1个 结点

#### 完全二叉树

- i>1，双亲结点编号 ⌊i/2⌋，i为偶数，是左孩子，i为奇数，是右孩子

- 2i<=N，有左孩子2i，否则没有左孩子

- 2i+1<=N，有有孩子2i+1，否则没有右孩子

- 结点i所在的层次深度 ⌊log2 i⌋ + 1

- 具有n个结点的完全二叉树高度为 **⌊log2 N⌋ + 1 **

- 任意一个二叉树的高度**可能**是 **⌊log2 N⌋ + 1 ~ N**

#### 典型例题

- 一棵完全二叉树具有1000个结点，此完全二叉树有多少个度为2的结点

- 完全二叉树，满树有 2^h - 1个结点，512 < 1000 < 1024，当前这棵树有10层

- 最底层最多有 2^9=512 个结点，现在缺少23个结点，叶子结点共有 512-23+(23/2)=500个

- 第10层每少两个结点，第9层就多一个叶子结点，然后用公式 N0 = N2 + 1， N2 = 499个

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

- n个结点的二叉链表含有 n+1 个空链域

#### 静态链表存储(双亲存储)

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Static-linked-list.png)

<table style="border-collapse: collapse;">
	<tr>
		<th>数组下标</th>
		<th></th>
		<th>双亲结点</th>
	</tr>
	<tr>
		<td>0</td>
		<td>V1</td>
		<td>-1</td>		
	</tr>
	<tr>
		<td>1</td>
		<td>V2</td>
		<td>0</td>		
	</tr>
	<tr>
		<td>2</td>
		<td>V3</td>
		<td>0</td>		
	</tr>
	<tr>
		<td>3</td>
		<td>V4</td>
		<td>1</td>		
	</tr>
	<tr>
		<td>4</td>
		<td>V5</td>
		<td>2</td>		
	</tr>
	<tr>
		<td>5</td>
		<td>V6</td>
		<td>2</td>		
	</tr>
	<tr>
		<td>6</td>
		<td>V7</td>
		<td>3</td>		
	</tr>
	<tr>
		<td>7</td>
		<td>V8</td>
		<td>4</td>		
	</tr>
	<tr>
		<td>8</td>
		<td>V9</td>
		<td>6</td>		
	</tr>
</table>

### 树的存储结构

#### 双亲表示法

- 实现：定义结构数组存放树的结点，每个结点含两个域
    
- 数据域：存放结点本身信息
 
- 双亲域：指示本结点的双亲结点在数组中位置
 
- 特点：找双亲容易，找孩子难

#### 孩子表示法

- 多重链表：每个结点有多个指针域，分别指向其子树的根
   
- 结点同构：结点的指针个数相等，为树的度
  
- 结点不同构：结点指针个数不等，为该结点的度

### 树与二叉树的转换

- 左孩子右兄弟

### 树的遍历

- 先根遍历：先访问树的根节点，再依次先根遍历子树

- 后根遍历：先依次后根遍历子树，再访问树的根节点

### 典型例题

- 由树转化得到的二叉树，**树的后序**遍历序列对应**二叉树的中序**遍历序列

- 设一棵三叉树中有2个度数为1的结点，2个度数为2的结点，2个度数为3的结点，则该三叉链表中有多少个度数为0的结点

- 树，结点数 - 1 = 边数，n0 + n1 + n2 + n3 - 1 = 2n1 + 2n2 + 2n3 => n0=7

### 典型例题

- 求二叉树的高度

```cpp

int getHeight(TreeNode &root){
	if(root==null){
		return 0;
	}
	int leftheight = getHeight(root->lchild);
	int rightheight = getHeight(root->rchild);
	return Math.max(leftheight, rightheight) + 1;
}

```

- 一棵有124个叶子的完全二叉树，至少有多少个结点，最多有多少个结点

- 2^6 < 124 < 2^7 ，这棵树有 8 层

- 第8层最多有，2^7=128个结点，现在有124个叶子结点

- 叶子结点是最底层的结点数 加 上一层叶结点

- 128 - x + x/2 = 124，x = 8 或 x = 9

- 最多有 256 - 8 = 248 个结点，最少有 256 - 9 = 247 个结点

- A、B为一棵二叉树上的两个结点，在后序遍历中，A在B前面的条件是，A在B的左方 (**后序遍历左右根**)

- A、B为一棵二叉树上的两个结点，在中序遍历中，A在B前面的条件是，A在B的左方 (**中序遍历左根右**)

- 满7叉树的叶子结点数n0和非叶结点n1之间的关系是 6n1 + 1 = n0
- 总结点数 = 总分支数 + 1， n0 + n1 = 7n1 + 1












