## 二叉树遍历

- 所谓二叉树的遍历，就是按照某种次序访问二叉树中每个节点，而且每个节点仅访问一次的过程

- 以L,N,R分别表示遍历左子树、访问根节点和遍历右子树，则可能有NLR、LNR、LRN、NRL、RNL、RLN等六种遍历方式

- 若限定先左后右，则只有前三种遍历，分别称为先序遍历、中序遍历、后序遍历，另外还有一种层序的遍历方式

### 二叉树的递归遍历

```cpp

// 先序遍历模板
void PreOrder(BiTree *T){
	if(T != NULL){
		visit(T);
		PreOrder(T->lchild);
		PreOrder(T->rchild);
	}
}
// 中序遍历模板
void InOrder(BiTree *T){
	if(T != NULL){		
		InOrder(T->lchild);
		visit(T);
		InOrder(T->rchild);
	}
}
// 后序遍历模板
void PostOrder(BiTree *T){
	if(T != NULL){		
		PostOrder(T->lchild);
		PostOrder(T->rchild);
		visit(T);
	}
}
// 三种遍历算法，每个节点都访问一次且仅访问一次，时间复杂度都是 O(n)。
// 在递归遍历中，递归工作栈的栈深度恰好为树的深度，在最坏的情况下，二叉树有n个结点且深度为n的单支树，遍历算法的空间复杂度为 O(n)

```

### 二叉树的非递归遍历

```cpp

// 先序遍历模板
void PreOrderNonrecursion(BiTNode *bt){
	if(bt != NULL){
		BiTNode *Stack[maxSize]; // 定义一个栈
		int top = -1;
		BiTNode *p;
		Stack[++top] = bt;		// 根节点入栈
		while(top != -1){		// 栈空循环退出，遍历结束
			p = Stack[top--];	// 输出栈顶元素
			Visit(p);			// 访问结点
			if(p->rchild != NULL){			// 栈顶结点右孩子存在，右孩子存在
				Stack[++top] = p->rchild;
			}
			if(p->lchild != NULL){
				Stack[++top] = p->lchild;	//栈顶结点左孩子存在，左孩子存在
			}
		}
	}
}

// 中序遍历模板
void InOrderNonrecursion(BiTNode *bt){
	if(bt != NULL){		
		BiTNode *Stack[maxSize];	// 定义一个栈
		int top = -1;
		BiTNode *p;
		p = bt;
		while(top != -1 || p != NULL){	// 空栈而且右子树遍历完则循环结束
			while(p != NULL){			// 左孩子不为空，左孩子进栈
				Stack[++top] = p;		
				p = p->lchild;
			}
			if(top != -1){				// 堆栈不空的情况下，出栈并输出出栈结点
				p = Stack[top--];
				Visit(p);				// visit 是访问p的函数，
				p = p->rchild;
			}				
		}
	}
}


// 后序遍历模板
// 逆后序遍历是先序遍历的左右子树遍历顺序交换得到
void PostOrderNonrecursion(BiTNode *bt){
	if(bt != NULL){		
		if(bt != NULL){
			// 定义两个栈
			// Stack1用来执行先序遍历，Stack2用来将先序遍历交换左右子树遍历顺序得到的序列逆序
			BiTNode *Stack1[maxSize];
			int top1 = -1;
			BiTNode *Stack2[maxSize];
			int top2 = -1;
			BiTNode *p = NULL;
			Stack1[++top1] = bt;		// 根结点入栈
			while(top1 != -1){
				p = Stack1[top1--];		
				Stack2[++top2] = p;		
				// 左右孩子入栈顺序相反
				if(p->rchild != NULL){
					Stack1[++top] = p->lchild;
				} 
				if(p->rchild != NULL){
					Stack1[++top] = p->rchild;
				} 
			}
			while(top2 != -1){
				p = Stack2[top2--];
				Visit(p);
			}
		}
	}
}

```

### 二叉树的层次遍历

```cpp

void level (BiTNode *p){
	int front, rear;
	BiTNode *que[maxSize];
	front = rear = 0;
	BiTNode *q;
	if(p != NULL){
		rear = (rear + 1) % maxSize;
		que[rear] = p;						// 根结点入队
		while(front != rear){
			q = que[front];					// 队头结点入队
			Visit(q);
			if(q->lchild != NULL){			// 如果左子树不为空，则左子树的根结点入队
				rear = (rear + 1) % maxSize;
				que[rear] = q->lchild;
			}
			if(q->rchild != NULL){
				rear = (rear + 1) % maxSize;// 如果右子树不空，则右子树的根结点入队
				que[rear] = q->rchild;
			}
		}
	}
}

```

### 典型例题

- 实现从**大到小**输出二叉排序树中所有其值不小于k的关键字

```cpp

void Output(BSTNode *bt, KeyType k){
	if(bt != NULL){
		Output(bt->rchild, k);
		if(bt->key >= k){
			print("%d, by->key");
		}
		Output(bt->lchild, k);
	}
}

```

- 先递归右孩子，输出，再递归左孩子，顺序从大到小(逆中序)

- 实现从**小到大**输出二叉排序树中所有其值不小于k的关键字

```cpp

void Output(BSTNode *bt, KeyType k){
	if(bt != NULL){
		Output(bt->lchild, k);
		if(bt->key >= k){
			print("%d, by->key");
		}
		Output(bt->rchild, k);
	}
}

```

- 先递归左孩子，输出，再递归右孩子，顺序从小到大(中序)