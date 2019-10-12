## 平衡二叉树

### 平衡二叉树的定义

为了避免树的高度增长过快，降低二叉排序树的性能

规定在插入和删除二叉树结点时，保证任意结点的左、右子树高度差绝对值不超过1，将这样的二叉树称为平衡二叉树

定义结点左子树与右子树的高度差为该结点的平衡因子，只可能是 -1, 0, 1

平衡二叉树可定义为它或者是一棵空树，或者具有下列性质：

- 它的左子树和右子树都是平衡二叉树，且左子树和右子树的高度差的绝对值不超过1

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Balanced-biary-tree.png)

#### 平衡二叉树的插入

每当在二叉排序树中插入(或删除)一个结点时，首先要检查其插入路径上的结点是否因为此次操作导致了不平衡

如果不平衡，先找插入路径上离插入结点最近的平衡因子绝对值大于1的结点A，以A为根子树，保持二叉排序树特性前提下，调整各结点的位置关系，使其重新到达平衡

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Balanced-binary-tree-demo.png)

- LL平衡旋转(右单旋转)

由于在结点A的左孩子的左子树插入新结点，A的平衡因子从1增加到2，导致以A为根的子树失去平衡

需要一次向右的旋转操作

将A的左孩子B向右上旋转代替A成为根结点，将A结点向右下旋转成为B的右子树的根结点，B的原右子树作为原右子树作为A结点的左子树

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/LL.png)

- RR平衡旋转(左单旋转)

由于在结点A的右孩子的右子树插入新结点，A的平衡因子从-1减至-2，导致以A为根的子树失去平衡

需要一次向右的旋转操作

将A的右孩子B向左上旋转代替A成为根结点，将A结点向左下旋转成为B的左子树的根结点，B的原左子树作为原右子树作为A结点的右子树

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/RR.png)

- LR平衡旋转(先左后右双旋转)

由于在结点A的左孩子的右子树插入新结点，A的平衡因子从1增至2，导致以A为根的子树失去平衡

需要进行两次旋转操作，先左旋转后右旋转。

先将A结点的左孩子B的右子树的根结点C向左上旋转提升到B结点的位置，再把该C结点向右上旋转提到A结点的位置

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/LR.png)

- RL平衡旋转(先右后左双旋转)

由于在结点A的右孩子的左子树插入新结点，A的平衡因子从-1减至-2，导致以A为根的子树失去平衡

需要进行两次旋转操作，先右旋转后左旋转。

先将A结点的右孩子B的左子树的根结点C向右上旋转提升到B结点的位置，再把该C结点向左上旋转提到A结点的位置

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/RL.png)

#### 注意，LR和RL旋转时，新结点插入在C的左子树还是右子树，不影响旋转过程

### 平衡二叉树的查找

平衡二叉树进行查找的过程和二叉排序树相同，查找过程中和给定值比较的关键字个数不超过树的深度

假设以Nh表示深度为h的平衡树中含有的最少结点数

含有n各结点的平衡二叉树的最大深度为O(log2 n)，平衡二叉树的平均查找长度为O(log2 n)